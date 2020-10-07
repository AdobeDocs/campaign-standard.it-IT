---
title: Best practice relative ai modelli dati in  Adobe Campaign Standard
description: Scoprite le procedure ottimali per la progettazione  modello dati Adobe Campaign Standard.
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 1%

---


# Best practice per i modelli di dati{#data-model-best-practices}

In questo documento vengono delineate le raccomandazioni chiave durante la progettazione del modello dati Adobe Campaign .


>[!NOTE]
>
>Per creare e modificare le risorse al fine di estendere il modello dati  Adobe Campaign predefinito, consultare [questa sezione](../../developing/using/key-steps-to-add-a-resource.md).
>
>È possibile trovare una rappresentazione modello dati delle risorse integrate in [questa pagina](../../developing/using/datamodel-introduction.md).

## Panoramica {#overview}

 sistema Adobe Campaign è estremamente flessibile e può essere esteso oltre l&#39;implementazione iniziale. Tuttavia, mentre le possibilità sono infinite, è fondamentale prendere decisioni sagge e creare solide basi per iniziare a progettare il modello dati.

In questo documento sono riportati i casi d’uso e le procedure ottimali più comuni per apprendere come architettare correttamente  strumento Adobe Campaign.

## Architettura del modello dati {#data-model-architecture}

 Adobe Campaign Standard è un potente sistema di gestione delle campagne multicanale che consente di allineare le strategie online e offline per creare esperienze cliente personalizzate.

### Metodo incentrato sul cliente {#customer-centric-approach}

Mentre la maggior parte dei provider di servizi e-mail comunica ai clienti tramite un approccio incentrato sugli elenchi,  Adobe Campaign si affida a un database relazionale per sfruttare una visione più ampia dei clienti e dei loro attributi.

Questo approccio incentrato sul cliente è riportato nel grafico seguente. La risorsa **Profilo** in grigio rappresenta la tabella cliente principale intorno alla quale viene creato tutto:

![](assets/customer-centric-data-model.png)

In questa [sezione](../../developing/using/datamodel-introduction.md)viene illustrato  modello dati predefinito Adobe Campaign.

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### Dati per  Adobe Campaign {#data-for-campaign}

Quali dati devono essere inviati a  Adobe Campaign? È fondamentale determinare i dati richiesti per le attività di marketing.

>[!NOTE]
>
> Adobe Campaign non è un data warehouse. Pertanto, non cercate di importare tutti i possibili clienti e le relative informazioni in  Adobe Campaign.

Per decidere se un attributo sarebbe necessario o meno in  Adobe Campaign, determinare se rientrerebbe in una delle seguenti categorie:
* Attributo utilizzato per la **segmentazione**
* Attributo utilizzato per i processi **di gestione dei** dati (ad esempio, calcolo aggregato)
* Attributo utilizzato per la **personalizzazione**
* Attributo utilizzato per il **reporting** (i rapporti possono essere creati in base ai dati di profilo personalizzati)

Se non si rientra in nessuno di questi, molto probabilmente non sarà necessario questo attributo in  Adobe Campaign.

### Tipi di dati {#data-types}

Per garantire una buona architettura e buone prestazioni del sistema, segui le best practice riportate di seguito per configurare i dati in  Adobe Campaign:
* La lunghezza di un campo stringa deve essere sempre definita con la colonna. Per impostazione predefinita, la lunghezza massima in  Adobe Campaign è di 255 caratteri, ma  Adobe consiglia di ridurre la lunghezza del campo se si è già certi che la dimensione non supererà una lunghezza inferiore.
* È accettabile avere un campo più breve in  Adobe Campaign rispetto a quello nel sistema di origine, se si è certi che la dimensione nel sistema di origine è stata sopravvalutata e non sarebbe stato raggiunto. Ciò potrebbe significare una stringa più corta o un numero intero più piccolo in  Adobe Campaign.

## Configurazione della struttura dei dati {#configuring-data-structure}

Questa sezione descrive le procedure ottimali per la [configurazione della struttura](../../developing/using/configuring-the-resource-s-data-structure.md)dati di una risorsa.

### Identificatori {#identifiers}

 risorse Adobe Campaign hanno tre identificatori ed è possibile aggiungere un identificatore aggiuntivo.

La tabella seguente descrive questi identificatori e la loro funzione.

