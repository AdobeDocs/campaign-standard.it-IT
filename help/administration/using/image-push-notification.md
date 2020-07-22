---
title: Visualizzazione di un’immagine da una notifica push di Adobe Campaign Standard
description: Scoprite come visualizzare un'immagine da una notifica push di Adobe Campaign  su un dispositivo iOS.
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
source-git-commit: 6c5cf90211451587537b9a6121430fc4f352384c
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 2%

---


# Aggiunta di immagini e video iOS {#image-push}

>[!NOTE]
>
>Questo documento si applica solo ai dispositivi iOS.

In questo documento, scoprite come visualizzare un&#39;immagine da una notifica push iOS  Adobe Campaign Standard.

## Passaggio 1: Configurare la notifica push {#set-up-push}

La notifica push è supportata  SDK Experience Platform.

Le applicazioni mobili che ricevono notifiche push devono essere configurate da un amministratore nell&#39;interfaccia del Adobe Campaign .

Configurando sia  Adobe Campaign che Adobe Mobile Services, potrete utilizzare i dati dell&#39;applicazione mobile per le campagne. For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Per inviare notifiche push con un&#39;applicazione SDK Experience Cloud , è necessario impostare un&#39;app mobile  Launch del Adobe Experience Platform e configurarla in  Adobe Campaign. For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

## Passaggio 2: Personalizzare la notifica push in  Adobe Campaign {#customize-push}

Per ottimizzare la notifica push,  Adobe Campaign consente di accedere a una serie di opzioni avanzate durante la progettazione di una notifica push.

1. Create una notifica push. For more on this, refer to this [page](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Dalla pagina del contenuto della notifica push, accedete alla **[!UICONTROL Advanced options]** sezione.

1. Immettete l’URL del file nel **[!UICONTROL Rich media content URL]** campo.
Per iOS 10 o versione successiva, potete inserire file immagine, gif, audio e video.

   ![](assets/push_notif_advanced_6.png)

1. Visualizzate l&#39;anteprima e salvate la notifica push.

## Passaggio 3: Adattamento del codice dell&#39;applicazione Mobile {#mobile-app-code}

Dopo aver personalizzato la notifica push in  Adobe Campaign, dovete configurare l&#39;applicazione mobile per visualizzare l&#39;immagine sui dispositivi.

>[!NOTE]
>
>Se l&#39;applicazione è in Objective-C, fare riferimento alla seguente [documentazione](https://docs.adobe.com/content/help/en/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html).

Se l’app è in [!DNL Swift]uso, effettuate le seguenti operazioni:

1. Aprite il progetto [DNL Xcode] .

1. Nel progetto [DNL Xcode] , selezionate **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL Target]**.

1. Selezionare **[!UICONTROL Notification Service Extension]**.

   ![](assets/push_notif_advanced_12.png)

1. Verificate che venga creata la classe di file **NotificationService.swift** .

1. Modificate questa classe e sostituite il contenuto predefinito con quanto segue.
Questo consente all’applicazione di gestire il parametro in entrata con l’URL dell’immagine, analizzarlo, copiarlo localmente e quindi visualizzarlo dalla notifica push.

   ```
   import UserNotifications
   
   class NotificationService: UNNotificationServiceExtension {
   
   var contentHandler: ((UNNotificationContent) -> Void)?
   var bestAttemptContent: UNMutableNotificationContent?
   
   override func didReceive(_ request: UNNotificationRequest, withContentHandler contentHandler: @escaping (UNNotificationContent) -> Void) {
       self.contentHandler = contentHandler
       bestAttemptContent = (request.content.mutableCopy() as? UNMutableNotificationContent)
   
       if let bestAttemptContent = bestAttemptContent {
           var urlString:String? = nil
           if let urlImageString = request.content.userInfo["media-attachment-url"] as? String {
               urlString = urlImageString
           }
   
           if urlString != nil, let fileUrl = URL(string: urlString!) {
               print("fileUrl: \(fileUrl)")
   
               // Download the attachment
               URLSession.shared.downloadTask(with: fileUrl) { (location, response, error) in
                   if let location = location {
                       // Move temporary file to remove .tmp extension
                       if (error == nil) {
                           let tmpDirectory = NSTemporaryDirectory()
                           let tmpFile = "file://".appending(tmpDirectory).appending(fileUrl.lastPathComponent)
                           let tmpUrl = URL(string: tmpFile)!
                           try! FileManager.default.moveItem(at: location, to: tmpUrl)
   
                           // Add the attachment to the notification content
                           if let attachment = try? UNNotificationAttachment(identifier: fileUrl.lastPathComponent, url: tmpUrl) {
                               bestAttemptContent.attachments = [attachment]
                               }
                       }
                       if(error != nil) {
                           print("Failed to download attachment: \(error.debugDescription)")
                       }
                   }
                   // Serve the notification content
                   contentHandler(bestAttemptContent)
               }.resume()
           }
       }
   }
   
   override func serviceExtensionTimeWillExpire() {
       // Called just before the extension will be terminated by the system.
       // Use this as an opportunity to deliver your "best attempt" at modified content, otherwise the original push payload will be used.
       if let contentHandler = contentHandler, let bestAttemptContent = bestAttemptContent {
           contentHandler(bestAttemptContent)
       }
   }
   
   }
   ```

Il cellulare deve ricevere il payload seguente durante l&#39;invio della notifica.

L’URL dell’immagine viene mappato con l’URL del supporto chiave-attachment-url. È la coppia chiave/valore che è necessario gestire dal punto di vista del codice dell&#39;applicazione per scaricare e visualizzare l&#39;immagine.

```
userInfo: [AnyHashable("media-attachment-url"): https://pbs.twimg.com/profile_images/876737835314950144/zPTs9b7o.jpg, AnyHashable("_dId"): 1de3ef93, AnyHashable("_mId"): h280a5, AnyHashable("aps"): {
 
    alert =     {
 
        body = "Message Body here";
 
        title = "This a push from Campaign";
 
    };
 
    badge = 1;
 
    "mutable-content" = 1;
 
}]
```

## Passaggio 4: Test dell&#39;invio del push {#test-send-push}

È ora possibile verificare la creazione dell&#39;applicazione e la consegna creata nel passaggio 2 precedente. Per ulteriori informazioni sulla preparazione e l&#39;invio della notifica push, consultate questa [pagina](../../channels/using/preparing-and-sending-a-push-notification.md).

![](assets/push_notif_advanced_34.png)

