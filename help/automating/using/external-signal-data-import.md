---
title: Importazione di segnali e dati esterni
description: L’esempio seguente illustra l’attività External signal utilizzata con l’importazione dei dati.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e2997cf5-861b-4202-aeb7-3a47c4d55bef
TQID: 'https://experienceleague.adobe.com/fQTQgLluJa5WPu4ju1gGs84gWfqQ-sWIWuJSTXgQYHA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 79%
---
# Importazione di segnali e dati esterni {#external-signal-data-import}

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

* Un’attività [Riconciliazione](../../automating/using/reconciliation.md) crea i collegamenti tra i dati importati e il database in modo tale che i dati delle transazioni siano collegati correttamente a profili e prodotti.
* Un’attività [Update data](../../automating/using/update-data.md) inserisce e aggiorna la risorsa Transazioni del database con i dati in entrata.
* Un&#39;attività [End](../../automating/using/start-and-end.md) attiva il flusso di lavoro di destinazione, utilizzato per aggiornare gli aggregati.

![](assets/signal_example_source1.png)

Il flusso di lavoro di destinazione viene presentato come segue:

* Un&#39;attività [External signal](../../automating/using/external-signal.md) attende il completamento del flusso di lavoro di origine.
* Un’attività [Query](../../automating/using/query.md#enriching-data) esegue il targeting dei profili e li arricchisce con una raccolta impostata per recuperare la data dell’ultimo acquisto.
* Un’attività [Update data](../../automating/using/update-data.md) memorizza i dati aggiuntivi in un campo personalizzato dedicato. Nota che la risorsa profilo è stata estesa per aggiungere il campo **Last purchase date**.

![](assets/signal_example_source2.png)
