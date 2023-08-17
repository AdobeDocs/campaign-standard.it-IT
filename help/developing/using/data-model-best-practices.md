---
title: Best practice per i modelli di dati in Adobe Campaign Standard
description: Scopri le best practice per la progettazione del modello dati di Adobe Campaign Standard.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
exl-id: 58d4e02f-3c9a-4e5d-a6aa-fdbcec0d8dda
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 1%

---

# Best practice per i modelli di dati{#data-model-best-practices}

Questo documento illustra i consigli chiave durante la progettazione del modello dati di Adobe Campaign.


>[!NOTE]
>
>Per creare e modificare le risorse al fine di estendere il modello dati predefinito di Adobe Campaign, consulta [questa sezione](../../developing/using/key-steps-to-add-a-resource.md).
>
>Puoi trovare una rappresentazione del modello dati delle risorse incorporate in [questa pagina](../../developing/using/datamodel-introduction.md).

## Panoramica {#overview}

Il sistema Adobe Campaign è estremamente flessibile e può essere esteso oltre l’implementazione iniziale. Tuttavia, anche se le possibilità sono infinite, è fondamentale prendere decisioni sagge e creare solide basi per iniziare a progettare il modello di dati.

Questo documento fornisce casi d’uso comuni e best practice per scoprire come progettare correttamente lo strumento Adobe Campaign.

## Architettura del modello dati {#data-model-architecture}

Adobe Campaign Standard è un potente sistema di gestione delle campagne cross-channel che consente di allineare le strategie online e offline per creare esperienze cliente personalizzate.

### Approccio incentrato sul cliente {#customer-centric-approach}

Mentre la maggior parte dei provider di servizi e-mail comunica con i clienti tramite un approccio incentrato sugli elenchi, Adobe Campaign si basa su un database relazionale per sfruttare una visione più ampia dei clienti e dei loro attributi.

Questo approccio incentrato sul cliente è illustrato nel grafico seguente. Il **Profilo** la risorsa in grigio rappresenta la tabella principale del cliente intorno alla quale viene creato tutto:

![](assets/customer-centric-data-model.png)

Il modello dati predefinito di Adobe Campaign è presentato in questo [sezione](../../developing/using/datamodel-introduction.md).

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### Dati per Adobe Campaign {#data-for-campaign}

Quali dati devono essere inviati ad Adobe Campaign? È fondamentale determinare i dati necessari per le attività di marketing.

>[!NOTE]
>
>Adobe Campaign non è un data warehouse. Pertanto, non cercare di importare in Adobe Campaign tutti i possibili clienti e le relative informazioni associate.

Per decidere se un attributo sia necessario o meno in Adobe Campaign, determina se rientra in una delle seguenti categorie:
* Attributo utilizzato per **segmentazione**
* Attributo utilizzato per **processi di gestione dei dati** (ad esempio, calcolo aggregato).
* Attributo utilizzato per **personalizzazione**
* Attributo utilizzato per **reportistica** (i rapporti possono essere creati in base a dati di profilo personalizzati)

Se non rientra in nessuno di questi, molto probabilmente non avrai bisogno di questo attributo in Adobe Campaign.

### Tipi di dati {#data-types}

Per garantire una buona architettura e prestazioni del sistema, segui le best practice riportate di seguito per configurare i dati in Adobe Campaign:
* La lunghezza di un campo stringa deve sempre essere definita con la colonna. Per impostazione predefinita, la lunghezza massima in Adobe Campaign è di 255 caratteri, ma l’Adobe consiglia di mantenere il campo più breve se sai già che la dimensione non supererà una lunghezza più breve.
* È accettabile avere un campo più breve in Adobe Campaign rispetto a quello presente nel sistema di origine se si è certi che la dimensione nel sistema di origine è stata sovrastimata e non sarebbe raggiunta. Questo potrebbe significare una stringa più breve o un numero intero più piccolo in Adobe Campaign.

## Configurazione della struttura dati {#configuring-data-structure}

Questa sezione descrive le best practice da seguire quando [configurazione della struttura dati di una risorsa](../../developing/using/configuring-the-resource-s-data-structure.md).

### Identificatori {#identifiers}

Le risorse Adobe Campaign hanno tre identificatori ed è possibile aggiungere un identificatore aggiuntivo.

