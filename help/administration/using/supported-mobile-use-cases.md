---
title: Casi di utilizzo per dispositivi mobili supportati in  Adobe Campaign Standard utilizzando gli SDK Adobe Experience Platform
description: Questo documento fornisce informazioni su come supportare i casi di utilizzo di dispositivi mobili.
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
source-git-commit: 5e1a0bea0a0b43b20830ffdb58c0b53d1ff1e36a
workflow-type: tm+mt
source-wordcount: '953'
ht-degree: 0%

---


# Casi d’uso per dispositivi mobili supportati all’interno di Adobe Campaign Standard {#mobile-use-cases}

In questa pagina, troverete l&#39;elenco di tutti i casi di utilizzo per dispositivi mobili supportati nell&#39; [!DNL Adobe Campaign Standard] utilizzo del [!DNL Adobe Experience Platform SDKs]. Tenere presente che il supporto di questi casi d’uso richiede l’installazione e la configurazione di [!DNL Adobe Experience Platform SDKs], [!DNL Adobe Experience Platform Launch]e [!DNL Adobe Campaign Standard]. For more information on this, refer to this [page](../../administration/using/configuring-a-mobile-application.md).

 Adobe Campaign Standard supporta i seguenti casi di utilizzo:

* [Registrazione di un profilo mobile in Campaign Standard](../../administration/using/supported-mobile-use-cases.md#register-mobile-profile)
* [Inviare un token push all&#39;Campaign Standard](../../administration/using/supported-mobile-use-cases.md#send-push-token)
* [Arricchisci un profilo mobile con dati personalizzati dall’applicazione](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-custom)
* [Arricchisci un profilo mobile con i dati del ciclo di vita dell’applicazione](../../administration/using/supported-mobile-use-cases.md#enrich-mobile-profile-lifecycle)
* [Tracciare l&#39;interazione degli utenti con le notifiche push](../../administration/using/supported-mobile-use-cases.md#track-user-push)
* [Implementare un evento personalizzato nell&#39;app mobile per attivare i messaggi in-app](../../administration/using/supported-mobile-use-cases.md#custom-event-inapp)
* [Impostare i campi di collegamento per l&#39;autenticazione aggiuntiva per il modello di profilo basato sui messaggi in-app](../../administration/using/supported-mobile-use-cases.md#linkage-fields-inapp)

Per configurare questi casi di utilizzo, è necessario disporre delle seguenti estensioni da [!DNL Experience Platform Launch]:

* **[!DNL Adobe Campaign Standard]** <br>Per installare e configurare l’estensione Campaign Standard, vedi [Configurare l’estensione Campaign Standard in Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#configure-the-campaign-standard-extension-in-experience-platform-launch).
* **[!DNL Mobile Core]**, che viene installato automaticamente. <br>Per ulteriori informazioni sull&#39;estensione Mobile Core, vedi [Mobile Core](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core).
* **[!DNL Profile]**, che viene installato automaticamente. <br>Per ulteriori informazioni sull’estensione Profilo, vedi [Profilo](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/profile).

## Registrazione di un profilo mobile in Campaign Standard {#register-mobile-profile}

### Con iOS {#register-mobile-profile-ios}

In iOS, [!DNL Experience Platform APIs] sono necessari i seguenti elementi:

* **[!UICONTROL Lifecycle Start]**, quando l&#39;app viene avviata e quando l&#39;app è in primo piano.
* **[!UICONTROL Lifecycle Pause]**, quando l&#39;app è in background.

Per ulteriori informazioni, vedi Estensione [del ciclo di vita in iOS](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios).

Esempio di implementazione di questo caso di utilizzo con iOS:

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

In Android, [!DNL Experience Platform APIs] sono necessari i seguenti elementi:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Per ulteriori informazioni, vedi Estensione [del ciclo di vita in Android](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android).

Esempio di implementazione per questo caso di utilizzo con Android:

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

## Inviare un token push a  Adobe Campaign Standard {#send-push-token}

### Con iOS {#send-push-token-ios}

In iOS, [!DNL Experience Platform SDK] è necessario quanto segue:

* **[!UICONTROL setPushIdentifier]** <br>Per ulteriori informazioni, vedi [setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier).

Esempio di implementazione per questo caso di utilizzo con iOS:

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
  
 // Register Device Token
 ACPCore.setPushIdentifier(deviceToken)
```

### Con Android {#send-push-token-android}

In Android, [!DNL Experience Platform SDK] è necessario quanto segue:

* **[!UICONTROL setPushIdentifier]** <br>Per ulteriori informazioni, vedi [setPushIdentifier](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#setpushidentifier).

Esempio di implementazione per questo caso di utilizzo con Android:

```
@Override
public void onNewToken(String token) {
    Log.d(TAG, "Refreshed token: " + token);
    MobileCore.setPushIdentifier(token);
}
```

## Arricchisci un profilo mobile con dati personalizzati dall’applicazione {#enrich-mobile-profile-custom}

Affinché questo caso d’uso funzioni, è necessario creare regole per i postback PII. Per ulteriori informazioni, vedi [Postback](../../administration/using/configuring-rules-launch.md#pii-postback)PII.

### Con iOS {#enrich-mobile-profile-custom-ios}

In iOS, [!DNL Experience Platform API] è necessario quanto segue:

* collectPII <br> Per ulteriori informazioni, vedi collectPII.

Esempio di implementazione di questo caso di utilizzo con iOS:

```
ACPCore.collectPii(["email":email, "firstName":firstName, "lastName":lastName])
```

### Con Android {#enrich-mobile-profile-custom-android}

In Android, [!DNL Experience Platform API] è necessario quanto segue:

* collectPII <br> Per ulteriori informazioni, vedi collectPII.

Esempio di implementazione per questo caso di utilizzo con Android:

```
HashMap<String, String> data = new HashMap<>();
data.put("firstName", firstNameText);
data.put("lastName", lastNameText);
data.put("email", emailText);
MobileCore.collectPii(data);
```

## Arricchisci un profilo mobile con i dati del ciclo di vita dell’applicazione {#enrich-mobile-profile-lifecycle}

Affinché questo caso d’uso funzioni, è necessario creare regole per i postback PII. Per ulteriori informazioni, vedi [Postback](../../administration/using/configuring-rules-launch.md#pii-postback)PII.

>[!NOTE]
>
> Adobe Campaign non fa distinzione tra dati personalizzati o dati del ciclo di vita dall&#39;app mobile. Entrambi i tipi di dati possono essere inviati al server utilizzando una regola di postback collectPii in risposta a un evento nell&#39;app mobile.

### Con iOS {#enrich-mobile-profile-lifecycle-ios}

In iOS, [!DNL Experience Platform APIs] sono necessari i seguenti elementi:

* **[!UICONTROL Lifecycle Start]**, quando l&#39;app viene avviata e quando l&#39;app è in primo piano.
* **[!UICONTROL Lifecycle Pause]**, quando l&#39;app è in background.

Per ulteriori informazioni, vedi Estensione [del ciclo di vita in iOS](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-ios).

Esempio di implementazione di questo caso di utilizzo con iOS:

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

In Android, [!DNL Experience Platform APIs] sono necessari i seguenti elementi:

* **[!UICONTROL OnResume]**
* **[!UICONTROL OnPause]**

Per ulteriori informazioni, vedi Estensione [del ciclo di vita in Android](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/lifecycle/lifecycle-extension-in-android).

Esempio di implementazione per questo caso di utilizzo con Android:

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

## Tracciare l&#39;interazione degli utenti con le notifiche push {#track-user-push}

Devi creare regole per il tracciamento dei postback delle notifiche push. Per ulteriori informazioni, vedi [Notifiche push con tracciamento postback](../../administration/using/configuring-rules-launch.md#push-tracking-postback).

### Con iOS {#track-user-push-ios}

In iOS, [!DNL Experience Platform SDK] è necessario quanto segue:

* **[!UICONTROL trackAction]**. Per ulteriori informazioni, vedi [Tracciare le azioni](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)dell&#39;app.

Esempio di implementazione di questo caso di utilizzo con iOS:

```
let deliveryId = userInfo["_dId"] as? String
let broadlogId = userInfo["_mId"] as? String
if (deliveryId != nil && broadlogId != nil) {
    ACPCore.trackAction("tracking", data: ["deliveryId": deliveryId!, "broadlogId": broadlogId!, "action":"2"])
}
```

### Con Android {#track-user-push-android}

In Android, [!DNL Experience Platform SDK] è necessario quanto segue:

* **[!UICONTROL trackAction]**
Per ulteriori informazioni, vedi [Tracciare le azioni](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)dell&#39;app.

Esempio di implementazione per questo caso di utilizzo con Android:

```
contextData.put("deliveryId", deliveryId);
contextData.put("broadlogId", messageId);
contextData.put("action", "2");
MobileCore.trackAction("tracking", contextData);
```

## Implementare un evento personalizzato nell&#39;applicazione per attivare i messaggi in-app {#custom-event-inapp}

### Con iOS {#custom-event-inapp-ios}

In iOS, [!DNL Experience Platform SDK] è necessario quanto segue:

* **[!UICONTROL trackAction]**. Per ulteriori informazioni, vedi [Tracciare le azioni](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)dell&#39;app.

Esempio di implementazione di questo caso di utilizzo con iOS:

```
ACPCore.trackAction(mobileEventName, data: [:] )
```

### Con Android {#custom-event-inapp-android}

In Android, [!DNL Experience Platform SDK] è necessario quanto segue:

* **[!UICONTROL trackAction]**
Per ulteriori informazioni, vedi [Tracciare le azioni](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions)dell&#39;app.

Esempio di implementazione per questo caso di utilizzo con Android:

```
MobileCore.trackAction(mobileEventText, new HashMap<String,String>());
```

## Impostare i campi di collegamento per l&#39;autenticazione aggiuntiva {#linkage-fields-inapp}

### Con iOS {#linkage-fields-inapp-ios}

Per impostare i campi di collegamento per l&#39;autenticazione aggiuntiva per il modello di profilo basato sui messaggi in-app in iOS, [!DNL Experience Platform SDK] è necessario quanto segue:

* Impostare i campi di collegamento <br>Per ulteriori informazioni, vedere [Impostare i campi](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)di collegamento.
* Reimpostare i campi di collegamento <br>Per ulteriori informazioni, vedere [Reimpostare i campi](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields)di collegamento.

Di seguito sono riportati alcuni esempi di implementazione di questo caso di utilizzo con iOS.

Per impostare i campi di collegamento:

```
var linkageFields = [String: String]()
linkageFields["cusEmail"] = "john.doe@email.com"
ACPCampaign.setLinkageFields(linkageFields)
```

Per ripristinare i campi di collegamento:

```
ACPCampaign.resetLinkageFields(linkageFields)
```

### Con Android {#linkage-fields-inapp-android}

Per impostare i campi di collegamento per l&#39;autenticazione aggiuntiva per il modello di profilo basato sui messaggi in-app in Android, è necessario il seguente SDK  Experience Platform:

* Impostare i campi di collegamento <br>Per ulteriori informazioni, vedere [Impostare i campi](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#set-linkage-fields)di collegamento.
* Reimpostare i campi di collegamento <br>Per ulteriori informazioni, vedere [Reimpostare i campi](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard/adobe-campaign-standard-api-reference#reset-linkage-fields)di collegamento.

Di seguito sono riportati alcuni esempi di implementazione di questo caso di utilizzo con Android.

Per impostare i campi di collegamento:

```
HashMap<String, String> linkageFields = new HashMap<String, String>();
linkageFields.put("cusEmail", "john.doe@email.com");
Campaign.setLinkageFields(linkageFields);
```

Per ripristinare i campi di collegamento:

```
Campaign.resetLinkageFields()
```
