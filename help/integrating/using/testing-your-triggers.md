---
title: Verifica degli attivatori
description: null
page-status-flag: mai attivato
uuid: b3a6667d-e843-4ad6-817e-d91542b5f2e2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integration
content-type: reference
topic-tags: utilizzo di attivatori per campagne
discoiquuid: f67e69f2-09fb-4f33-b2c3-c67a060743e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Verifica degli attivatori{#testing-your-triggers}

I seguenti suggerimenti per la risoluzione dei problemi ti aiuteranno a risolvere i problemi più comuni che potresti incontrare quando utilizzi Triggers con Adobe Campaign:

**La funzionalità è attivata?**

Per verificare se l'integrazione Triggers - Campagna è attivata, fai clic sul logo Adobe Campaign, nell'angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]**. Dovresti vedere l' **[!UICONTROL Experience Cloud Triggers]** elemento.

Se lo vedi, passa al passaggio successivo.

In caso contrario, contattate il vostro responsabile commerciale Adobe o il partner di servizi professionali. Consultate [Attivazione della funzionalità](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Prova a creare un trigger**

Segui i passaggi descritti in [Creazione di un trigger mappato in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) per creare un trigger.

Se l'attivatore viene creato, passare al passaggio successivo. In caso contrario, significa che la connessione del punto finale dell'attivatore non è riuscita. Verifica se il provisioning di Triggers in Experience Cloud (servizi di attivazione). In caso contrario, contattate il vostro responsabile commerciale Adobe o il partner di servizi professionali. Sono necessarie le seguenti informazioni:

* Nome società Marketing Cloud
* ID ORG IMS
* Società di accesso Analytics (può corrispondere al Nome società Marketing Cloud)

**Provare a pubblicare il trigger**

Seguite i passaggi descritti in [Creazione di un trigger mappato in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) per pubblicare l'attivatore.

Se la pubblicazione ha esito positivo, passare al passaggio successivo. In caso contrario, contattate Adobe per riavviare l'istanza e riprovare.

**Generare il trigger dal sito Web**

Seguite i passaggi descritti in [Modifica del modello](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) di messaggi transazionali per modificare e pubblicare il modello transazionale. Quindi, verificare la generazione dell'attivatore dal sito Web.

Se l'attivatore viene ricevuto da Analytics, passa al passaggio successivo. In caso contrario, verificare quanto segue:

* Trigger abilitato per Analytics
* Il sito Web utilizzato MCID e Analytics è abilitato in DTM
* La suite di rapporti Analytics corretta viene utilizzata durante la creazione di attivatori

**Il trigger ricevuto da Campaign?**

In caso contrario, verificate che il trigger sia ricevuto dalla pipeline.

In caso contrario, contattate Adobe per verificare la configurazione dei punti finali della pipeline.

In caso affermativo, seguire le seguenti linee guida:

* Verifica il tipo di ID riconciliazione nell'origine dati Campagna.
* L'origine dati CustomerId viene creata tramite attributi cliente.
* Controllare l'ID origine dati.
* Chiedi ad Adobe di riavviare l'istanza Campaign dopo la configurazione dell'origine dati.
* Controllare i problemi di analisi attivati nel rapporto di attivazione.

**Il trigger è nello stato in sospeso?**

In caso contrario, passate al passaggio successivo. In caso affermativo, seguire le seguenti linee guida:

* Verificate che il modello transazionale sia pubblicato.
* Se la soglia di propensioneScore è abilitata per Campaign, controlla il punteggio di propensione dell'attivatore dalla pipeline.
* Verificate che il profilo non sia in lista nera.
* Controllare l'applicazione delle regole di tipologia.
* Controlla i registri dei messaggi transazionali.

**Il messaggio è valido?**

Se il messaggio non è valido, verifica quanto segue:

* Per attivare i campi di personalizzazione dell'arricchimento contrassegnati come non validi, convalidate il modello transazionale dalle raccolte eventCusResource associate.
* Convalida del formato del messaggio

