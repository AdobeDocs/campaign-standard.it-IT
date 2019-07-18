---
title: Query incrementali
seo-title: Query incrementali
description: Query incrementali
seo-description: L'attività query incrementale consente di filtrare ed estrarre una popolazione di elementi dal database Adobe Campaign.
page-status-flag: never-activated
uuid: 73 b 42422-e 815-43 ef -84 c 0-97 c 4433 ccc 98
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: targeting-activity
discoiquuid: 80961 e 73-42 ec -463 a -8496-cff 69 fab 0475
context-tags: incremental, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 15bba7a6f76cbd17b07f1243075da0832619278b

---


# Incremental query{#incremental-query}

## Description {#description}

![](assets/incremental.png)

The **[!UICONTROL Incremental query]** activity allows you to filter and extract a population of elements from the Adobe Campaign database. Ogni volta che questa attività viene eseguita, i risultati delle esecuzioni precedenti sono esclusi. In questo modo potete eseguire il targeting solo di nuovi elementi.

You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. Questi dati sono memorizzati in colonne aggiuntive e possono essere utilizzati solo per il flusso di lavoro in corso.

L'attività utilizza lo strumento di modifica query. This tool is detailed in a [dedicated section](../../automating/using/editing-queries.md#about-query-editor).

## Context of use {#context-of-use}

An **[!UICONTROL Incremental query]** has to be linked to a **[!UICONTROL Scheduler]** in order to define the execution frequency of the workflow, and therefore the query.

The **[!UICONTROL Processed data]** tab, which is specific to this activity, allows you to view any results of the activity's previous executions, if required.

The **[!UICONTROL Incremental query]** activity can be used for various types of uses:

* Segmentazione della destinazione di messaggi, audience e così via
* Esportazione dei dati.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Incremental query]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If you would like to run a query on a resource other than the profile resource, go to the activity's **[!UICONTROL Properties]** tab and select a **[!UICONTROL Resource]** and a **[!UICONTROL Targeting dimension]**.

   The **[!UICONTROL Resource]** allows you to refine the filters displayed in the palette whereas the **[!UICONTROL Targeting dimension]**, contextual with regard to the resource selected, corresponds to the type of population that you would like to obtain (identified profiles, deliveries, data linked to the selected resource, etc.).

1. In the **[!UICONTROL Target]** tab, run your query by defining and combining rules.
1. In the **[!UICONTROL Processed data]** tab, choose the incremental mode you want to use for the next executions of the workflow:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: i risultati delle esecuzioni precedenti per ogni nuova esecuzione sono esclusi.
   * **[!UICONTROL Use a date field]**: le esecuzioni successive prendono in considerazione solo i risultati che hanno il campo data selezionato maggiore o uguale all'ultima data di esecuzione dell **[!UICONTROL Incremental query]** 'attività. You can select any date field pertaining to the resource selected in the **[!UICONTROL Properties]** tab. Questa modalità offre prestazioni migliori durante la query di risorse di grandi dimensioni come i dati del registro.

      Dopo la prima esecuzione del flusso di lavoro, puoi vedere in questa scheda l'ultima data di esecuzione che verrà utilizzata per l'esecuzione successiva. Viene aggiornato automaticamente ogni volta che il flusso di lavoro viene eseguito. È comunque possibile ignorare questo valore immettendo manualmente un nuovo elemento in modo da adattarlo alle proprie esigenze.
   >[!NOTE]
   >
   >The **[!UICONTROL Use a date field]** mode allows more flexibility depending on the date field that is selected. Ad esempio, se il campo selezionato corrisponde a una data di modifica, la modalità campo data consentirà di recuperare dati aggiornati di recente, mentre l'altro metodo escluderà semplicemente le registrazioni già impostate come destinazione in un'esecuzione precedente, anche se sono state modificate dall'ultima esecuzione del flusso di lavoro.

   ![](assets/incremental_query_usedatefield.png)

1. You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. Questi dati sono memorizzati in colonne aggiuntive e possono essere utilizzati solo per il flusso di lavoro in corso. In particolare, puoi aggiungere dati dalle tabelle di database di Adobe Campaign collegate alla dimensione di targeting della query. Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Enriching data {#enriching-data}

Just as for a query, you can enrich the data from an **[!UICONTROL Incremental query]**. Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

## Example: incremental query on subscribers to a service {#example--incremental-query-on-subscribers-to-a-service}

The following example shows the configuration of an **[!UICONTROL Incremental query]** activity which filters the profiles in the Adobe Campaign database that are subscribed to the **Running Newsletter** service, to send them a welcome email containing a promo code.

Il flusso di lavoro è costituito dai seguenti elementi:

![](assets/incremental_query_example1.png)

* A **[!UICONTROL Scheduler]** activity, to execute the workflow every Monday at 7 am.

   ![](assets/incremental_query_example2.png)

* An **[!UICONTROL Incremental query]** activity, which targets all of the current subscribers during the first execution, then only the new subscribers of that week during the following executions.

   ![](assets/incremental_query_example3.png)

* An **[!UICONTROL Email delivery]** activity. Il flusso di lavoro viene eseguito una volta alla settimana, ma è possibile aggregare le e-mail inviate e i risultati al mese, ad esempio per generare rapporti per un periodo di un mese intero e non per una sola settimana.

   To do this, choose to create a **[!UICONTROL Recurring email]** here regrouping the emails and the results **[!UICONTROL By month]**.

   Definite il contenuto dell'e-mail e inserite il codice promozionale di benvenuto.

   For more on this, refer to the [Email delivery](../../automating/using/email-delivery.md) and [Defining email content](../../designing/using/about-personalization.md) sections.

Quindi avviate l'esecuzione del flusso di lavoro. Ogni settimana i nuovi abbonati riceveranno il messaggio e-mail di benvenuto con il codice promozionale.

## Example: incremental query on delivery logs {#example--incremental-query-on-delivery-logs}

You can use an **[!UICONTROL Incremental query]** activity to regularly export new logs in files. Può essere utile ad esempio per utilizzare i dati del registro in reporting esterni o strumenti BI.

A complete example is available in the [Exporting logs](../../automating/using/exporting-logs.md) section.
