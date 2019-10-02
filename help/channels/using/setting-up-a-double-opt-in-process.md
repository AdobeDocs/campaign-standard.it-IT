---
title: Impostazione di un doppio processo di consenso
seo-title: Impostazione di un doppio processo di consenso
description: Impostazione di un doppio processo di consenso
seo-description: Segui questi passaggi per impostare un processo di doppio consenso utilizzando le pagine di destinazione in Adobe Campaign.
page-status-flag: mai attivato
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: landing page
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e89bd70459c92ba9706bbec5c488cbb340b14651

---


# Impostazione di un doppio processo di consenso{#setting-up-a-double-opt-in-process}

## Informazioni sul doppio consenso {#about-double-opt-in}

Il doppio meccanismo di consenso è una procedura consigliata per l'invio di e-mail. Protegge la piattaforma da indirizzi e-mail errati o non validi, spambots e impedisce possibili reclami di spam.

Il principio consiste nell'inviare un'e-mail per confermare l'accordo del visitatore prima di memorizzarlo come "profili" nel database Campaign: il visitatore compila una pagina di destinazione online, quindi riceve un messaggio e-mail e deve fare clic sul collegamento di conferma per finalizzare l’iscrizione.

![](assets/optin_mechanism.png)

Per configurare questa impostazione, è necessario:

