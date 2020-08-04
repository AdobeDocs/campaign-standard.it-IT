---
title: Modifica delle query
description: Genera una popolazione grazie ai filtri e alle regole preimpostati.
page-status-flag: never-activated
uuid: a49c7739-a96c-45cb-9ac5-1ce299161a97
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: filtering-data
discoiquuid: 84306a1e-0d9f-44cc-88a7-36d7e5b4da1f
context-tags: queryFilter,overview;audience,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '782'
ht-degree: 100%

---


# Modifica delle query{#editing-queries}

## Informazioni sull’editor delle query {#about-query-editor}

L’editor delle query è una procedura guidata che ti consente di filtrare i dati contenuti nel database di Adobe Campaign.

Questa funzione ti consente di generare una popolazione con obiettivi migliori per i destinatari grazie ai filtri e alle regole preimpostati.

Diverse funzionalità dell’applicazione la utilizzano per:

* Creare **tipi di pubblico** di tipo **Query**
* Definire i target delle **e-mail**
* Definire le popolazioni nelle attività del **flusso di lavoro**

## Interfaccia dell’editor delle query {#query-editor-interface}

L’editor delle query è composto da una **palette** e da un’**area di lavoro**.

![](assets/query_editor_overview.png)

### Palette {#palette}

La palette, situata a sinistra dell’editor, è divisa in due schede, che contengono elementi suddivisi in blocchi tematici. Queste schede sono:

* Le **Shortcuts**, disponibili per impostazione predefinita o create dall’amministratore dell’istanza. Qui trovi campi, nodi, raggruppamenti, collegamenti 1-1, collegamenti 1-N e altri filtri preimpostati.
* L’**Explorer**, che ti consente di accedere a tutti i campi disponibili nella risorsa target: nodi, elementi di raggruppamento, collegamenti (1-1 e 1-N).

È necessario spostare nell’area di lavoro gli elementi contenuti nelle schede per configurarli e prenderli in considerazione per la query. A seconda della dimensione di targeting selezionata (consulta [Dimensioni di targeting e risorse](../../automating/using/query.md#targeting-dimensions-and-resources)), puoi:

* Selezionare tipi di pubblico o profili uno per uno;
* Usare filtri preimpostati
* Definire regole semplici per i campi selezionati
* Definire regole avanzate che ti consentono di applicare funzioni a determinati campi

### Area di lavoro {#workspace}

L’area di lavoro è l’area centrale dove puoi configurare e combinare regole, tipi di pubblico e filtri preimpostati aggiunti dalla palette.

Quando si sposta un elemento dalla palette nell’area di lavoro, viene visualizzata una nuova finestra e puoi iniziare la [Creazione delle query](#creating-queries).

## Creazione delle query {#creating-queries}

Puoi utilizzare l’editor delle query per definire un pubblico o un profilo di test in un messaggio, una popolazione in un flusso di lavoro e per creare un pubblico di tipo query.

È possibile definire le query nella finestra **[!UICONTROL Audience]** durante la creazione di una consegna o in un’attività **Query** durante la creazione di un flusso di lavoro.

1. Sposta un elemento dalla palette nell’area di lavoro. Viene visualizzata la finestra per modificare la regola.

   * Per una stringa o un **campo** numerico, specifica l’operatore di confronto e il valore.

      ![](assets/query_editor_audience_definition2.png)

   * Per un **campo** data o data e ora, puoi scegliere di definire una data specifica, un intervallo tra due date o un periodo relativo alla data di esecuzione della query.

      ![](assets/query_editor_date_field.png)

   * Per un **campo** booleano, seleziona le caselle collegate ai possibili valori del campo.
   * Per un campo di **raggruppamento**, seleziona il campo di raggruppamento desiderato per creare la regola, quindi definisci la condizione nello stesso modo degli altri campi.

      ![](assets/query_editor_audience_definition4.png)

   * Per un collegamento **1-1** con un’altra risorsa di database, seleziona un valore direttamente dalla tabella di destinazione.

      ![](assets/query_editor_audience_definition5.png)

   * Per un collegamento **1-N** con un’altra risorsa del database, puoi definire una sottoquery sui campi di questa seconda risorsa.

      Non devi specificare una sottocondizione.

      Ad esempio, puoi selezionare l’operatore **[!UICONTROL Exists]** solo nei log di tracciamento del profilo e approvare la regola. La regola restituisce tutti i profili per i quali esistono dei log di tracciamento.

      ![](assets/query_editor_audience_definition6.png)

   * Per un **filtro predefinito**, inserisci o seleziona gli elementi desiderati in base ai criteri offerti.

      Gli amministratori possono creare filtri per facilitare query complesse e ripetitive. Vengono visualizzate nell’editor delle query sotto forma di regole preconfigurate e limitano il numero di passaggi necessari per l’utente.

      ![](assets/query-editor_filter_email-audience_filter.png)

1. Puoi specificare un nome per la regola. Viene quindi visualizzato come nome della regola nell’area di lavoro. Se alla regola non viene assegnato un nome, viene visualizzata una descrizione automatica delle condizioni.
1. Per combinare gli elementi dell’area di lavoro, puoi unirli per creare diversi gruppi e/o livelli di gruppo. Puoi quindi selezionare un operatore logico per combinare elementi sullo stesso livello:

   * **[!UICONTROL AND]**: un’intersezione di due criteri. Vengono considerati solo gli elementi che corrispondono a ciascun criterio.
   * **[!UICONTROL OR]**: un’unione di due criteri. Vengono considerati gli elementi che corrispondono ad almeno uno dei due criteri.
   * **[!UICONTROL EXCEPT]**: criteri di esclusione. Vengono considerati gli elementi che corrispondono al primo criterio a meno che non corrispondano anche al secondo criterio.

1. Puoi ora calcolare e visualizzare in anteprima il numero di elementi interessati dalla query utilizzando i pulsanti ![](assets/count.png) e ![](assets/preview.png) nella barra delle azioni.

   ![](assets/query_editor_combining_rules.png)

Se desideri modificare un elemento della query, fai clic sull’icona di modifica. La regola viene aperta così come era stata configurata in precedenza e puoi quindi eseguire tutte le regolazioni necessarie.

Le query vengono ora create e definite, in modo da generare una popolazione in grado di personalizzare meglio le consegne.

**Argomenti correlati:**

* [Funzioni avanzate](../../automating/using/advanced-expression-editing.md)
* [Definizione dei filtri](../../developing/using/configuring-filter-definition.md)
* [Caso di utilizzo: creare una consegna e-mail settimanale](../../automating/using/workflow-weekly-offer.md)
* [Caso di utilizzo: creazione di una consegna segmentata sulla posizione](../../automating/using/workflow-segmentation-location.md)
* [Caso di utilizzo: creazione di consegne con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso di utilizzo: invio di una nuova consegna a non-opener tramite un flusso di lavoro di retargeting](../../automating/using/workflow-cross-channel-retargeting.md)
