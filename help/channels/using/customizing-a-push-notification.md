---
title: Personalizzazione di una notifica push
seo-title: Personalizzazione di una notifica push
description: Personalizzazione di una notifica push
seo-description: Scopri come personalizzare le notifiche push con varie opzioni avanzate.
page-status-flag: never-activated
uuid: 8 cf 74 cad-b 1 ba -4 aad -83 bd -7289 cb 22 d 5 f 4
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: notifiche push
discoiquuid: dc 944 c 85-2059-46 df-b 396-676 fe 3617 dd 1
context-tags: delivery, mobileappcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Customizing a push notification{#customizing-a-push-notification}

Per perfezionare la notifica push, Adobe Campaign consente di accedere a un set di opzioni avanzate durante la progettazione di una notifica push.

As an expert user, to configure mobile applications in Adobe Campaign, refer to the following technote [Understanding Campaign Standard Push Notifications Payload Structure](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html).

![](assets/push_notif_advanced.png)

**Contenuto correlato:**

* [Rapporto notifiche push](../../reporting/using/push-notification-report.md)
* [Invio di una notifica push all'interno di un flusso di lavoro](../../automating/using/push-notification-delivery.md)

## Play a sound {#play-a-sound}

The function **[!UICONTROL Play a sound]** gives the application the ability to play sounds on your device with the delivery of a push notification, when the app isn't running.

Un suono avverte gli utenti di una notifica push, conferendogli maggiore visibilità. Per includere un suono nell'app mobile:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. In the **[!UICONTROL Play a sound]** field, enter the filename of the sound file, without the extension, to be played by the mobile device when the notification is received.

   For more information on supported media formats, refer to [Apple](https://support.apple.com/kb/PH16864?locale=en_US) and [Android](https://developer.android.com/guide/topics/media/media-formats.html) documentations.

   ![](assets/push_notif_advanced_7.png)

1. Il file audio viene riprodotto durante la distribuzione della notifica se il file è definito nel pacchetto dell'applicazione mobile. In caso contrario, viene riprodotto il suono predefinito del dispositivo.

L'utente riceverà quindi la notifica push e il suono solo se il cellulare non è disattivato.

## Refresh the badge value {#refresh-the-badge-value}

Un contrassegno viene usato per visualizzare direttamente sull'icona dell'applicazione il numero di nuove informazioni non letto. Il valore contrassegno scompare non appena l'utente apre o legge il nuovo contenuto dall'applicazione.

Quando una notifica viene ricevuta su un dispositivo, può aggiornare o aggiungere un valore distintivo per l'app correlata. Per inviare un valore contrassegno dal lato Server:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. Il valore contrassegno deve essere un numero intero e può essere aggiornato in modi diversi:

   * To refresh the badge, enter 0 in the **[!UICONTROL Value of the badge]** field. Questo rimuove il contrassegno dall'icona dell'applicazione.
   * To add a badge value, enter any number in the **[!UICONTROL Value of the badge]** field. Questo numero verrà visualizzato automaticamente nel contrassegno non appena l'utente riceve la notifica push.
   * Se il campo è vuoto o non contiene un numero intero, il valore del simbolo non cambia.
   Here, we entered 1 in the **[!UICONTROL Value of the badge]** field to let the users know that they have a new information in their application.

   ![](assets/push_notif_advanced_8.png)

1. Dopo aver inviato il messaggio, gli utenti riceveranno la notifica push e la relativa applicazione visualizza automaticamente il nuovo valore.

   ![](assets/push_notif_advanced_1.png)

## Add a deeplink {#add-a-deeplink}

Un collegamento facilitato consente di portare gli utenti direttamente al contenuto contenuto all'interno dell'applicazione (invece di aprire una pagina del browser Web).

Un collegamento profondo può includere dati personalizzati per un'esperienza in-app personalizzata. Ad esempio, i primi nomi dei destinatari vengono compilati automaticamente nella pagina a cui l'applicazione li invia.

Per aggiungere un collegamento profondo in una notifica push:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. Enter the link in the **[!UICONTROL Add a deeplink]** field.

   ![](assets/push_notif_advanced_3.png)

1. Dopo aver inviato il messaggio, gli utenti riceveranno la notifica push e accedono alla pagina specifica nell'app interagendo con la notifica, ad es. toccando o facendo clic sul pulsante di invito all'azione.

   ![](assets/push_notif_advanced_4.png)

## Define an action {#define-an-action}

Puoi aggiungere un ID categoria, se disponibile nell'applicazione mobile, e visualizzare i pulsanti di azione. Queste notifiche forniscono all'utente un modo più rapido per eseguire attività diverse in risposta a una notifica senza aprire o navigare nell'applicazione.

La finestra di dialogo visualizzata sul telefono dell'utente richiede la decisione di procedere. Quando l'utente seleziona una delle azioni, il sistema notifica l'applicazione in modo che possa eseguire le attività associate.

Per aggiungere una categoria in una notifica push:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. Enter a predefined category name in the **[!UICONTROL Category]** field to display actionable buttons when the push notification is received.

   Lo sviluppatore di applicazioni mobili deve definire l'ID categoria e il comportamento previsto per i pulsanti nell'applicazione. For more on this, refer to the [Apple Developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html) (**Configuring Categories and Actionable Notifications** section) or the [Android Developer documentation](https://developer.android.com/guide/topics/ui/notifiers/notifications.html).

   ![](assets/push_notif_advanced_9.png)

1. Dopo aver inviato la notifica push, gli utenti la ricevono e devono intervenire con i pulsanti fruibili in precedenza.

   ![](assets/push_notif_actionable_buttons.png)

A seconda dell'azione dell'utente, l'applicazione riceve una notifica in modo che possa eseguire qualsiasi attività associata.

## Add custom fields {#add-custom-fields}

I campi personalizzati consentono di trasmettere dati personalizzati nel payload sotto forma di coppia di valori chiave. Questa opzione può essere utilizzata per trasmettere dati aggiuntivi all'applicazione oltre le chiavi predefinite.

A tal fine:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. In the **[!UICONTROL Custom fields]** category, click the **[!UICONTROL Add an element]** button.
1. Enter your **[!UICONTROL Keys]** then the **[!UICONTROL Values]** associated with each key.

   ![](assets/push_notif_advanced_10.png)

1. La gestione e lo scopo dei campi personalizzati dipende interamente dall'app mobile. Nella notifica push sotto, i campi personalizzati sono stati utilizzati dall'app per visualizzare etichette di pulsanti per la notifica push.

   ![](assets/push_notif_actionable_buttons.png)

## Add rich media content {#add-rich-media-content}

Il contenuto multimediale avanzato consente di ottenere un livello di coinvolgimento utenti migliore, il che significa che l'utente sarà più propensi ad aprire la notifica push.

Potete includere un file immagine, gif, audio o video che verrà riprodotto o visualizzato nella notifica stessa. Gli utenti dell'app non dovranno aprire l'applicazione per visualizzarla.

Per includere contenuti multimediali nella notifica push:

1. Open the push notification and access the **[!UICONTROL Advanced options]** section.
1. Enter the URL of your file in the **[!UICONTROL Rich media content URL]** field for each format: iOS and Android.

   Per iOS 10 o versione successiva, potete inserire file immagine, gif, audio e video. Per le versioni precedenti di iOS, la notifica push verrà visualizzata senza contenuto dettagliato. For detailed steps on how to display an image from an Adobe Campaign push notification on an iOS device, refer to this [page](https://helpx.adobe.com/campaign/kb/display-image-push.html).

   Per Android, potete includere solo immagini.

   ![](assets/push_notif_advanced_6.png)

1. Dopo aver inviato il messaggio, l'utente riceve la notifica push e potrà visualizzare il contenuto multimediale.

   ![](assets/push_notif_advanced_2.png)

## Change the notification behavior for iOS {#change-the-notification-behavior-for-ios}

![](assets/push_notif_advanced_5.png)

For iOS 10 or higher, two additional options are available in the **[!UICONTROL Advanced options]** section of push notifications: **[!UICONTROL Mutable content]** and **[!UICONTROL Content available]**.

When the **[!UICONTROL Mutable content]** option is checked and/or a Rich media content URL is added, the mutable-content flag will be sent in the push payload and will allow the push notification content to be modified by a notification service application extension provided in iOS SDK. For more on this, refer to [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html).

Puoi quindi sfruttare le estensioni delle app mobili per modificare ulteriormente il contenuto o la presentazione delle notifiche push in arrivo inviate da Adobe Campaign. Ad esempio, gli utenti possono sfruttare questa opzione per:

* Decrittografare i dati inviati in formato crittografato
* Scaricare immagini o altri file multimediali e aggiungerli come allegati a una notifica
* Modificare il corpo o il testo del titolo di una notifica
* Aggiungere un identificatore di thread a una notifica

When **[!UICONTROL Content available]** is checked, the content available flag will be sent in the push payload to ensure that the app is woken up as soon as it receives the push notification, meaning that the app will be able to access the payload data. Questo funziona anche se l'app è in esecuzione in background e senza necessità di interazione con l'utente (ad es. se si tocca la notifica push), ma questo non si applica se l'app non è in esecuzione. For more on this, refer to the [Apple developer documentation](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html).

## Change the notification behavior for Android {#change-the-notification-behavior-for-android}

For Android, you can enter the URL of your file in the **Rich media content URL** field. Mentre con la versione iOS, per Android potete includere solo immagini e non file audio, video o video.

The **[!UICONTROL High priority]** checkbox allows you to set up a high or normal priority for your push notifications. For more information on message priority, refer to the [Google developer documentation](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message).

![](assets/push_notif_advanced_11.png)

