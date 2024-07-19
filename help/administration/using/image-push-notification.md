---
title: Visualizzare un’immagine da una notifica push di Adobe Campaign Standard
description: Scopri come visualizzare un’immagine da una notifica push di Adobe Campaign su un dispositivo iOS
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 474c8002-4263-4617-9480-6a9b603bde8e
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 12%

---

# Aggiunta di immagini e video iOS {#image-push}

>[!NOTE]
>
>Questo documento si applica solo al dispositivo iOS.

In questo documento, scopri come visualizzare un’immagine da una notifica push di Adobe Campaign Standard iOS.

## Passaggio 1: configurare la notifica push {#set-up-push}

La notifica push è supportata dagli SDK Experience Platform.

Le app mobili che ricevono notifiche push devono essere configurate da un amministratore nell’interfaccia di Adobe Campaign.

Configurando sia Adobe Campaign che Adobe Mobile Services, potrai utilizzare i dati dell’app mobile per le tue campagne. Per ulteriori informazioni, consulta questa [pagina](../../administration/using/configuring-a-mobile-application.md).

Per inviare notifiche push con un’applicazione SDK Experience Cloud, è necessario configurare un’app mobile nell’interfaccia utente di Data Collection e configurarla all’interno di Adobe Campaign. Per ulteriori informazioni, consulta questa [pagina](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

## Passaggio 2: personalizzare la notifica push in Adobe Campaign {#customize-push}

Per ottimizzare la notifica push, Adobe Campaign ti consente di accedere a un set di opzioni avanzate durante la progettazione di una notifica push.

1. Creare una notifica push. Per ulteriori informazioni, consulta questa [pagina](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Dalla pagina del contenuto della notifica push, accedi alla sezione **[!UICONTROL Advanced options]**.

1. Immettere l&#39;URL del file nel campo **[!UICONTROL Rich media content URL]**.
Per iOS 10 o versioni successive, puoi inserire file immagine, gif, audio e video.

   ![](assets/push_notif_advanced_6.png)

1. Visualizza l’anteprima e salva la notifica push.

## Passaggio 3: adattare il codice dell’applicazione mobile {#mobile-app-code}

Dopo aver personalizzato la notifica push in Adobe Campaign, devi configurare l’app mobile per visualizzare l’immagine sui dispositivi.

>[!NOTE]
>
>Se l&#39;applicazione si trova in Objective-C, consulta la [documentazione](https://experienceleague.adobe.com/docs/mobile-services/ios/messaging-ios/push-messaging/c-set-up-rich-push-notif-ios.html) seguente.

Se l&#39;app si trova in [!DNL Swift], eseguire la procedura seguente:

1. Apri il progetto [!DNL Xcode].

1. Nel progetto [!DNL Xcode], selezionare **[!UICONTROL File]** > **[!UICONTROL New]** > **[!UICONTROL Target]**.

1. Seleziona **[!UICONTROL Notification Service Extension]**.

   ![](assets/push_notif_advanced_12.png)

1. Verificare che sia stata creata la classe di file **NotificationService.swift**.

1. Modifica questa classe e sostituisci il contenuto predefinito con quanto segue.
Questo consente all’applicazione di gestire il parametro in ingresso con l’URL dell’immagine, analizzarlo, copiarlo localmente e quindi visualizzarlo dalla notifica push.

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

Il dispositivo mobile deve ricevere il seguente payload mentre viene inviata la notifica.

L’URL dell’immagine è mappato con l’URL dell’allegato multimediale chiave. Questa è la coppia chiave/valore che devi gestire dal punto di vista del codice dell’applicazione per scaricare e visualizzare l’immagine.

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

## Passaggio 4: testare l’invio del push {#test-send-push}

Ora puoi testare la creazione dell’applicazione e la consegna creata nel passaggio 2 di cui sopra. Per ulteriori informazioni sulla preparazione e l&#39;invio della notifica push, consulta questa [pagina](../../channels/using/preparing-and-sending-a-push-notification.md).

![](assets/push_notif_advanced_34.png)
