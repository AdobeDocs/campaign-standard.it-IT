---
title: Impostazione di un doppio processo di consenso
description: Segui questi passaggi per impostare un processo di doppio consenso utilizzando le pagine di destinazione in Adobe Campaign.
page-status-flag: never-activated
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# Impostazione di un doppio processo di consenso{#setting-up-a-double-opt-in-process}

## Informazioni sul doppio consenso {#about-double-opt-in}

Il doppio meccanismo di consenso è una procedura consigliata per l&#39;invio di e-mail. Protegge la piattaforma da indirizzi e-mail errati o non validi, spambots e impedisce possibili reclami di spam.

Il principio consiste nell&#39;inviare un&#39;e-mail per confermare l&#39;accordo del visitatore prima di memorizzarlo come &quot;profili&quot; nel database Campaign: il visitatore compila una pagina di destinazione online, quindi riceve un messaggio e-mail e deve fare clic sul collegamento di conferma per finalizzare l’iscrizione.

![](assets/optin_mechanism.png)

Per configurare questa impostazione, è necessario:

1. Create e pubblicate una pagina di destinazione in modo che i visitatori possano registrarsi e iscriversi. Questa pagina di destinazione sarà disponibile da un sito Web. I visitatori che compilano e inviano la pagina di destinazione saranno memorizzati nel database ma &quot;inseriti in blacklist&quot;, per non ricevere alcuna comunicazione prima della convalida finale (vedi [Gestione della blacklist in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).
1. Crea e invia automaticamente l’e-mail di consenso, con un collegamento di conferma. Questo messaggio e-mail verrà indirizzato alla popolazione che ha inviato la pagina di destinazione. Sarà basato su un modello e-mail che consente di eseguire il targeting dei profili di rinuncia.
1. Reindirizza a una pagina di destinazione di conferma. Questa pagina di destinazione finale proporrà un pulsante di conferma: i visitatori devono fare clic su di esso. Potete progettare un messaggio e-mail di benvenuto da inviare al termine della conferma e, ad esempio, aggiungere un’offerta speciale nell’e-mail per i nuovi destinatari.

Questi passaggi devono essere configurati in Adobe Campaign in un ordine specifico affinché tutti i parametri siano attivati correttamente.

## Passaggio 1: Creare la pagina di destinazione di conferma {#step-1--create-the-confirmation-landing-page}

Il processo di impostazione del meccanismo di doppio opt-in inizia con la creazione della pagina di destinazione di conferma: questa pagina verrà visualizzata quando i visitatori hanno fatto clic sul messaggio e-mail di conferma per registrarsi.

Per creare e configurare questa pagina di destinazione, è necessario:

1. Progettate una [nuova pagina](../../channels/using/getting-started-with-landing-pages.md) di destinazione basata sul **[!UICONTROL Profile acquisition (acquisition)]** modello. Inserire l&#39;etichetta &quot;**CONFERMA**&quot;.

   Se è necessario utilizzare [i servizi](../../audiences/using/about-subscriptions.md), è anche possibile utilizzare il **[!UICONTROL Subscription (sub)]** modello.

1. Modificate le proprietà della pagina di destinazione e, nella **[!UICONTROL Access and loading]** sezione, deselezionate l’opzione **[!UICONTROL Authorize unidentified visitors]**, selezionate **[!UICONTROL Preload visitor data]** (questa non è obbligatoria).

   ![](assets/optin_confirmlp_param.png)

1. Nella sezione **[!UICONTROL Job]** > **[!UICONTROL Additional data]** , fate clic su **[!UICONTROL Add an element]** e immettete il percorso contestuale seguente:

   /context/profile/blackList

   Impostate il valore su **false** e fate clic su **[!UICONTROL Add]**.

   ![](assets/optin_confirmlp_newelement.png)

   Questo contesto rimuove il campo della blacklist per poter inviare le e-mail. In seguito verrà visualizzato che la prima pagina di destinazione impostava questo campo su **true** prima della conferma, per impedire l’invio di e-mail a profili non confermati. Per ulteriori informazioni, consulta [il Passaggio 3: Crea la pagina](#step-3--create-the-acquisition-landing-page)di destinazione dell’acquisizione.

1. Personalizzare il contenuto della pagina di destinazione: potete visualizzare dati personalizzati e cambiare l&#39;etichetta del pulsante di conferma in &quot;Fare clic qui per confermare l&#39;iscrizione&quot;, ad esempio.

   ![](assets/optin_confirmlp_design.png)

1. Adatta il contenuto della pagina di conferma per informare gli utenti che sono ora registrati.

   ![](assets/optin_confimlp_page2.png)

1. [Test e pubblicazione](../../channels/using/testing-publishing-landing-page.md) della pagina di destinazione.

## Passaggio 2: Creare il messaggio e-mail di conferma {#step-2--create-the-confirmation-email}

Una volta creata la pagina di destinazione di conferma, potete progettare il messaggio e-mail di conferma: questo messaggio e-mail verrà inviato automaticamente a ogni visitatore che convalida la pagina di destinazione dell’acquisizione. Questa convalida è considerata un evento e l&#39;e-mail è un messaggio transazionale, collegato a una regola di tipologia specifica che consente di eseguire il targeting delle popolazioni di rifiuto.

I passaggi per creare questi elementi sono descritti di seguito. Devi seguirli prima di creare la pagina di destinazione dell’acquisizione stessa, in quanto a questo modello e-mail verrà fatto riferimento in essa.

### Creazione dell’evento {#create-the-event}

Il messaggio e-mail di conferma è un messaggio [](../../channels/using/about-transactional-messaging.md) transazionale che risponde a un evento: la convalida del modulo. È innanzitutto necessario creare l&#39;evento e quindi creare il modello del messaggio transazionale.

1. Create un evento dal **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]** menu, accessibile dal logo di Adobe Campaign, e immettete l&#39;etichetta &quot;**CONFIRM**&quot;.
1. Selezionate la dimensione di **[!UICONTROL Profile]** targeting e fate clic su **[!UICONTROL Create]**.

   ![](assets/optin_eventcreate.png)

1. Nella **[!UICONTROL Fields]** sezione fare clic su **[!UICONTROL Create element]** e aggiungere il **[!UICONTROL email]** contenuto nella struttura dati per abilitare la riconciliazione.
1. Nella **[!UICONTROL Enrichment]** sezione, fate clic su **[!UICONTROL Create element]** e selezionate la risorsa di **[!UICONTROL Profile]** destinazione. È quindi possibile eseguire la mappatura sul **[!UICONTROL email]** campo nella **[!UICONTROL Join definition]** sezione o su qualsiasi altra chiave di riconciliazione composita, a seconda delle esigenze.

   ![](assets/optin_eventcreate_join.png)

   Per utilizzare i servizi, aggiungi la risorsa di **[!UICONTROL Service]** destinazione ed esegui il mapping sul **[!UICONTROL serviceName]** campo. Per ulteriori informazioni, vedere .

1. Selezionare **[!UICONTROL Profile]** come **[!UICONTROL Targeting enrichment]** nell&#39;elenco a discesa.
1. Fate clic **[!UICONTROL Publish]** per pubblicare l’evento.

L&#39;evento è pronto. Ora potete progettare il modello e-mail. Questo modello deve includere un collegamento alla pagina di destinazione **CONFERMA** creata in precedenza. Per ulteriori informazioni, vedi [Progettare il messaggio](#design-the-confirmation-message)di conferma.

### Creare la tipologia {#create-the-typology-rule}

È necessario creare una [tipologia](../../sending/using/about-typology-rules.md)specifica duplicando unaesistente. La tipologia consentirà di inviare messaggi ai profili che non hanno ancora confermato il loro accordo e che sono ancora in lista nera. Per impostazione predefinita, le tipologie escludono i profili di rifiuto (ad es. in lista nera). Per creare questa tipologia, procedere come segue:

1. Dal logo Adobe Campaign, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** e fai clic su **[!UICONTROL Typologies]**.
1. Duplica la tipologia predefinita **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**.
1. Una volta confermata la duplicazione, modificate la nuova tipologia e immettete l&#39;etichetta **TYPOLOGY_PROFILE**.
1. Rimuovere la regola dell&#39;indirizzo **** inserito nella blacklist.
1. Clic **[!UICONTROL Save]**.

È ora possibile associare questa tipologia all&#39;e-mail di conferma.

### Progettare il messaggio di conferma {#design-the-confirmation-message}

L&#39;e-mail di conferma è un messaggio transazionale basato sull&#39;evento creato in precedenza. Per creare il messaggio, procedi come indicato di seguito:

1. Dal logo Adobe Campaign, seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** e fai clic su **[!UICONTROL Transactional messages]**.
1. Modificate il modello e-mail **CONFERMA** e personalizzatelo. Potete caricare un contenuto esistente o utilizzare un modello predefinito.
1. Aggiungete un collegamento alla pagina di destinazione **CONFERMA** e fate clic **[!UICONTROL Confirm]** per salvare le modifiche.

   ![](assets/optin_email_selectlp.png)

1. Modificate le proprietà del modello e-mail. Nella sezione **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** , selezionare la tipologia **TYPOLOGY_PROFILE** creata in precedenza.
1. Salva e pubblica il messaggio transazionale.

## Passaggio 3: Creare la pagina di destinazione di acquisizione {#step-3--create-the-acquisition-landing-page}

Devi creare la pagina di destinazione dell’acquisizione iniziale: il modulo di partecipazione verrà pubblicato sul sito Web.

Per creare e configurare questa pagina di destinazione, è necessario:

1. Progettate una [nuova pagina](../../channels/using/getting-started-with-landing-pages.md) di destinazione basata sul **[!UICONTROL Profile acquisition (acquisition)]** modello. Inserire l&#39;etichetta &quot;**ACQUISIZIONE**&quot;.
1. Modificate le proprietà della pagina di destinazione: nella sezione **[!UICONTROL Job]** > **[!UICONTROL Additional data]** , fate clic su **[!UICONTROL Add an element]** e immettete il percorso contestuale seguente:

   /context/profile/blackList

   e impostare il valore su **true**.

   Questo è obbligatorio per forzare la blacklist ed evitare di inviare messaggi ai visitatori che non hanno confermato il loro accordo. La convalida della pagina di destinazione CONFERMA imposta questo campo su **false** dopo la conferma. Per ulteriori informazioni, vedere [Passaggio 1: Creare la pagina](#step-1--create-the-confirmation-landing-page)di destinazione di conferma.

1. Nella sezione **[!UICONTROL Job]** > **[!UICONTROL Specific actions]** , selezionare l&#39;opzione **[!UICONTROL Start sending messages]**.
1. Nell&#39;elenco a discesa associato, scegliete il modello di messaggio **CONFERMA** transazionale creato.

   ![](assets/optin_acquisition_startoption.png)

1. Personalizza il contenuto della pagina di destinazione, in base al marchio e ai dati da acquisire. Potete visualizzare dati personalizzati e cambiare l&#39;etichetta del pulsante di conferma per **confermare ad esempio l&#39;iscrizione** .

   ![](assets/optin_acquisition_page1.png)

1. Personalizzate la pagina di conferma per informare il nuovo utente che deve convalidare l’iscrizione.

   ![](assets/optin_acquisition_page2.png)

1. [Test e pubblicazione](../../channels/using/testing-publishing-landing-page.md) della pagina di destinazione.

È ora configurato il meccanismo di doppio consenso. È possibile eseguire e verificare la procedura da fine a fine, a partire dall&#39;URL pubblico di questa pagina di **[!UICONTROL ACQUISITION]** destinazione. Questo URL viene visualizzato nel dashboard della pagina di destinazione.
