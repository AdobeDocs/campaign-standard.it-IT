---
title: Query incrementale sugli abbonati a un servizio
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# Query incrementale sugli abbonati a un servizio {#example--incremental-query-on-subscribers-to-a-service}

L&#39;esempio seguente mostra la configurazione di un&#39; **[!UICONTROL Incremental query]** attività che filtra i profili nel database del Adobe Campaign  sottoscritti al servizio Newsletter **in** esecuzione, per inviare loro un messaggio e-mail di benvenuto contenente un codice promozionale.

Il flusso di lavoro è costituito dai seguenti elementi:

![](assets/incremental_query_example1.png)

* Un&#39;attività [Scheduler](../../automating/using/scheduler.md) , per eseguire il flusso di lavoro ogni lunedì alle 6.

   ![](assets/incremental_query_example2.png)

* Un&#39;attività di query [](../../automating/using/incremental-query.md) incrementale, che si rivolge a tutti gli utenti correnti durante la prima esecuzione, quindi solo ai nuovi sottoscrittori della settimana durante le seguenti esecuzioni.

   ![](assets/incremental_query_example3.png)

* Un&#39;attività di consegna [tramite e-](../../automating/using/email-delivery.md) mail. Il flusso di lavoro viene eseguito una volta alla settimana, ma potete aggregare i messaggi e-mail inviati e i risultati mensili, ad esempio per generare rapporti su un periodo di un intero mese e non solo una settimana.

   A questo scopo, scegliete di creare una **[!UICONTROL Recurring email]** struttura che raggruppa le e-mail e i risultati **[!UICONTROL By month]**.

   Definite il contenuto dell&#39;e-mail e inserite il codice promozionale di benvenuto. Per ulteriori informazioni, consulta [Definizione delle sezioni relative al contenuto](../../designing/using/personalization.md) delle e-mail.

Quindi avviate l&#39;esecuzione del flusso di lavoro. Ogni settimana i nuovi abbonati riceveranno l&#39;e-mail di benvenuto con il codice promozionale.
