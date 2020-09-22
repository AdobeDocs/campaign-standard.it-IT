---
title: Impostazione di un doppio processo di consenso
description: Segui questi passaggi per impostare un doppio processo di consenso utilizzando le pagine di destinazione in Adobe Campaign.
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
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Impostazione di un doppio processo di consenso{#setting-up-a-double-opt-in-process}

## Informazioni sul doppio consenso {#about-double-opt-in}

Il doppio meccanismo di consenso è una best practice per l’invio di e-mail. Esso protegge la piattaforma da indirizzi e-mail errati o non validi, da spambot e impedisce possibili reclami di spam.

Il principio consiste nell’inviare un’e-mail per confermare il consenso del visitatore prima di memorizzarlo tra i “profili” nel database di Campaign: il visitatore compila una pagina di destinazione online, quindi riceve un messaggio e-mail e deve fare clic sul collegamento di conferma per finalizzare l’abbonamento.

![](assets/optin_mechanism.png)

Per configurare questa impostazione devi effettuare le seguenti operazioni:

1. Crea e pubblica una pagina di destinazione in modo tale che i visitatori possano registrarsi e abbonarsi. Questa pagina di destinazione sarà disponibile da un sito web. Visitors who fill in and submit this landing page will be stored in the database but added to the denylist, in order not to receive any communication before the final validation (see [Denylist management in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).
1. Crea e invia automaticamente l’e-mail di consenso, con un collegamento di conferma. Questa e-mail eseguirà il targeting della popolazione che ha inviato la pagina di destinazione. Sarà basata su un modello e-mail che consente di eseguire il targeting dei profili di rinuncia.
1. Reindirizza a una pagina di destinazione di conferma. Questa pagina di destinazione finale proporrà un pulsante di conferma: i visitatori devono fare clic su di esso. Puoi progettare un’e-mail di benvenuto da inviare al termine della conferma e, ad esempio, aggiungere un’offerta speciale nell’e-mail per i nuovi destinatari.

Questi passaggi devono essere configurati in Adobe Campaign in un ordine specifico affinché tutti i parametri siano attivati correttamente.

## Passaggio 1: creare la pagina di destinazione di conferma {#step-1--create-the-confirmation-landing-page}

Il processo di impostazione del doppio meccanismo di consenso inizia con la creazione della pagina di destinazione di conferma: questa pagina verrà visualizzata quando i visitatori hanno fatto clic sull’e-mail di conferma per registrarsi.

Per creare e configurare questa pagina di destinazione, devi eseguire le seguenti operazioni:

1. Progetta una [nuova pagina di destinazione](../../channels/using/getting-started-with-landing-pages.md) basata sul modello **[!UICONTROL Profile acquisition (acquisition)]**. Inserisci l’etichetta “**CONFIRMATION**”.

   Se devi utilizzare dei [servizi](../../audiences/using/about-subscriptions.md), puoi utilizzare anche il modello **[!UICONTROL Subscription (sub)]**.

1. Modifica le proprietà della pagina di destinazione e, nella sezione **[!UICONTROL Access and loading]**, deseleziona l’opzione **[!UICONTROL Authorize unidentified visitors]** e seleziona **[!UICONTROL Preload visitor data]** (questo non è obbligatorio).

   ![](assets/optin_confirmlp_param.png)

1. Nella sezione **[!UICONTROL Job]** > **[!UICONTROL Additional data]**, fai clic su **[!UICONTROL Add an element]** e immetti il percorso contestuale seguente:

   /context/profile/blackList

   Imposta il valore su **false** e fai clic su **[!UICONTROL Add]**.

   ![](assets/optin_confirmlp_newelement.png)

   Questo contesto rimuove il campo &quot;Su elenco Bloccati&quot; per poter inviare e-mail. Si nota in seguito che la prima pagina di destinazione impostava questo campo su **true** prima della conferma, per impedire l’invio di e-mail a profili non confermati. Per ulteriori informazioni, consulta il [Passaggio 3: creare la pagina di destinazione di acquisizione](#step-3--create-the-acquisition-landing-page).

1. Personalizza il contenuto della pagina di destinazione: puoi visualizzare dati personalizzati e cambiare l’etichetta del pulsante di conferma in “Fai clic qui per confermare l’abbonamento”, ad esempio.

   ![](assets/optin_confirmlp_design.png)

1. Adatta il contenuto della pagina di conferma per informare gli abbonati che ora sono registrati.

   ![](assets/optin_confimlp_page2.png)

1. [Verifica e pubblica](../../channels/using/testing-publishing-landing-page.md) la pagina di destinazione.

## Passaggio 2: creare l’e-mail di conferma {#step-2--create-the-confirmation-email}

Una volta creata la pagina di destinazione di conferma, puoi progettare l’e-mail di conferma: questa e-mail verrà inviata automaticamente a ogni visitatore che convalida la pagina di destinazione di acquisizione. Questa convalida è considerata un evento e l’e-mail è un messaggio transazionale, collegato a una regola di tipologia specifica che consente di eseguire il targeting delle popolazioni di rinuncia.

I passaggi per creare questi elementi sono descritti di seguito. Devi seguirli prima di creare la pagina di destinazione di acquisizione stessa, poiché in essa si farà riferimento a questo modello e-mail.

### Creare l’evento {#create-the-event}

L’e-mail di conferma è un [messaggio transazionale](../../channels/using/getting-started-with-transactional-msg.md) poiché risponde a un evento: la convalida del modulo. Devi innanzitutto creare l’evento e poi creare il modello del messaggio transazionale.

1. Crea un evento dal menu **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**, accessibile dal logo Adobe Campaign, e immetti l’etichetta “**CONFIRM**”.
1. Seleziona la dimensione di targeting **[!UICONTROL Profile]** e fai clic su **[!UICONTROL Create]**.

   ![](assets/optin_eventcreate.png)

1. Nella sezione **[!UICONTROL Fields]**, fai clic su **[!UICONTROL Create element]** e aggiungi l’**[!UICONTROL email]** nella struttura dati per abilitare la riconciliazione.
1. Nella sezione **[!UICONTROL Enrichment]**, fai clic su **[!UICONTROL Create element]** e seleziona la risorsa target **[!UICONTROL Profile]**. Puoi quindi eseguire la mappatura sul campo **[!UICONTROL email]** nella sezione **[!UICONTROL Join definition]** o su qualsiasi altra chiave di riconciliazione composita, a seconda delle tue esigenze.

   ![](assets/optin_eventcreate_join.png)

   Se devi utilizzare dei servizi, aggiungi la risorsa target **[!UICONTROL Service]** ed esegui la mappatura sul campo **[!UICONTROL serviceName]**. Per ulteriori informazioni, consulta .

1. Seleziona **[!UICONTROL Profile]** come **[!UICONTROL Targeting enrichment]** nell’elenco a discesa.
1. Fai clic su **[!UICONTROL Publish]** per pubblicare l’evento.

L’evento è pronto. Ora puoi progettare il modello e-mail. Questo modello deve includere un collegamento alla pagina di destinazione **CONFIRMATION** creata in precedenza. Per ulteriori informazioni, consulta [Progettare il messaggio di conferma](#design-the-confirmation-message).

### Creare la tipologia {#create-the-typology-rule}

Devi creare una [tipologia](../../sending/using/about-typology-rules.md) specifica duplicandone una preconfigurata. La tipologia consentirà di inviare messaggi ai profili che non hanno ancora confermato il loro accordo e che sono ancora in elenco Bloccati. Per impostazione predefinita, le tipologie escludono i profili di rifiuto (ad es. per elenco Bloccati). Per creare questa tipologia, segui questi passaggi:

1. Dal logo Adobe Campaign, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** e fai clic su **[!UICONTROL Typologies]**.
1. Duplica la tipologia preconfigurata **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**.
1. Una volta confermata la duplicazione, modifica la nuova tipologia e immetti l’etichetta **TYPOLOGY_PROFILE**.
1. Rimuovere l&#39; **indirizzo elenco Bloccati regola di** .
1. Fai clic su **[!UICONTROL Save]**.

Questa tipologia può ora essere associata all’e-mail di conferma.

### Progettare il messaggio di conferma {#design-the-confirmation-message}

L’e-mail di conferma è un messaggio transazionale basato sull’evento creato in precedenza. Per creare il messaggio, segui i passaggi seguenti:

1. Dal logo di Adobe Campaign, seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** e fai clic su **[!UICONTROL Transactional messages]**.
1. Modifica il modello e-mail **CONFIRM** e personalizzalo. Puoi caricare un contenuto esistente o utilizzare un modello preconfigurato.
1. Aggiungi un collegamento alla pagina di destinazione **CONFIRMATION** e fai clic su **[!UICONTROL Confirm]** per salvare le modifiche.

   ![](assets/optin_email_selectlp.png)

1. Modifica le proprietà del modello e-mail. Nella sezione **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]**, seleziona la tipologia **TYPOLOGY_PROFILE** creata in precedenza.
1. Salva e pubblica il messaggio transazionale.

## Passaggio 3: creare la pagina di destinazione di acquisizione {#step-3--create-the-acquisition-landing-page}

Devi creare la pagina di destinazione di acquisizione iniziale: il modulo di consenso verrà pubblicato sul sito web.

Per creare e configurare questa pagina di destinazione, devi eseguire le seguenti operazioni:

1. Progetta una [nuova pagina di destinazione](../../channels/using/getting-started-with-landing-pages.md) basata sul modello **[!UICONTROL Profile acquisition (acquisition)]**. Inserisci l’etichetta “**ACQUISITION**”.
1. Modifica le proprietà della pagina di destinazione: nella sezione **[!UICONTROL Job]** > **[!UICONTROL Additional data]**, fai clic su **[!UICONTROL Add an element]** e immetti il percorso contestuale seguente:

   /context/profile/blackList

   Quindi imposta il valore su **true**.

   Questo è obbligatorio per forzare l&#39;aggiunta al elenco Bloccati ed evitare di inviare messaggi ai visitatori che non hanno confermato il loro accordo. La convalida della pagina di destinazione CONFIRMATION imposta questo campo su **false** dopo la conferma. Per ulteriori informazioni, consulta il [Passaggio 1: creare la pagina di destinazione di conferma](#step-1--create-the-confirmation-landing-page).

1. Nella sezione **[!UICONTROL Job]** > **[!UICONTROL Specific actions]**, seleziona l’opzione **[!UICONTROL Start sending messages]**.
1. Nell’elenco a discesa associato, scegli il modello di messaggio transazionale **CONFIRM** creato.

   ![](assets/optin_acquisition_startoption.png)

1. Personalizza il contenuto della pagina di destinazione, in base al brand e ai dati da acquisire. Puoi visualizzare dati personalizzati e cambiare l’etichetta del pulsante di conferma in **Conferma l’abbonamento**, ad esempio.

   ![](assets/optin_acquisition_page1.png)

1. Personalizza la pagina di conferma per informare il nuovo abbonato che deve convalidare l’abbonamento.

   ![](assets/optin_acquisition_page2.png)

1. [Verifica e pubblica](../../channels/using/testing-publishing-landing-page.md) la pagina di destinazione.

Il doppio meccanismo di consenso è ora configurato. Puoi eseguire e verificare la procedura dall’inizio alla fine, a partire dall’URL pubblico di questa pagina di destinazione **[!UICONTROL ACQUISITION]**. Questo URL viene visualizzato nel dashboard della pagina di destinazione.
