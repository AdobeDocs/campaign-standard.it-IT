---
title: Query
description: L’attività Query ti consente di filtrare ed estrarre una popolazione di elementi dal database di Adobe Campaign.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1708'
ht-degree: 96%

---


# Query{#query}

## Descrizione {#description}

![](assets/query.png)

L’attività **[!UICONTROL Query]** ti consente di filtrare ed estrarre una popolazione di elementi dal database di Adobe Campaign. Puoi definire **[!UICONTROL Additional data]** per la popolazione target tramite una scheda dedicata. Questi dati vengono memorizzati in colonne aggiuntive e possono essere utilizzati solo per il flusso di lavoro in corso.

L’attività utilizza lo strumento editor delle query. Questo strumento è descritto in una [sezione dedicata](../../automating/using/editing-queries.md#about-query-editor).

**Argomenti correlati:**

* [Esempi di query](../../automating/using/query-samples.md)
* [Caso di utilizzo: invio di una nuova consegna a non-opener tramite un flusso di lavoro di retargeting](../../automating/using/workflow-cross-channel-retargeting.md)

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Query]** può avere vari tipi di utilizzi:

* Segmentazione di singoli utenti per definire il target di un messaggio, un pubblico, ecc.
* Arricchimento dei dati dell’intera tabella di database di Adobe Campaign.
* Esportazione dei dati.

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Query]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate. Per impostazione predefinita l’attività è preconfigurata per ricercare profili.
1. Se desideri eseguire una query su una risorsa diversa da quella del profilo, passa alla scheda **[!UICONTROL Properties]** dell’attività e seleziona una **[!UICONTROL Resource]** e una **[!UICONTROL Targeting dimension]**.

   La **[!UICONTROL Resource]** ti consente di perfezionare i filtri visualizzati nella palette, mentre la **[!UICONTROL Targeting dimension]**, contestuale rispetto alla risorsa selezionata, corrisponde al tipo di popolazione che desideri ottenere (profili identificati, consegne, dati collegati alla risorsa selezionata, ecc.).

   Per ulteriori informazioni, consulta [Dimensioni di targeting e risorse](#targeting-dimensions-and-resources).

1. Nella scheda **[!UICONTROL Target]**, esegui la query definendo e combinando regole.
1. Puoi definire **[!UICONTROL Additional data]** per la popolazione target tramite una scheda dedicata. Questi dati vengono memorizzati in colonne aggiuntive e possono essere utilizzati solo per il flusso di lavoro in corso. In particolare, puoi aggiungere dati dalle tabelle del database di Adobe Campaign collegate alla dimensione di targeting della query. Consulta la sezione [Arricchimento dei dati](#enriching-data).

   >[!NOTE]
   >
   >Per impostazione predefinita, l’opzione **[!UICONTROL Remove duplicate rows (DISTINCT)]** è selezionata nelle **[!UICONTROL Advanced options]** della scheda **[!UICONTROL Additional data]** della query. Se l’attività **[!UICONTROL Query]** contiene molti (a partire da 100) dati aggiuntivi definiti, è consigliabile deselezionare questa opzione per motivi di prestazioni. Attenzione: se deselezioni questa opzione puoi ottenere duplicati, a seconda dei dati interrogati.

1. Nella scheda **[!UICONTROL Transition]**, l’opzione **[!UICONTROL Enable an outbound transition]** ti consente di aggiungere una transizione in uscita dopo l’attività Query, anche se non recupera dati.

   The outbound transition&#39;s segment code can be personalized using a standard expression and events variables (see [](../../automating/using/customizing-workflow-external-parameters.md)).

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

## Dimensioni di targeting e risorse {#targeting-dimensions-and-resources}

Le dimensioni di targeting e le risorse ti consentono di definire su quali elementi basare una query per determinare il target di una consegna.

Sono configurati nelle mappature [di](../../administration/using/target-mappings-in-campaign.md)destinazione e sono definiti durante la creazione di un flusso di lavoro nella **[!UICONTROL Properties]** scheda di un&#39;attività Query.

>[!NOTE]
>
>Puoi anche definire la dimensione di targeting durante la creazione di un pubblico (vedi [questa sezione](../../audiences/using/creating-audiences.md)).

![](assets/targeting_dimension1.png)

Le dimensioni di targeting e le risorse sono collegate. Le dimensioni di targeting disponibili dipendono quindi dalla risorsa selezionata.

Ad esempio, per la risorsa **[!UICONTROL Profiles (profile)]**, sono disponibili le seguenti dimensioni di targeting:

![](assets/targeting_dimension2.png)

Mentre per **[!UICONTROL Deliveries (delivery)]**, l’elenco contiene le seguenti dimensioni di targeting:

![](assets/targeting_dimension3.png)

Dopo la specificazione della dimensione di targeting e della risorsa, nella query sono disponibili filtri diversi.

Esempio di filtri disponibili per la risorsa **[!UICONTROL Profiles (profile)]**:

![](assets/targeting_dimension4.png)

Esempio di filtri disponibili per la risorsa **[!UICONTROL Deliveries (delivery)]**:

![](assets/targeting_dimension5.png)

Per impostazione predefinita, la dimensione di targeting e la risorsa sono impostati per eseguire il targeting dei profili. Tuttavia, se desideri cercare un record specifico in una tabella lontana, potrebbe risultare utile usare una risorsa diversa dalla dimensione di targeting.

Per ulteriori informazioni, consulta questo caso di utilizzo: [Utilizzo di risorse diverse dalle dimensioni di targeting](../../automating/using/using-resources-different-from-targeting-dimensions.md)

## Arricchimento dei dati {#enriching-data}

La scheda **[!UICONTROL Additional data]** delle attività **[!UICONTROL Query]**, **[!UICONTROL Incremental query]** e **[!UICONTROL Enrichment]** ti consentono di arricchire i dati target e trasferirli alle seguenti attività del flusso di lavoro, dove è possibile utilizzarli. In particolare, puoi aggiungere:

* Dati semplici
* Aggregati
* Raccolte

Per aggregati e raccolte, viene automaticamente definito un **[!UICONTROL Alias]** per assegnare un ID tecnico a un’espressione complessa. Questo alias, che deve essere univoco, ti consente di trovare facilmente gli aggregati e le raccolte in seguito. Puoi modificarlo per assegnargli un nome facilmente riconoscibile.

>[!NOTE]
>
>Gli alias devono rispettare le seguenti regole di sintassi: sono autorizzati solo caratteri alfanumerici e i caratteri &quot;_&quot;. Gli alias distinguono tra maiuscole e minuscole. L’alias deve iniziare con il carattere &quot;@&quot;. Il carattere immediatamente successivo a &quot;@&quot; non deve essere numerico. Ad esempio: @mioAlias_1 e @_1Alias sono corretti, mentre @mioAlias#1 e @1Alias non sono corretti.

Dopo l’aggiunta di eventuali dati aggiuntivi, puoi applicare un livello di filtro aggiuntivo ai dati inizialmente interessati dal targeting creando condizioni in base ai dati aggiuntivi definiti.

>[!NOTE]
>
>Per impostazione predefinita, l’opzione **[!UICONTROL Remove duplicate rows (DISTINCT)]** è selezionata nelle **[!UICONTROL Advanced options]** della scheda **[!UICONTROL Additional data]** della query. Se l’attività **[!UICONTROL Query]** contiene molti (a partire da 100) dati aggiuntivi definiti, è consigliabile deselezionare questa opzione per motivi di prestazioni. Attenzione: se deselezioni questa opzione puoi ottenere duplicati, a seconda dei dati interrogati.

In [questa sezione](../../automating/using/personalizing-email-with-additional-data.md)viene illustrato un esempio di utilizzo per la personalizzazione di un’e-mail con dati aggiuntivi.

### Aggiunta di un campo semplice {#adding-a-simple-field}

Aggiungendo un campo semplice come dati aggiuntivi, quel campo diventa direttamente visibile nella transizione in uscita dell’attività. In questo modo l’utente può verificare, ad esempio, che i dati della query corrispondano ai dati desiderati.

1. Aggiungi un nuovo elemento dalla scheda **[!UICONTROL Additional data]**.
1. Nella finestra visualizzata, nel campo **[!UICONTROL Expression]**, seleziona uno dei campi disponibili direttamente dalla dimensione di targeting o in una dimensione collegata. Puoi modificare espressioni e utilizzare funzioni o calcoli semplici (ad eccezione di aggregati) dai campi della dimensione.

   Se modifichi un’espressione che non è un semplice percorso XPATH, viene creato automaticamente un **[!UICONTROL Alias]** (ad esempio: &quot;Year(&lt;@datadinascita>)&quot;). Se lo desideri, puoi modificarlo. Se selezioni un solo campo (ad esempio: &quot;@età&quot;), non devi definire un **[!UICONTROL Alias]**.

1. Seleziona **[!UICONTROL Add]** per confermare l’aggiunta del campo ai dati aggiuntivi. Quando la query viene eseguita, nella transizione in uscita dell’attività è presente una colonna aggiuntiva corrispondente al campo aggiunto.

![](assets/enrichment_add_simple_field.png)

### Aggiunta di un aggregato {#adding-an-aggregate}

Gli aggregati consentono di calcolare valori dai campi della dimensione di targeting o dai campi delle dimensioni a essa collegati. Ad esempio: l’importo medio acquistato da un profilo.
Quando utilizzi l’aggregato con la query, la sua funzione può tornare a zero, venendo quindi considerata NULL. Utilizza la scheda **[!UICONTROL Output filtering]** della query per filtrare il valore aggregato:

* se desideri valori zero, imposta il filtro su **[!UICONTROL is null]**.
* se non desideri valori zero, imposta il filtro su **[!UICONTROL is not null]**.

Se devi applicare l’ordinamento all’aggregato, dovresti filtrare valori zero, altrimenti il valore NULL viene visualizzato come numero maggiore.

1. Aggiungi un nuovo elemento dalla scheda **[!UICONTROL Additional data]**.
1. Nella finestra visualizzata, seleziona la raccolta che desideri utilizzare per creare l’aggregato nel campo **[!UICONTROL Expression]**.

   Un **[!UICONTROL Alias]** viene creato automaticamente. Se lo desideri, puoi modificarlo tornando alla scheda **[!UICONTROL Additional data]** della query.

   Viene visualizzata la finestra di definizione dell’aggregato.

1. Definisci un aggregato dalla scheda **[!UICONTROL Data]**. A seconda del tipo di aggregato selezionato, nel campo **[!UICONTROL Expression]** sono disponibili solo gli elementi che presentano dati compatibili. Ad esempio, è possibile calcolare una somma solo con dati numerici.

   ![](assets/enrichment_add_aggregate.png)

   Puoi aggiungere diversi aggregati per i campi della raccolta selezionata. Assicurati di definire etichette esplicite per distinguere in dettaglio le diverse colonne dei dati in uscita dell’attività.

   Puoi anche modificare gli alias definiti automaticamente per ogni aggregato.

   ![](assets/enrichment_add_aggregate2.png)

1. Se necessario, puoi aggiungere un filtro per limitare i dati presi in considerazione.

   Consulta la sezione [Filtro dei dati aggiunti](#filtering-added-data).

1. Seleziona **[!UICONTROL Confirm]** per aggiungere aggregati.

>[!NOTE]
>
>Non puoi creare un’espressione contenente un aggregato direttamente dal campo **[!UICONTROL Expression]** della finestra **[!UICONTROL New additional data]**.

### Aggiunta di una raccolta {#adding-a-collection}

1. Aggiungi un nuovo elemento dalla scheda **[!UICONTROL Additional data]**.
1. Nella finestra visualizzata, seleziona la raccolta che desideri aggiungere nel campo **[!UICONTROL Expression]**. Un **[!UICONTROL Alias]** viene creato automaticamente. Se lo desideri, puoi modificarlo tornando alla scheda **[!UICONTROL Additional data]** della query.
1. Seleziona **[!UICONTROL Add]**. Viene visualizzata una nuova finestra che ti consente di perfezionare i dati della raccolta da visualizzare.
1. Nella scheda **[!UICONTROL Parameters]**, seleziona **[!UICONTROL Collection]** e definisci il numero di righe della raccolta da aggiungere. Ad esempio, se desideri ottenere i tre acquisti più recenti effettuati da ciascun profilo, immetti &quot;3&quot; nel campo **[!UICONTROL Number of lines to return]**.

   >[!NOTE]
   >
   >Devi immettere un numero maggiore o uguale a 1.

1. Definisci i campi della raccolta da visualizzare per ogni riga dalla scheda **[!UICONTROL Data]**.

   ![](assets/enrichment_add_collection.png)

1. Se lo desideri, puoi aggiungere un filtro per limitare le righe della raccolta presa in considerazione.

   Consulta la sezione [Filtro dei dati aggiunti](#filtering-added-data).

1. Se lo desideri, puoi definire un ordinamento dei dati.

   Ad esempio, se hai selezionato 3 righe da restituire nella scheda **[!UICONTROL Parameters]** e desideri determinare i tre acquisti più recenti, puoi definire un ordinamento decrescente nel campo &quot;date&quot; della raccolta corrispondente alle transazioni.

1. Consulta la sezione [Ordinamento dei dati aggiuntivi](#sorting-additional-data).
1. Seleziona **[!UICONTROL Confirm]** per aggiungere la raccolta.

### Filtro dei dati aggiunti {#filtering-added-data}

Quando aggiungi un aggregato o una raccolta, puoi specificare un filtro aggiuntivo per limitare i dati da visualizzare.

Ad esempio, se desideri elaborare solo le righe della raccolta delle transazioni con importi pari o superiori a 50 dollari, puoi aggiungere una condizione nel campo corrispondente all’importo della transazione dalla scheda **[!UICONTROL Filter]**.

![](assets/enrichment_filter_data.png)

### Ordinamento dei dati aggiuntivi {#sorting-additional-data}

Quando aggiungi un aggregato o una raccolta ai dati di una query, puoi specificare se desideri applicare un ordinamento, crescente o decrescente, in base al valore del campo o all’espressione definita.

Ad esempio, se desideri salvare solo la transazione eseguita più di recente da un profilo, immetti &quot;1&quot; nel campo **[!UICONTROL Number of lines to return]** della scheda **[!UICONTROL Parameters]** e applica un ordinamento decrescente nel campo corrispondente alla data della transazione tramite la scheda **[!UICONTROL Sort]**.

![](assets/enrichment_sort_data.png)

### Filtri dei dati target in base ai dati aggiuntivi {#filtering-the-targeted-data-according-to-additional-data}

Dopo l’aggiunta dei dati aggiuntivi, nella **[!UICONTROL Query]** viene visualizzata una nuova scheda **[!UICONTROL Output filtering]**. Questa scheda ti consente di applicare un filtro aggiuntivo ai dati inizialmente inclusi nella scheda **[!UICONTROL Target]** tenendo conto dei dati aggiunti.

Ad esempio, se hai eseguito il targeting di tutti i profili che hanno effettuato almeno una transazione e un aggregato calcolando l’importo medio della transazione eseguita per ciascun profilo aggiunto agli **[!UICONTROL Additional data]**, puoi perfezionare la popolazione inizialmente calcolata utilizzando questa media.

A questo scopo, nella scheda **[!UICONTROL Output filtering]** aggiungi semplicemente una condizione a questi dati aggiuntivi.

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)
