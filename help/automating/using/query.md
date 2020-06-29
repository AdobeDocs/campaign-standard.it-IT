---
title: Query
description: L'attività Query consente di filtrare ed estrarre una serie di elementi dal database del Adobe Campaign .
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '1725'
ht-degree: 0%

---


# Query{#query}

## Descrizione {#description}

![](assets/query.png)

L&#39; **[!UICONTROL Query]** attività consente di filtrare ed estrarre una serie di elementi dal database del Adobe Campaign . È possibile definire **[!UICONTROL Additional data]** per la popolazione di destinazione tramite una scheda dedicata. Questi dati vengono memorizzati in colonne aggiuntive e possono essere utilizzati solo per il flusso di lavoro in corso.

L&#39;attività utilizza lo strumento di editor di query. Questo strumento è dettagliato in una sezione [](../../automating/using/editing-queries.md#about-query-editor)dedicata.

**Argomenti correlati:**

* [Esempi di query](../../automating/using/query-samples.md)
* [Caso di utilizzo: Flusso di lavoro di retargeting che invia una nuova consegna a non-openers](../../automating/using/workflow-cross-channel-retargeting.md)

## Contesto di utilizzo {#context-of-use}

L&#39; **[!UICONTROL Query]** attività può essere utilizzata per vari tipi di usi:

* Segmentazione di singoli utenti per definire la destinazione di un messaggio, un pubblico ecc.
* Arricchimento dei dati dell&#39;intera tabella di database  Adobe Campaign.
* Esportazione dei dati.

## Configurazione {#configuration}