>[!NOTE]
>
>Il nome visualizzato è il nome del campo visualizzato all&#39;utente tramite l&#39;interfaccia utente  Adobe Campaign. Il nome tecnico è il nome del campo effettivo nella definizione delle risorse (e il nome della colonna della tabella).

| Nome visualizzato | Nome tecnico | Descrizione | Best practice |
|--- |--- |--- |--- |
|  | PKey | <ul><li>PKey è la chiave primaria fisica di una tabella Adobe Campaign .</li><li>Questo identificatore è in genere univoco per una specifica istanza di Adobe Campaign .</li><li>In  Adobe Campaign Standard, questo valore non è visibile all’utente finale (tranne che negli URL).</li></ul> | <ul><li>Attraverso il sistema [](../../api/using/get-started-apis.md)API è possibile recuperare un valore PKey (che è un valore generato/con hash, non la chiave fisica).</li><li>Si consiglia di non utilizzarlo per nient&#39;altro che per recuperare, aggiornare o eliminare record tramite API.</li></ul> |
| ID | name o internalName | <ul><li>Queste informazioni sono un identificatore univoco di un record in una tabella. Questo valore può essere aggiornato manualmente.</li><li>Questo identificatore mantiene il suo valore quando viene distribuito in un’altra istanza di  Adobe Campaign. Deve avere un nome diverso dal valore generato per essere esportabile tramite un pacchetto.</li><li>Questa non è la chiave primaria effettiva della tabella.</li></ul> | <ul><li>Non utilizzate caratteri speciali come lo spazio &quot;&quot;, la semicolona &quot;:&quot; o il trattino &quot;-&quot;.</li><li>Tutti questi caratteri vengono sostituiti da un carattere di sottolineatura &quot;_&quot; (caratteri consentiti). Ad esempio, &quot;abc-def&quot; e &quot;abc:def&quot; vengono memorizzati come &quot;abc_def&quot; e si sovrascrivono a vicenda.</li></ul> |
| Etichetta | label | <ul><li>L&#39;etichetta è l&#39;identificatore aziendale di un oggetto o di un record in  Adobe Campaign.</li><li>Questo oggetto consente spazi e caratteri speciali.</li><li>Non garantisce l&#39;unicità di un documento.</li></ul> | <ul><li>È consigliabile determinare una struttura per le etichette degli oggetti.</li><li>Si tratta della soluzione più semplice da utilizzare per identificare un record o un oggetto per un utente Adobe Campaign .</li></ul> |
| ID ACS | acsId | <ul><li>È possibile generare un identificatore aggiuntivo: l’ID [](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)ACS.</li><li>Poiché il PKey non può essere utilizzato nell&#39;interfaccia utente  Adobe Campaign, si tratta di una soluzione per ottenere un valore univoco generato durante l&#39;inserimento di un record di profilo.</li><li>Il valore può essere generato automaticamente solo se l&#39;opzione è abilitata nella risorsa prima che un record venga inserito in  Adobe Campaign.</li></ul> | <ul><li>Questo UUUID può essere utilizzato come chiave di riconciliazione.</li><li>Un ID ACS generato automaticamente non può essere utilizzato come riferimento in un flusso di lavoro o in una definizione di pacchetto.</li><li>Questo valore è specifico per un&#39;istanza di Adobe Campaign .</li></ul> |

### Chiavi di identificazione {#keys}

Ogni risorsa creata in  Adobe Campaign deve avere almeno una chiave [di](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)identificazione univoca.

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

Quando create una risorsa personalizzata, sono disponibili due opzioni:

* Combinazione di chiave generata automaticamente e chiave personalizzata interna. Questa opzione è interessante se la chiave di sistema è una chiave composita o non un numero intero. Gli interi forniranno prestazioni più elevate nelle grandi tabelle e uniranno ad altre tabelle.
* Utilizzo della chiave primaria come chiave primaria del sistema esterno. Questa soluzione è generalmente preferita in quanto semplifica l&#39;approccio all&#39;importazione e all&#39;esportazione dei dati, con una chiave coerente tra i diversi sistemi.

Le chiavi di identificazione non devono essere utilizzate come riferimento nei flussi di lavoro.

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### Indici {#indexes}

 Adobe Campaign aggiunge automaticamente un [indice](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) a tutte le chiavi primarie e interne definite in una risorsa.

