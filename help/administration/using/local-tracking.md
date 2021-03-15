---
solution: Campaign Standard
product: campaign
title: Implementazione del tracciamento push
description: Questo documento ti consente di garantire che il tracciamento delle notifiche push sia stato implementato correttamente su iOS e Android.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Impostazioni delle istanze
role: Amministratore
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '730'
ht-degree: 0%

---


# Implementazione del tracciamento locale {#local-tracking}

## Informazioni sul tracciamento locale {#about-local-tracking}

In questa pagina, scopri come garantire che il tracciamento delle notifiche locali sia stato implementato correttamente. Tieni presente che ciò implica che la notifica locale è già stata configurata.

Il tracciamento delle notifiche locali può essere suddiviso in tre tipi:

* **Impressioni locali**  - Quando una notifica locale viene recapitata al dispositivo ed è situata nel centro notifiche, ma non è stata toccata per nulla. Nella maggior parte dei casi, il numero di impression deve essere simile a quello fornito. In questo modo il dispositivo riceve il messaggio e restituisce tali informazioni al server.

* **Clic locale** : quando una notifica locale viene recapitata al dispositivo e l’utente fa clic su di esso. L’utente voleva visualizzare la notifica (che a sua volta passerà al tracciamento aperto locale) o ignorare la notifica.

* **Apertura locale** : evento di consegna di una notifica locale al dispositivo e dopo che l’utente ha fatto clic sulla notifica che causa l’apertura dell’applicazione. È simile al clic locale, ma se la notifica è stata rifiutata non verrà attivata un’apertura locale.

Per implementare il tracciamento per Adobe Campaign Standard, l’app mobile deve includere Mobile SDK nell’applicazione. Questi SDK sono disponibili in [!DNL Adobe Mobile Services].

Per inviare le informazioni di tracciamento, sono necessarie tre variabili: due sono parte dei dati ricevuti da Adobe Campaign e l’altro è una variabile di azione che determina se si tratta di un’impression, un clic o un’apertura.

| Variabile | Valore |
| :-: | :-: |
| deliveryId | &quot;deliveryId&quot; dai dati in arrivo (simile al tracciamento push in cui viene utilizzato&quot;_dld&quot;) |
| broadlogId | &quot;broadlogId&quot; dai dati in arrivo (simile al tracciamento push in cui viene utilizzato &quot;_mld&quot;) |
| action | &quot;1&quot; per Open, &quot;2&quot; per Click e &quot;7&quot; per Impression |

## Implementazione del tracciamento locale delle impression {#implement-local-impression-tracking}

Per il tracciamento delle impression, devi inviare il valore &quot;7&quot; per l’azione quando chiami le funzioni collectMessageInfo() o trackAction() .

### Per Android {#implement-local-impression-tracking-android}

L&#39;SDK di Adobe Experience Platform Mobile avvia il tracciamento delle impression per le notifiche locali quando vengono attivate.

### Per iOS {#implement-local-impression-tracking-ios}

Per spiegare come implementare il tracciamento delle impression, è necessario comprendere i tre stati di un’applicazione:

* **Primo piano**: quando l&#39;applicazione è attualmente attiva e sullo schermo in primo piano.

* **Contesto**: quando l&#39;applicazione non è visualizzata sullo schermo ma il processo non è chiuso. Quando si fa doppio clic sul pulsante Home, in genere vengono visualizzate tutte le applicazioni in background.

* **Off/Closed**: quando il processo dell&#39;applicazione è stato interrotto. Se un&#39;applicazione viene chiusa, Apple non la chiamerà fino al riavvio dell&#39;applicazione. Questo significa che non puoi mai sapere quando la notifica è stata ricevuta su iOS.

Per far sì che il tracciamento delle impression funzioni ancora mentre l’applicazione è in background, è necessario inviare &quot;Contenuto disponibile&quot; per informare l’applicazione che è necessario eseguire il tracciamento.

L&#39;SDK di Adobe Experience Platform Mobile avvia il tracciamento delle impression per le notifiche locali quando vengono attivate.

>[!CAUTION]
>
>Il tracciamento delle impression iOS non è accurato e non deve essere esaminato in modo affidabile.

