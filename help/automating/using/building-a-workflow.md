---
title: Creazione di un flusso di lavoro
seo-title: Creazione di un flusso di lavoro
description: Creazione di un flusso di lavoro
seo-description: Questa sezione descrive i principi principali e le procedure ottimali per la creazione di un nuovo flusso di lavoro.
page-status-flag: never-activated
uuid: 11374 f 64-8 d 34-40 da -937 b -09 f 419250 f 4 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: workflow-general-operation
discoiquuid: c 26 fcb 0 e -19 d 5-4 bd 5-b 7 d 6-2 d 22 ce 92 ad 90
context-tags: flusso di lavoro, procedura guidata; flusso di lavoro, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# Creazione di un flusso di lavoro{#building-a-workflow}

Questa sezione descrive i principi principali e le procedure ottimali per la creazione di un nuovo flusso di lavoro:

* Creazione di un flusso di lavoro.
* Aggiunta e collegamento delle attività.
* Configurazione delle attività.

## Creazione di un flusso di lavoro {#creating-a-workflow}

Potete creare un flusso di lavoro da un programma, una campagna o l'elenco delle attività di marketing.

La creazione di un'attività di marketing è dettagliata nella sezione [Creazione delle attività](../../start/using/marketing-activities.md#creating-a-marketing-activity) di marketing.

1. Dopo aver creato un'attività di marketing tipo di flusso di lavoro, selezionate il modello che desiderate utilizzare.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Per impostazione predefinita, ogni attività di marketing offre diversi tipi. Queste consentono di preconfigurare determinati parametri in base alle esigenze. Per ulteriori informazioni, consultate la [sezione Gestione dei modelli](../../start/using/about-templates.md) .

1. Inserite le proprietà generali del flusso di lavoro.

   ![](assets/workflow_creation_2.png)

   Puoi immettere un nome nel campo **Etichetta** e modificare l'ID. Il nome dell'attività e il relativo ID compaiono nell'interfaccia, ma non sono visibili dai destinatari del messaggio.

   >[!NOTE]
   >
   >Potete creare il flusso di lavoro all'interno di una campagna principale dall'elenco delle attività di marketing. Potete collegare questo flusso di lavoro a una campagna selezionandone una già creata.

   Potete aggiungere una descrizione che l'utente può vedere nel contenuto della campagna.

   Poiché semplifica la ricerca e la risoluzione dei problemi in caso contrario, Adobe consiglia di fornire ai tuoi flussi di lavoro nomi e etichette adeguati: compilare il campo di descrizione del flusso di lavoro per riepilogare il processo da eseguire in modo che l'operatore possa facilmente comprenderlo.

1. Confermate la creazione dell'attività e il dashboard per quell'attività verrà visualizzato. Per ulteriori informazioni, consulta la sezione [relativa all'interfaccia](../../automating/using/workflow-interface.md) del flusso di lavoro.

**Argomento correlato:**

[Creazione di](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-workflow-feature-video-use.html) un video sul flusso di lavoro

## Aggiunta e collegamento delle attività {#adding-and-linking-activities}

Ora devi definire le varie attività e collegarle nel diagramma.

>[!NOTE]
>
>Se la palette non viene visualizzata, fare clic sul primo pulsante della barra degli strumenti per visualizzarla.

Le attività sono raggruppate per categoria all'interno delle diverse sezioni della palette.

* La prima sezione contiene attività di targeting.
* La seconda sezione contiene le attività di esecuzione, utilizzate principalmente per coordinare altre attività.
* La terza sezione contiene attività che possono essere utilizzate per inviare messaggi su diversi canali. Le attività in questa sezione possono variare a seconda dei canali abilitati nell'istanza.
* La quarta sezione contiene le attività di manipolazione dei file e gestione dati.

Per creare il diagramma:

1. Aggiungere un'attività trascinandola dalla palette e rilasciandola nel diagramma.

   Ad esempio, aggiungete un'attività **Start** e quindi un **'attività di consegna** e-mail sul diagramma.

1. Collegate insieme le attività trascinando la transizione **Avvia** attività e rilasciandola nell' **attività di consegna** delle e-mail.

   >[!NOTE]
   >
   >Potete collegare automaticamente un'attività al precedente inserendo la nuova attività alla fine della transizione precedente.

1. Aggiungi le attività necessarie e collega le attività per completare il flusso di lavoro.

   >[!NOTE]
   >
   >Potete anche duplicare le attività esistenti copiandole. In tal modo vengono mantenute le impostazioni definite originariamente. Per ulteriori informazioni, consultate [Attività di duplicazione del flusso di lavoro](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

Una volta collegate le attività del flusso di lavoro, potete personalizzare le transizioni tra di loro con l' **etichetta** scelta. A tal fine, fate doppio clic sulla transizione per accedere alle relative proprietà.

Inoltre, **[!UICONTROL Targeting]****[!UICONTROL Data management (ETL)]** le attività consentono di definire **i codici dei segmenti** per le transizioni in uscita. Potete quindi creare rapporti basati su questi codici del segmento per misurare l'efficienza delle campagne di inclusione. For more on this, refer to [this section](../../reporting/using/creating-a-report-workflow-segment.md).

**Casi d'uso del flusso di lavoro:**

* [Caso d'uso: Creazione di una consegna e-mail una tantum](../../automating/using/workflow-weekly-offer.md)
* [Caso d'uso: Creazione di una distribuzione segmentata sulla posizione](../../automating/using/workflow-segmentation-location.md)
* [Caso d'uso: Creazione di consegne con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso d'uso: Flusso di lavoro di retargeting che invia una nuova consegna a non-openers](../../automating/using/workflow-cross-channel-retargeting.md)

## Configurazione delle attività {#configuring-activities}

Per impostazione predefinita, le attività non vengono impostate e non elaborano correttamente i dati se non sono configurati. Ciascuna attività contiene diverse schede per gestire configurazioni specifiche e opzioni generiche attività quali transizioni in uscita, etichette, ecc.

1. Assicuratevi che tutte le attività siano connesse correttamente. Alcune attività richiedono di rilevare la struttura o la natura dei dati in entrata per offrire le opzioni di configurazione corrette.
1. Fate doppio clic su un'attività o selezionatela e fate clic sull'azione **[!UICONTROL Edit]** contestuale per aprire la relativa finestra di configurazione.
1. Modificate l'etichetta dell'attività.
1. Definire tutte le opzioni diverse necessarie per elaborare i dati. Per informazioni sulle opzioni disponibili per ogni attività, consultate la sezione specifica dell'attività.
1. Salvate l'attività e ripetete queste operazioni per ogni attività del flusso di lavoro.
1. Salvate il flusso di lavoro.
