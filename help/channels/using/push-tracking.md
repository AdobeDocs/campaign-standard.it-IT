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
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# Implementazione del tracciamento push {#push-tracking}

## Informazioni sul tracciamento push {#about-push-tracking}

Per garantire che la notifica push sia stata completamente sviluppata, è necessario assicurarsi che la parte di tracciamento sia stata implementata correttamente.

I passaggi seguenti consentono di garantire che il tracciamento push sia stato implementato correttamente. Presuppone che siano già state implementate le prime parti dell&#39;implementazione delle notifiche push: Registrazione dell&#39;utente dell&#39;app e gestione di un messaggio di notifica push.

Il tracciamento push è separato in tre tipi:

* **Impressioni** push - Quando una notifica push viene inviata al dispositivo e si trova nel centro di notifica ma non è stata toccata per niente.  Questa è considerata un&#39;impressione.  Nella maggior parte dei casi, i numeri di impression devono essere simili a quelli forniti. Garantisce che il dispositivo abbia ricevuto il messaggio e abbia inviato tali informazioni al server.

* **Clic** push - Quando una notifica push viene inviata al dispositivo e l&#39;utente fa clic sul dispositivo.  L&#39;utente desiderava visualizzare la notifica (che a sua volta si sposterà al tracciamento dell&#39;apertura push) oppure chiudeva la notifica.

* **Push Open** - Quando una notifica push viene inviata al dispositivo e l&#39;utente fa clic sulla notifica che causa l&#39;apertura dell&#39;app.  Questo è simile al clic push, tranne per il fatto che l&#39;apertura push non viene attivata se la notifica è stata chiusa.

Per implementare il tracciamento per Campaign Standard, l&#39;app mobile deve includere Mobile SDK. Questi SDK sono disponibili in Adobe Mobile Services.

Per inviare le informazioni di tracciamento, sono necessarie tre variabili. Due dati che fanno parte dei dati ricevuti da Campaign Standard e una variabile di azione che stabilisce se si tratta di un&#39; **Impression**, **Click** o **Open**.

| Variabile | Valore |
|:-:|:-:|
| broadlogId | _mId dai dati |
| deliveryId | _dId dai dati |
| action | 1 per Open, 2 per Click e 7 per Impression |

## Implementazione per Android {#implementation-android}

### Come implementare il tracciamento delle impression push {#push-impression-tracking-android}

Per il tracciamento delle impressioni, devi inviare il valore &quot;7&quot; per l&#39;azione quando chiami la funzione trackAction().

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### Come implementare il tracciamento dei clic {#push-click-tracking-android}

Per il monitoraggio dei clic, devi inviare il valore &quot;2&quot; per l&#39;azione quando chiami la funzione trackAction().

Per tenere traccia del clic, è necessario gestire due scenari:

* L’utente visualizza la notifica ma la cancella.
* L’utente visualizza la notifica e fa clic su di essa per trasformarla in un tracciamento aperto.

Per gestire questo problema, è necessario utilizzare due Intenti: uno per fare clic sulla notifica e uno per chiudere la notifica.

MyFirebaseMessagingService.java

```
private void sendNotification(Map<String, String> data) {
    Intent openIntent = new Intent(this, CollectPIIActivity.class);
    Intent dismissIntent = new Intent(this, NotificationDismissedReceiver.class);
    openIntent.addFlags(Intent.FLAG_ACTIVITY_CLEAR_TOP);
  
    //put the data map into the intent to track clickthroughs
    Bundle pushData = new Bundle();
    Set<String> keySet = data.keySet();
    for (String key : keySet) {
        pushData.putString(key, data.get(key));
    }
    openIntent.putExtras(pushData);
    dissmissIntent.putExtras(pushData);
  
  
    PendingIntent pendingIntent = PendingIntent.getActivity(this, 0, openIntent,
        PendingIntent.FLAG_UPDATE_CURRENT);
    PendingIntent onDismissPendingIntent = PendingIntent.getBroadcast(this.getApplicationContext(), 0, dismissIntent, 0);
  
    //<BUILD NOTIFICATION using notification builder>
    //Add both Intents to the notification
    notificationBuilder.setContentIntent(pendingIntent);
    notificationBuilder.setDeleteIntent(onDismissPendingIntent);
}
```

Affinché il BroadcastReceiver funzioni, è necessario registrarlo in AndroidManifest.xml

```
<manifest>
    <application>
        <receiver android:name=".NotificationDismissedReceiver">
        </receiver>
    </application>
</manifest>
```