## Implementazione del tracciamento dei clic {#implementing-click-tracking}

Per il tracciamento dei clic, devi inviare il valore &quot;2&quot; per l’azione quando chiami le funzioni collectMessageInfo() o trackAction() .

### Per Android {#implement-click-tracking-android}

Per tenere traccia dei clic, è necessario gestire due scenari:

* L’utente visualizza la notifica ma la cancella.

* L’utente visualizza la notifica e fa clic su di essa, per attivare un tracciamento aperto.

Il primo scenario di clic è tracciato dall’SDK di Adobe Experience Platform Mobile.

### Per iOS {#implement-click-tracking-ios}

```
// AppDelegate.swift
...
import os.log
import UserNotifications
...
  
func registerForPushNotifications() {
        let center = UNUserNotificationCenter.current()
        center.delegate = notificationDelegate
        //Here we are creating a new Category that allows us to handle Dismiss Actions
        let defaultCategory = UNNotificationCategory(identifier: "DEFAULT", actions: [], intentIdentifiers: [], options: .customDismissAction)
        //Add it to our array of Category, in this case we only have one
        center.setNotificationCategories([defaultCategory])
        center.requestAuthorization(options: [.alert, .sound, .badge]) {
            (granted, error) in
            os_log("Permission granted: %{public}@", type:. debug, granted.description)
            if error != nil {
                return
            }
            if granted {
                os_log("Notifications allowed", type: .debug)
            }
            else {
                os_log("Notifications denied", type: .debug)
            }
  
            // 2. Attempt registration for remote notifications on the main thread
            DispatchQueue.main.async {
                UIApplication.shared.registerForRemoteNotifications()
            }
        }
    }
```

Quindi, per gestire la chiusura e inviare un’informazione di tracciamento, devi aggiungere quanto segue:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                // Else comment out the above line and uncomment the line below
                // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

## Implementazione del tracciamento aperto {#implement-open-tracking}

Devi inviare &quot;1&quot; e &quot;2&quot; perché l&#39;utente deve fare clic sulla notifica per aprire l&#39;applicazione. Se l&#39;applicazione non viene avviata/aperta tramite notifica locale, non si verificano eventi di tracciamento.

### Per Android {#implement-open-tracking-android}

Per tenere traccia dell&#39;apertura, è necessario creare un intento. Gli oggetti Intent consentono ad Android OS di chiamare il metodo al termine di determinate azioni, in questo caso facendo clic sulla notifica per aprire l’app.

Questo codice si basa sull’implementazione del tracciamento delle impression dei clic. Con l’impostazione dell’intento, ora devi inviare nuovamente le informazioni di tracciamento ad Adobe Campaign. In questo caso, la visualizzazione Android([!DNL Activity]) che ha attivato la notifica verrà aperta o portata in primo piano come risultato del clic dell&#39;utente. L&#39;oggetto intento in [!DNL Activity] contiene i dati di notifica che possono essere utilizzati per tenere traccia dell&#39;apertura.

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
        //Looks it was opened based on the notification, lets get the tracking we passed on.
        Map<String, String> notificationData = (Map<String, Object>)data.getSerializableExtra("NOTIFICATION_USER_INFO");
        String deliveryId = (String)notificationData.get("deliveryId");
        String messageId = (String)notificationData.get("broadlogId");
  
  
  
        if (deliveryId != null && messageId != null) {
            HashMap<String, String> contextData = new HashMap<>();
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
  
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
            // MobileCore.trackAction("tracking", contextData);
  
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            // If you're using  ACPCore v1.4.0 or later, use the next line.
            MobileCore.collectMessageInfo(contextData);
            // Else comment out the above line and uncomment the line below
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
  
    // Called when user clicks the local notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
  
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
            // If you're using  ACPCore v2.3.0 or later, use the line below.
                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            // Else comment out the above line and uncomment the line below
            // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["deliveryId"] as? String
            let broadlogId = userInfo["broadlogId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               // If you're using  ACPCore v2.3.0 or later, use the line below.
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
               // Else comment out the above line and uncomment the line below
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
               // ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
