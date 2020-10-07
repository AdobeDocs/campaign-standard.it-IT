---
title: Creazione di un flusso di lavoro
description: Questa sezione descrive i principi fondamentali e le best practice per la creazione di un nuovo flusso di lavoro.
page-status-flag: never-activated
uuid: 11374f64-8d34-40da-937b-09f419250f4c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: c26fcb0e-19d5-4bd5-b7d6-2d22ce92ad90
context-tags: workflow,wizard;workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 100%

---


# Creazione di un flusso di lavoro{#building-a-workflow}

Questa sezione descrive i principi fondamentali e le best practice per la creazione di un nuovo flusso di lavoro.

## Principi di funzionamento di un flusso di lavoro{#workflow-operating-principles}

Un flusso di lavoro è una **sequenza di attività configurabili**. Ciascuna attività ha un ruolo specifico nel processo. Il risultato di ciascuna attività viene inoltrato all’attività seguente da una **transizione**, rappresentata da una freccia.

Il tipo di dati scambiato tra un’attività e un’altra può influenzare la configurazione delle attività seguenti. Ad esempio, se una popolazione viene stabilita prima dell’attività di consegna e-mail, essa può fungere da destinazione per l’e-mail in questione.

Puoi aprire le attività per verificare o modificare parametri prima o dopo l’esecuzione del flusso di lavoro.

Puoi aprire le transizioni per verificare che i dati inviati siano corretti durante o dopo l’esecuzione del flusso di lavoro. Per accedere alla vista dettagliata delle transizioni, devi selezionare l’opzione **[!UICONTROL Keep interim results]** nella sezione **[!UICONTROL Execution]** delle proprietà del flusso di lavoro.

>[!CAUTION]
>
>Questa opzione consuma molto spazio su disco ed è progettata per consentire la creazione di un flusso di lavoro, garantendone la corretta configurazione e il giusto comportamento. Lascia deselezionata questa opzione nelle istanze di produzione.

![](assets/workflow_overview.png)


## Creazione di un flusso di lavoro {#creating-a-workflow}

Puoi creare un flusso di lavoro da un programma, da una campagna o dall’elenco delle attività di marketing.

