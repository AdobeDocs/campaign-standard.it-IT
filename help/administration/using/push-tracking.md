---
solution: Campaign Standard
product: campaign
title: Implementazione del tracciamento push
description: Questo documento ti consente di garantire che il tracciamento delle notifiche push sia stato implementato correttamente su iOS e Android.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Administrator
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 1%

---


# Implementazione del tracciamento push {#push-tracking}

## Informazioni sul tracciamento push {#about-push-tracking}

Per garantire che la notifica push sia stata completamente sviluppata, è necessario assicurarsi che la parte di tracciamento sia stata implementata correttamente, in quanto non tutte le notifiche push hanno abilitato il tracciamento. Per abilitare questo, gli sviluppatori devono identificare quali consegne hanno abilitato il tracciamento, Adobe Campaign Standard invierà un flag chiamato `_acsDeliveryTracking` con due valori **on** o **off**. Lo sviluppatore dell’app deve inviare una richiesta di tracciamento solo per le consegne per le quali la variabile è impostata come **on**.

>[!IMPORTANT]
>
>Questa variabile non è disponibile per le consegne impostate prima della versione 21.1 o per le consegne che utilizzano modelli personalizzati.

Il tracciamento push è separato in tre tipi:

* **Impression push** : quando una notifica push viene recapitata al dispositivo e si trova sul centro notifiche ma non è stata toccata per nulla.  Questa è considerata un&#39;impressione.  Nella maggior parte dei casi i numeri di impression devono essere simili se non uguali al numero consegnato. In questo modo il dispositivo riceve il messaggio e ritrasmette le informazioni al server.

* **Click push** : quando una notifica push viene recapitata al dispositivo e l’utente fa clic su di esso.  L’utente desiderava visualizzare la notifica (che a sua volta passerà al tracciamento Push Open) o ignorare la notifica.

* **Push Open**  (Apri push) - Quando una notifica push è stata recapitata al dispositivo e l&#39;utente ha fatto clic sulla notifica che causa l&#39;apertura dell&#39;app.  È simile al clic push, tranne per il fatto che l’apertura push non viene attivata se la notifica è stata ignorata.

Per implementare il tracciamento per Campaign Standard, l’app mobile deve includere Mobile SDK. Questi SDK sono disponibili su Adobe Mobile Services. Per ulteriori informazioni, consulta questa [pagina](../../administration/using/configuring-a-mobile-application.md).

Per inviare le informazioni di tracciamento sono necessarie tre variabili. Due elementi che fanno parte dei dati ricevuti da Campaign Standard e una variabile di azione che determina se si tratta di un **Impression**, **Click** o **Apri**.

| Variabile | Valore |
|:-:|:-:|
| broadlogId | _mId dai dati |
| deliveryId | _dId dai dati |
| action | 1 per Open, 2 per Click e 7 per Impression |

## Implementazione per Android {#implementation-android}

### Come implementare il tracciamento delle impression push {#push-impression-tracking-android}

Per il tracciamento delle impression, è necessario inviare il valore &quot;7&quot; per l’azione quando si chiama la funzione **[!UICONTROL trackAction()]** .

