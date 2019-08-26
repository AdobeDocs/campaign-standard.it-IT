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
source-git-commit: 43183a3adc35da3dac807a888f1b694fbb9a623c

---


# Personalizzazione di un messaggio in-app{#customizing-an-in-app-message}

Per perfezionare il messaggio in-app, Adobe Campaign consente di accedere a un set di opzioni avanzate durante la progettazione di un'in-app.

L'Editor contenuti in-app consente di scegliere tra due modalità Messaggi in-app:

* [Modello messaggio](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-message-template): Questo modello consente di personalizzare completamente l'interno dell'app con immagini, video e pulsanti di azione.
* [Messaggio personalizzato](../../channels/using/customizing-an-in-app-message.md#customizing-with-a-custom-html-message): Questo modello consente di importare HTML personalizzato.

![](assets/inapp_customize_1.png)

**Argomenti correlati:**

* [Invio del messaggio in-app](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [Generazione rapporti in-app](../../reporting/using/in-app-report.md)

## Personalizzazione con un modello di messaggio {#customizing-with-a-message-template}

### Layout {#layout}

Il **[!UICONTROL Layout]** menu a discesa offre quattro opzioni diverse per scegliere tra le diverse esigenze di messaggi:

* **[!UICONTROL Full page]**: Questo tipo di layout copre l'intero schermo dei dispositivi di audience.

   Supporta supporti (immagini, video), testo e componenti pulsante.

* **[!UICONTROL Large modal]**: Questo layout viene visualizzato in una finestra di avviso di grandi dimensioni, che rimane visibile in background.

   Supporta supporti (immagini, video), testo e componenti pulsante.

* **[!UICONTROL Small modal]**: Questo layout viene visualizzato come una piccola finestra di tipo avviso, l'applicazione è ancora visibile in background.

   Supporta supporti (immagini, video), testo e componenti pulsante.

* **[!UICONTROL Alert]**: Questo tipo di layout viene visualizzato come messaggio di avviso nativo del sistema operativo.

   Può supportare solo i componenti di testo e pulsante.

* **[!UICONTROL Local notification]**: Questo tipo di layout viene visualizzato come messaggio banner.

   Può supportare solo audio, testo e destinazione. Per ulteriori informazioni sulla notifica locale, consultate [Personalizzazione di un tipo di messaggio di notifica locale](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type).

Ogni tipo di layout può essere visualizzato in anteprima su dispositivi diversi come telefono, tablet, piattaforma, ad es. Android o iOS e orientamento, ad esempio orizzontale o verticale nella finestra a destra dell'Editor di contenuto.

![](assets/inapp_customize_4.png)

### Media {#media}

Il **[!UICONTROL Media]** menu a discesa consente di aggiungere file multimediali al messaggio in-app per creare un'esperienza coinvolgente per l'utente finale.

1. Seleziona tra **[!UICONTROL Media Type]** immagini e video.
1. Per il tipo **[!UICONTROL Image]** di supporto, immettete l'URL nel **[!UICONTROL Media URL]** campo basato sui formati supportati.

   Se necessario, potete anche immettere il percorso di un **[!UICONTROL Bundled image]** oggetto che può essere usato se il dispositivo è offline.

   ![](assets/inapp_customize_5.png)

1. Per il tipo **[!UICONTROL Video]** di supporto, immettete l'URL nel **[!UICONTROL Media URL]** campo.

   Quindi, immettete il testo **[!UICONTROL Video poster]** da usare mentre il video viene scaricato sui dispositivi di destinazione o finché gli utenti non toccano il pulsante di riproduzione.

   ![](assets/inapp_customize_6.png)

### Testo {#text}

Se necessario, potete anche aggiungere il titolo e il contenuto di un messaggio al messaggio In-app. Per personalizzare meglio il messaggio in-app, puoi aggiungere al contenuto campi di personalizzazione diversi, blocchi di contenuto e testo dinamico.

1. Nel **[!UICONTROL Text]** menu a discesa, aggiungete un titolo nel **[!UICONTROL Message title]** campo.

   ![](assets/inapp_customize_9.png)

1. Aggiungete il contenuto nel **[!UICONTROL Message content]** campo.
1. Per personalizzare ulteriormente il testo, fai clic sull' ![](assets/edit_darkgrey-24px.png) icona per aggiungere campi personalizzati.

   ![](assets/inapp_customize_8.png)

1. Digita il contenuto del messaggio e aggiungi i campi personalizzati, se necessario.

   Per ulteriori informazioni sul campo di personalizzazione, consulta questa [sezione](../../designing/using/inserting-a-personalization-field.md).

   ![](assets/inapp_customize_10.png)

1. Controllate il contenuto del messaggio nella finestra di anteprima.

   ![](assets/inapp_customize_11.png)

### Pulsanti {#buttons}

Potete aggiungere fino a due pulsanti al messaggio in-app.

1. Nel **[!UICONTROL Buttons]** menu a discesa, inserite il testo del primo pulsante nella **[!UICONTROL Primary]** categoria.

   ![](assets/inapp_customize_12.png)

1. Scegliete quale delle due azioni **[!UICONTROL Dismiss]** assegnare **[!UICONTROL Redirect]** al pulsante principale.
1. Nella **[!UICONTROL Secondary]** categoria, aggiungi un secondo pulsante all'interno dell'app, se necessario immettendo il testo.
1. Selezionate l'azione associata al secondo pulsante.
1. Se si sceglie l **[!UICONTROL Redirect]** 'azione, inserire l'URL Web o il collegamento profondo nel **[!UICONTROL Destination URL]** campo.

   ![](assets/inapp_customize_13.png)

1. Se scegliete l'azione, inserite l'URL Web o il collegamento profondo nel **[!UICONTROL Destination URL]****[!UICONTROL Redirect]** campo,
1. Controllate il contenuto del messaggio nella finestra di anteprima o fate clic sul pulsante Anteprima.

   Consultate [Anteprima della pagina dei messaggi](../../channels/using/customizing-an-in-app-message.md#previewing-the-in-app-message) in-app.

   ![](assets/inapp_customize_11.png)

### Impostazioni {#settings}

1. Nella **[!UICONTROL Settings]** categoria, seleziona il colore di sfondo tra chiaro e scuro.
1. Scegliete di visualizzare o meno un pulsante di chiusura con **[!UICONTROL Show close button]** l'opzione per chiudere il messaggio in-app.
1. Selezionare se l'allineamento del pulsante sarà orizzontale o verticale con l' **[!UICONTROL Button alignment]** opzione.
1. Scegli se il messaggio in-app può essere chiuso automaticamente o meno dopo alcuni secondi.

   ![](assets/inapp_customize_7.png)

## Personalizzazione di un tipo di messaggio di notifica locale {#customizing-a-local-notification-message-type}

Le notifiche locali possono essere attivate solo da un'app in un determinato momento e a seconda di un evento. Avviseranno gli utenti che sta accadendo qualcosa nella loro app, anche senza accedere a Internet.

Per personalizzare una notifica locale:

1. Dalla **[!UICONTROL Content]** pagina, selezionate **[!UICONTROL Local notification]** nella **[!UICONTROL Layout]** categoria

   ![](assets/inapp_customize_17.png)

1. Nella **[!UICONTROL Text]** categoria, digita il tuo **[!UICONTROL Message title]** e **[!UICONTROL Message content]**.

   ![](assets/inapp_customize_18.png)

1. Nella **[!UICONTROL Advanced option]** categoria, nel **[!UICONTROL Wait to display]** campo, scegliete quanto tempo in secondi la notifica locale verrà visualizzata sullo schermo una volta che l'evento viene attivato.
1. Nel **[!UICONTROL Sound]** campo, immettete il nome file del file audio, con l'estensione, che deve essere riprodotto dal dispositivo mobile quando viene ricevuta la notifica locale.

   Il file audio viene riprodotto durante la distribuzione della notifica se il file è definito nel pacchetto dell'applicazione mobile. In caso contrario, viene riprodotto il suono predefinito del dispositivo.

   ![](assets/inapp_customize_19.png)

1. Specificate una destinazione per reindirizzare gli utenti quando interagiscono con la notifica locale nel **[!UICONTROL Deeplink URL]** campo.
1. Per trasmettere dati personalizzati nel payload sotto forma di coppia di valori chiave, è possibile aggiungere campi personalizzati alla notifica locale. Nella **[!UICONTROL Custom fields]** categoria, fate clic sul **[!UICONTROL Create an element]** pulsante.
1. Inserite il testo **[!UICONTROL Keys]****[!UICONTROL Values]** associato a ogni chiave.

   Tieni presente che la gestione e lo scopo dei campi personalizzati è completamente all'interno dell'app mobile.

1. Nella **[!UICONTROL Apple options]** categoria, compila i **[!UICONTROL Category]** campi per aggiungere un ID categoria per azioni personalizzate, se disponibili nell'applicazione mobile Apple.

## Personalizzazione con un messaggio HTML personalizzato {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>Il messaggio HTML personalizzato non supporta la personalizzazione dei contenuti.

La **[!UICONTROL Custom message]** modalità consente di importare direttamente uno dei messaggi HTML preconfigurati.

Per farlo, devi semplicemente trascinare o selezionare il file dal computer.

Il file deve avere un layout specifico che si trova facendo clic sull'opzione **Scarica file** di esempio.

![](assets/inapp_customize_16.png)

Puoi anche trovare un elenco di requisiti HTML personalizzati per l'importazione corretta in Adobe Campaign.

![](assets/inapp_customize_3.png)

Una volta importato il codice HTML, potete trovare un'anteprima del file su dispositivi diversi nella finestra di anteprima.

## Anteprima del messaggio in-app {#previewing-the-in-app-message}

Prima di inviare il messaggio in-app, potete eseguire il test con i profili di prova per verificare cosa vedranno i destinatari di destinazione quando riceveranno la distribuzione.

1. Fate clic sul **[!UICONTROL Preview]** pulsante.

   ![](assets/inapp_sending_2.png)

1. Fai clic sul **[!UICONTROL Select a test profile]** pulsante e seleziona uno dei profili di prova per avviare l'anteprima della distribuzione. Per ulteriori informazioni sui profili di prova, consulta questa [sezione](../../sending/using/managing-test-profiles-and-sending-proofs.md).
1. Controllate il messaggio su dispositivi diversi come Android, iphone telefoni o anche tablet. È inoltre possibile verificare se i campi di personalizzazione recuperano i dati corretti.

   ![](assets/inapp_sending_3.png)

1. Ora puoi inviare il messaggio e misurarne l'impatto con i rapporti sulla distribuzione. For more on reporting, refer to [this section](../../reporting/using/in-app-report.md).

