---
title: Modifica delle query
seo-title: Modifica delle query
description: Modifica delle query
seo-description: Creare una popolazione grazie ai filtri e alle regole predefiniti.
page-status-flag: never-activated
uuid: a 49 c 7739-a 96 c -45 cb -9 ac 5-1 ce 299161 a 97
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: filtering-data
discoiquuid: 84306 a 1 e -0 d 9 f -44 cc -88 a 7-36 d 7 e 5 b 4 da 1 f
context-tags: Queryfilter, overview; audience, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Editing queries{#editing-queries}

## About query editor {#about-query-editor}

L'editor query è una procedura guidata che consente di filtrare i dati contenuti nel database Adobe Campaign.

Questa funzione consente di creare una popolazione per un targeting migliore dei destinatari grazie ai filtri e alle regole predefiniti.

Diverse funzionalità dell'applicazione lo utilizzano per:

* Create **Query** type **audiences**
* Define **email** targets
* Define populations in **workflow** activities

## Query editor interface {#query-editor-interface}

The query editor is made up of a **Palette** and a **Workspace**.

![](assets/query_editor_overview.png)

### Palette {#palette}

La palette, posizionata sul lato sinistro dell'editor, è divisa in due schede che contengono elementi suddivisi in blocchi tematici. Queste schede sono:

* **Le scelte rapide**, per impostazione predefinita, oppure create dall'amministratore dell'istanza. Qui troverai campi, nodi, raggruppamenti, collegamenti 1-1, collegamenti 1-N e altri filtri predefiniti.
* **Esplora risorse** consente di accedere a tutti i campi disponibili nella risorsa di destinazione: nodi, elementi di raggruppamento, collegamenti (1-1 e 1-N).

Gli elementi contenuti nelle schede devono essere spostati nell'area di lavoro per essere configurati e presi in considerazione per la query. Depending on the targeting dimension selected (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)), you can:

* Selezione di tipi di pubblico o profili uno per uno
* Usare filtri predefiniti
* Definire regole semplici per i campi scelti
* Definire regole avanzate che consentono di applicare funzioni a determinati campi

### Workspace {#workspace}

L'area di lavoro è la zona centrale in cui potete configurare e combinare regole, tipi di pubblico e filtri predefiniti aggiunti dalla palette.

When you move an element from the palette into the workspace, a new window opens and you can start [Creating queries](../../automating/using/editing-queries.md#creating-queries).

## Creating queries {#creating-queries}

L'editor query può essere utilizzato per definire un'audience o eseguire il test del profilo in un messaggio, una popolazione in un flusso di lavoro e per creare un'audience di tipo «tipo di query».

Queries can be defined in the **[!UICONTROL Audience]** window while creating a delivery or in a **Query** activity while creating a workflow.

1. Spostare un elemento dalla palette nell'area di lavoro. Viene aperta la finestra per la modifica della regola.

   * For a string or numerical **field**, specify the comparison operator and the value.

      ![](assets/query_editor_audience_definition2.png)

   * For a date or date and time **field**, you can choose to define a specific date, a range between two dates, or a period relative to the query's execution date.

      ![](assets/query_editor_date_field.png)

   * For a Boolean **field**, check the boxes linked to the possible values for the field.
   * For a **grouping** field, select the grouping field on which you want to create the rule, then define the condition in the same way as for the other fields.

      ![](assets/query_editor_audience_definition4.png)

   * For a **1-1** link with another database resource, select a value directly from the table targeted.

      ![](assets/query_editor_audience_definition5.png)

   * For a **1-N** link with another database resource, you can define a sub-query on the fields of this second resource.

      Non è necessario specificare una condizione secondaria.

      For example, you can only select the **[!UICONTROL Exists]** operator on the profile tracking logs and approve the rule. La regola restituirà tutti i profili per i quali esistono i registri di tracciamento.

      ![](assets/query_editor_audience_definition6.png)

   * For a **predefined filter**, enter or select the elements you like according to the criteria offered.

      Gli amministratori possono creare filtri per facilitare query complesse e ripetitive. Queste vengono visualizzate nell'editor query sotto forma di regole pre-configurate e limitano il numero di passaggi necessari per eseguire l'utente.

      ![](assets/query-editor_filter_email-audience_filter.png)

1. Potete specificare un nome per la regola. Viene quindi visualizzato come nome della regola nell'area di lavoro. Se alla regola non viene assegnato un nome, viene visualizzata una descrizione automatica delle condizioni.
1. Per combinare gli elementi dell'area di lavoro, potete interblocgerli tra loro per creare gruppi e/o livelli di gruppo diversi. Potete quindi selezionare un operatore logico per combinare gli elementi sullo stesso livello:

   * **[!UICONTROL AND]**: un'intersezione di due criteri. Vengono presi in considerazione solo gli elementi che corrispondono a ciascun criterio.
   * **[!UICONTROL OR]**: un'unione di due criteri. Gli elementi che corrispondono ad almeno uno dei due criteri vengono considerati.
   * **[!UICONTROL EXCEPT]**: criteri di esclusione. Gli elementi che corrispondono al primo criterio vengono considerati a meno che non corrispondano al secondo criterio.

1. You can now calculate and preview the number of elements targeted by your query using the ![](assets/count.png) and ![](assets/preview.png) buttons from the action bar.

   ![](assets/query_editor_combining_rules.png)

Se desiderate modificare un elemento della query, fate clic sull'icona di modifica. La regola viene aperta in quanto era stata configurata in precedenza e potete quindi eseguire qualsiasi regolazione necessaria.

Le query sono ora create e definite, il che consente di creare una popolazione per personalizzare meglio le consegne.

**Argomenti correlati:**

* [Funzioni avanzate](../../automating/using/advanced-expression-editing.md)
* [Definizione dei filtri](../../developing/using/configuring-filter-definition.md)