La tabella seguente descrive tali identificatori e il loro scopo.

>[!NOTE]
>
>Il nome visualizzato è il nome del campo visualizzato dall’utente tramite l’interfaccia utente di Adobe Campaign. Il nome tecnico è il nome effettivo del campo nella definizione della risorsa (e il nome della colonna della tabella).

| Nome visualizzato | Nome tecnico | Descrizione | Best practice |
|--- |--- |--- |--- |
|  | PKey | <ul><li>PKey è la chiave primaria fisica di una tabella Adobe Campaign.</li><li>Questo identificatore è in genere univoco per una specifica istanza di Adobe Campaign.</li><li>In Adobe Campaign Standard, questo valore non è visibile all’utente finale (tranne negli URL).</li></ul> | <ul><li>Attraverso il [Sistema API](../../api/using/get-started-apis.md), è possibile recuperare un valore PKey (che è un valore generato/con hash, non la chiave fisica).</li><li>Si consiglia di non utilizzarlo per scopi diversi dal recupero, aggiornamento o eliminazione di record tramite API.</li></ul> |
| ID | nome o internalName | <ul><li>Queste informazioni sono un identificatore univoco di un record in una tabella. Questo valore può essere aggiornato manualmente.</li><li>Questo identificatore mantiene il suo valore quando distribuito in un’istanza diversa di Adobe Campaign. Deve avere un nome diverso rispetto al valore generato per essere esportabile tramite un pacchetto.</li><li>Questa non è la chiave primaria effettiva della tabella.</li></ul> | <ul><li>Non utilizzare caratteri speciali come lo spazio &quot;&quot;, la semiconna &quot;:&quot; o il trattino &quot;-&quot;.</li><li>Tutti questi caratteri verrebbero sostituiti da un carattere di sottolineatura &quot;_&quot; (carattere consentito). Ad esempio, &quot;abc-def&quot; e &quot;abc:def&quot; verrebbero memorizzati come &quot;abc_def&quot; e si sovrascriverebbero a vicenda.</li></ul> |
| Etichetta | label | <ul><li>L’etichetta è l’identificatore aziendale di un oggetto o di un record in Adobe Campaign.</li><li>Questo oggetto consente spazi e caratteri speciali.</li><li>Non garantisce l&#39;univocità di un record.</li></ul> | <ul><li>Si consiglia di determinare una struttura per le etichette degli oggetti.</li><li>Questa è la soluzione più semplice da usare per identificare un record o un oggetto per un utente di Adobe Campaign.</li></ul> |
| ID ACS | acsId | <ul><li>È possibile generare un identificatore aggiuntivo: [ID ACS](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).</li><li>Poiché PKey non può essere utilizzato nell’interfaccia utente di Adobe Campaign, si tratta di una soluzione per ottenere un valore univoco generato durante l’inserimento di un record di profilo.</li><li>Il valore può essere generato automaticamente solo se l’opzione è abilitata nella risorsa prima che un record venga inserito in Adobe Campaign.</li></ul> | <ul><li>Questo UUID può essere utilizzato come chiave di riconciliazione.</li><li>Un ID ACS generato automaticamente non può essere utilizzato come riferimento in un flusso di lavoro o in una definizione di pacchetto.</li><li>Questo valore è specifico di un’istanza Adobe Campaign.</li></ul> |

### Chiavi di identificazione {#keys}

