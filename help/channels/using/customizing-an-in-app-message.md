---
title: Personalizzazione di un messaggio in-app
seo-title: Personalizzazione di un messaggio in-app
description: Personalizzazione di un messaggio in-app
seo-description: Scopri come personalizzare i messaggi in-app con varie opzioni.
page-status-flag: never-activated
uuid: 1 d 9 c 08 ed -4 de 5-440 d-bf 51-4 a 437 eec 67 d 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: messaggistica in-app
discoiquuid: c 9 c 3 e 033-e 319-447 b -8 d 87-ff 7 dd 4941876
context-tags: delivery, inappcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Customizing an In-App message{#customizing-an-in-app-message}

Per perfezionare il messaggio in-app, Adobe Campaign consente di accedere a un set di opzioni avanzate durante la progettazione di un'in-app.

L'Editor contenuti in-app consente di scegliere tra due modalità Messaggi in-app:

* [Modello messaggio](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-message-template): Questo modello consente di personalizzare completamente l'interno dell'app con immagini, video e pulsanti di azione.
* [Messaggio personalizzato](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-custom-html-message): Questo modello consente di importare HTML personalizzato.

![](assets/inapp_customize_1.png)

**Argomenti correlati:**

* [Invio del messaggio in-app](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [Generazione rapporti in-app](../../reporting/using/in-app-report.md)

## Customizing with a message template {#customizing-with-a-message-template}

### Layout {#layout}

The **[!UICONTROL Layout]** drop-down provides you with four different options to choose from depending on your messaging needs:

* **[!UICONTROL Full page]**: Questo tipo di layout copre l'intero schermo dei dispositivi di audience.

   Supporta supporti (immagini, video), testo e componenti pulsante.

* **[!UICONTROL Large modal]**: Questo layout viene visualizzato in una finestra di avviso di grandi dimensioni, che rimane visibile in background.

   Supporta supporti (immagini, video), testo e componenti pulsante.

* **[!UICONTROL Small modal]**: Questo layout viene visualizzato come una piccola finestra di tipo avviso, l'applicazione è ancora visibile in background.

   Supporta supporti (immagini, video), testo e componenti pulsante.

* **[!UICONTROL Alert]**: Questo tipo di layout viene visualizzato come messaggio di avviso nativo del sistema operativo.

   Può supportare solo i componenti di testo e pulsante.

* **[!UICONTROL Local notification]**: Questo tipo di layout viene visualizzato come messaggio banner.

   Può supportare solo audio, testo e destinazione. For more on local notification, refer to [Customizing a local notification message type](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

Ogni tipo di layout può essere visualizzato in anteprima su dispositivi diversi come telefono, tablet, piattaforma, ad es. Android o iOS e orientamento, ad esempio orizzontale o verticale nella finestra a destra dell'Editor di contenuto.

![](assets/inapp_customize_4.png)

### Media {#media}

The **[!UICONTROL Media]** drop-down allows you to add media to your In-App message to create a compelling experience for end user.

1. Select your **[!UICONTROL Media Type]** between image and video.
1. For the **[!UICONTROL Image]** media type, enter your URL in the **[!UICONTROL Media URL]** field based on the supported formats.

   If needed, you can also enter the path to a **[!UICONTROL Bundled image]** which can be used if the device is offline.

   ![](assets/inapp_customize_5.png)

1. For the **[!UICONTROL Video]** media type, enter your URL in the **[!UICONTROL Media URL]** field.

   Then, enter your **[!UICONTROL Video poster]** to be used while the video is downloading on the audience devices or until users tap the play button.

   ![](assets/inapp_customize_6.png)

### Text {#text}

Se necessario, potete anche aggiungere il titolo e il contenuto di un messaggio al messaggio In-app. Per personalizzare meglio il messaggio in-app, puoi aggiungere al contenuto campi di personalizzazione diversi, blocchi di contenuto e testo dinamico.

1. In the **[!UICONTROL Text]** drop-down, add a title in the **[!UICONTROL Message title]** field.

   ![](assets/inapp_customize_9.png)

1. Add your content in the **[!UICONTROL Message content]** field.
1. To further personalize your text, click the ![](assets/edit_darkgrey-24px.png) icon to add personalization fields.

   ![](assets/inapp_customize_8.png)

1. Digita il contenuto del messaggio e aggiungi i campi personalizzati, se necessario.

   For more information on personalization field, refer to this [section](../../designing/using/inserting-a-personalization-field.md).

   ![](assets/inapp_customize_10.png)

1. Controllate il contenuto del messaggio nella finestra di anteprima.

   ![](assets/inapp_customize_11.png)

### Buttons {#buttons}

Potete aggiungere fino a due pulsanti al messaggio in-app.

1. In the **[!UICONTROL Buttons]** drop-down, enter the text of your first button in the **[!UICONTROL Primary]** category.

   ![](assets/inapp_customize_12.png)

1. Choose which of the two actions **[!UICONTROL Dismiss]** and **[!UICONTROL Redirect]** will be assigned to your primary button.
1. In the **[!UICONTROL Secondary]** category, add a second button to your In-App if needed by entering your text.
1. Selezionate l'azione associata al secondo pulsante.
1. If you chose the **[!UICONTROL Redirect]** action, enter your web URL or deeplink in the **[!UICONTROL Destination URL]** field.

   ![](assets/inapp_customize_13.png)

1. Enter your web URL or deeplink in the **[!UICONTROL Destination URL]** field, if you chose the **[!UICONTROL Redirect]** action,
1. Controllate il contenuto del messaggio nella finestra di anteprima o fate clic sul pulsante Anteprima.

   Refer to the [Previewing the In-App message](../../channels/using/customizing-an-in-app-message.md#previewing-the-in-app-message) page.

   ![](assets/inapp_customize_11.png)

### Settings {#settings}

1. In the **[!UICONTROL Settings]** category, select your background color between light and dark.
1. Choose to display or not a close button with the **[!UICONTROL Show close button]** option to provide users a way to dismiss the In-App message.
1. Select if your button alignment will be horizontal or vertical with the **[!UICONTROL Button alignment]** option.
1. Scegli se il messaggio in-app può essere chiuso automaticamente o meno dopo alcuni secondi.

   ![](assets/inapp_customize_7.png)

## Customizing a local notification message type {#customizing-a-local-notification-message-type}

Le notifiche locali possono essere attivate solo da un'app in un determinato momento e a seconda di un evento. Avviseranno gli utenti che sta accadendo qualcosa nella loro app, anche senza accedere a Internet.

Per personalizzare una notifica locale:

1. From your **[!UICONTROL Content]** page, select **[!UICONTROL Local notification]** in the **[!UICONTROL Layout]** category

   ![](assets/inapp_customize_17.png)

1. Under the **[!UICONTROL Text]** category, type down your **[!UICONTROL Message title]** and **[!UICONTROL Message content]**.

   ![](assets/inapp_customize_18.png)

1. Under the **[!UICONTROL Advanced option]** category, in the **[!UICONTROL Wait to display]** field, choose how long in seconds your local notification will be displayed on screen once your event is triggered.
1. In the **[!UICONTROL Sound]** field, enter the filename of the sound file, without the extension, to be played by the mobile device when the local notification is received.

   Il file audio viene riprodotto durante la distribuzione della notifica se il file è definito nel pacchetto dell'applicazione mobile. In caso contrario, viene riprodotto il suono predefinito del dispositivo.

   ![](assets/inapp_customize_19.png)

1. Specify a destination to redirect your users when they interact with your local notification in the **[!UICONTROL Deeplink URL]** field.
1. Per trasmettere dati personalizzati nel payload sotto forma di coppia di valori chiave, è possibile aggiungere campi personalizzati alla notifica locale. In the **[!UICONTROL Custom fields]** category, click the **[!UICONTROL Create an element]** button.
1. Enter your **[!UICONTROL Keys]** then the **[!UICONTROL Values]** associated with each key.

   Tieni presente che la gestione e lo scopo dei campi personalizzati è completamente all'interno dell'app mobile.

1. In the **[!UICONTROL Apple options]** category, fill in the **[!UICONTROL Category]** fields to add a category ID for custom actions if available in your Apple mobile application.

## Customizing with a custom HTML message {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>Il messaggio HTML personalizzato non supporta la personalizzazione dei contenuti.

The **[!UICONTROL Custom message]** mode allows you to directly import one of your pre-configured HTML message.

Per farlo, devi semplicemente trascinare o selezionare il file dal computer.

Your file must have a specific layout which can be found by clicking the **Download the sample file** option.

![](assets/inapp_customize_16.png)

Puoi anche trovare un elenco di requisiti HTML personalizzati per l'importazione corretta in Adobe Campaign.

![](assets/inapp_customize_3.png)

Una volta importato il codice HTML, potete trovare un'anteprima del file su dispositivi diversi nella finestra di anteprima.

## Previewing the In-App message {#previewing-the-in-app-message}

Prima di inviare il messaggio in-app, potete eseguire il test con i profili di prova per verificare cosa vedranno i destinatari di destinazione quando riceveranno la distribuzione.

1. Click the **[!UICONTROL Preview]** button.

   ![](assets/inapp_sending_2.png)

1. Click the **[!UICONTROL Select a test profile]** button and select one of your test profiles to start previewing your delivery. For more information on test profiles, refer to this [section](../../sending/using/managing-test-profiles-and-sending-proofs.md).
1. Controllate il messaggio su dispositivi diversi come Android, iphone telefoni o anche tablet. È inoltre possibile verificare se i campi di personalizzazione recuperano i dati corretti.

   ![](assets/inapp_sending_3.png)

1. Ora puoi inviare il messaggio e misurarne l'impatto con i rapporti sulla distribuzione. For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).

