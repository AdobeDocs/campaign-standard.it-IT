---
title: Implementazione del tracciamento locale
description: Scopri come garantire che il tracciamento delle notifiche push sia stato implementato correttamente su iOS e Android
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b983d0a3-c345-44d4-bc82-202bf6ed26ab
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 0%

---

# Implementazione del tracciamento locale {#local-tracking}

## Informazioni sul tracciamento locale {#about-local-tracking}

In questa pagina, scopri come garantire che il tracciamento delle notifiche locali sia stato implementato correttamente. Tieni presente che ciò implica che la notifica locale è già stata configurata.

Il tracciamento delle notifiche locali può essere diviso in tre tipi:

* **Impression locali** - Quando una notifica locale è stata recapitata al dispositivo e si trova nel centro notifiche, ma non è stata toccata. Nella maggior parte dei casi, il numero di impression deve essere simile, se non uguale, al numero di consegna. In questo modo, il dispositivo riceve il messaggio e inoltra le informazioni al server.

* **Clic locale** - Quando una notifica locale è stata recapitata al dispositivo e l&#39;utente ha fatto clic sulla notifica. L’utente voleva visualizzare la notifica (che a sua volta passerà al tracciamento aperto locale) o ignorare la notifica.

* **Apertura locale** - Quando una notifica locale è stata recapitata al dispositivo e l&#39;utente ha fatto clic sulla notifica causando l&#39;apertura dell&#39;applicazione. È simile al clic locale, tranne per il fatto che un’apertura locale non verrà attivata se la notifica viene chiusa.

Per implementare il tracciamento per Adobe Campaign Standard, l’app mobile deve includere Mobile SDK nell’applicazione. Questi SDK sono disponibili in [!DNL Adobe Mobile Services].

Per inviare le informazioni di tracciamento, è necessario inviare tre variabili: due fanno parte dei dati ricevuti da Adobe Campaign e l’altra è una variabile di azione che determina se si tratta di un’impression, di un clic o di un’apertura.

| Variabile | Elemento “value” |
| :-: | :-: |
| deliveryId | `deliveryId` dai dati in arrivo (simile al tracciamento push in cui viene utilizzato `_dld`) |
| broadlogId | `broadlogId` dai dati in arrivo (simile al tracciamento push in cui viene utilizzato `_mld`) |
| azione | &quot;1&quot; per Apri, &quot;2&quot; per Clic e &quot;7&quot; per Impression |

## Implementare il tracciamento delle impression locali {#implement-local-impression-tracking}

L’SDK di Adobe Experience Platform Mobile invierà automaticamente l’evento di impression sia per Android che per iOS senza alcuna configurazione aggiuntiva.

## Implementare il tracciamento dei clic {#implementing-click-tracking}

Per il tracciamento dei clic, è necessario inviare il valore &quot;2&quot; per l&#39;azione quando si chiamano le funzioni `collectMessageInfo()` o `trackAction()`.

### Per Android {#implement-click-tracking-android}

Per tenere traccia dei clic, è necessario implementare due scenari:

* L’utente visualizza la notifica ma la cancella.

  Per tenere traccia dei clic in caso di scenario di interruzione, aggiungere il destinatario della trasmissione `NotificationDismissalHandler` nel file AndroidManifest del modulo applicativo.

  ```
  <receiver
  android:name="com.adobe.marketing.mobile.NotificationDismissalHandler">
  </receiver>
  ```

* L’utente visualizza la notifica e fa clic su di essa; si apre il tracciamento.

  Questo scenario dovrebbe produrre un clic e un messaggio aperto. Il tracciamento di questo clic farà parte dell’implementazione necessaria per tracciare l’apertura. Vedere [Implementazione del tracciamento aperto](#implement-open-tracking).

### Per iOS {#implement-click-tracking-ios}

Per inviare le informazioni di tracciamento dei clic, è necessario aggiungere quanto segue:

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

## Implementare il tracciamento delle aperture {#implement-open-tracking}

Devi inviare &quot;1&quot; e &quot;2&quot; perché l’utente deve fare clic sulla notifica per aprire l’applicazione. Se l’applicazione non viene avviata/aperta tramite notifica locale, non si verificano eventi di tracciamento.

### Per Android {#implement-open-tracking-android}

Per tenere traccia dell’apertura, è necessario creare un intento. Gli oggetti intento consentono al sistema operativo Android di chiamare il metodo quando vengono eseguite determinate azioni, in questo caso facendo clic sulla notifica per aprire l’app.

Questo codice si basa sull’implementazione del tracciamento delle impression di clic. Con l’intento impostato, ora devi inviare nuovamente le informazioni di tracciamento ad Adobe Campaign. In questo caso, la visualizzazione Android ([!DNL Activity]) che ha attivato la notifica verrà aperta o portata in primo piano in seguito al clic dell&#39;utente. L&#39;oggetto intento in [!DNL Activity] contiene i dati di notifica che possono essere utilizzati per tenere traccia dell&#39;apertura.

MainActivity.java (estende [!DNL Activity])

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
