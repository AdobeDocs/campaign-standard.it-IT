---
title: Verifica degli attivatori
description: null
page-status-flag: never-activated
uuid: b3a6667d-e843-4ad6-817e-d91542b5f2e2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: f67e69f2-09fb-4f33-b2c3-c67a060743e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bd74905985734412b4fb11ad11d70faf9fcc9ca6
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---


# Verifica degli attivatori{#testing-your-triggers}

I seguenti suggerimenti per la risoluzione dei problemi aiuteranno a risolvere i problemi più comuni che si possono incontrare quando si utilizzano Attivatori con  Adobe Campaign:

**La funzionalità è attivata?**

Per verificare se l&#39;integrazione Attivatori - Campagna è attivata, fai clic sul logo del Adobe Campaign , nell&#39;angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. Dovresti vedere l&#39; **[!UICONTROL Experience Cloud Triggers]** elemento.

Se lo vedi, passa al passaggio successivo.

In caso contrario, contattate il vostro responsabile commerciale Adobe o il partner di servizi professionali. Consultate [Attivazione della funzionalità](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Prova a creare un trigger**

Segui i passaggi descritti in [Creazione di un trigger mappato in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) per creare un trigger.

Se l&#39;attivatore viene creato, passare al passaggio successivo. In caso contrario, significa che la connessione del punto finale dell&#39;attivatore non è riuscita. Verificate se il provisioning di Triggers in  Experience Cloud (Servizi attivazione). In caso contrario, contattate il vostro responsabile commerciale Adobe o il partner di servizi professionali. Sono necessarie le seguenti informazioni:

* Nome società Marketing Cloud
* ID organizzazione IMS
*  Società di accesso Analytics (può corrispondere al Nome società Marketing Cloud)

**Provare a pubblicare il trigger**

Seguite i passaggi descritti in [Creazione di un trigger mappato in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) per pubblicare l&#39;attivatore.

Se la pubblicazione ha esito positivo, passare al passaggio successivo. In caso contrario, contattate Adobe per riavviare l&#39;istanza e riprovare.

**Generare il trigger dal sito Web**

Seguite i passaggi descritti in [Modifica del modello](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) di messaggi transazionali per modificare e pubblicare il modello transazionale. Quindi, verificare la generazione dell&#39;attivatore dal sito Web.

Se l&#39;attivatore viene ricevuto da  Analytics, passare al passaggio successivo. In caso contrario, verificare i seguenti elementi:

* Trigger è abilitato per  Analytics
* Il sito Web utilizzato per MCID e  Analytics è abilitato in DTM
*  suite di rapporti Analytics corretta viene utilizzata durante la creazione di attivatori

**Il trigger ricevuto da Campaign?**

In caso contrario, verificate che il trigger sia ricevuto dalla pipeline.

In caso contrario, contattate Adobe per verificare la configurazione dei punti finali della pipeline.

In caso affermativo, seguire le seguenti linee guida:

* Verifica il tipo di ID riconciliazione nell&#39;origine dati Campagna.
* L&#39;origine dati CustomerId viene creata tramite gli attributi cliente.
* Controllare l&#39;ID dell&#39;origine dati.
* Chiedi ad Adobe di riavviare l&#39;istanza Campaign dopo la configurazione dell&#39;origine dati.
* Controllare i problemi di analisi attivati nel rapporto di attivazione.

**Il trigger è nello stato in sospeso?**

In caso contrario, passate al passaggio successivo. In caso affermativo, seguire le seguenti linee guida:

* Verificate che il modello transazionale sia pubblicato.
* Verificare che il profilo non sia  elenco Bloccati.
* Controllare l&#39;applicazione delle regole di tipologia.
* Controlla i registri dei messaggi transazionali.

**Il messaggio è valido?**

Se il messaggio non è valido, verifica quanto segue:

* Per attivare i campi di personalizzazione dell&#39;arricchimento contrassegnati come non validi, convalidate il modello transazionale dalle raccolte eventCusResource associate.
* Convalida del formato del messaggio