1. Create e pubblicate una pagina di destinazione in modo che i visitatori possano registrarsi e iscriversi. Questa pagina di destinazione sarà disponibile da un sito Web. I visitatori che compilano e inviano la pagina di destinazione saranno memorizzati nel database ma "inseriti in blacklist", per non ricevere alcuna comunicazione prima della convalida finale (vedi [Gestione della blacklist in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).
1. Crea e invia automaticamente l’e-mail di consenso, con un collegamento di conferma. Questo messaggio e-mail verrà indirizzato alla popolazione che ha inviato la pagina di destinazione. Sarà basato su un modello e-mail che consente di eseguire il targeting dei profili di rinuncia.
1. Reindirizza a una pagina di destinazione di conferma. Questa pagina di destinazione finale proporrà un pulsante di conferma: i visitatori devono fare clic su di esso. Potete progettare un messaggio e-mail di benvenuto da inviare al termine della conferma e, ad esempio, aggiungere un’offerta speciale nell’e-mail per i nuovi destinatari.

Questi passaggi devono essere configurati in Adobe Campaign in un ordine specifico affinché tutti i parametri siano attivati correttamente.

## Step 1: Create the confirmation landing page {#step-1--create-the-confirmation-landing-page}

The process to setup double opt-in mechanism starts with the creation of the confirmation landing page: this page will be displayed when the visitors clicked on the confirmation email in order to register.

To create and configure this landing page, you need to:

1. Design a [new landing page](../../channels/using/about-landing-pages.md) based on the **[!UICONTROL Profile acquisition (acquisition)]** template. Enter the label 'CONFIRMATION'.****

   If you need to use services, you can also use the  template.[](../../audiences/using/about-subscriptions.md)**[!UICONTROL Subscription (sub)]**

1. Edit the landing page properties and under the  section, unselect the option , select  (this one is not mandatory).**[!UICONTROL Access and loading]****[!UICONTROL Authorize unidentified visitors]****[!UICONTROL Preload visitor data]**

   ![](assets/optin_confirmlp_param.png)

1. In the  &gt;  section, click  and enter the following context path:**[!UICONTROL Job]****[!UICONTROL Additional data]****[!UICONTROL Add an element]**

   /context/profile/blackList

   Set the value to false and click .******[!UICONTROL Add]**

   ![](assets/optin_confirmlp_newelement.png)

   This context removes the blacklist field, in order to be able to send emails. We will see later that the first landing page was setting this field to true before confirmation, to prevent from sending emails to non-confirmed profiles. **** For more on this, see Step 3: Create the acquisition landing page.[](../../channels/using/setting-up-a-double-opt-in-process.md#step-3--create-the-acquisition-landing-page)

1. Personalizzare il contenuto della pagina di destinazione: potete visualizzare dati personalizzati e cambiare l'etichetta del pulsante di conferma in "Fare clic qui per confermare l'iscrizione", ad esempio.

   ![](assets/optin_confirmlp_design.png)

1. Adapt the content of the confirmation page to inform your subscribers that they are now registered.

   ![](assets/optin_confimlp_page2.png)

1. [Test and publish](../../channels/using/sharing-a-landing-page.md) the landing page.

## Passaggio 2: Creare il messaggio e-mail di conferma {#step-2--create-the-confirmation-email}

Una volta creata la pagina di destinazione di conferma, potete progettare il messaggio e-mail di conferma: questo messaggio e-mail verrà inviato automaticamente a ogni visitatore che convalida la pagina di destinazione dell’acquisizione. Questa convalida è considerata un evento e l'e-mail è un messaggio transazionale, collegato a una regola di tipologia specifica che consente di eseguire il targeting delle popolazioni di rinuncia.

I passaggi per creare questi elementi sono descritti di seguito. Devi seguirli prima di creare la pagina di destinazione dell’acquisizione stessa, in quanto a questo modello e-mail verrà fatto riferimento in essa.

### Creazione dell’evento {#create-the-event}

Il messaggio e-mail di conferma è un messaggio [](../../channels/using/about-transactional-messaging.md) transazionale che risponde a un evento: la convalida del modulo. È innanzitutto necessario creare l'evento e quindi creare il modello del messaggio di transazione.

1. Create un evento dal **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]** menu, accessibile dal logo Adobe Campaign, e immettete l'etichetta "**CONFIRM**".
1. Selezionate la dimensione di **[!UICONTROL Profile]** targeting e fate clic su **[!UICONTROL Create]**.

   ![](assets/optin_eventcreate.png)

1. Nella **[!UICONTROL Fields]** sezione fare clic su **[!UICONTROL Create element]** e aggiungere il **[!UICONTROL email]** contenuto nella struttura dati per abilitare la riconciliazione.
1. Nella **[!UICONTROL Enrichment]** sezione, fate clic su **[!UICONTROL Create element]** e selezionate la risorsa di **[!UICONTROL Profile]** destinazione. È quindi possibile eseguire la mappatura sul **[!UICONTROL email]** campo nella **[!UICONTROL Join definition]** sezione o su qualsiasi altra chiave di riconciliazione composita, a seconda delle esigenze.

   ![](assets/optin_eventcreate_join.png)

   Per utilizzare i servizi, aggiungi la risorsa di **[!UICONTROL Service]** destinazione ed esegui il mapping sul **[!UICONTROL serviceName]** campo. Per ulteriori informazioni, vedere .

1. Selezionare **[!UICONTROL Profile]** come **[!UICONTROL Targeting enrichment]** nell'elenco a discesa.
1. Fate clic **[!UICONTROL Publish]** per pubblicare l’evento.

L'evento è pronto. Ora potete progettare il modello e-mail. Questo modello deve includere un collegamento alla pagina di destinazione **CONFERMA** creata in precedenza. Per ulteriori informazioni, vedi [Progettare il messaggio](../../channels/using/setting-up-a-double-opt-in-process.md#design-the-confirmation-message)di conferma.

### Creare la regola di tipologia {#create-the-typology-rule}

È necessario creare una regola [di](../../administration/using/about-typology-rules.md)tipologia specifica duplicando una regola predefinita. Questa regola consentirà di inviare messaggi ai profili che non hanno ancora confermato il loro accordo e che sono ancora in lista nera. Per impostazione predefinita, le regole di tipologia escludono i profili di rifiuto (ad es. in lista nera). Per creare questa regola di tipologia, procedere come segue:

1. Dal logo Adobe Campaign, seleziona **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** e fai clic su **[!UICONTROL Typologies]**.
1. Duplica la tipologia predefinita **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**.
1. Una volta confermata la duplicazione, modificare la nuova tipologia e immettere l'etichetta **TYPOLOGY_PROFILE**.
1. Remove the blacklisted address rule.****
1. Click **[!UICONTROL Save]**.

This typology can now be associated to the confirmation email.

### Design the confirmation message {#design-the-confirmation-message}

The confirmation email is a transactional message based on the event created before. Follow the steps below to create this message:

1. From the Adobe Campaign logo, select  &gt;  and click .**[!UICONTROL Marketing plans]****[!UICONTROL Transactional messages]****[!UICONTROL Transactional messages]**
1. Modificate il modello e-mail **CONFERMA** e personalizzatelo. You can upload an existing content or use an out-of-box template.
1. Add a link to the CONFIRMATION landing page, and click  to save modifications.******[!UICONTROL Confirm]**

   ![](assets/optin_email_selectlp.png)

1. Edit the email template properties. In the  &gt;  section, select the TYPOLOGY_PROFILE typology created before.**[!UICONTROL Advanced parameters]****[!UICONTROL Preparation]******
1. Save and publish the transactional message.

## Step 3: Create the acquisition landing page {#step-3--create-the-acquisition-landing-page}

You have to create the initial acquisition landing page: this opt-in form will be published on your website.

To create and configure this landing page, you need to:

1. Progettate una [nuova pagina](../../channels/using/about-landing-pages.md) di destinazione basata sul **[!UICONTROL Profile acquisition (acquisition)]** modello. Enter the label 'ACQUISITION'.****
1. Modificate le proprietà della pagina di destinazione: nella sezione **[!UICONTROL Job]** &gt; **[!UICONTROL Additional data]** , fate clic su **[!UICONTROL Add an element]** e immettete il percorso contestuale seguente:

   /context/profile/blackList

   e impostare il valore su **true**.

   Questo è obbligatorio per forzare la blacklist ed evitare di inviare messaggi ai visitatori che non hanno confermato il loro accordo. La convalida della pagina di destinazione CONFERMA imposta questo campo su **false** dopo la conferma. Per ulteriori informazioni, vedere [Passaggio 1: Creare la pagina](../../channels/using/setting-up-a-double-opt-in-process.md#step-1--create-the-confirmation-landing-page)di destinazione di conferma.

1. Nella sezione **[!UICONTROL Job]** &gt; **[!UICONTROL Specific actions]** , selezionare l'opzione **[!UICONTROL Start sending messages]**.
1. Nell'elenco a discesa associato, scegliete il modello di messaggio **CONFERMA** transazionale creato.

   ![](assets/optin_acquisition_startoption.png)

1. Personalizza il contenuto della pagina di destinazione, in base al marchio e ai dati da acquisire. Potete visualizzare dati personalizzati e cambiare l'etichetta del pulsante di conferma per **confermare ad esempio l'iscrizione** .

   ![](assets/optin_acquisition_page1.png)

1. Personalizzate la pagina di conferma per informare il nuovo utente che deve convalidare l’iscrizione.

   ![](assets/optin_acquisition_page2.png)

1. [Test e pubblicazione](../../channels/using/sharing-a-landing-page.md) della pagina di destinazione.

È ora configurato il meccanismo di doppio consenso. È possibile eseguire e verificare la procedura da fine a fine, a partire dall'URL pubblico di questa pagina di **[!UICONTROL ACQUISITION]** destinazione. Questo URL viene visualizzato nel dashboard della pagina di destinazione.
