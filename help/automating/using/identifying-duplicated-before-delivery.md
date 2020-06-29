---
title: Identificazione di duplicati prima della consegna
description: L'esempio seguente illustra una deduplicazione che consente di escludere i duplicati di una destinazione prima di inviare un'e-mail. Ciò significa che eviti di inviare una comunicazione più volte allo stesso profilo.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# Identificazione di duplicati prima della consegna {#identifying-duplicates-before-a-delivery}

L&#39;esempio seguente illustra una deduplicazione che consente di escludere i duplicati di una destinazione prima di inviare un&#39;e-mail. Ciò significa che eviti di inviare una comunicazione più volte allo stesso profilo.

Il flusso di lavoro è costituito da:

![](assets/deduplication_example_workflow.png)

* Una [query](../../automating/using/query.md) che consente di definire la destinazione dell&#39;e-mail. In questo caso, il flusso di lavoro si applica a tutti i profili di età compresa tra i 18 e i 25 anni presenti nel database client da oltre un anno.

   ![](assets/deduplication_example_query.png)

* Un&#39;attività di [deduplicazione](../../automating/using/deduplication.md) che consente di identificare i duplicati derivanti dalla query precedente. In questo esempio viene salvato un solo record per ogni duplicato. I duplicati vengono identificati utilizzando l&#39;indirizzo e-mail. Ciò significa che la consegna dell&#39;e-mail può essere inviata solo una volta per ogni indirizzo e-mail presente nel targeting.

   Il metodo di deduplicazione selezionato è **[!UICONTROL Non-empty value]**. Questo consente di garantire che tra i record conservati in caso di duplicati, sia data priorità a quelli in cui è stato fornito il **Nome** . Questo renderà più coerente l’utilizzo del nome nei campi di personalizzazione del contenuto dell’e-mail.

   Inoltre, viene aggiunta una transizione aggiuntiva per mantenere i duplicati e per poterli elencare.

   ![](assets/deduplication_example_dedup.png)

* Una consegna [](../../automating/using/email-delivery.md) e-mail inserita dopo la transizione in uscita principale della deduplicazione.
* Un&#39;attività [Salva audience](../../automating/using/save-audience.md) inserita dopo l&#39;ulteriore transizione della deduplicazione per salvare i duplicati in un pubblico **Duplicati** . Questo pubblico può essere riutilizzato per escludere direttamente i suoi membri da ogni invio di e-mail.
