---
title: Creazione di consegne alla data di creazione del profilo
description: Questo caso di utilizzo mostra come creare consegne alla data di creazione del profilo.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 38%

---


# Creazione di consegne nella data di creazione dei profili {#creation-date-query}

Potete inviare un&#39;offerta via e-mail in occasione dell&#39;anniversario della creazione del profilo del cliente.

1. In **[!UICONTROL Marketing Activities]**, fai clic su **[!UICONTROL Create]** e seleziona **[!UICONTROL Workflow]**.
1. Seleziona **[!UICONTROL New Workflow]** come tipo di flusso di lavoro e fai clic su **[!UICONTROL Next]**.
1. Inserisci le proprietà del flusso di lavoro e fai clic su **[!UICONTROL Create]**.

## Creazione di un’attività Scheduler {#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, drag and drop a [Scheduler](../../automating/using/scheduler.md) activity.
1. Fai doppio clic sull’attività.
1. Configura l’esecuzione della consegna.
1. In **[!UICONTROL Execution frequency]**, seleziona **[!UICONTROL Daily]**.
1. Selezionate un **[!UICONTROL Time]** e l’ **[!UICONTROL Repetition frequency]** esecuzione del flusso di lavoro.
1. Seleziona una **[!UICONTROL Start]** data e **[!UICONTROL Expiration]** il flusso di lavoro.
1. Conferma l’attività e salva il flusso di lavoro.

>[!NOTE]
>
>To start your workflow at a specific time zone, in the **[!UICONTROL Execution options]** tab, set up the time zone for your scheduler in the **[!UICONTROL Time zone]** field. Per impostazione predefinita, il fuso orario selezionato è quello definito nelle proprietà del flusso di lavoro (vedi [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)).

![](assets/time_zone.png)

## Creazione di un’attività query {#creating-a-query-activity}

1. To select recipients, drag and drop a [Query](../../automating/using/query.md) activity and double-click it.
1. Aggiungete **[!UICONTROL Profiles]** e selezionate **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL no]**.

### Profili di ripristino creati lo stesso giorno dell&#39;esecuzione {#retriving-profiles-created-on-the-same-day}

1. In **[!UICONTROL Profile]**, trascinare il **[!UICONTROL Created]** campo. e fate clic su **[!UICONTROL Advanced Mode]**.
   ![](assets/advanced_mode.png)
1. In **[!UICONTROL list of functions]**, fare doppio clic **[!UICONTROL Day]** dal **[!UICONTROL Date]** nodo.
1. Quindi, inserire il campo **[!UICONTROL Created]** come argomento.
1. Select **[!UICONTROL equals to (=)]** as the operator.
1. Per Valore, selezionate **[!UICONTROL Day]** dal **[!UICONTROL Date]** nodo nella **[!UICONTROL List of functions]**.
1. Inserire la **[!UICONTROL GetDate()]** funzione come argomento.

Hai recuperato i profili il giorno di creazione corrispondente al giorno corrente.

Dovreste finire con:

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Fai clic su **[!UICONTROL Confirm]**.

### Profili di ripristino creati lo stesso mese del mese di esecuzione{#retriving-profiles-created-on-the-same-month}

1. Nell’ **[!UICONTROL Query]** editor, selezionate la prima query e duplicatela.
1. Aprite il duplicato.
1. Sostituire **[!UICONTROL Day]** con **[!UICONTROL Month]** nella query.
1. Fai clic su **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

Dovreste finire con questo:

``` Month(@created) = Month(GetDate()) ```

Viene visualizzata la query finale:

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Creazione di una consegna e-mail{#creating-an-email-delivery}

1. Trascinate e rilasciate un&#39;attività di consegna [tramite](../../automating/using/email-delivery.md) e-mail.
1. Fai clic sull’attività e seleziona ![](assets/edit_darkgrey-24px.png) per modificarla.
1. Seleziona **[!UICONTROL Recurring email]** e fai clic su **[!UICONTROL Next]**.
1. Seleziona un modello di e-mail e fai clic su **[!UICONTROL Next]**.
1. Immetti le proprietà dell’e-mail e fai clic su **[!UICONTROL Next]**.
1. Per creare il layout dell’e-mail, fai clic su **[!UICONTROL Email Designer]**.
1. Inserisci elementi o seleziona un modello esistente.
1. Personalizza il messaggio e-mail utilizzando campi e collegamenti.
Per ulteriori informazioni, consulta [progettazione di un’e-mail](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Seleziona **[!UICONTROL Preview]** per controllare il layout.
1. Fai clic su **[!UICONTROL Save]**.

**Argomenti correlati:**

* [Canale e-mail](../../channels/using/creating-an-email.md)
