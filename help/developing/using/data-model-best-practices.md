---
title: Best practice relative ai modelli di dati in Adobe Campaign Standard
description: Scopri le best practice per la progettazione del modello dati Adobe Campaign Standard.
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

Questo documento delinea i consigli chiave durante la progettazione del modello dati Adobe Campaign.


>[!NOTE]
>
>Per creare e modificare le risorse per estendere il modello dati predefinito di Adobe Campaign, consulta [questa sezione](../../developing/using/key-steps-to-add-a-resource.md).
>
>Puoi trovare una rappresentazione del modello dati delle risorse integrate in [questa pagina](../../developing/using/datamodel-introduction.md).

## Panoramica {#overview}

Il sistema Adobe Campaign è estremamente flessibile e può essere esteso oltre l&#39;implementazione iniziale. Tuttavia, mentre le possibilità sono infinite, è fondamentale prendere decisioni sagge e creare solide basi per iniziare a progettare il modello dati.

Questo documento fornisce casi d’uso comuni e best practice per imparare a eseguire correttamente l’architettura dello strumento Adobe Campaign.

## Architettura del modello dati {#data-model-architecture}

Adobe Campaign Standard è un potente sistema di gestione delle campagne cross-channel che consente di allineare le strategie online e offline per creare esperienze cliente personalizzate.

### Approccio incentrato sul cliente {#customer-centric-approach}

Mentre la maggior parte dei provider di servizi e-mail comunica ai clienti con un approccio incentrato sull’elenco, Adobe Campaign si basa su un database relazionale per sfruttare una visione più ampia dei clienti e dei loro attributi.

Questo approccio incentrato sul cliente è mostrato nel grafico seguente. La **Profilo** la risorsa in grigio rappresenta la tabella cliente principale intorno alla quale viene creato tutto:

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

Per decidere se un attributo sarebbe necessario o meno in Adobe Campaign, determina se rientrerebbe in una di queste categorie:
* Attributo utilizzato per **segmentazione**
* Attributo utilizzato per **processi di gestione dei dati** (calcolo aggregato, ad esempio)
* Attributo utilizzato per **personalizzazione**
* Attributo utilizzato per **reporting** (è possibile creare rapporti basati sui dati di profilo personalizzati)

Se non rientra in nessuno di questi, è molto probabile che questo attributo non sarà necessario in Adobe Campaign.

### Tipi di dati {#data-types}

Per garantire una buona architettura e prestazioni del sistema, segui le best practice riportate di seguito per configurare i dati in Adobe Campaign:
* La lunghezza di un campo stringa deve sempre essere definita con la colonna . Per impostazione predefinita, la lunghezza massima in Adobe Campaign è di 255 caratteri, ma l’Adobe consiglia di mantenere il campo più breve se sai già che la dimensione non supererà una lunghezza più breve.
* È accettabile avere un campo più breve in Adobe Campaign rispetto al sistema di origine se si è certi che la dimensione nel sistema di origine è stata sopravvalutata e non verrà raggiunta. Ciò potrebbe significare una stringa più breve o un numero intero più piccolo in Adobe Campaign.

## Configurazione della struttura dati {#configuring-data-structure}

Questa sezione descrive le best practice per [configurazione della struttura dati di una risorsa](../../developing/using/configuring-the-resource-s-data-structure.md).

### Identificatori {#identifiers}

Le risorse Adobe Campaign hanno tre identificatori ed è possibile aggiungere un identificatore aggiuntivo.

Nella tabella seguente sono descritti questi identificatori e il loro scopo.

>[!NOTE]
>
>Il nome visualizzato corrisponde al nome del campo visualizzato all’utente tramite l’interfaccia utente di Adobe Campaign. Il nome tecnico è il nome effettivo del campo nella definizione della risorsa (e il nome della colonna della tabella).

