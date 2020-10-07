---
title: Query incrementale per gli abbonati a un servizio
description: Nell'esempio seguente viene illustrato come configurare un'attività di query incrementale per filtrare gli abbonati a un servizio.
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 67%

---


# Query incrementale per gli abbonati a un servizio {#example--incremental-query-on-subscribers-to-a-service}

L’esempio seguente mostra la configurazione di un’attività **[!UICONTROL Incremental query]** che filtra i profili abbonati al servizio **Running Newsletter** nel database di Adobe Campaign, al fine di inviare loro un messaggio e-mail di benvenuto contenente un codice promozionale.

Il flusso di lavoro è costituito dai seguenti elementi:

![](assets/incremental_query_example1.png)

* A [Scheduler](../../automating/using/scheduler.md) activity, to execute the workflow every Monday at 6 am.

   ![](assets/incremental_query_example2.png)

* An [Incremental query](../../automating/using/incremental-query.md) activity, which targets all of the current subscribers during the first execution, then only the new subscribers of that week during the following executions.

   ![](assets/incremental_query_example3.png)

* Un&#39;attività di consegna [tramite e-](../../automating/using/email-delivery.md) mail. Il flusso di lavoro viene eseguito una volta alla settimana, ma puoi aggregare le e-mail inviate e i risultati per mese, ad esempio per generare report per un periodo di un mese intero e non per una sola settimana.

   A tale scopo, scegli di creare una **[!UICONTROL Recurring email]** che raggruppa le e-mail e i risultati **[!UICONTROL By month]**.

   Definisci il contenuto dell’e-mail e inserisci il codice promozionale di benvenuto. For more on this, refer to [Defining email content](../../designing/using/personalization.md) sections.

Quindi avvia l’esecuzione del flusso di lavoro. Ogni settimana i nuovi abbonati riceveranno l’e-mail di benvenuto con il codice promozionale.
