---
title: Implementazione del tracciamento push
description: Scopri come garantire che il tracciamento delle notifiche push sia stato implementato correttamente su iOS e Android
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 950d24e2-358f-44f8-98ea-643be61d4573
source-git-commit: 1346f7d833515fb2e6feabb39d199ffd5610c88e
workflow-type: tm+mt
source-wordcount: '932'
ht-degree: 0%

---

# Implementazione del tracciamento push {#push-tracking}

## Informazioni sul tracciamento push {#about-push-tracking}

Per garantire che la notifica push sia stata completamente sviluppata, è necessario assicurarsi che la parte di tracciamento sia stata implementata correttamente, poiché il tracciamento non è stato abilitato per tutte le notifiche push. Per abilitare questa funzione, gli sviluppatori devono identificare quali consegne hanno abilitato il tracciamento, Adobe Campaign Standard invierà un flag denominato `_acsDeliveryTracking` con due valori **on** o **off**. Lo sviluppatore di app deve inviare una richiesta di tracciamento solo per le consegne con variabile impostata come **il**.

>[!IMPORTANT]
>
>Questa variabile non è disponibile per le consegne impostate prima della versione 21.1 o per le consegne che utilizzano modelli personalizzati.

Il tracciamento push è diviso in tre tipi:

* **Impression push** - Quando una notifica push è stata recapitata correttamente al dispositivo, che risiede nel centro notifiche senza alcuna interazione da parte dell&#39;utente.

* **Clic push** - Quando una notifica push è stata recapitata al dispositivo e l&#39;utente ha fatto clic sul dispositivo.  L’utente desidera visualizzare la notifica (che a sua volta passerà al tracciamento delle aperture push) o ignorare la notifica.

* **Push Open** - Quando una notifica push è stata recapitata al dispositivo e l&#39;utente ha fatto clic sulla notifica causando l&#39;apertura dell&#39;app. È simile al Clic push, tranne per il fatto che l’apertura push non viene attivata se la notifica viene chiusa.

Per implementare il tracciamento per Campaign Standard, l’app mobile deve includere gli SDK di Adobe Experience Platform. Questi SDK sono disponibili nella [documentazione degli SDK Adobe Experience Platform](https://github.com/Adobe-Marketing-Cloud/acp-sdks).

Per inviare le informazioni di tracciamento sono necessarie tre variabili. Due che fanno parte dei dati ricevuti da Campaign Standard e una variabile di azione che determina se si tratta di un **Impression**, **Click** o **Open**.

| Variabile | Elemento “value” |
|:-:|:-:|
| broadlogId | _mId da dati |
| deliveryId | _dId da dati |
| azione | &quot;1&quot; per Apri, &quot;2&quot; per Clic e &quot;7&quot; per Impression |

## Implementazione per Android {#implementation-android}

### Come implementare il tracciamento delle impression push {#push-impression-tracking-android}

Per il tracciamento delle impression, dovrai inviare il valore &quot;7&quot; per l&#39;azione quando chiami le funzioni `collectMessageInfo()` o `trackAction()`.

Per le consegne create prima della versione 21.1 o per le consegne con modello personalizzato, fai riferimento a questa [sezione](../../administration/using/push-tracking.md#about-push-tracking).

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
    if( deliveryId != null && messageId != null && acsDeliveryTracking.equals("on")) {
      contextData.put("deliveryId", deliveryId);
      contextData.put("broadlogId", messageId);
      contextData.put("action", "7");

    //If you are using ACPCore v1.4.0 or later, use the next line.
      
      MobileCore.collectMessageInfo(contextData);
      
    //Else comment out the above line and uncomment the line below
        
    //MobileCore.trackAction("tracking", contextData) ;
    }
  }
}
```

### Come implementare il tracciamento dei clic {#push-click-tracking-android}

Per il tracciamento dei clic, è necessario inviare il valore &quot;2&quot; per l&#39;azione quando si chiamano le funzioni `collectMessageInfo()` o `trackAction()`.
Per tenere traccia dei clic, è necessario gestire due scenari:

* L’utente visualizza la notifica ma la cancella.
* L’utente visualizza la notifica e fa clic su di essa, trasformandola in un tracciamento aperto.

Per gestire questo problema, è necessario utilizzare due Intenti: uno per fare clic sulla notifica e un altro per ignorare la notifica.

Per le consegne create prima della versione 21.1 o per le consegne con modello personalizzato, fai riferimento a questa [sezione](../../administration/using/push-tracking.md#about-push-tracking).

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

Per il corretto funzionamento di **[!UICONTROL BroadcastReceiver]** è necessario registrarlo in **[!UICONTROL AndroidManifest.xml]**

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
            
        //If you are using ACPCore v1.4.0 or later, use the next line.
        
            MobileCore.collectMessageInfo(contextData);
            
        //Else comment out the above line and uncomment the line below
        
            //MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

### Come implementare il tracciamento aperto {#push-open-tracking-android}

Dovrai inviare &quot;1&quot; e &quot;2&quot; perché l’utente deve fare clic sulla notifica per aprire l’app. Se l’app non viene avviata/aperta tramite notifica push, non si verifica alcun evento di tracciamento.

Per tenere traccia dell’apertura, è necessario creare un Intento. Gli oggetti intento consentono al sistema operativo Android di chiamare il metodo quando vengono eseguite determinate azioni. In questo caso, fai clic sulla notifica per aprire l’app.

Questo codice si basa sull’implementazione del tracciamento delle impression di clic. Con **[!UICONTROL Intent]** impostato, ora devi inviare nuovamente le informazioni di tracciamento ad Adobe Campaign Standard. In questo caso, è necessario impostare **[!UICONTROL Open Intent]** per l&#39;apertura a una determinata visualizzazione nell&#39;app. Verrà chiamato il metodo onResume con i dati di notifica in **[!UICONTROL Intent Object]**.

Per le consegne create prima della versione 21.1 o per le consegne con modello personalizzato, fai riferimento a questa [sezione](../../administration/using/push-tracking.md#about-push-tracking).

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
            contextData.put("action", "2");
            
            //Send Click Tracking since the user did click on the notification
              
                //If you are using ACPCore v1.4.0 or later, use the next line.

                MobileCore.collectMessageInfo(contextData);
                  
                //Else comment out the above line and uncomment the line below
        
                //MobileCore.trackAction("tracking", contextData);
 
                //Send Open Tracking since the user opened the app
            
                contextData.put("action", "1");
                
                //If you are using ACPCore v1.4.0 or later, use the next line.

                MobileCore.collectMessageInfo(contextData);
                //Else comment out the above line and uncomment the line below
        
                //MobileCore.trackAction("tracking", contextData);
        }
    }
}
```