| Nome visualizzato | Nome tecnico | Descrizione | Best practice |
|--- |--- |--- |--- |
|  | PKey | <ul><li>PKey è la chiave primaria fisica di una tabella Adobe Campaign.</li><li>Questo identificatore è in genere univoco per una specifica istanza di Adobe Campaign.</li><li>In Adobe Campaign Standard, questo valore non è visibile all’utente finale (eccetto negli URL).</li></ul> | <ul><li>Tramite il [Sistema API](../../api/using/get-started-apis.md), è possibile recuperare un valore PKey (che è un valore generato/con hash, non la chiave fisica).</li><li>È consigliabile non utilizzarlo per altri scopi se non per recuperare, aggiornare o eliminare record tramite API.</li></ul> |
| ID | name o internalName | <ul><li>Queste informazioni sono un identificatore univoco di un record in una tabella. Questo valore può essere aggiornato manualmente.</li><li>Questo identificatore mantiene il suo valore quando viene distribuito in un’istanza diversa di Adobe Campaign. Deve avere un nome diverso dal valore generato per essere esportabile tramite un pacchetto.</li><li>Questa non è la chiave primaria effettiva della tabella.</li></ul> | <ul><li>Non utilizzare caratteri speciali come lo spazio &quot;&quot;, la semicolonna &quot;:&quot; o il trattino &quot;-&quot;.</li><li>Tutti questi caratteri verranno sostituiti da un carattere di sottolineatura &quot;_&quot; (carattere consentito). Ad esempio, &quot;abc-def&quot; e &quot;abc:def&quot; vengono memorizzati come &quot;abc_def&quot; e si sovrascrivono a vicenda.</li></ul> |
| Etichetta | label | <ul><li>L’etichetta è l’identificatore aziendale di un oggetto o record in Adobe Campaign.</li><li>Questo oggetto consente spazi e caratteri speciali.</li><li>Non garantisce l&#39;unicità di un documento.</li></ul> | <ul><li>È consigliabile determinare una struttura per le etichette degli oggetti.</li><li>Questa è la soluzione più semplice da usare per identificare un record o un oggetto per un utente Adobe Campaign.</li></ul> |
| ID ACS | acsId | <ul><li>È possibile generare un identificatore aggiuntivo: la [ID ACS](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).</li><li>Poiché non è possibile utilizzare PKey nell’interfaccia utente di Adobe Campaign, si tratta di una soluzione per ottenere un valore univoco generato durante l’inserimento di un record di profilo.</li><li>Il valore può essere generato automaticamente solo se l’opzione è abilitata nella risorsa prima che un record venga inserito in Adobe Campaign.</li></ul> | <ul><li>Questo UUID può essere utilizzato come chiave di riconciliazione.</li><li>Un ID ACS generato automaticamente non può essere utilizzato come riferimento in un flusso di lavoro o in una definizione di pacchetto.</li><li>Questo valore è specifico per un&#39;istanza di Adobe Campaign.</li></ul> |

### Chiavi di identificazione {#keys}

