---
title: Implementazione del tracciamento push
description: Questo documento consente di garantire che il tracciamento delle notifiche push sia stato implementato correttamente su iOS e Android.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d0a0c59763af8babc9701206cc39fe41b98e0cd4
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 0%

---


# Implementazione del tracciamento locale {#local-tracking}

## Informazioni sul tracciamento locale {#about-local-tracking}

In questa pagina, scopri come garantire che il tracciamento delle notifiche locali sia stato implementato correttamente. Questo implica che la notifica locale è già stata configurata.

Il tracciamento delle notifiche locali può essere suddiviso in tre tipi:

* **Impressioni** locali - Quando una notifica locale è stata inviata al dispositivo e si trova sul centro di notifica, ma non è stata toccata per nulla. Nella maggior parte dei casi, il numero di impression deve essere simile a quello distribuito. Garantisce che il dispositivo abbia ricevuto il messaggio e ritrasmetta tali informazioni al server.

* **Clic** locale - Quando viene inviata una notifica locale al dispositivo e l&#39;utente fa clic sul dispositivo. L&#39;utente voleva visualizzare la notifica (che a sua volta si sposterà al tracciamento aperto locale) o chiudere la notifica.

* **Aperto** locale - Quando una notifica locale è stata inviata al dispositivo e l&#39;utente ha fatto clic sulla notifica che causa l&#39;apertura dell&#39;applicazione. Questa operazione è simile al clic locale, ma se la notifica è stata chiusa, non verrà attivata alcuna apertura locale.

Per implementare il tracciamento per  Adobe Campaign Standard, l’applicazione mobile deve includere Mobile SDK nell’applicazione. Questi SDK sono disponibili in [!DNL Adobe Mobile Services].

Per inviare le informazioni di tracciamento, è necessario inviare tre variabili: due fanno parte dei dati ricevuti da  Adobe Campaign e l&#39;altro è una variabile di azione che determina se si tratta di un&#39;impressione, clic o apertura.

| Variabile | Valore |
| :-: | :-: |
| deliveryId | &quot;deliveryId&quot; dai dati in arrivo (simile al tracciamento push in cui viene utilizzato&quot;_dld&quot;) |
| broadlogId | &quot;broadlogId&quot; dai dati in arrivo (simile al tracciamento push in cui viene utilizzato &quot;_mld&quot;) |
| action | &quot;1&quot; per Open, &quot;2&quot; per Click e &quot;7&quot; per Impression |

## Implementazione del tracciamento dell&#39;impressione locale {#implement-local-impression-tracking}

Per il tracciamento delle impressioni, è necessario inviare il valore &quot;7&quot; per l&#39;azione quando si chiamano le funzioni collectMessageInfo() o trackAction().

### Per Android {#implement-local-impression-tracking-android}

L’SDK di Mobile per  Adobe Experience Platform avvia il tracciamento dell’impressione per la notifica locale quando viene attivata.

### Per iOS {#implement-local-impression-tracking-ios}

Per spiegare come implementare il tracciamento dell&#39;impressione, dobbiamo comprendere i tre stati di un&#39;applicazione:

* **Primo piano**: quando l&#39;applicazione è attualmente attiva e sullo schermo in primo piano.

* **Sfondo**: quando l&#39;applicazione non è visualizzata sullo schermo ma il processo non è chiuso. Quando si fa doppio clic sul pulsante Home, in genere vengono visualizzate tutte le applicazioni in background.

* **Disattivato/Chiuso**: quando il processo dell&#39;applicazione è stato eliminato. Se un&#39;applicazione viene chiusa, Apple non la chiamerà fino al riavvio dell&#39;applicazione. Ciò significa che non potrai mai sapere con certezza quando la notifica è stata ricevuta su iOS.

Per avere un monitoraggio delle impression ancora funzionante mentre l&#39;applicazione è in background, è necessario inviare &quot;Content-Available&quot; per far sapere all&#39;applicazione che il tracciamento deve essere fatto.

L’SDK di Mobile per  Adobe Experience Platform avvia il tracciamento dell’impressione per la notifica locale quando viene attivata.

>[!CAUTION]
>
>Il tracciamento delle impressioni iOS non è accurato e non deve essere considerato affidabile.

## Implementazione del monitoraggio dei clic {#implementing-click-tracking}

Per il monitoraggio dei clic, è necessario inviare il valore &quot;2&quot; per l&#39;azione quando si chiamano le funzioni collectMessageInfo() o trackAction().

### Per Android {#implement-click-tracking-android}

Per tenere traccia del clic, è necessario gestire due scenari:

* L’utente visualizza la notifica ma la cancella.

* L&#39;utente visualizza la notifica e fa clic su di essa, per attivare un tracciamento aperto.

Il primo scenario di clic viene tracciato da  SDK di Mobile Adobe Experience Platform.

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

Quindi per gestire la chiusura e inviare le informazioni di tracciamento, devi aggiungere quanto segue:

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

È necessario inviare &quot;1&quot; e &quot;2&quot; perché l&#39;utente deve fare clic sulla notifica per aprire l&#39;applicazione. Se l’applicazione non viene avviata/aperta tramite notifica locale, non si verificano eventi di tracciamento.

### Per Android {#implement-open-tracking-android}

Per tenere traccia dell&#39;apertura, è necessario creare un intento. Gli oggetti Intent consentono ad Android OS di chiamare il metodo al termine di determinate azioni, in questo caso facendo clic sulla notifica per aprire l&#39;app.

Questo codice è basato sull’implementazione del monitoraggio delle impression dei clic. Con l&#39;intento impostato, ora è necessario inviare le informazioni di tracciamento al  Adobe Campaign. In questo caso, la visualizzazione Android([!DNL Activity]) che ha attivato la notifica verrà aperta o portata in primo piano a seguito del clic dell&#39;utente. L&#39;oggetto intento in [!DNL Activity] contiene i dati di notifica che possono essere utilizzati per tenere traccia dell&#39;apertura.

MainActivity.java (extension [!DNL Activity])

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
