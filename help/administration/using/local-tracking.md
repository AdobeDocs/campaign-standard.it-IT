---
title: Implementazione del tracciamento push
description: Questo documento ti consente di garantire che il tracciamento delle notifiche push sia stato implementato correttamente in iOS e Android.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 0%

---

# Implementazione del tracciamento locale {#local-tracking}

## Informazioni sul tracciamento locale {#about-local-tracking}

In questa pagina, scopri come garantire che il tracciamento delle notifiche locali sia stato implementato correttamente. Tieni presente che ciò implica che la notifica locale è già stata configurata.

Il tracciamento delle notifiche locali può essere suddiviso in tre tipi:

* **Impressioni locali** - Quando una notifica locale è stata inviata al dispositivo e si trova sul centro di notifica, ma non è stata toccata affatto. Nella maggior parte dei casi, il numero di impression deve essere simile a quello fornito. In questo modo il dispositivo riceve il messaggio e restituisce tali informazioni al server.

* **Clic locale** - Quando viene inviata una notifica locale al dispositivo e l’utente fa clic sulla notifica. L’utente voleva visualizzare la notifica (che a sua volta passerà al tracciamento aperto locale) o ignorare la notifica.

* **Apri locale** - Quando viene inviata una notifica locale al dispositivo e l&#39;utente fa clic sulla notifica che causa l&#39;apertura dell&#39;applicazione. È simile al clic locale, ma se la notifica è stata rifiutata non verrà attivata un’apertura locale.

Per implementare il tracciamento per Adobe Campaign Standard, l’app mobile deve includere Mobile SDK nell’applicazione. Questi SDK sono disponibili in [!DNL Adobe Mobile Services].

Per inviare le informazioni di tracciamento, sono necessarie tre variabili: due sono parte dei dati ricevuti da Adobe Campaign e l’altro è una variabile di azione che determina se si tratta di un’impression, un clic o un’apertura.

| Variabile | Elemento “value” |
| :-: | :-: |
| deliveryId | `deliveryId` dai dati in arrivo (simile al tracciamento push dove `_dld` è utilizzato) |
| broadlogId | `broadlogId` dai dati in arrivo (simile al tracciamento push dove `_mld` è utilizzato) |
| action | &quot;1&quot; per Open, &quot;2&quot; per Click e &quot;7&quot; per Impression |

## Implementare il tracciamento locale delle impression {#implement-local-impression-tracking}

L’SDK di Adobe Experience Platform Mobile invierà automaticamente l’evento impression per Android e iOS senza alcuna configurazione aggiuntiva.

## Implementare il tracciamento dei clic {#implementing-click-tracking}

Per il tracciamento dei clic, devi inviare il valore &quot;2&quot; per l’azione durante la chiamata `collectMessageInfo()` o `trackAction()` funzioni.

### Per Android {#implement-click-tracking-android}

Per tenere traccia dei clic, è necessario implementare due scenari:

* L’utente visualizza la notifica ma la cancella.

   Per tenere traccia del clic in caso di licenziamento, aggiungi il destinatario della trasmissione `NotificationDismissalHandler` nel file AndroidManifest del modulo applicativo.

   ```
   <receiver
   android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
   </receiver>
   ```

* L’utente visualizza la notifica e fa clic su di essa, per attivare un tracciamento aperto.

   Questo scenario deve produrre un clic e un&#39;apertura. Il tracciamento di questo clic farà parte dell’implementazione necessaria per tenere traccia dell’apertura. Vedi [Implementazione del tracciamento aperto](#implement-open-tracking).

### Per iOS {#implement-click-tracking-ios}

Per inviare le informazioni di tracciamento dei clic, devi aggiungere quanto segue:

```
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {

   func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                
                //If you are using ACPCore v2.3.0 or later, use the next line.
                
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
                //Else comment out the above line and uncomment the line below
                
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            
            ////MORE CODE
        }
        completionHandler()
    }
}
```

## Implementare il tracciamento delle operazioni di apertura {#implement-open-tracking}

Devi inviare &quot;1&quot; e &quot;2&quot; perché l&#39;utente deve fare clic sulla notifica per aprire l&#39;applicazione. Se l&#39;applicazione non viene avviata/aperta tramite notifica locale, non si verificano eventi di tracciamento.

### Per Android {#implement-open-tracking-android}

Per tenere traccia dell&#39;apertura, è necessario creare un intento. Gli oggetti Intent consentono ad Android OS di chiamare il metodo al termine di determinate azioni, in questo caso facendo clic sulla notifica per aprire l’app.

Questo codice si basa sull’implementazione del tracciamento delle impression dei clic. Con l’impostazione dell’intento, ora devi restituire le informazioni di tracciamento ad Adobe Campaign. In questo caso, Android View([!DNL Activity]) che ha attivato la notifica, verrà aperta o portata in primo piano in seguito al clic dell’utente. L&#39;oggetto intento in [!DNL Activity] contiene i dati di notifica che possono essere utilizzati per tenere traccia di apertura.

MainActivity.java (extensions [!DNL Activity])

```
@Override
protected void onResume() {
    super.onResume();
    handleTracking();
}
 
 
private void handleTracking() {

    //Check to see if this view was opened based on a notification

    Intent intent = getIntent();
    Bundle data = intent.getExtras();
 
    if (data != null) {

        //Opened based on the notification, you must get the tracking that was passed on.

        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");

        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
 
            //Send click tracking since the user did click on the notification

            contextData.put("action", "2");

            //If you are using ACPCore v1.4.0 or later, use the next line.
    
            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
 
            //Send open tracking since the user opened the app

            contextData.put("action", "1");

            //If you are using  ACPCore v1.4.0 or later, use the next line.

            MobileCore.collectMessageInfo(contextData);

            //Else comment out the above line and uncomment the line below

            // MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Per iOS {#implement-open-tracking-ios}

```
import os.log
import Foundation
import UserNotifications
import UserNotificationsUI
import ACPCore
 
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
 
    //Called when user clicks the local notification or also called from willPresent()

    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
 
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:

            //This is to handle the Dismiss action

            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

                //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

                //Else comment out the above line and uncomment the line below

                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {

               //If you are using ACPCore v2.3.0 or later, use the next line.

               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])

               //Else comment out the above line and uncomment the line below

               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
