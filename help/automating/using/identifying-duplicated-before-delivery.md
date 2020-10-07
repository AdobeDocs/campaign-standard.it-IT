---
title: Identificazione di duplicati prima di una consegna
description: L’esempio seguente illustra una deduplicazione che ti consente di escludere i duplicati di un target prima di inviare un’e-mail. Ciò significa che eviti di inviare una comunicazione diverse volte allo stesso profilo.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 78%

---


# Identificazione di duplicati prima di una consegna {#identifying-duplicates-before-a-delivery}

L’esempio seguente illustra una deduplicazione che ti consente di escludere i duplicati di un target prima di inviare un’e-mail. Ciò significa che eviti di inviare una comunicazione diverse volte allo stesso profilo.

Il flusso di lavoro è costituito da:

![](assets/deduplication_example_workflow.png)

* A [Query](../../automating/using/query.md) which allows you to define the target of the email. In questo caso, il flusso di lavoro esegue il targeting di tutti i profili di età compresa tra i 18 e i 25 anni presenti nel database dei clienti da oltre un anno.

   ![](assets/deduplication_example_query.png)

* A [Deduplication](../../automating/using/deduplication.md) activity, which allows you to identify the duplicates that come from the preceding query. In questo esempio viene salvato un solo record per ogni duplicato. I duplicati vengono identificati utilizzando l’indirizzo e-mail. Ciò significa che la consegna e-mail può essere inviata solo una volta per ogni indirizzo e-mail presente nel targeting.

   Il metodo di deduplicazione selezionato è **[!UICONTROL Non-empty value]**. Questo ti consente di garantire che tra i record conservati in caso di duplicati, sia data priorità a quelli in cui è stato fornito il **Nome**. Questo renderà più coerente l’utilizzo del nome nei campi di personalizzazione del contenuto dell’e-mail.

   Inoltre, viene aggiunta una transizione aggiuntiva per conservare i duplicati e per poterli elencare.

   ![](assets/deduplication_example_dedup.png)

* An [Email delivery](../../automating/using/email-delivery.md) placed after the main outbound transition of the deduplication.
* A [Save audience](../../automating/using/save-audience.md) activity placed after the additional transition of the deduplication to save the duplicates in a **Duplicates** audience. Questo pubblico può essere riutilizzato per escludere direttamente i suoi membri da ogni consegna e-mail.
