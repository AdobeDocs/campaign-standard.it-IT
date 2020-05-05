---
title: Creazione di un flusso di lavoro
description: Questa sezione descrive i principi principali e le procedure ottimali per la creazione di un nuovo flusso di lavoro.
page-status-flag: never-activated
uuid: 11374f64-8d34-40da-937b-09f419250f4c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: c26fcb0e-19d5-4bd5-b7d6-2d22ce92ad90
context-tags: workflow,wizard;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Creazione di un flusso di lavoro{#building-a-workflow}

Questa sezione descrive i principi principali e le procedure ottimali per la creazione di un nuovo flusso di lavoro.

## Principi operativi del flusso di lavoro{#workflow-operating-principles}

Un flusso di lavoro è una **sequenza di attività** configurabili. Ogni attività ha un ruolo specifico nel processo. Il risultato di ogni attività viene inoltrato alla seguente attività da una **transizione**, rappresentata da una freccia.

Il tipo di dati scambiati tra un&#39;attività e un&#39;altra può influenzare la configurazione delle seguenti attività. Ad esempio, se una popolazione viene stabilita prima dell&#39;attività di consegna delle e-mail, può fungere da destinazione per l&#39;e-mail in questione.

Potete aprire le attività per controllare o modificare i parametri prima o dopo l&#39;esecuzione del flusso di lavoro.

Potete aprire le transizioni per verificare che i dati inviati siano corretti durante o dopo l&#39;esecuzione del flusso di lavoro. Per accedere alla visualizzazione dettagliata delle transizioni, è necessario selezionare l&#39; **[!UICONTROL Keep interim results]** opzione nella **[!UICONTROL Execution]** sezione delle proprietà del flusso di lavoro.

![](assets/workflow_overview.png)


## Creazione di un flusso di lavoro {#creating-a-workflow}

Puoi creare un flusso di lavoro da un programma, una campagna o l&#39;elenco delle attività di marketing.

La creazione di un&#39;attività di marketing è dettagliata nella sezione [Creazione di attività](../../start/using/marketing-activities.md#creating-a-marketing-activity) di marketing.

1. Dopo aver iniziato a creare un tipo di flusso di lavoro attività di marketing, seleziona il modello da utilizzare.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Per impostazione predefinita, ogni attività di marketing offre diversi tipi. che consentono di preconfigurare alcuni parametri in base alle esigenze. Per ulteriori informazioni, consultare la sezione [Gestione dei modelli](../../start/using/marketing-activity-templates.md) .

1. Immettete le proprietà generali del flusso di lavoro.

   ![](assets/workflow_creation_2.png)

   Potete immettere un nome nel campo **Etichetta** e modificare l’ID. Il nome dell&#39;attività e il relativo ID vengono visualizzati nell&#39;interfaccia, ma non sono visibili dai destinatari del messaggio.

   >[!NOTE]
   >
   >Puoi creare il flusso di lavoro all’interno di una campagna padre dall’elenco delle attività di marketing. Potete collegare questo flusso di lavoro a una campagna selezionandone una già creata.

   Potete aggiungere una descrizione che l&#39;utente può visualizzare nel contenuto della campagna.

   Poiché semplifica la ricerca e la risoluzione dei problemi se non vengono eseguite nei modi previsti, Adobe consiglia di assegnare ai flussi di lavoro nomi ed etichette corretti: compilare il campo di descrizione del flusso di lavoro per riepilogare il processo da eseguire in modo che l&#39;operatore possa capirlo facilmente.

1. Confermate la creazione dell&#39;attività e verrà visualizzata la dashboard per tale attività. Per ulteriori informazioni, consulta la sezione dell’interfaccia [](../../automating/using/workflow-interface.md) Flusso di lavoro.

1. Una volta configurato il flusso di lavoro, potete accedere alle opzioni aggiuntive facendo clic sul **[!UICONTROL Edit properties]** pulsante. Ad esempio, potete definire un fuso orario specifico da utilizzare per impostazione predefinita in tutte le attività del flusso di lavoro. Per impostazione predefinita, il fuso orario del flusso di lavoro è quello definito per l&#39;operatore Campaign corrente.

   ![](assets/workflow_properties.png)

**Argomento correlato:**

* [Creazione di un video di workflow](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html)
* [Proprietà flusso di lavoro](../../automating/using/executing-a-workflow.md#workflow-properties)

## Aggiunta e collegamento di attività {#adding-and-linking-activities}

È ora necessario definire le varie attività e collegarle insieme nel diagramma.

>[!NOTE]
>
>Se la palette non è visualizzata, fare clic sul primo pulsante della barra degli strumenti per visualizzarla.

Le attività sono raggruppate per categoria all&#39;interno delle diverse sezioni della palette.

* La prima sezione contiene attività di [targeting](../../automating/using/about-targeting-activities.md)
* La seconda sezione contiene le attività [di](../../automating/using/about-execution-activities.md)esecuzione, utilizzate principalmente per coordinare altre attività.
* La terza sezione contiene le attività che possono essere utilizzate per inviare messaggi su [canali](../../automating/using/about-channel-activities.md)diversi. Le attività in questa sezione possono variare a seconda dei canali abilitati nell&#39;istanza.
* La quarta sezione contiene le attività [di gestione dei](../../automating/using/about-data-management-activities.md)file e dei dati.

Per creare il diagramma:

1. Aggiungete un&#39;attività trascinandola dalla palette e rilasciandola nel diagramma.

   Ad esempio, aggiungere un&#39;attività **[Start](../../automating/using/start-and-end.md)**e quindi un&#39;attività di distribuzione**[](../../automating/using/email-delivery.md)** tramite e-mail nel diagramma.

1. Collegate le attività trascinando la transizione dell&#39;attività **Avvia** e rilasciandola sull&#39;attività di consegna **tramite** e-mail.

   >[!NOTE]
   >
   >Potete collegare automaticamente un&#39;attività alla precedente inserendo la nuova attività alla fine della transizione della precedente.

1. Aggiungete le attività necessarie e collegatele per completare il flusso di lavoro.

   >[!NOTE]
   >
   >Potete anche duplicare le attività esistenti copiandole e incollandole. In questo modo, potete mantenere le impostazioni originariamente definite. Per ulteriori informazioni, vedere [Duplicazione delle attività](../../automating/using/workflow-interface.md#duplicating-workflow-activities)del flusso di lavoro.

Una volta collegate le attività del flusso di lavoro, potete personalizzare le transizioni tra di esse con l’ **etichetta** desiderata. A questo scopo, fate doppio clic sulla transizione per accedere alle relative proprietà.

Inoltre, **[!UICONTROL Targeting]** e **[!UICONTROL Data management (ETL)]** le attività consentono di definire codici **di** segmento per le loro transizioni in uscita. Potete quindi creare rapporti basati su questi codici di segmento per misurare l&#39;efficienza delle campagne di marketing. For more on this, refer to [this section](../../reporting/using/creating-a-report-workflow-segment.md).

**Casi di utilizzo del flusso di lavoro:**

* [Caso di utilizzo: Creare una consegna di e-mail una volta alla settimana](../../automating/using/workflow-weekly-offer.md)
* [Caso di utilizzo: Creazione di una consegna segmentata sulla posizione](../../automating/using/workflow-segmentation-location.md)
* [Caso di utilizzo: Creazione di consegne con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso di utilizzo: Flusso di lavoro di retargeting che invia una nuova consegna a non-openers](../../automating/using/workflow-cross-channel-retargeting.md)

## Configurazione delle attività {#configuring-activities}

Per impostazione predefinita, le attività non sono impostate e non elaborano correttamente i dati se non sono configurate. Ogni attività contiene diverse schede per gestire configurazioni specifiche e opzioni generiche dell&#39;attività come transizioni in uscita, etichette e così via.

1. Assicuratevi che tutte le attività siano correttamente connesse. Alcune attività richiedono di rilevare la struttura o la natura dei dati in arrivo per offrire le opzioni di configurazione corrette.
1. Fate doppio clic su un&#39;attività o selezionatela e fate clic sull&#39;azione **[!UICONTROL Edit]** contestuale per aprire la relativa finestra di configurazione.
1. Modificate l&#39;etichetta dell&#39;attività.
1. Definire tutte le diverse opzioni necessarie per elaborare i dati. Fate riferimento alla sezione specifica dell&#39;attività di questa documentazione per apprendere le possibili opzioni per ogni attività.
1. Salvate l&#39;attività e ripetete queste operazioni per ogni attività del flusso di lavoro.
1. Salvare il flusso di lavoro.