1. Trascinate e rilasciate un&#39; **[!UICONTROL Query]** attività nel flusso di lavoro.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate. Per impostazione predefinita, l&#39;attività è preconfigurata per la ricerca di profili.
1. Se desiderate eseguire una query su una risorsa diversa dalla risorsa del profilo, andate alla **[!UICONTROL Properties]** scheda dell&#39;attività e selezionate un **[!UICONTROL Resource]** e un **[!UICONTROL Targeting dimension]**.

   Questo **[!UICONTROL Resource]** consente di perfezionare i filtri visualizzati nella palette, mentre il **[!UICONTROL Targeting dimension]**, contestuale rispetto alla risorsa selezionata, corrisponde al tipo di popolazione che si desidera ottenere (profili identificati, consegne, dati collegati alla risorsa selezionata, ecc.).

   Per ulteriori informazioni, consulta [Impostazione del targeting di dimensioni e risorse](#targeting-dimensions-and-resources).

1. Nella **[!UICONTROL Target]** scheda, eseguire la query definendo e combinando le regole.
1. È possibile definire **[!UICONTROL Additional data]** per la popolazione di destinazione tramite una scheda dedicata. Questi dati vengono memorizzati in colonne aggiuntive e possono essere utilizzati solo per il flusso di lavoro in corso. In particolare, è possibile aggiungere dati dalle tabelle del database del Adobe Campaign  collegate alla dimensione di targeting della query. Consulta la sezione [Arricchimento dei dati](#enriching-data) .

   >[!NOTE]
   >
   >Per impostazione predefinita, l’ **[!UICONTROL Remove duplicate rows (DISTINCT)]** opzione è selezionata nella **[!UICONTROL Advanced options]** scheda della **[!UICONTROL Additional data]** query. Se l&#39; **[!UICONTROL Query]** attività contiene molti (da 100) dati aggiuntivi definiti, si consiglia di deselezionare questa opzione, per motivi di prestazioni. Attenzione: se si deseleziona questa opzione è possibile ottenere duplicati, a seconda dei dati interrogati.

1. Nella **[!UICONTROL Transition]** scheda, l&#39; **[!UICONTROL Enable an outbound transition]** opzione consente di aggiungere una transizione in uscita dopo l&#39;attività di query, anche se non recupera dati.

   Il codice del segmento della transizione in uscita può essere personalizzato utilizzando un&#39;espressione standard e variabili di eventi (consultate [Personalizzazione delle attività con le variabili](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)di eventi).

1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.

## Targeting di dimensioni e risorse {#targeting-dimensions-and-resources}

Le dimensioni e le risorse di targeting consentono di definire gli elementi su cui verrà basata una query per determinare la destinazione di una consegna.

Le dimensioni di targeting sono definite nelle mappature di destinazione. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../administration/using/target-mappings-in-campaign.md).

La dimensione di targeting e le risorse vengono definite durante la creazione di un flusso di lavoro, nella **[!UICONTROL Properties]** scheda di un&#39;attività Query.

>[!NOTE]
>
>La dimensione di targeting può essere definita anche durante la creazione di un&#39;audience (vedere [questa sezione](../../audiences/using/creating-audiences.md)).

![](assets/targeting_dimension1.png)

Dimensioni e risorse di destinazione collegate. Le dimensioni di targeting disponibili dipendono quindi dalla risorsa selezionata.

Ad esempio, per la risorsa **[!UICONTROL Profiles (profile)]** saranno disponibili le seguenti dimensioni di targeting:

![](assets/targeting_dimension2.png)

Mentre per **[!UICONTROL Deliveries (delivery)]**, l&#39;elenco conterrà le seguenti dimensioni di targeting:

![](assets/targeting_dimension3.png)

Una volta specificate la dimensione di targeting e la risorsa, nella query sono disponibili filtri diversi.

Esempio di filtri disponibili per la **[!UICONTROL Profiles (profile)]** risorsa:

![](assets/targeting_dimension4.png)

Esempio di filtri disponibili per la **[!UICONTROL Deliveries (delivery)]** risorsa:

![](assets/targeting_dimension5.png)

Per impostazione predefinita, la dimensione di targeting e la risorsa sono impostate per i profili di destinazione. Tuttavia, potrebbe essere utile utilizzare una risorsa diversa dalla dimensione di targeting se si desidera cercare un record specifico in una tabella lontana.

Per ulteriori informazioni, consulta questo caso di utilizzo: [Utilizzo di risorse diverse dalle dimensioni di targeting](../../automating/using/using-resources-different-from-targeting-dimensions.md)

## Arricchimento dei dati {#enriching-data}

La **[!UICONTROL Additional data]** scheda delle attività **[!UICONTROL Query]**, **[!UICONTROL Incremental query]** e **[!UICONTROL Enrichment]** consente di arricchire i dati di destinazione e trasferire tali dati alle seguenti attività del flusso di lavoro, dove possono essere utilizzati. In particolare, potete aggiungere:

* Dati semplici
* Aggregati
* Raccolte

Per gli aggregati e le raccolte, **[!UICONTROL Alias]** viene automaticamente definito un ID tecnico per assegnare un&#39;espressione complessa. Questo alias, che deve essere univoco, consente di trovare facilmente gli aggregati e le raccolte in seguito. Potete modificarlo per assegnargli un nome facilmente riconoscibile.

>[!NOTE]
>
>Gli alias devono rispettare le seguenti regole di sintassi: Sono autorizzati solo i caratteri alfanumerici e i caratteri &quot;_&quot;. Gli alias seguono la distinzione tra maiuscole e minuscole. L&#39;alias deve iniziare con il carattere &quot;@&quot;. Il carattere immediatamente successivo a &quot;@&quot; non deve essere numerico. Ad esempio: @myAlias_1 e @_1Alias corretti; mentre @myAlias#1 e @1Alias non sono corretti.

Dopo aver aggiunto eventuali dati aggiuntivi, puoi applicare un livello di filtro aggiuntivo ai dati inizialmente interessati creando condizioni in base ai dati aggiuntivi definiti.

>[!NOTE]
>
>Per impostazione predefinita, l’ **[!UICONTROL Remove duplicate rows (DISTINCT)]** opzione è selezionata nella **[!UICONTROL Advanced options]** scheda della **[!UICONTROL Additional data]** query. Se l&#39; **[!UICONTROL Query]** attività contiene molti (da 100) dati aggiuntivi definiti, si consiglia di deselezionare questa opzione, per motivi di prestazioni. Attenzione: se si deseleziona questa opzione è possibile ottenere duplicati, a seconda dei dati interrogati.

In [questa sezione](../../automating/using/personalizing-email-with-additional-data.md)viene illustrato un esempio di utilizzo per la personalizzazione di un’e-mail con dati aggiuntivi.

### Aggiunta di un campo semplice {#adding-a-simple-field}

Aggiungendo un campo semplice come dati aggiuntivi, tale campo diventa direttamente visibile nella transizione in uscita dell&#39;attività. Questo consente all&#39;utente di verificare, ad esempio, che i dati della query siano i dati desiderati.

1. Dalla **[!UICONTROL Additional data]** scheda, aggiungete un nuovo elemento.
1. Nella finestra che si apre, nel **[!UICONTROL Expression]** campo, selezionate uno dei campi disponibili direttamente nella dimensione di targeting o in una delle dimensioni collegate. È possibile modificare le espressioni e utilizzare funzioni o calcoli semplici (ad eccezione degli aggregati) dai campi dimensione.

   Se si modifica un&#39;espressione che non è un semplice percorso XPATH, **[!UICONTROL Alias]** viene creata automaticamente (ad esempio: &quot;Year(&lt;@publicationDate>)&quot;). Se volete, potete modificarlo. Se si seleziona un solo campo (ad esempio: &quot;@age&quot;), non è necessario definire un **[!UICONTROL Alias]**.

1. Selezionare **[!UICONTROL Add]** per confermare l&#39;aggiunta del campo ai dati aggiuntivi. Quando la query viene eseguita, nella transizione in uscita dell&#39;attività sarà presente una colonna aggiuntiva corrispondente al campo aggiunto.

![](assets/enrichment_add_simple_field.png)

### Aggiunta di un&#39;aggregazione {#adding-an-aggregate}

Gli aggregati consentono di calcolare i valori dai campi della dimensione di targeting o dai campi di dimensioni collegati alla dimensione di targeting. Ad esempio: l&#39;importo medio acquistato da un profilo.
Quando si utilizza l&#39;aggregazione con la query, la sua funzione può tornare a zero, che viene quindi considerata NULL. Utilizzate la **[!UICONTROL Output filtering]** scheda della query per filtrare il valore aggregato:

* se desiderate valori zero, filtrate **[!UICONTROL is null]**.
* se non si desidera che il filtro dei valori zero sia attivato **[!UICONTROL is not null]**.

Se è necessario applicare l&#39;ordinamento all&#39;aggregazione, è necessario filtrare i valori zero, altrimenti il valore NULL verrà visualizzato come numero maggiore.

1. Dalla **[!UICONTROL Additional data]** scheda, aggiungete un nuovo elemento.
1. Nella finestra visualizzata, selezionate la raccolta da utilizzare per creare l&#39;aggregazione nel **[!UICONTROL Expression]** campo.

   Viene **[!UICONTROL Alias]** creato automaticamente un oggetto. Se lo si desidera, è possibile modificarlo tornando alla **[!UICONTROL Additional data]** scheda della query.

   Viene visualizzata la finestra Definizione aggregazione.

1. Definire un aggregato dalla **[!UICONTROL Data]** scheda. A seconda del tipo di aggregazione selezionato, nel **[!UICONTROL Expression]** campo sono disponibili solo gli elementi i cui dati sono compatibili. Ad esempio, una somma può essere calcolata solo con dati numerici.

   ![](assets/enrichment_add_aggregate.png)

   È possibile aggiungere diversi aggregati per i campi della raccolta selezionata. Assicuratevi di definire etichette esplicite per distinguere le diverse colonne nel dettaglio dei dati in uscita dell&#39;attività.

   È inoltre possibile modificare gli alias definiti automaticamente per ogni aggregazione.

   ![](assets/enrichment_add_aggregate2.png)

1. Se necessario, potete aggiungere un filtro per limitare i dati presi in considerazione.

   Fare riferimento alla sezione [Filtro dei dati](#filtering-added-data) aggiunti.

1. Selezionare **[!UICONTROL Confirm]** per aggiungere aggregati.

>[!NOTE]
>
>Non è possibile creare un&#39;espressione contenente un aggregato direttamente dal **[!UICONTROL Expression]** campo della **[!UICONTROL New additional data]** finestra.

### Aggiunta di una raccolta {#adding-a-collection}

1. Dalla **[!UICONTROL Additional data]** scheda, aggiungete un nuovo elemento.
1. Nella finestra che si apre, selezionate la raccolta che desiderate aggiungere nel **[!UICONTROL Expression]** campo. Viene **[!UICONTROL Alias]** creato automaticamente un oggetto. Se lo si desidera, è possibile modificarlo tornando alla **[!UICONTROL Additional data]** scheda della query.
1. Selezionare **[!UICONTROL Add]**. Si apre una nuova finestra che consente di perfezionare i dati della raccolta che si desidera visualizzare.
1. Nella **[!UICONTROL Parameters]** scheda, selezionare **[!UICONTROL Collection]** e definire il numero di righe della raccolta che si desidera aggiungere. Ad esempio, per ottenere i tre acquisti più recenti effettuati da ciascun profilo, immettete &quot;3&quot; nel **[!UICONTROL Number of lines to return]** campo.

   >[!NOTE]
   >
   >È necessario immettere un numero maggiore o uguale a 1.

1. Dalla **[!UICONTROL Data]** scheda, definire i campi della raccolta che si desidera visualizzare per ogni riga.

   ![](assets/enrichment_add_collection.png)

1. Se lo desiderate, potete aggiungere un filtro per limitare le righe di raccolta prese in considerazione.

   Fare riferimento alla sezione [Filtro dei dati](#filtering-added-data) aggiunti.

1. Se lo desideri, puoi definire un ordinamento dei dati.

   Ad esempio, se hai selezionato 3 righe da restituire nella **[!UICONTROL Parameters]** scheda e vuoi determinare i tre acquisti più recenti, puoi definire un ordinamento decrescente nel campo &quot;data&quot; della raccolta che corrisponde alle transazioni.

1. Fare riferimento alla sezione [Ordinamento di dati](#sorting-additional-data) aggiuntivi.
1. Selezionare **[!UICONTROL Confirm]** per aggiungere la raccolta.

### Filtrare i dati aggiunti {#filtering-added-data}

Quando aggiungete un aggregato o una raccolta, potete specificare un filtro aggiuntivo per limitare i dati da visualizzare.

Ad esempio, se si desidera elaborare solo le linee di raccolta delle transazioni con importi pari o superiori a 50 dollari, è possibile aggiungere una condizione nel campo corrispondente all&#39;importo della transazione dalla **[!UICONTROL Filter]** scheda.

![](assets/enrichment_filter_data.png)

### Ordinamento di dati aggiuntivi {#sorting-additional-data}

Quando si aggiunge un aggregato o una raccolta ai dati di una query, è possibile specificare se applicare un ordinamento, ascendente o discendente, in base al valore del campo o all&#39;espressione definita.

Ad esempio, se si desidera salvare solo la transazione eseguita più di recente da un profilo, immettere &quot;1&quot; nel **[!UICONTROL Number of lines to return]** campo della **[!UICONTROL Parameters]** scheda e applicare un ordinamento decrescente nel campo corrispondente alla data della transazione tramite la **[!UICONTROL Sort]** scheda.

![](assets/enrichment_sort_data.png)

### Applicazione di filtri ai dati di destinazione in base a dati aggiuntivi {#filtering-the-targeted-data-according-to-additional-data}

Dopo aver aggiunto dati aggiuntivi, nella finestra di dialogo viene visualizzata una nuova **[!UICONTROL Output filtering]** scheda **[!UICONTROL Query]**. Questa scheda consente di applicare un filtro aggiuntivo ai dati inizialmente inclusi nella **[!UICONTROL Target]** scheda, tenendo conto dei dati aggiunti.

Ad esempio, se hai eseguito il targeting di tutti i profili che hanno eseguito almeno una transazione e un aggregato che calcola l&#39;importo medio della transazione eseguita per ciascun profilo è stato aggiunto al **[!UICONTROL Additional data]**, puoi perfezionare la popolazione inizialmente calcolata utilizzando questa media.

A questo scopo, nella **[!UICONTROL Output filtering]** scheda, è sufficiente aggiungere una condizione a questi dati aggiuntivi.

![](assets/enrichment_output_filtering2.png)

![](assets/enrichment_output_filtering.png)
