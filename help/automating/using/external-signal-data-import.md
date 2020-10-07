---
title: Importazione di segnali esterni e dati
description: L'esempio seguente illustra l'attività del segnale esterno utilizzata con l'importazione di dati.
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 79%

---


# External signal and data import {#external-signal-data-import}

L’esempio seguente illustra l’attività **[!UICONTROL External signal]** in un caso d’uso tipico. Un’importazione dati viene eseguita in un flusso di lavoro sorgente. Dopo l’importazione dei dati e l’aggiornamento del database, viene attivato un secondo flusso di lavoro. Questo secondo flusso di lavoro viene utilizzato per aggiornare un aggregato sui dati importati.

Il flusso di lavoro sorgente viene presentato come segue:

* Un’attività [Load file](../../automating/using/load-file.md) carica un file contenente nuovi dati di acquisto. Nota che il [database è stato esteso](../../developing/using/data-model-concepts.md) di conseguenza, in quanto i dati di acquisto non sono presenti per impostazione predefinita nel data mart.

   Ad esempio:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* Un’attività [Reconciliation](../../automating/using/reconciliation.md) crea i collegamenti tra i dati importati e il database in modo tale che i dati delle transazioni siano collegati correttamente a profili e prodotti.
* Un’attività [Update data](../../automating/using/update-data.md) inserisce e aggiorna la risorsa Transazioni del database con i dati in entrata.
* An [End](../../automating/using/start-and-end.md) activity triggers the destination workflow, which is used to update aggregates.

![](assets/signal_example_source1.png)

Il flusso di lavoro di destinazione viene presentato come segue:

* An [External signal](../../automating/using/external-signal.md) activity waits for the source workflow to be successfully finished.
* Un’attività [Query](../../automating/using/query.md#enriching-data) esegue il targeting dei profili e li arricchisce con una raccolta impostata per recuperare la data dell’ultimo acquisto.
* Un’attività [Update data](../../automating/using/update-data.md) memorizza i dati aggiuntivi in un campo personalizzato dedicato. Nota che la risorsa profilo è stata estesa per aggiungere il campo **Last purchase date**.

![](assets/signal_example_source2.png)