Per le consegne create prima della versione 21.1 o le consegne con modello personalizzato, consulta questa [sezione](../../administration/using/push-tracking.md#about-push-tracking).

```
@Override
public void onMessageReceived(RemoteMessage remoteMessage) {
....{Handle push messages}....
  if (data.size() > 0) {
    String deliveryId = data.get("_dId");
    String messageId = data.get("_mId");
    String acsDeliveryTracking = data.get("_acsDeliveryTracking");
 
    /*
    This is to handle deliveries created before 21.1 release or deliveries with custom template
    where acsDeliveryTracking is not available.
    */
    if( acsDeliveryTracking == null ) {
        acsDeliveryTracking = "on";
    }
 
    HashMap<String, String> contextData = new HashMap<>();
    if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
                contextData.put("deliveryId", deliveryId);
                contextData.put("broadlogId", messageId);
                contextData.put("action", "7");
                MobileCore.trackAction("tracking", contextData);
    }
  }
}
```

### Come implementare il tracciamento dei clic {#push-click-tracking-android}

Per il tracciamento dei clic, è necessario inviare il valore &quot;2&quot; per l&#39;azione quando si chiama la funzione **[!UICONTROL trackAction()]** .

Per tenere traccia dei clic, è necessario gestire due scenari:

* L’utente visualizza la notifica ma la cancella.
* L’utente visualizza la notifica e fa clic su di essa per trasformarla in un tracciamento aperto.

Per gestire questo problema, è necessario utilizzare due Intenti: uno per fare clic sulla notifica e un altro per ignorare la notifica.

Per le consegne create prima della versione 21.1 o le consegne con modello personalizzato, consulta questa [sezione](../../administration/using/push-tracking.md#about-push-tracking).

**[!UICONTROL MyFirebaseMessagingService.java]**

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

Affinché il **[!UICONTROL BroadcastReceiver]** funzioni, è necessario registrarlo nel **[!UICONTROL AndroidManifest.xml]**

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
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
         
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null ) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, Object> contextData = new HashMap<>();
 
        //We only send the click tracking since the user dismissed the notification
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
            contextData.put("deliveryId", deliveryId);
            contextData.put("broadlogId", messageId);
            contextData.put("action", "2");
            MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Come implementare il tracciamento delle aperture {#push-open-tracking-android}

Dovrai inviare &quot;1&quot; e &quot;2&quot; poiché l’utente deve fare clic sulla notifica per aprire l’app. Se l&#39;app non viene avviata/aperta tramite notifica push, non si verificano eventi di tracciamento.

Per tenere traccia dell’apertura, devi creare Intent. Gli oggetti Intent consentono ad Android OS di chiamare il metodo al termine di determinate azioni. In questo caso, fai clic sulla notifica per aprire l’app.

Questo codice si basa sull’implementazione del tracciamento delle impression dei clic. Con **[!UICONTROL Intent]** impostato, ora devi inviare nuovamente le informazioni di tracciamento ad Adobe Campaign Standard. In questo caso, devi impostare l’ **[!UICONTROL Open Intent]** per aprire una determinata visualizzazione nell’app, chiamando il metodo onResume con i dati di notifica nel percorso **[!UICONTROL Intent Object]**.

Per le consegne create prima della versione 21.1 o le consegne con modello personalizzato, consulta questa [sezione](../../administration/using/push-tracking.md#about-push-tracking).

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
        //This was opened based on the notification, you need to get the tracking that was passed on.
        String deliveryId = data.getString("_dId");
        String messageId = data.getString("_mId");
        String acsDeliveryTracking = data.get("_acsDeliveryTracking");
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template
        where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == null) {
            acsDeliveryTracking = "on";
        }
 
        HashMap<String, String> contextData = new HashMap<>();
 
        if (deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
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

Per il tracciamento delle impression, è necessario inviare il valore &quot;7&quot; per l’azione quando si chiama la funzione **[!UICONTROL trackAction()]** .

Per comprendere il funzionamento delle notifiche iOS, è necessario specificare i tre stati di un’app:

* **Primo piano**: quando l’app è attualmente attiva e sullo schermo (in primo piano).
* **Contesto**: quando l’app is non è sullo schermo ma il processo non è chiuso. Quando fai doppio clic sul pulsante Home, in genere mostra tutte le app che sono in background.
* **Disattivato/chiuso**: un&#39;app il cui processo è stato interrotto.

Se un’app viene chiusa, Apple non chiamerà l’app finché non viene riavviata. Questo significa che non potrai sapere quando la notifica è stata ricevuta su iOS.

Per far sì che il tracciamento funzioni ancora **[!UICONTROL Impression]** mentre l’app è in background, è necessario inviare **[!UICONTROL Content-Available]** per informare l’app che è necessario eseguire il tracciamento.

>[!CAUTION]
>
>Il tracciamento delle impression iOS non è accurato e non deve essere considerato affidabile.

Per le consegne create prima della versione 21.1 o le consegne con modello personalizzato, consulta questa [sezione](../../administration/using/push-tracking.md#about-push-tracking).

Il codice seguente esegue il targeting dell&#39;app in background:

```
// In didReceiveRemoteNotification event handler in AppDelegate.m
 
//In order to handle push notification when only in background with content-available: 1
func application(_ application: UIApplication, didReceiveRemoteNotification userInfo: [AnyHashable : Any], fetchCompletionHandler completionHandler: @escaping (UIBackgroundFetchResult) -> Void) {
 
        //Check if the app is not in the foreground right now
        if(UIApplication.shared.applicationState != .active) {
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
               ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

Il codice seguente è destinato all&#39;app in primo piano:

```
// This will get called when the app is in the foreground
 
func userNotificationCenter(_ center: UNUserNotificationCenter, willPresent notification: UNNotification, withCompletionHandler completionHandler: @escaping (UNNotificationPresentationOptions) -> Void) {
 
 
        let userInfo = notification.request.content.userInfo
        let deliveryId = userInfo["_dId"] as? String
        let broadlogId = userInfo["_mId"] as? String
        let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
        /*
        This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
        */
        if( acsDeliveryTracking == nil ) {
            acsDeliveryTracking = "on";
        }
        if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
             ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
        }
        completionHandler([.alert,.sound])
    }
```

### Come implementare il tracciamento dei clic {#push-click-tracking-iOS}

Per il tracciamento dei clic, è necessario inviare il valore &quot;2&quot; per l&#39;azione quando si chiama la funzione **[!UICONTROL trackAction()]** .
Per le consegne create prima della versione 21.1 o le consegne con modello personalizzato, consulta questa [sezione](../../administration/using/push-tracking.md#about-push-tracking).

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

Ora, quando invii le notifiche push devi aggiungere una categoria. In questo caso, l&#39;abbiamo chiamato &quot;PREDEFINITO&quot;.

![](assets/tracking_push.png)

Quindi, per gestire il **[!UICONTROL Dismiss]** e inviare una informazioni di tracciamento devi aggiungere quanto segue:

```
func userNotificationCenter(_ center: UNUserNotificationCenter, didReceive response: UNNotificationResponse, withCompletionHandler completionHandler: @escaping () -> Void) {
        let userInfo = response.notification.request.content.userInfo
        switch response.actionIdentifier {
        case UNNotificationDismissActionIdentifier:
            print("Dismiss Action")
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### Come implementare il tracciamento delle aperture {#push-open-tracking-iOS}

Dovrai inviare &quot;1&quot; e &quot;2&quot; poiché l’utente deve fare clic sulla notifica per aprire l’app. Se l&#39;app non viene avviata/aperta tramite notifica push, non si verificano eventi di tracciamento.

Per le consegne create prima della versione 21.1 o le consegne con modello personalizzato, consulta questa [sezione](../../administration/using/push-tracking.md#about-push-tracking).

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
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
            }
        default:
            //This is to handle the tracking when the app opens
            let deliveryId = userInfo["_dId"] as? String
            let broadlogId = userInfo["_mId"] as? String
            let acsDeliveryTracking = userInfo["_acsDeliveryTracking"] as? String
            /*
            This is to handle deliveries created before 21.1 release or deliveries with custom template where acsDeliveryTracking is not available.
            */
            if( acsDeliveryTracking == nil ) {
                acsDeliveryTracking = "on";
            }
            if (deliveryId != nil && broadlogId != nil && acsDeliveryTracking?.caseInsensitiveCompare("on") == ComparisonResult.orderedSame) {
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                ADBMobile.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
            }
        }
        completionHandler()
    }
}
```
