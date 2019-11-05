---
title: Modifica delle query
description: Creare una popolazione grazie ai filtri e alle regole predefiniti.
page-status-flag: mai attivato
uuid: a49c7739-a96c-45cb-9ac5-1ce299161a97
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: filter-data
discoiquuid: 84306a1e-0d9f-44cc-88a7-36d7e5b4da1f
context-tags: queryFilter,panoramica;audience,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Modifica delle query{#editing-queries}

## Informazioni sull'editor query {#about-query-editor}

L'editor di query è una procedura guidata che consente di filtrare i dati contenuti nel database Adobe Campaign.

Questa funzione consente di creare una popolazione con obiettivi migliori per i destinatari grazie ai filtri e alle regole predefiniti.

Diverse funzionalità dell'applicazione la utilizzano per:

* Creare **tipi di** pubblico di tipo Query ****
* Definizione delle destinazioni **e-mail**
* Definizione delle popolazioni nelle attività del **flusso di lavoro**

## Interfaccia editor query {#query-editor-interface}

L’editor di query è composto da una **palette** e da un’ **area di lavoro**.

![](assets/query_editor_overview.png)

### Palette {#palette}

La palette, situata a sinistra dell'editor, è divisa in due schede, che contengono elementi suddivisi in blocchi tematici. Le seguenti schede sono:

* Le **scelte rapide**, disponibili per impostazione predefinita, o create dall'amministratore di istanza. Qui troverete campi, nodi, raggruppamenti, 1-1 collegamenti, 1-N collegamenti e altri filtri predefiniti.
* In **Esplora risorse** è possibile accedere a tutti i campi disponibili nella risorsa di destinazione: nodi, elementi di raggruppamento, collegamenti (1-1 e 1-N).

Gli elementi contenuti nelle schede devono essere spostati nell'area di lavoro per essere configurati e presi in considerazione per la query. A seconda della dimensione di targeting selezionata (consultate Dimensioni e risorse [di](../../automating/using/query.md#targeting-dimensions-and-resources)targeting), potete:

* Selezione di audience o profili uno per uno
* Usa filtri predefiniti
* Definizione di regole semplici per i campi selezionati
* Definizione di regole avanzate che consentono di applicare funzioni a determinati campi

### Area di lavoro {#workspace}

L'area di lavoro è l'area centrale in cui è possibile configurare e combinare regole, audience e filtri predefiniti aggiunti dalla palette.

Quando si sposta un elemento dalla palette nell'area di lavoro, si apre una nuova finestra e si può iniziare a [creare query](#creating-queries).

## Creazione di query {#creating-queries}

L'editor di query può essere utilizzato per definire un'audience o un profilo di test in un messaggio, una popolazione in un flusso di lavoro e per creare un'audience di tipo query.

Le query possono essere definite nella **[!UICONTROL Audience]** finestra durante la creazione di una consegna o in un'attività **Query** durante la creazione di un flusso di lavoro.

1. Spostare un elemento dalla palette nell'area di lavoro. Viene visualizzata la finestra per la modifica della regola.

   * Per una stringa o un **campo** numerico, specificare l'operatore di confronto e il valore.

      ![](assets/query_editor_audience_definition2.png)

   * Per un **campo** data o data e ora, è possibile scegliere di definire una data specifica, un intervallo tra due date o un periodo relativo alla data di esecuzione della query.

      ![](assets/query_editor_date_field.png)

   * Per un **campo** booleano, selezionare le caselle collegate ai possibili valori del campo.
   * Per un campo di **raggruppamento** , selezionate il campo di raggruppamento in cui desiderate creare la regola, quindi definite la condizione nello stesso modo degli altri campi.

      ![](assets/query_editor_audience_definition4.png)

   * Per un collegamento **1-1** con un'altra risorsa di database, selezionate un valore direttamente dalla tabella di destinazione.

      ![](assets/query_editor_audience_definition5.png)

   * Per un collegamento **1-N** con un'altra risorsa del database, potete definire una sottoquery sui campi di questa seconda risorsa.

      Non è necessario specificare una condizione secondaria.

      Ad esempio, è possibile selezionare l' **[!UICONTROL Exists]** operatore solo nei registri di tracciamento del profilo e approvare la regola. La regola restituirà tutti i profili per i quali esistono dei registri di tracciamento.

      ![](assets/query_editor_audience_definition6.png)

   * Per un filtro **** predefinito, inserite o selezionate gli elementi desiderati in base ai criteri offerti.

      Gli amministratori possono creare filtri per facilitare query complesse e ripetitive. Questi vengono visualizzati nell'editor di query sotto forma di regole preconfigurate e limitano il numero di passaggi necessari all'utente.

      ![](assets/query-editor_filter_email-audience_filter.png)

1. È possibile specificare un nome per la regola. Viene quindi visualizzato come nome della regola nell’area di lavoro. Se alla regola non viene assegnato un nome, viene visualizzata una descrizione automatica delle condizioni.
1. Per combinare gli elementi dell’area di lavoro, potete unirli per creare diversi gruppi e/o livelli di gruppo. È quindi possibile selezionare un operatore logico per combinare elementi sullo stesso livello:

   * **[!UICONTROL AND]**: un'intersezione di due criteri. Vengono presi in considerazione solo gli elementi che corrispondono a ciascun criterio.
   * **[!UICONTROL OR]**: un'unione di due criteri. Vengono presi in considerazione gli elementi che corrispondono ad almeno uno dei due criteri.
   * **[!UICONTROL EXCEPT]**: criteri di esclusione. Gli elementi che corrispondono al primo criterio sono presi in considerazione a meno che non corrispondano anche al secondo criterio.

1. È ora possibile calcolare e visualizzare in anteprima il numero di elementi interessati dalla query utilizzando i ![](assets/count.png) pulsanti e della barra delle azioni ![](assets/preview.png) .

   ![](assets/query_editor_combining_rules.png)

Se desiderate modificare un elemento della query, fate clic sull'icona di modifica. La regola viene aperta così come era stata configurata in precedenza e potete quindi eseguire tutte le regolazioni necessarie.

Le query vengono ora create e definite, in modo da creare una popolazione in grado di personalizzare meglio le consegne.

**Argomenti correlati:**

* [Funzioni avanzate](../../automating/using/advanced-expression-editing.md)
* [Definizione dei filtri](../../developing/using/configuring-filter-definition.md)
* [Caso di utilizzo: Creare una consegna di e-mail una volta alla settimana](../../automating/using/workflow-weekly-offer.md)
* [Caso di utilizzo: Creazione di una consegna segmentata sulla posizione](../../automating/using/workflow-segmentation-location.md)
* [Caso di utilizzo: Creazione di consegne con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso di utilizzo: Flusso di lavoro di retargeting che invia una nuova consegna a non-openers](../../automating/using/workflow-cross-channel-retargeting.md)
