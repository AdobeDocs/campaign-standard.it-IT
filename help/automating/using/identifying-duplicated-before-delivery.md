---
solution: Campaign Standard
product: campaign
title: Identificazione di duplicati prima di una consegna
description: L’esempio seguente illustra una deduplicazione che ti consente di escludere i duplicati di un target prima di inviare un’e-mail. Ciò significa che eviti di inviare una comunicazione diverse volte allo stesso profilo.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 78%

---


# Identificazione di duplicati prima di una consegna {#identifying-duplicates-before-a-delivery}

L’esempio seguente illustra una deduplicazione che ti consente di escludere i duplicati di un target prima di inviare un’e-mail. Ciò significa che eviti di inviare una comunicazione diverse volte allo stesso profilo.

Il flusso di lavoro è costituito da:

![](assets/deduplication_example_workflow.png)

* Una [Query](../../automating/using/query.md) che ti consente di definire il target dell’e-mail. In questo caso, il flusso di lavoro esegue il targeting di tutti i profili di età compresa tra i 18 e i 25 anni presenti nel database dei clienti da oltre un anno.

   ![](assets/deduplication_example_query.png)

* Un&#39;attività [Deduplication](../../automating/using/deduplication.md) che ti consente di identificare i duplicati derivanti dalla query precedente. In questo esempio viene salvato un solo record per ogni duplicato. I duplicati vengono identificati utilizzando l’indirizzo e-mail. Ciò significa che la consegna e-mail può essere inviata solo una volta per ogni indirizzo e-mail presente nel targeting.

   Il metodo di deduplicazione selezionato è **[!UICONTROL Non-empty value]**. Questo ti consente di garantire che tra i record conservati in caso di duplicati, sia data priorità a quelli in cui è stato fornito il **Nome**. Questo renderà più coerente l’utilizzo del nome nei campi di personalizzazione del contenuto dell’e-mail.

   Inoltre, viene aggiunta una transizione aggiuntiva per conservare i duplicati e per poterli elencare.

   ![](assets/deduplication_example_dedup.png)

* Una [consegna e-mail](../../automating/using/email-delivery.md) inserita dopo la transizione in uscita principale della deduplicazione.
* Un’attività [Save audience](../../automating/using/save-audience.md) inserita dopo la transizione aggiuntiva della deduplicazione per salvare i duplicati in un pubblico **Duplicati** . Questo pubblico può essere riutilizzato per escludere direttamente i suoi membri da ogni consegna e-mail.
