---
title: Query incrementale per gli abbonati a un servizio
description: L’esempio seguente illustra come configurare un’attività Incremental query per filtrare gli abbonati a un servizio.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c80ed1f6-ad8a-4448-a6df-b9881327228a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 61%

---

# Query incrementale per gli abbonati a un servizio {#example--incremental-query-on-subscribers-to-a-service}

L’esempio seguente mostra la configurazione di un’attività **[!UICONTROL Incremental query]** che filtra i profili abbonati al servizio **Running Newsletter** nel database di Adobe Campaign, al fine di inviare loro un messaggio e-mail di benvenuto contenente un codice promozionale.

Il flusso di lavoro è costituito dai seguenti elementi:

![](assets/incremental_query_example1.png)

* A [Scheduler](../../automating/using/scheduler.md) per eseguire il flusso di lavoro ogni lunedì alle 6.

  ![](assets/incremental_query_example2.png)

* Un [Query incrementale](../../automating/using/incremental-query.md) attività, che esegue il targeting per tutti gli abbonati correnti durante la prima esecuzione, quindi solo per i nuovi abbonati della settimana durante le esecuzioni successive.

  ![](assets/incremental_query_example3.png)

* Un [Consegna e-mail](../../automating/using/email-delivery.md) attività. Il flusso di lavoro viene eseguito una volta alla settimana, ma puoi aggregare le e-mail inviate e i risultati per mese, ad esempio per generare report per un periodo di un mese intero e non per una sola settimana.

  A tale scopo, scegli di creare una **[!UICONTROL Recurring email]** che raggruppa le e-mail e i risultati **[!UICONTROL By month]**.

  Definisci il contenuto dell’e-mail e inserisci il codice promozionale di benvenuto. Per ulteriori informazioni, consulta [Definizione del contenuto delle e-mail](../../designing/using/personalization.md) sezioni.

Quindi avvia l’esecuzione del flusso di lavoro. Ogni settimana i nuovi abbonati riceveranno l’e-mail di benvenuto con il codice promozionale.
