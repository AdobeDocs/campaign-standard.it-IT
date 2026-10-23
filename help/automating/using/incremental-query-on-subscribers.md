---
title: Query incrementale per gli abbonati a un servizio
description: L’esempio seguente illustra come configurare un’attività Incremental query per filtrare gli abbonati a un servizio.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: c80ed1f6-ad8a-4448-a6df-b9881327228a
TQID: 'https://experienceleague.adobe.com/MHB1ETCecN9gQq51bSii-keTyFaYof0JtAyckFSCKQE'
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
source-wordcount: '212'
ht-degree: 61%
---
# Query incrementale per gli abbonati a un servizio {#example--incremental-query-on-subscribers-to-a-service}

L’esempio seguente mostra la configurazione di un’attività **[!UICONTROL Incremental query]** che filtra i profili abbonati al servizio **Running Newsletter** nel database di Adobe Campaign, al fine di inviare loro un messaggio e-mail di benvenuto contenente un codice promozionale.

Il flusso di lavoro è costituito dai seguenti elementi:

![](assets/incremental_query_example1.png)

* Un&#39;attività [Scheduler](../../automating/using/scheduler.md), per eseguire il flusso di lavoro ogni lunedì alle 6.

  ![](assets/incremental_query_example2.png)

* Un&#39;attività [Incremental query](../../automating/using/incremental-query.md), che esegue il targeting per tutti i sottoscrittori correnti durante la prima esecuzione, quindi solo per i nuovi sottoscrittori della settimana durante le esecuzioni successive.

  ![](assets/incremental_query_example3.png)

* Un&#39;attività [Email delivery](../../automating/using/email-delivery.md). Il flusso di lavoro viene eseguito una volta alla settimana, ma puoi aggregare le e-mail inviate e i risultati per mese, ad esempio per generare report per un periodo di un mese intero e non per una sola settimana.

  A tale scopo, scegli di creare una **[!UICONTROL Recurring email]** che raggruppa le e-mail e i risultati **[!UICONTROL By month]**.

  Definisci il contenuto dell’e-mail e inserisci il codice promozionale di benvenuto. Per ulteriori informazioni, consulta le sezioni [Definizione del contenuto delle e-mail](../../designing/using/personalization.md).

Quindi avvia l’esecuzione del flusso di lavoro. Ogni settimana i nuovi abbonati riceveranno l’e-mail di benvenuto con il codice promozionale.