Ogni risorsa creata in Adobe Campaign deve avere almeno una [chiave di identificazione](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

Quando crei una risorsa personalizzata, puoi scegliere tra due opzioni:

* Una combinazione di chiave generata automaticamente e chiave personalizzata interna. Questa opzione è interessante se la chiave di sistema è una chiave composita o non un numero intero. Gli interi forniranno prestazioni più elevate nelle tabelle di grandi dimensioni e uniranno le tabelle ad altre.
* Utilizzo della chiave primaria come chiave primaria del sistema esterno. Questa soluzione è in genere preferita in quanto semplifica l’approccio all’importazione e all’esportazione dei dati, con una chiave coerente tra i diversi sistemi.

Le chiavi di identificazione non devono essere utilizzate come riferimento nei flussi di lavoro.

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### Indici {#indexes}

Adobe Campaign aggiunge automaticamente un [index](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) a tutte le chiavi primarie e interne definite in una risorsa.

* L’Adobe consiglia di definire indici aggiuntivi in quanto possono migliorare le prestazioni.
* Tuttavia, non aggiungere troppi indici in quanto utilizzano spazio nel database. Anche numerosi indici possono avere un impatto negativo sulle prestazioni.
* Seleziona con attenzione gli indici da definire.

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### Collegamenti {#links}

La definizione dei collegamenti con altre risorse è presentata in [questa sezione](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).

* Anche se è possibile unire qualsiasi tabella in un flusso di lavoro, l’Adobe consiglia di definire collegamenti comuni tra le risorse direttamente nella definizione della struttura dati.
* Il collegamento deve essere definito in allineamento con i dati effettivi nelle tabelle. Una definizione errata potrebbe influire sui dati recuperati tramite collegamenti, ad esempio duplicando in modo imprevisto i record.
* Assegna al collegamento un nome coerente con il nome della risorsa: il nome del collegamento dovrebbe aiutare a comprendere cosa è la tabella lontana.
* Non denominare un collegamento con &quot;id&quot; come suffisso. Ad esempio, denominalo &quot;transaction&quot; invece di &quot;transactionId&quot;.

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## Prestazioni {#performance}

Per garantire prestazioni migliori in qualsiasi momento, segui le best practice riportate di seguito.

### Raccomandazioni generali {#general-recommendations}

* Evita di utilizzare operazioni come &quot;CONTAINS&quot; nelle query. Se sai cosa è previsto e desideri filtrare, applica la stessa condizione con un &quot;UGUALE A&quot; o altri operatori di filtro specifici.
* Evita l’unione di con campi non indicizzati durante la creazione di dati nei flussi di lavoro.
* Prova ad assicurarti che i processi come l’importazione e l’esportazione avvengano al di fuori dell’orario di lavoro.
* Assicurati che sia presente una pianificazione per tutte le attività giornaliere e attieniti alla pianificazione.
* Se uno o più processi giornalieri non riescono e se è obbligatorio eseguirli nello stesso giorno, assicurarsi che non vi siano processi in conflitto in esecuzione quando il processo manuale viene avviato, in quanto ciò potrebbe influire sulle prestazioni del sistema.
* Assicurati che nessuna della campagna giornaliera venga eseguita durante il processo di importazione o quando viene eseguito un processo manuale.
* Utilizzare una o più tabelle di riferimento anziché duplicare un campo in ogni riga. Quando si utilizzano coppie chiave/valore, è preferibile scegliere una chiave numerica.
* Una stringa breve rimane accettabile. Se in un sistema esterno sono già presenti tabelle di riferimento, il riutilizzo delle stesse faciliterà l’integrazione dei dati con Adobe Campaign.

### Relazioni uno-a-molti {#one-to-many-relationships}

* La progettazione dei dati influisce su usabilità e funzionalità. Se progetti il modello dati con numerose relazioni uno-a-molti, per gli utenti diventa più difficile creare una logica significativa nell’applicazione. La logica del filtro &quot;uno-a-molti&quot; può essere difficile da costruire e comprendere correttamente per gli esperti di marketing non tecnici.
* È utile disporre di tutti i campi essenziali in una tabella, in quanto consente agli utenti di creare query in modo più semplice. A volte è utile anche per le prestazioni duplicare alcuni campi tra le tabelle, se si può evitare un join.
* Alcune funzionalità integrate non potranno fare riferimento a relazioni uno-a-molti, ad esempio Formula di ponderazione delle offerte e Consegne.

### Tabelle grandi {#large-tables}

Di seguito sono riportate alcune best practice da seguire per la progettazione del modello dati utilizzando tabelle di grandi dimensioni e join complessi.

* Riduci il numero di colonne, in particolare identificando quelle non utilizzate.
* Ottimizza le relazioni del modello dati evitando join complessi, ad esempio join su più condizioni e/o colonne.
* Per le chiavi di join, utilizzare sempre dati numerici anziché stringhe di caratteri.
* Riduci il più possibile la profondità di conservazione dei registri. Se hai bisogno di una cronologia più approfondita, puoi aggregare il calcolo e/o gestire tabelle di registro personalizzate per memorizzare una cronologia più ampia.