NotificationDismessedReceiver.java

```
public class NotificationDismissedReceiver extends BroadcastReceiver {
    private static final String TAG = NotificationDismissedReceiver.class.getSimpleName();
    @Override
    public void onReceive(Context context, Intent intent) {
        Bundle data = intent.getExtras();
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Come implementare il tracciamento aperto {#push-open-tracking-android}

Dovrete inviare &quot;1&quot; e &quot;2&quot; perché l&#39;utente deve fare clic sulla notifica per aprire l&#39;app. Se l&#39;app non viene avviata/aperta tramite la notifica push, non si verificano eventi di tracciamento.

Per tenere traccia dell&#39;apertura, è necessario creare Intent. Gli oggetti Intent consentono ad Android OS di chiamare il metodo al termine di determinate azioni. In questo caso, fate clic sulla notifica per aprire l&#39;app.

Questo codice è basato sull’implementazione del monitoraggio delle impression dei clic. Con Intento impostato, è ora necessario inviare nuovamente le informazioni di tracciamento a Campaign. In questo caso, è necessario impostare Open Intent per aprire una determinata vista nell&#39;app, che chiamerà il metodo onResume CON i dati di notifica nell&#39;oggetto Intent.

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
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
  
        HashMap<String, Object> contextData = new HashMap<>();
  
        if (deliveryId != null && messageId != null) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
  
            //Send Click Tracking since the user did click on the notification
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
  
            //Send Open Tracking since the user opened the app
            contextData.put("action", "1");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## Implementazione per iOS {#implementation-iOS}

### Come implementare il tracciamento delle impression push {#push-impression-tracking-iOS}

Per il tracciamento delle impressioni, devi inviare il valore &quot;7&quot; per l&#39;azione quando chiami la funzione trackAction().

Per comprendere il funzionamento delle notifiche iOS, i tre stati di un&#39;app devono essere dettagliati:

* **Primo piano**: quando l&#39;app è attualmente attiva e si trova sullo schermo (in primo piano).
* **Sfondo**: quando l&#39;app is non è sullo schermo ma il processo non è chiuso. Quando fai doppio clic sul pulsante Home, in genere vengono visualizzate tutte le app che si trovano in background.
* **Disattivato/chiuso**: un&#39;app il cui processo è stato eliminato.

Se un&#39;app viene chiusa, Apple non chiamerà l&#39;app finché l&#39;app non viene riavviata. Ciò significa che non sarete in grado di sapere quando la notifica è stata ricevuta su iOS.

Per poter continuare a utilizzare il tracciamento dell&#39;impressione mentre l&#39;app è in background, dobbiamo inviare all&#39;app **Content-Available** per informarla che è necessario eseguire il tracciamento.

>[!CAUTION]
>
>Il tracciamento dell&#39;impressione iOS non è accurato e non deve essere considerato affidabile.

Il codice seguente ha come destinazione l&#39;app in background:

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
  
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
  
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
               ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

Il codice seguente ha come destinazione l&#39;app in primo piano:

```
// This will get called when the app is in the foreground
  
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
  
  
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        if (deliveryId != nil && broadlogId != nil) {
             ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### Come implementare il tracciamento dei clic {#push-click-tracking-iOS}

Per il monitoraggio dei clic, devi inviare il valore &quot;2&quot; per l&#39;azione quando chiami la funzione trackAction().

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

Ora, quando invii notifiche push devi aggiungere una categoria. In questo caso, l&#39;abbiamo chiamato &quot;DEFAULT&quot;.

![](assets/tracking_push.png)

Quindi per gestire il Dismiss e inviare le informazioni di tracciamento è necessario aggiungere quanto segue:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### Come implementare il tracciamento aperto {#push-open-tracking-iOS}

Dovrete inviare &quot;1&quot; e &quot;2&quot; perché l&#39;utente deve fare clic sulla notifica per aprire l&#39;app. Se l&#39;app non viene avviata/aperta tramite la notifica push, non si verificano eventi di tracciamento.

```
import Foundation
import UserNotifications
import UserNotificationsUI
  
class NotificationDelegate: NSObject, UNUserNotificationCenterDelegate {
  
    // Called when user clicks the push notification or also called from willPresent()
    func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
  
        let userInfo = response.notification.request.content.userInfo
        os_log("App push data %{public}@, in userNotificationCenter:didReceive()", type: .debug, userInfo)
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            //This is to handle the Dismiss Action
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            if (deliveryId != nil && broadlogId != nil) {
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
