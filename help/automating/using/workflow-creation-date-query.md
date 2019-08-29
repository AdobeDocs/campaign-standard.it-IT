---
title: '" Esempio di utilizzo del flusso di lavoro: Creazione di consegne nella data di creazione del profilo "'
seo-title: '" Esempio di utilizzo del flusso di lavoro: Creazione di consegne nella data di creazione del profilo "'
description: '" Esempio di utilizzo del flusso di lavoro: Creazione di consegne nella data di creazione del profilo "'
seo-description: '" Esempio di utilizzo del flusso di lavoro: Creazione di consegne nella data di creazione del profilo "'
page-status-flag: never-activated
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: 'esecuzione-attività '
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: flusso di lavoro, casi d'uso, query
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f57775ec88925d43046fe4162f2753c189d50c62

---


# Caso d'uso flusso di lavoro: Creazione di consegne sulla data di creazione dei profili {#creation-date-query}

Puoi inviare un'offerta tramite e-mail all'anniversario della creazione del profilo del cliente.

1. In **[!UICONTROL Marketing Activities]**, fate clic **[!UICONTROL Create]** e selezionate **[!UICONTROL Workflow]**.
1. Selezionate **[!UICONTROL New Workflow]** il tipo di flusso di lavoro e fate clic **[!UICONTROL Next]** su.
1. Immettete le proprietà del flusso di lavoro e fate clic **[!UICONTROL Create]** su.

## Creazione di un'attività Pianificatore {#creating-a-scheduler-activity}

1. In **[!UICONTROL Activities]** &gt; **[!UICONTROL Execution]**, trascina e rilascia un **[!UICONTROL Scheduler activity]**![](assets/scheduler_icon.png).
1. Fate doppio clic sull'attività.
1. Configurare l'esecuzione della distribuzione.
1. In **[!UICONTROL Execution frequency]**, seleziona **[!UICONTROL Daily]**.
1. Seleziona un **[!UICONTROL Time]** e l' **[!UICONTROL Repetition frequency]** esecuzione del flusso di lavoro.
1. Selezionate una **[!UICONTROL Start]** data e **[!UICONTROL Expiration]** il flusso di lavoro.

>[!NOTE]
>
>Per avviare il flusso di lavoro in un determinato fuso orario, nella **[!UICONTROL Execution options]** scheda impostate il fuso orario per il pianificatore nel **[!UICONTROL Time zone]** campo.

![](assets/time_zone.png)

1. Confermate l'attività e salvate il flusso di lavoro.

## Creazione di un'attività query {#creating-a-query-activity}

1. Per selezionare i destinatari, trascinateli e **[!UICONTROL Query activity]** fate doppio clic.
1. Aggiungete **[!UICONTROL Profiles]** e selezionate **[!UICONTROL no longer contact by email]** con il valore **[!UICONTROL no]**.

### Recupero dei profili creati lo stesso giorno del giorno dell'esecuzione {#retriving-profiles-created-on-the-same-day}

1. In **[!UICONTROL Profile]**, trascina e rilascia il **[!UICONTROL Created]** campo. e fate clic **[!UICONTROL Advanced Mode]**su.
   ![](assets/advanced_mode.png)
1. In **[!UICONTROL list of functions]**, fate doppio clic **[!UICONTROL Day]** sul **[!UICONTROL Date]** nodo.
1. Quindi, inserite il campo **[!UICONTROL Created]** come argomento.
1. Selezionare **[!UICONTROL equals to (=)]** l'operatore.
1. Per Valore, selezionare **[!UICONTROL Day]** dal **[!UICONTROL Date]** nodo in **[!UICONTROL List of functions]**.
1. Inserire la **[!UICONTROL GetDate()]** funzione come argomento.

Avete recuperato i profili che la giornata di creazione è uguale al giorno corrente.

È necessario disporre di:

```Day(@created) = Day(GetDate())```

![](assets/day_creation_query.png)

Click **[!UICONTROL Confirm]**.

### Recupero dei profili creati lo stesso mese del mese di esecuzione{#retriving-profiles-created-on-the-same-month}

1. Nell **[!UICONTROL Query]** 'editor, selezionate la prima query e duplicatela.
1. Aprite il duplicato.
1. Sostituite **[!UICONTROL Day]** nella **[!UICONTROL Month]** query.
Si consiglia di:

``` Month(@created) = Month(GetDate()) ```

1. Click **[!UICONTROL Confirm]**.

![](assets/month_rule.png)

Viene visualizzata la query finale:

```Day(@created) = Day(GetDate()) AND Month(@created) = Month(GetDate())```

![](assets/expression_editor_1.png)

## Creazione di una consegna e-mail{#creating-an-email-delivery}

1. Trascina e rilascia una consegna tramite e-mail.
1. Fate clic sull'attività e ![](assets/edit_darkgrey-24px.png) selezionatela.
1. Selezionate **[!UICONTROL Recurring email]** e fate clic **[!UICONTROL Next]** su.
1. Selezionate un modello e-mail e fate clic **[!UICONTROL Next]** su.
1. Immettete le proprietà e-mail e fate clic **[!UICONTROL Next]** su.
1. Per creare il layout dell'e-mail, fai clic **[!UICONTROL Email Designer]** su.
1. Inserire elementi o selezionare un modello esistente.
1. Personalizzate l'e-mail utilizzando i campi e i collegamenti.
Per ulteriori informazioni, fare riferimento [alla progettazione di un messaggio e-mail](../../designing/using/about-email-content-design.md#designing-an-email-content-from-scratch).
1. Fate clic su **[!UICONTROL Preview]** per controllare il layout.
1. Click **[!UICONTROL Save]**.

**Argomenti correlati:**

* [Query](../../automating/using/query.md)
* [Pianificatore](../../automating/using/scheduler.md)
* [Consegna e-mail](../../automating/using/email-delivery.md)
* [Canale e-mail](../../channels/using/creating-an-email.md)
