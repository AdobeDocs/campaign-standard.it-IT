---
solution: Campaign Standard
product: campaign
title: Identificazione di duplicati prima di una consegna
description: L’esempio seguente illustra una deduplicazione che ti consente di escludere i duplicati di un target prima di inviare un’e-mail. Ciò significa che eviti di inviare una comunicazione diverse volte allo stesso profilo.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 78%

---


# Identificazione di duplicati prima di una consegna {#identifying-duplicates-before-a-delivery}

L’esempio seguente illustra una deduplicazione che ti consente di escludere i duplicati di un target prima di inviare un’e-mail. Ciò significa che eviti di inviare una comunicazione diverse volte allo stesso profilo.

Il flusso di lavoro è costituito da:

![](assets/deduplication_example_workflow.png)

* Una [Query](../../automating/using/query.md) che consente di definire la destinazione dell&#39;e-mail. In questo caso, il flusso di lavoro esegue il targeting di tutti i profili di età compresa tra i 18 e i 25 anni presenti nel database dei clienti da oltre un anno.

   ![](assets/deduplication_example_query.png)

* Un&#39;attività [Deduplicazione](../../automating/using/deduplication.md) che consente di identificare i duplicati derivanti dalla query precedente. In questo esempio viene salvato un solo record per ogni duplicato. I duplicati vengono identificati utilizzando l’indirizzo e-mail. Ciò significa che la consegna e-mail può essere inviata solo una volta per ogni indirizzo e-mail presente nel targeting.

   Il metodo di deduplicazione selezionato è **[!UICONTROL Non-empty value]**. Questo ti consente di garantire che tra i record conservati in caso di duplicati, sia data priorità a quelli in cui è stato fornito il **Nome**. Questo renderà più coerente l’utilizzo del nome nei campi di personalizzazione del contenuto dell’e-mail.

   Inoltre, viene aggiunta una transizione aggiuntiva per conservare i duplicati e per poterli elencare.

   ![](assets/deduplication_example_dedup.png)

* Una [distribuzione di posta elettronica](../../automating/using/email-delivery.md) inserita dopo la transizione in uscita principale della deduplicazione.
* Un&#39;attività [Save audience](../../automating/using/save-audience.md) inserita dopo l&#39;ulteriore transizione della deduplicazione per salvare i duplicati in un pubblico **Duplicates**. Questo pubblico può essere riutilizzato per escludere direttamente i suoi membri da ogni consegna e-mail.