Ogni risorsa creata in Adobe Campaign deve avere almeno un’unica [chiave di identificazione](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

Quando crei una risorsa personalizzata, hai due opzioni:

* Combinazione di chiave generata automaticamente e chiave personalizzata interna. Questa opzione è interessante se la chiave di sistema è una chiave composita o non un numero intero. I numeri interi forniranno prestazioni più elevate nei grandi tavoli e uniranno ad altri tavoli.
* Utilizzo della chiave primaria come chiave primaria del sistema esterno. Questa soluzione è solitamente preferita in quanto semplifica l&#39;approccio all&#39;importazione e all&#39;esportazione di dati, con una chiave coerente tra i diversi sistemi.

Le chiavi di identificazione non devono essere utilizzate come riferimento nei flussi di lavoro.

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### Indici {#indexes}

Adobe Campaign aggiunge automaticamente un [index](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) a tutte le chiavi primarie e interne definite in una risorsa.

* Adobe consiglia di definire indici aggiuntivi in quanto potrebbero migliorare le prestazioni.
* Tuttavia, non aggiungere troppi indici in quanto utilizzano spazio nel database. Anche numerosi indici possono avere un impatto negativo sulle prestazioni.
* Seleziona con attenzione gli indici da definire.

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### Collegamenti {#links}

La definizione dei collegamenti con altre risorse è presentata in [questa sezione](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).

* Sebbene sia possibile unire qualsiasi tabella in un flusso di lavoro, Adobe consiglia di definire collegamenti comuni tra le risorse direttamente nella definizione della struttura dati.
* Il collegamento deve essere definito in allineamento con i dati effettivi nelle tabelle. Una definizione errata potrebbe influire sui dati recuperati tramite i collegamenti, ad esempio duplicando inaspettatamente i record.
* Assegna al collegamento un nome coerente con il nome della risorsa: il nome del collegamento dovrebbe aiutare a comprendere cosa sia la tabella lontana.
* Non denominare un collegamento con &quot;id&quot; come suffisso. Ad esempio, denominalo &quot;transaction&quot; anziché &quot;transactionId&quot;.

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## Prestazioni {#performance}

Per garantire prestazioni migliori in qualsiasi momento, segui le best practice riportate di seguito.

### Raccomandazioni generali {#general-recommendations}

* Evitare di utilizzare operazioni come &quot;CONTAINS&quot; nelle query. Se sai cosa ci si aspetta e vuoi filtrare, applica la stessa condizione con un operatore di filtro &quot;EQUAL TO&quot; o con altri operatori di filtro specifici.
* Evita di unirsi a campi non indicizzati durante la creazione di dati nei flussi di lavoro.
* Cerca di assicurarsi che i processi come l&#39;importazione e l&#39;esportazione avvengano al di fuori dell&#39;orario di lavoro.
* Assicurati che ci sia una pianificazione per tutte le attività quotidiane e attieniti alla pianificazione.
* Se uno o pochi dei processi giornalieri non riescono e se è obbligatorio eseguirlo lo stesso giorno, assicurati che non vi siano processi in conflitto in esecuzione quando il processo manuale viene avviato in quanto ciò potrebbe influire sulle prestazioni del sistema.
* Assicurati che nessuna delle campagne giornaliere venga eseguita durante il processo di importazione o quando viene eseguito un processo manuale.
* Utilizzare una o più tabelle di riferimento anziché duplicare un campo in ogni riga. Quando si utilizzano coppie chiave/valore, è preferibile scegliere una chiave numerica.
* Una stringa breve rimane accettabile. Nel caso in cui le tabelle di riferimento siano già presenti in un sistema esterno, il riutilizzo dello stesso agevolerà l’integrazione dei dati con Adobe Campaign.

### Relazioni uno-a-molti {#one-to-many-relationships}

* La progettazione dei dati influisce su usabilità e funzionalità. Se si progetta il modello dati con molte relazioni uno-a-molti, risulta più difficile per gli utenti creare una logica significativa nell’applicazione. La logica di filtro uno-a-molti può essere difficile per gli addetti al marketing non tecnici creare e comprendere correttamente.
* È opportuno disporre di tutti i campi essenziali in una tabella, in quanto semplifica la creazione delle query da parte degli utenti. A volte è anche utile che le prestazioni duplichino alcuni campi tra le tabelle, se è possibile evitare un join.
* Alcune funzionalità integrate non saranno in grado di fare riferimento a relazioni uno-a-molti, ad esempio, formula di ponderazione delle offerte e consegne.

### Tabelle grandi {#large-tables}

Di seguito sono riportate alcune best practice da seguire per progettare il modello dati utilizzando tabelle di grandi dimensioni e join complessi.

* Ridurre il numero di colonne, in particolare identificando quelle inutilizzate.
* Ottimizza le relazioni del modello dati evitando join complessi, ad esempio join su più condizioni e/o più colonne.
* Per le chiavi di join, utilizzare sempre dati numerici anziché stringhe di caratteri.
* Riduci quanto più possibile la profondità di conservazione del registro. Se hai bisogno di una cronologia più approfondita, puoi aggregare il calcolo e/o gestire tabelle di log personalizzate per memorizzare una cronologia più grande.