*  Adobe consiglia di definire indici aggiuntivi in quanto potrebbero migliorare le prestazioni.
* Tuttavia, non aggiungete troppi indici in quanto utilizzano spazio nel database. Numerosi indici possono anche avere un impatto negativo sulle prestazioni.
* Selezionare attentamente gli indici da definire.

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### Collegamenti {#links}

In [questa sezione](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)viene illustrata la definizione di collegamenti con altre risorse.

* Sebbene sia possibile unire qualsiasi tabella in un flusso di lavoro,  Adobe consiglia di definire collegamenti comuni tra le risorse direttamente nella definizione della struttura dati.
* Il collegamento deve essere definito in linea con i dati effettivi nelle tabelle. Una definizione errata potrebbe avere un impatto sui dati recuperati tramite collegamenti, ad esempio la duplicazione inattesa di record.
* Denominate il collegamento in modo coerente con il nome della risorsa: il nome del collegamento deve essere utile per comprendere la tabella lontana.
* Non assegnate un nome a un collegamento con &quot;id&quot; come suffisso. Ad esempio, denominatelo &quot;transaction&quot; anziché &quot;transactionId&quot;.

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## Prestazioni {#performance}

Per garantire prestazioni migliori in qualsiasi momento, segui le best practice riportate di seguito.

### Raccomandazioni generali {#general-recommendations}

* Evitare di utilizzare operazioni come &quot;CONTAINS&quot; nelle query. Se sai cosa ci si aspetta e vuoi filtrare, applica la stessa condizione con &quot;EQUAL TO&quot; o altri operatori filtro specifici.
* Evitare di unirsi a campi non indicizzati durante la creazione di dati nei flussi di lavoro.
* Cercate di assicurarsi che i processi come l&#39;importazione e l&#39;esportazione avvengano al di fuori dell&#39;orario di lavoro.
* Assicurarsi che ci sia un programma per tutte le attività giornaliere e attenersi al programma.
* Se uno o pochi processi giornalieri non riescono e se è obbligatorio eseguirli nello stesso giorno, assicurarsi che non siano in esecuzione processi in conflitto quando il processo manuale viene avviato, in quanto ciò potrebbe influire sulle prestazioni del sistema.
* Accertatevi che nessuna delle campagne giornaliere venga eseguita durante il processo di importazione o quando viene eseguito un processo manuale.
* Utilizzare una o più tabelle di riferimento anziché duplicare un campo in ogni riga. Quando si utilizzano coppie chiave/valore, è preferibile scegliere una chiave numerica.
* Una stringa breve rimane accettabile. Nel caso in cui le tabelle di riferimento siano già presenti in un sistema esterno, il riutilizzo dello stesso agevolerà l&#39;integrazione dei dati con  Adobe Campaign.

### Relazioni uno-a-molti {#one-to-many-relationships}

* La progettazione dei dati influisce su usabilità e funzionalità. Se si progetta il modello dati con molte relazioni uno-a-molti, diventa più difficile per gli utenti costruire logiche significative nell&#39;applicazione. La logica del filtro uno-molti può essere difficile per gli addetti al marketing non tecnico da costruire e comprendere correttamente.
* È utile avere tutti i campi essenziali in una tabella, perché semplifica la creazione di query da parte degli utenti. A volte è anche utile che le prestazioni di alcuni campi vengano duplicate tra le tabelle, se è possibile evitare un join.
* Alcune funzionalità integrate non saranno in grado di fare riferimento a relazioni uno-molti, ad esempio, formula di ponderazione dell&#39;offerta e consegne.

### Tabelle grandi {#large-tables}

Di seguito sono riportate alcune best practice da seguire per la progettazione del modello dati utilizzando tabelle di grandi dimensioni e join complessi.

* Ridurre il numero di colonne, in particolare identificando quelle non utilizzate.
* Ottimizzate le relazioni del modello dati evitando join complessi, ad esempio join su più condizioni e/o più colonne.
* Per le chiavi di join, utilizzare sempre dati numerici anziché stringhe di caratteri.
* Ridurre al massimo la profondità di conservazione del registro. Se si desidera una cronologia più approfondita, è possibile aggregare il calcolo e/o gestire tabelle di registro personalizzate per memorizzare una cronologia più grande.