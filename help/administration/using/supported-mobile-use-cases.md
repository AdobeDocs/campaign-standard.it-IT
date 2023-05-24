---
title: Casi d’uso per dispositivi mobili supportati in Adobe Campaign Standard utilizzando gli SDK di Adobe Experience Platform
description: Scopri come supportare i casi d’uso per dispositivi mobili
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 3cd8d756-a271-4e53-8ed0-984ce20298bc
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 0%

---

# Casi d’uso per dispositivi mobili supportati in Adobe Campaign Standard {#mobile-use-cases}

In questa pagina è riportato l’elenco di tutti i casi d’uso per dispositivi mobili supportati in [!DNL Adobe Campaign Standard] utilizzando [!DNL Adobe Experience Platform SDKs]. Il supporto di questi casi d’uso richiede l’installazione e la configurazione di [!DNL Adobe Experience Platform SDKs], [!DNL tags in Adobe Experience Platform], e [!DNL Adobe Campaign Standard]. Per ulteriori informazioni, consulta questa [pagina](../../administration/using/configuring-a-mobile-application.md).

Adobe Campaign Standard supporta i seguenti casi d’uso:

* [Registrare un profilo mobile in Campaign Standard](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Inviare un token push a Campaign Standard](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [Arricchire un profilo mobile con dati personalizzati dell’applicazione](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [Arricchire un profilo mobile con i dati del ciclo di vita dell’applicazione](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [Tracciare l’interazione dell’utente con le notifiche push](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [Implementare un evento personalizzato nell’app mobile per attivare i messaggi in-app](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [Imposta i campi di collegamento per l’autenticazione aggiuntiva per il modello di profilo basato sui messaggi in-app](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

Per configurare questi casi d’uso, sono necessarie le seguenti estensioni:

* **[!DNL Adobe Campaign Standard]** <br>Per installare e configurare l’estensione Campaign Standard, consulta [Configurare l’estensione Campaign Standard nell’interfaccia utente di Data Collection](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#configure-the-campaign-standard-extension).
* **[!DNL Mobile Core]**, che viene installato automaticamente. <br>Per ulteriori informazioni sull’estensione core per dispositivi mobili, consulta [Core mobile](https://developer.adobe.com/client-sdks/documentation/mobile-core/).
* **[!DNL Profile]**, che viene installato automaticamente. <br>Per ulteriori informazioni sull’estensione Profilo, consulta [Profilo](https://developer.adobe.com/client-sdks/documentation/profile/).

## Registrare un profilo mobile in Campaign Standard {#register-mobile-profile}

### Con iOS {#register-mobile-profile-ios}

In iOS, i seguenti elementi [!DNL Experience Platform APIs] sono obbligatori:

* **[!UICONTROL Lifecycle Start]**, quando l&#39;app viene avviata e quando l&#39;app è in primo piano.
* **[!UICONTROL Lifecycle Pause]**, quando l&#39;app è in background.

Per ulteriori informazioni, consulta [Estensione del ciclo di vita in iOS](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

Di seguito è riportato un esempio di implementazione di questo caso d’uso con iOS:

```
 func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Con Android {#register-mobile-profile-android}

In Android, i seguenti [!DNL Experience Platform APIs] sono obbligatori:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Per ulteriori informazioni, consulta [Estensione del ciclo di vita in Android](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

Di seguito è riportato un esempio di implementazione per questo caso d’uso con Android:

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## Inviare un token push ad Adobe Campaign Standard {#send-push-token}

### Con iOS {#send-push-token-ios}

In iOS, i seguenti elementi [!DNL Experience Platform SDK] è obbligatorio:

* **[!UICONTROL setPushIdentifier]** <br>Per ulteriori informazioni, consulta [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

Di seguito è riportato un esempio di implementazione per questo caso d’uso con iOS:

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Con Android {#send-push-token-android}

In Android, i seguenti [!DNL Experience Platform SDK] è obbligatorio:

* **[!UICONTROL setPushIdentifier]** <br>Per ulteriori informazioni, consulta [setPushIdentifier](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/).

Di seguito è riportato un esempio di implementazione per questo caso d’uso con Android:

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## Arricchire un profilo mobile con dati personalizzati dell’applicazione {#enrich-mobile-profile-custom}

Affinché questo caso d’uso funzioni, devi creare regole per i postback PII. Per ulteriori informazioni, consulta [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback).

### Con iOS {#enrich-mobile-profile-custom-ios}

In iOS, i seguenti elementi [!DNL Experience Platform API] è obbligatorio:

* collectPII <br> Per ulteriori informazioni, consulta collectPII.

Di seguito è riportato un esempio di implementazione di questo caso d’uso con iOS:

```
ACPCore.collectPii(["pushPlatform":"apns", "email":email, "firstName":firstName, "lastName":lastName])
```

### Con Android {#enrich-mobile-profile-custom-android}

In Android, i seguenti [!DNL Experience Platform API] è obbligatorio:

* collectPII <br> Per ulteriori informazioni, consulta collectPII.

Di seguito è riportato un esempio di implementazione per questo caso d’uso con Android:

```
HashMap<String, String> data = new HashMap<>();
data.put("pushPlatform", "gcm");
data.put("firstName", firstNameText); 
data.put("lastName", lastNameText); 
data.put("email", emailText); 
MobileCore.collectPii(data);
```

## Arricchire un profilo mobile con i dati del ciclo di vita dell’applicazione {#enrich-mobile-profile-lifecycle}

Affinché questo caso d’uso funzioni, devi creare regole per i postback PII. Per ulteriori informazioni, consulta [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback).

>[!NOTE]
>
>Adobe Campaign non distingue tra dati personalizzati o dati del ciclo di vita e l’app mobile. Entrambi i tipi di dati possono essere inviati al server utilizzando una regola di postback collectPii in risposta a un evento nell’app mobile.

### Con iOS {#enrich-mobile-profile-lifecycle-ios}

In iOS, i seguenti elementi [!DNL Experience Platform APIs] sono obbligatori:

* **[!UICONTROL Lifecycle Start]**, quando l&#39;app viene avviata e quando l&#39;app è in primo piano.
* **[!UICONTROL Lifecycle Pause]**, quando l&#39;app è in background.

Per ulteriori informazioni, consulta [Estensione del ciclo di vita in iOS](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/ios/).

Di seguito è riportato un esempio di implementazione di questo caso d’uso con iOS:

```
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
  
  
 ACPCore.setLogLevel(.debug)
 appId = SettingsBundle.getLaunchAppId()
   
 //===== START Set up Adobe SDK =====
 ACPCore.configure(withAppId: appId)
   
 ACPCampaign.registerExtension()
 ACPIdentity.registerExtension()
 ACPLifecycle.registerExtension()
 ACPUserProfile.registerExtension()
 ACPSignal.registerExtension()
 ACPCore.start()
 ACPCore.lifecycleStart(nil)
   
 return true
 }
  
func applicationDidEnterBackground(_ application: UIApplication) {
 ACPCore.lifecyclePause()
 }
   
 func applicationDidBecomeActive(_ application: UIApplication) {
 // Workaround until jira AMSDK-7411 is fixed.
 sleep(2)
 ACPCore.lifecycleStart(nil)
 }
```

### Con Android {#enrich-mobile-profile-lifecycle-android}

In Android, i seguenti [!DNL Experience Platform APIs] sono obbligatori:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Per ulteriori informazioni, consulta [Estensione del ciclo di vita in Android](https://developer.adobe.com/client-sdks/documentation/mobile-core/lifecycle/android/).

Di seguito è riportato un esempio di implementazione per questo caso d’uso con Android:

```
@Override
  
public void onResume() {
 super.onResume();
 MobileCore.setApplication(getApplication());
 MobileCore.lifecycleStart(null);
 handleOpenTracking();
 }
  
 @Override
 public void onPause() {
 super.onPause();
 MobileCore.lifecyclePause();
 }
```

## Tracciare l’interazione dell’utente con le notifiche push {#track-user-push}

Devi creare regole per il postback del tracciamento delle notifiche push. Per ulteriori informazioni, consulta [Postback tracciamento notifiche push](../../administration/using/configuring-rules-launch.md#push-tracking-postback).

### Con iOS {#track-user-push-ios}

In iOS, i seguenti elementi [!DNL Experience Platform SDK] è obbligatorio:

* **[!UICONTROL trackAction]**. Per ulteriori informazioni, consulta [Tracciare le azioni eseguite nell’app](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Di seguito è riportato un esempio di implementazione di questo caso d’uso con iOS:

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Con Android {#track-user-push-android}

In Android, i seguenti [!DNL Experience Platform SDK] è obbligatorio:

* **[!UICONTROL trackAction]**
Per ulteriori informazioni, consulta [Tracciare le azioni eseguite nell’app](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Di seguito è riportato un esempio di implementazione per questo caso d’uso con Android:

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## Implementare un evento personalizzato nell’applicazione per attivare i messaggi in-app {#custom-event-inapp}

### Con iOS {#custom-event-inapp-ios}

In iOS, i seguenti elementi [!DNL Experience Platform SDK] è obbligatorio:

* **[!UICONTROL trackAction]**. Per ulteriori informazioni, consulta [Tracciare le azioni eseguite nell’app](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Di seguito è riportato un esempio di implementazione di questo caso d’uso con iOS:

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Con Android {#custom-event-inapp-android}

In Android, i seguenti [!DNL Experience Platform SDK] è obbligatorio:

* **[!UICONTROL trackAction]**
Per ulteriori informazioni, consulta [Tracciare le azioni eseguite nell’app](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#trackaction).

Di seguito è riportato un esempio di implementazione per questo caso d’uso con Android:

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## Imposta campi di collegamento per autenticazione aggiuntiva {#linkage-fields-inapp}

### Con iOS {#linkage-fields-inapp-ios}

Per impostare i campi di collegamento per l’autenticazione aggiuntiva per il modello di profilo basato sui messaggi in-app in iOS, procedi come segue [!DNL Experience Platform SDK] è obbligatorio:

* Imposta campi di collegamento <br>Per ulteriori informazioni, consulta [Imposta campi di collegamento](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* Reimposta campi di collegamento <br>Per ulteriori informazioni, consulta [Reimposta campi di collegamento](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).

Di seguito sono riportati esempi di implementazioni di questo caso d’uso con iOS.

Per impostare i campi di collegamento:

```
var linkageFields = [String: String]()
linkageFields["cusEmail"] = "john.doe@email.com"
ACPCampaign.setLinkageFields(linkageFields)
```

Per reimpostare i campi di collegamento:

```
ACPCampaign.resetLinkageFields(linkageFields)
```

### Con Android {#linkage-fields-inapp-android}

Per impostare i campi di collegamento per un’autenticazione aggiuntiva per il modello di profilo basato sui messaggi in-app in Android, è necessario il seguente SDK di Experience Platform:

* Imposta campi di collegamento <br>Per ulteriori informazioni, consulta [Imposta campi di collegamento](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#setlinkagefields).
* Reimposta campi di collegamento <br>Per ulteriori informazioni, consulta [Reimposta campi di collegamento](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/api-reference/#resetlinkagefields).

Di seguito sono riportati esempi di implementazioni di questo caso d’uso con Android.

Per impostare i campi di collegamento:

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

Per reimpostare i campi di collegamento:

```
Campaign.resetLinkageFields()
```
