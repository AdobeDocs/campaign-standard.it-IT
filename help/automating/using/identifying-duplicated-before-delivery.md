---
title: Identificazione di duplicati prima di una consegna
description: L’esempio seguente illustra una deduplicazione che ti consente di escludere i duplicati di un target prima di inviare un’e-mail. Ciò significa che eviti di inviare una comunicazione diverse volte allo stesso profilo.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: a09b101b-f76f-4377-9854-1fcffaad4f9a
TQID: 'https://experienceleague.adobe.com/4t0TujgM3kHTT36-Gy2lmiVQIRMy3OeChAw-Xx5MnWY'
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
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 79%
---
# Identificazione di duplicati prima di una consegna {#identifying-duplicates-before-a-delivery}

L’esempio seguente illustra una deduplicazione che ti consente di escludere i duplicati di un target prima di inviare un’e-mail. Ciò significa che eviti di inviare una comunicazione diverse volte allo stesso profilo.

Il flusso di lavoro è costituito da:

![](assets/deduplication_example_workflow.png)

* Una [Query](../../automating/using/query.md) che ti consente di definire la destinazione dell&#39;e-mail. In questo caso, il flusso di lavoro esegue il targeting di tutti i profili di età compresa tra i 18 e i 25 anni presenti nel database dei clienti da oltre un anno.

  ![](assets/deduplication_example_query.png)

* Un&#39;attività [Deduplication](../../automating/using/deduplication.md), che ti consente di identificare i duplicati provenienti dalla query precedente. In questo esempio viene salvato un solo record per ogni duplicato. I duplicati vengono identificati utilizzando l’indirizzo e-mail. Ciò significa che la consegna e-mail può essere inviata solo una volta per ogni indirizzo e-mail presente nel targeting.

  Il metodo di deduplicazione selezionato è **[!UICONTROL Non-empty value]**. Questo ti consente di garantire che tra i record conservati in caso di duplicati, sia data priorità a quelli in cui è stato fornito il **Nome**. Questo renderà più coerente l’utilizzo del nome nei campi di personalizzazione del contenuto dell’e-mail.

  Inoltre, viene aggiunta una transizione aggiuntiva per conservare i duplicati e per poterli elencare.

  ![](assets/deduplication_example_dedup.png)

* Una [consegna e-mail](../../automating/using/email-delivery.md) effettuata dopo la transizione in uscita principale della deduplicazione.
* Un&#39;attività [Save audience](../../automating/using/save-audience.md) inserita dopo la transizione aggiuntiva della deduplicazione per salvare i duplicati in un pubblico **Duplicates**. Questo pubblico può essere riutilizzato per escludere direttamente i suoi membri da ogni consegna e-mail.