## Implementazione per iOS {#implementation-iOS}

### Come implementare il tracciamento delle impression push {#push-impression-tracking-iOS}

Per il tracciamento delle impression, dovrai inviare il valore &quot;7&quot; per l&#39;azione quando chiami le funzioni `collectMessageInfo()` o `trackAction()`.

Per comprendere come funzionano le notifiche di iOS, è necessario specificare i tre stati di un’app:

* **Primo piano**: quando l&#39;app è attiva ed è attualmente sullo schermo (in primo piano).
* **Sfondo**: quando l&#39;app is non è sullo schermo ma il processo non è chiuso. Quando si fa doppio clic sul pulsante Home, in genere vengono mostrate tutte le app in background.
* **Disattivata/chiusa**: un&#39;app il cui processo è stato interrotto.

Per far sì che il monitoraggio di **[!UICONTROL Impression]** continui a funzionare mentre l&#39;app è in background, è necessario inviare **[!UICONTROL Content-Available]** per informare l&#39;app che è necessario eseguire un monitoraggio.

>[!CAUTION]
>
> Se un’app viene chiusa, Apple non la chiamerà finché l’app non viene riavviata. Ciò significa che non potrai sapere quando è stata ricevuta la notifica su iOS. </br> Per questo motivo, il tracciamento delle impression di iOS potrebbe non essere accurato e non dovrebbe essere considerato affidabile.

Per le consegne create prima della versione 21.1 o per le consegne con modello personalizzato, fai riferimento a questa [sezione](../../administration/using/push-tracking.md#about-push-tracking).

La seguente app di destinazione del codice è l&#39;app in background:

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
            }
        }
        completionHandler(UIBackgroundFetchResult.noData)
    }
```

Il seguente codice esegue il targeting dell’app in primo piano:

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"7"])        
            }
        completionHandler([.alert,.sound])
    }
```

### Come implementare il tracciamento dei clic {#push-click-tracking-iOS}

Per il tracciamento dei clic, è necessario inviare il valore &quot;2&quot; per l&#39;azione quando si chiamano le funzioni `collectMessageInfo()` o `trackAction()`.
Per le consegne create prima della versione 21.1 o per le consegne con modello personalizzato, fai riferimento a questa [sezione](../../administration/using/push-tracking.md#about-push-tracking).

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

Ora, quando invii notifiche push, devi aggiungere una categoria. In questo caso, l’abbiamo chiamata &quot;DEFAULT&quot;.

![](assets/tracking_push.png)

Quindi per gestire **[!UICONTROL Dismiss]** e inviare le informazioni di tracciamento è necessario aggiungere quanto segue:

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])   
            }
        default:
            ////MORE CODE
        }
        completionHandler()
    }
```

### Come implementare il tracciamento aperto {#push-open-tracking-iOS}

Dovrai inviare &quot;1&quot; e &quot;2&quot; perché l’utente deve fare clic sulla notifica per aprire l’app. Se l’app non viene avviata/aperta tramite notifica push, non si verifica alcun evento di tracciamento.

Per le consegne create prima della versione 21.1 o per le consegne con modello personalizzato, fai riferimento a questa [sezione](../../administration/using/push-tracking.md#about-push-tracking).

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

            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])

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
            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])                
                
            //If you are using ACPCore v2.3.0 or later, use the next line.

                ACPCore.collectMessageInfo(["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
                
            //Else comment out the above line and uncomment the line below
        
                //ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"1"])
                
            }
        }
        completionHandler()
    }
}
```