La creazione di un’attività di marketing è descritta nella sezione [Creazione di attività di marketing](../../start/using/marketing-activities.md#creating-a-marketing-activity).

1. Dopo aver iniziato la creazione di un’attività di marketing di tipo flusso di lavoro, seleziona il modello da utilizzare.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Per impostazione predefinita, ciascuna attività di marketing ne offre diversi tipi. Questi ultimi ti consentono di preconfigurare determinati parametri in base alle tue esigenze. Per ulteriori informazioni, consulta la sezione [Gestione dei modelli](../../start/using/marketing-activity-templates.md).

1. Immetti le proprietà generali del flusso di lavoro.

   ![](assets/workflow_creation_2.png)

   Puoi immettere un nome nel campo **Etichetta** e modificare l’ID. Il nome dell’attività e il relativo ID vengono visualizzati nell’interfaccia, ma non sono visibili dai destinatari del messaggio.

   >[!NOTE]
   >
   >Puoi creare il flusso di lavoro all’interno di una campagna principale dall’elenco delle attività di marketing. Puoi collegare questo flusso di lavoro a una campagna selezionandone una già creata.

   Puoi aggiungere una descrizione che l’utente può visualizzare nel contenuto della campagna.

   Poiché ciò ne semplifica la ricerca e la risoluzione dei problemi se non stanno ottenendo le prestazioni previste, Adobe consiglia di assegnare ai flussi di lavoro nomi ed etichette corretti: compila il campo di descrizione del flusso di lavoro per riepilogare il processo da eseguire in modo tale che l’operatore possa comprenderlo facilmente.

1. Conferma la creazione dell’attività per visualizzarne il dashboard. Per ulteriori informazioni, consulta la sezione [Interfaccia dei flussi di lavoro](../../automating/using/workflow-interface.md).

1. Quando il flusso di lavoro è pronto per essere configurato, puoi accedere alle opzioni aggiuntive facendo clic sul pulsante **[!UICONTROL Edit properties]**. Ad esempio, puoi definire un fuso orario specifico da utilizzare per impostazione predefinita in tutte le attività del flusso di lavoro. Per impostazione predefinita, il fuso orario del flusso di lavoro è quello definito per l’operatore corrente di Campaign.

   ![](assets/workflow_properties.png)

**Argomento correlato:**

* Video [Creazione di un flusso di lavoro](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html)
* [Proprietà del flusso di lavoro](../../automating/using/managing-execution-options.md)

## Aggiunta e collegamento di attività {#adding-and-linking-activities}

Devi ora definire le varie attività e collegarle nel diagramma.

>[!NOTE]
>
>Se la palette non viene visualizzata, fai clic sul primo pulsante della barra degli strumenti per visualizzarla.

Le attività sono raggruppate per categoria all’interno delle diverse sezioni della palette.

* La prima sezione contiene [attività di targeting](../../automating/using/about-targeting-activities.md)
* La seconda sezione contiene le [attività di esecuzione](../../automating/using/about-execution-activities.md), utilizzate principalmente per coordinare altre attività.
* La terza sezione contiene attività che possono essere utilizzate per inviare messaggi su diversi [canali](../../automating/using/about-channel-activities.md). Le attività in questa sezione possono variare a seconda dei canali abilitati nell’istanza.
* La quarta sezione contiene [attività di manipolazione file e di gestione dati](../../automating/using/about-data-management-activities.md).

Per creare il diagramma:

1. Aggiungi un’attività trascinandola dalla palette e rilasciandola nel diagramma.

   Ad esempio, aggiungi un’attività **[Inizio](../../automating/using/start-and-end.md)** e quindi un’attività **[Email delivery](../../automating/using/email-delivery.md)** nel diagramma.

1. Collega le attività trascinando la transizione dell’attività **Inizio** e rilasciandola sull’attività **Email delivery**.

   >[!NOTE]
   >
   >Puoi collegare automaticamente un’attività alla precedente inserendo la nuova attività alla fine della transizione della precedente.

1. Aggiungi le attività necessarie e collegale per completare il tuo flusso di lavoro.

   >[!NOTE]
   >
   >Puoi anche duplicare le attività esistenti copiandole e incollandole. In questo modo, puoi mantenere le impostazioni definite in origine. Per ulteriori informazioni, consulta [Duplicazione delle attività del flusso di lavoro](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

Una volta collegate le attività del flusso di lavoro, puoi personalizzare le transizioni tra di esse con l’**etichetta** desiderata. A tale scopo, fai doppio clic sulla transizione per accedere alle relative proprietà.

Inoltre, le attività **[!UICONTROL Targeting]** e **[!UICONTROL Data management (ETL)]** ti consentono di definire **codici di segmento** per le loro transizioni in uscita. Puoi quindi creare report basati su questi codici di segmento per misurare l’efficienza delle campagne di marketing. Per ulteriori informazioni, consulta [questa sezione](../../reporting/using/creating-a-report-workflow-segment.md).

**Casi di utilizzo del flusso di lavoro:**

* [Caso di utilizzo: creare una consegna e-mail settimanale](../../automating/using/workflow-weekly-offer.md)
* [Caso di utilizzo: creazione di una consegna segmentata sulla posizione](../../automating/using/workflow-segmentation-location.md)
* [Caso di utilizzo: creazione di consegne con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso di utilizzo: invio di una nuova consegna a non-opener tramite un flusso di lavoro di retargeting](../../automating/using/workflow-cross-channel-retargeting.md)

## Configurazione delle attività {#configuring-activities}

Per impostazione predefinita, le attività non sono impostate e non elaborano correttamente i dati se non sono configurate. Ciascuna attività contiene diverse schede per gestire configurazioni specifiche e opzioni generiche dell’attività come transizioni in uscita, etichette e così via.

1. Assicurati che tutte le attività siano collegate correttamente. Alcune attività richiedono di rilevare la struttura o la natura dei dati in arrivo per offrire le opzioni di configurazione corrette.
1. Fai doppio clic su un’attività o selezionala e fai clic sull’azione contestuale **[!UICONTROL Edit]** per aprire la relativa finestra di configurazione.
1. Modifica l’etichetta dell’attività.
1. Definisci tutte le diverse opzioni necessarie a elaborare i dati. Per informazioni sulle opzioni possibili per ciascuna attività, fai riferimento alla sezione specifica di tale attività in questa documentazione.
1. Salva l’attività e ripeti queste operazioni per ciascuna attività del flusso di lavoro.
1. Salva il flusso di lavoro.
