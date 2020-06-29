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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---


# Importazione di segnali esterni e dati {#external-signal-data-import}

L&#39;esempio seguente illustra l&#39; **[!UICONTROL External signal]** attività in un caso d&#39;uso tipico. Un&#39;importazione di dati viene eseguita in un flusso di lavoro di origine. Dopo l&#39;importazione e l&#39;aggiornamento del database, viene attivato un secondo flusso di lavoro. Questo secondo flusso di lavoro viene utilizzato per aggiornare un aggregato sui dati importati.

Il flusso di lavoro di origine viene presentato come segue:

* Un&#39;attività [Carica file](../../automating/using/load-file.md) carica carica un file contenente nuovi dati di acquisto. Si noti che il [database è stato esteso](../../developing/using/data-model-concepts.md) di conseguenza, in quanto i dati di acquisto non sono presenti per impostazione predefinita nel datamart.

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

* Un&#39;attività di [riconciliazione](../../automating/using/reconciliation.md) crea i collegamenti tra i dati importati e il database in modo che i dati delle transazioni siano correttamente collegati a profili e prodotti.
* Un&#39;attività [Aggiorna dati](../../automating/using/update-data.md) inserisce e aggiorna la risorsa Transazioni del database con i dati in arrivo.
* Un&#39;attività [End](../../automating/using/start-and-end.md) attiva il flusso di lavoro di destinazione, utilizzato per aggiornare gli aggregati.

![](assets/signal_example_source1.png)

Il flusso di lavoro di destinazione viene presentato come segue:

* Un&#39;attività di segnale [](../../automating/using/external-signal.md) esterno attende il completamento del flusso di lavoro di origine.
* Un&#39;attività [Query](../../automating/using/query.md#enriching-data) esegue il targeting dei profili e li arricchisce con una raccolta impostata per recuperare l&#39;ultima data di acquisto.
* Un&#39;attività [Aggiorna dati](../../automating/using/update-data.md) memorizza i dati aggiuntivi in un campo personalizzato dedicato. La risorsa profilo è stata estesa per aggiungere il campo Data **** ultimo acquisto.

![](assets/signal_example_source2.png)
