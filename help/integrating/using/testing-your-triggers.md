---
title: Test degli attivatori
seo-title: Test degli attivatori
description: Test degli attivatori
seo-description: null
page-status-flag: never-activated
uuid: b 3 a 6667 d-e 843-4 ad 6-817 e-d 91542 b 5 f 2 e 2
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-triggers
discoiquuid: f 67 e 69 f 2-09 fb -4 f 33-b 2 c 3-c 67 a 060743 e 3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Testing your triggers{#testing-your-triggers}

I seguenti suggerimenti per la risoluzione di problemi ti aiuteranno a risolvere i problemi più comuni che potresti incontrare quando usi Triggers con Adobe Campaign:

**La funzionalità è attivata?**

To check if the Triggers - Campaign integration is activated, click the Adobe Campaign logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]**. You should see the **[!UICONTROL Experience Cloud Triggers]** item.

Se la visualizzate, passate al passaggio successivo.

In caso contrario, contatta il tuo partner di servizi manager o servizi professionali Adobe. See [Activating the functionality](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Provare a creare un trigger**

Follow the steps described in [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) to create a trigger.

Se il trigger viene creato, passate al passaggio successivo. In caso contrario, la connessione del punto finale trigger non è riuscita. Verifica se il provisioning di Triggers in Experience Cloud (servizi Attivazione) è eseguito. In caso contrario, contattate il vostro partner di servizi di Adobe o Executive Services. Sono richieste le seguenti informazioni:

* Nome società Marketing Cloud
* ID organizzazione IMS
* Analytics Login Company (può essere uguale al Nome società di Marketing Cloud)

**Provare a pubblicare il trigger**

Follow the steps described in [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) to publish the trigger.

Se la pubblicazione è riuscita, passate al passaggio successivo. In caso contrario, contattate Adobe per riavviare l'istanza e riprovare.

**Generare il trigger dal sito Web**

Follow the steps described in [Editing the transactional message template](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) to edit and publish the transactional template. Quindi, verificate la generazione del trigger dal sito Web.

Se il trigger viene ricevuto da Analytics, passate al passaggio successivo. In caso contrario, verificate i seguenti elementi:

* Attivatore abilitato per Analytics
* Il sito Web utilizzato per MCID e Analytics è abilitato in DTM
* La suite di rapporti corretta di Analytics viene utilizzata durante la creazione di trigger

**L'attivatore ricevuto da Campaign?**

In caso contrario, verificate che il trigger venga ricevuto dalla pipeline.

In caso contrario, contattate Adobe per controllare la configurazione dei punti finali della pipeline.

In caso affermativo, segui queste linee guida:

* Verifica il tipo ID riconciliazione in Campaign datasource.
* Customerid Datasource viene creato tramite Attributi del cliente.
* Controllare l'ID datasource.
* Chiedi ad Adobe di riavviare l'istanza Campaign dopo la configurazione di Datasource.
* Verificate l'attivazione dei problemi di analisi nel rapporto attivatore.

**Il trigger è in sospeso?**

In caso contrario, passate al passaggio successivo. In caso affermativo, segui queste linee guida:

* Verificate che il modello transazionali sia pubblicato.
* Se la soglia propensityscore è abilitata per Campaign, controlla il punteggio propensione dell'attivatore dalla pipeline.
* Verificate che il profilo non sia in lista nera.
* Controllate l'applicazione delle regole di tipologie.
* Controllate i registri dei messaggi transazionali.

**Il messaggio è valido?**

Se il messaggio non è valido, controlla i seguenti elementi:

* Per attivare i campi di personalizzazione di arricchimento contrassegnati come non validi, convalidate il modello transazionali dalle raccolte eventcusresource associate.
* Convalida del formato messaggio

