---
solution: Campaign Standard
product: campaign
title: Verifica degli attivatori
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Architetto dati
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 2%

---


# Verifica degli attivatori{#testing-your-triggers}

I seguenti suggerimenti per la risoluzione dei problemi aiutano a risolvere i problemi più comuni che si possono incontrare quando si utilizzano Triggers con Adobe Campaign:

**La funzionalità è attivata?**

Per verificare se l’integrazione Triggers - Campaign è attivata, fai clic sul logo Adobe Campaign, nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. Dovresti visualizzare l’elemento **[!UICONTROL Experience Cloud Triggers]** .

Se lo vedi, passa al passaggio successivo.

In caso contrario, contatta il tuo responsabile dell&#39;account Adobe o un partner di servizi professionali. Consulta [Attivazione della funzionalità](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Prova a creare un trigger**

Per creare un trigger, segui i passaggi descritti in [Creazione di un trigger mappato in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) .

Se il trigger viene creato, passa al passaggio successivo. In caso contrario, significa che la connessione al punto finale dell’attivatore non è riuscita. Controlla se il provisioning di Triggers avviene in Experience Cloud (Servizi di Attivazione). In caso contrario, contatta il tuo responsabile dell&#39;account Adobe o un partner di servizi professionali. Sono necessarie le seguenti informazioni:

* Nome società Marketing Cloud
* ID organizzazione IMS
* Società di accesso di Analytics (può essere la stessa del nome dell’azienda del Marketing Cloud)

**Prova a pubblicare il trigger**

Per pubblicare il trigger, segui i passaggi descritti in [Creazione di un trigger mappato in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) .

Se la pubblicazione è riuscita, passa al passaggio successivo. In caso contrario, contatta l&#39;Adobe per riavviare l&#39;istanza e riprova.

**Genera il trigger dal sito web**

Segui i passaggi descritti in [Modifica del modello di messaggio transazionale](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) per modificare e pubblicare il modello transazionale. Quindi, verifica la generazione del trigger dal sito web.

Se il trigger viene ricevuto da Analytics, passa al passaggio successivo. In caso contrario, controlla i seguenti elementi:

* Trigger abilitato per Analytics
* Il sito web utilizzato MCID e Analytics è abilitato in DTM
* La suite di rapporti di Analytics corretta viene utilizzata durante la creazione dei trigger

**Il trigger viene ricevuto da Campaign?**

In caso contrario, verifica se il trigger viene ricevuto dalla pipeline.

In caso contrario, contatta l’Adobe per controllare la configurazione degli endpoint della pipeline.

In caso affermativo, attenersi alle seguenti linee guida:

* Verifica il tipo di ID riconciliazione nell’origine dati Campaign.
* L&#39;origine dati CustomerId viene creata tramite Attributi del cliente.
* Controlla l&#39;ID dell&#39;origine dati.
* Chiedi ad Adobe di riavviare l’istanza Campaign dopo la configurazione dell’origine dati.
* Controlla i problemi di analisi del trigger nel report trigger.

**Il trigger è nello stato in sospeso?**

In caso contrario, passa al passaggio successivo. In caso affermativo, attenersi alle seguenti linee guida:

* Verifica che il modello transazionale sia pubblicato.
* Verifica che il profilo non sia elenco Bloccati.
* Controlla l&#39;applicazione delle regole di tipologia.
* Controlla i registri del messaggio transazionale.

**Il messaggio è valido?**

Se il messaggio non è valido, controlla i seguenti elementi:

* Per attivare i campi di personalizzazione dell’arricchimento contrassegnati come non validi, convalida il modello transazionale dalle raccolte eventCusResource associate.
* Convalida il formato del messaggio

