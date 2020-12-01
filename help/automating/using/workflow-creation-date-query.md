---
solution: Campaign Standard
product: campaign
title: Creazione di consegne alla data di creazione del profilo
description: Questo caso di utilizzo mostra come creare consegne alla data di creazione del profilo.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: workflow,use-case,query
translation-type: tm+mt
source-git-commit: 45c80b5e6bf2169c5acf6eea70da9e2f130982c8
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

1. In **[!UICONTROL Activities]** > **[!UICONTROL Execution]**, trascinare un&#39;attività [Scheduler](../../automating/using/scheduler.md).
1. Fai doppio clic sull’attività.
1. Configura l’esecuzione della consegna.
1. In **[!UICONTROL Execution frequency]**, seleziona **[!UICONTROL Daily]**.
1. Selezionare un **[!UICONTROL Time]** e **[!UICONTROL Repetition frequency]** di esecuzione per il flusso di lavoro.
1. Selezionare una data **[!UICONTROL Start]** e **[!UICONTROL Expiration]** per il flusso di lavoro.
1. Conferma l’attività e salva il flusso di lavoro.

>[!NOTE]
>
>Per avviare il flusso di lavoro in un fuso orario specifico, nella scheda **[!UICONTROL Execution options]** impostare il fuso orario per il pianificatore nel campo **[!UICONTROL Time zone]**. Per impostazione predefinita, il fuso orario selezionato è quello definito nelle proprietà del flusso di lavoro (vedi [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)).

![](assets/time_zone.png)

## Creazione di un’attività query {#creating-a-query-activity}

1. Per selezionare i destinatari, trascinate un&#39;attività [Query](../../automating/using/query.md) e fate doppio clic su di essa.
1. Aggiungete **[!UICONTROL Profiles]** e selezionate **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL no]**.

### Recupero dei profili creati lo stesso giorno del giorno di esecuzione {#retrieving-profiles-created-on-the-same-day}

1. In **[!UICONTROL Profile]**, trascinare e rilasciare il campo **[!UICONTROL Created]**. e fare clic su **[!UICONTROL Advanced Mode]**.
   ![](assets/advanced_mode.png)
1. In **[!UICONTROL list of functions]**, fare doppio clic su **[!UICONTROL Day]** dal nodo **[!UICONTROL Date]**.
1. Quindi, inserire il campo **[!UICONTROL Created]** come argomento.
1. Selezionare **[!UICONTROL equals to (=)]** come operatore.
1. Per Valore, selezionare **[!UICONTROL Day]** dal nodo **[!UICONTROL Date]** in **[!UICONTROL List of functions]**.
1. Inserire la funzione **[!UICONTROL GetDate()]** come argomento.

Hai recuperato i profili il giorno di creazione corrispondente al giorno corrente.

Dovreste finire con:

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Fai clic su **[!UICONTROL Confirm]**.

### Recupero dei profili creati lo stesso mese del mese di esecuzione{#retrieving-profiles-created-on-the-same-month}

1. Nell&#39;editor **[!UICONTROL Query]**, selezionate la prima query e duplicatela.
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

1. Trascinare un&#39;attività [Invio e-mail](../../automating/using/email-delivery.md).
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
