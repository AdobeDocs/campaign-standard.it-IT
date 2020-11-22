---
solution: Campaign Standard
product: campaign
title: Ottimizzazione della distribuzione dei messaggi
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: tm+mt
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 6%

---


# Ottimizzare la consegna {#optimize-delivery}

Prima ancora di iniziare a creare le consegne, puoi intraprendere diverse azioni per proteggere e ottimizzare il processo di invio a monte.

La sezione seguente illustra le procedure ottimali e consigliate per una configurazione ottimale di  Adobe Campaign. Seguendo queste pratiche, si riducono al minimo i problemi che si possono affrontare a valle.

## Prestazioni della piattaforma

Diversi fattori possono influire direttamente sulle prestazioni del server e rallentare la piattaforma:

* Numero e tipo di elementi di personalizzazione: la personalizzazione nelle e-mail estrae i dati dal database per ciascun destinatario. Se sono presenti molti elementi di personalizzazione, questo aumenta la quantità di dati necessari per preparare la consegna.  Learn more about email personalization in [this section](../../designing/using/personalization.md)

* Caricamento del server: quando Campaign gestisce contemporaneamente diverse attività, può rallentare le prestazioni. Il server deve coordinare tutti i dati in entrata e in uscita per tutte le consegne, in modo da garantire che i dati siano corretti e puntuali.

   **SUGGERIMENTO** : per evitare questo problema, coordinare la programmazione delle consegne con gli altri membri del team al fine di garantire le migliori prestazioni.

* Esecuzione [del](../../automating/using/about-workflow-execution.md)flusso di lavoro: il monitoraggio dei flussi di lavoro è essenziale per evitare problemi di prestazioni della piattaforma. Seguite le linee guida elencate [in questa pagina](../../automating/using/monitoring-workflow-execution.md). Ulteriori informazioni sono disponibili nella sezione Best practice [per il](../../automating/using/best-practices-workflows.md) flusso di lavoro.

* Puoi sfruttare le funzionalità [del Pannello di controllo](https://docs.adobe.com/content/help/en/control-panel/using/discover-control-panel/key-features.html) campagna per monitorare la tua piattaforma, utilizzando le funzionalità di monitoraggio [delle](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/about-performance-monitoring.html) prestazioni.

## Verifica della configurazione di rete {#network-config}

Per ottimizzare la distribuzione quando si gestiscono e-mail in grandi volumi ed evitare errori per uno spammer, assicurarsi di disporre di una configurazione di rete legittima che non tenti di nascondere l&#39;identità del server.

**Suggerimento**:  Utilizza un indirizzo mittente trasparente corrispondente al sito Web del tuo marchio. Ad esempio, la società TravelAgency gestisce la catena alberghiera di Valentino. Possiede il dominio valentino.com per il suo sito web. Per promuovere il Valentino hotel a Parigi, utilizza il sottodominio paris.valentino.com. Pertanto, un indirizzo mittente rilevante può essere hotel@paris.valentino.com.

## Gestione del recapito messaggi {#deliverability-management}

Per raggiungere la casella in entrata dei destinatari senza rimbalzare o contrassegnare come spam, è necessario migliorare il tasso di recapito dei messaggi.

* Che cos&#39;è l&#39;erogabilità?

   * Si riferisce ai fattori di un&#39;e-mail che ne determinano la capacità di essere accettata dal server del destinatario. I provider di servizi Internet (Internet Service Provider) escludono i messaggi e-mail che identificano come SPAM o impediscono il download di immagini. Se determinano che un determinato dominio sta inviando troppe e-mail, verrà impostato un limite al numero di e-mail che verranno accettate da quel mittente.

   * Quando controlli la tua e-mail per verificare la recapito, vuoi concentrarti su quattro categorie principali: qualità dei dati, messaggi e contenuti, infrastruttura di invio e reputazione. Per informazioni più approfondite sull&#39;argomento, consulta [questa sezione](../../sending/using/about-deliverability.md).

* Quando avviate una nuova piattaforma, applicate le raccomandazioni dettagliate [in questa pagina](../../sending/using/starting-new-platform.md).

* Contattate il rappresentante del Adobe  per assistenza.

## Gestione della quarantena {#quarantine-management}

È nel vostro interesse mantenere buoni processi di gestione della quarantena.

Quando iniziate a inviare e-mail su una nuova piattaforma, potete utilizzare un elenco di indirizzi non completi. Se si inviano a indirizzi non validi o a indirizzi per le chat (le caselle di posta solo create per gli spammers ingannevoli), questo inizierà a ridurre la reputazione della piattaforma. Una buona gestione della quarantena aiuta a: mantenere la qualità degli indirizzi, evitare elenchi Bloccati da parte dei provider di accesso a Internet e ridurre il tasso di errore, velocizzare le consegne e la velocità di trasmissione.

**Suggerimenti**

* I destinatari i cui indirizzi sono posti in quarantena sono esclusi per impostazione predefinita durante l&#39;analisi del recapito: non sono mirati. In questo modo le consegne sono più rapide, poiché il tasso di errore ha un effetto significativo sulla velocità di consegna. Un indirizzo e-mail può essere messo in quarantena, ad esempio se la casella in entrata è piena o se l’indirizzo non esiste. [Ulteriori informazioni](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

*  Adobe Campaign gestisce gli indirizzi errati in base al tipo di errore restituito. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../sending/using/understanding-quarantine-management.md).

* Alcuni provider di accesso a Internet considerano automaticamente le e-mail come spam se il tasso di indirizzi non validi è troppo alto. Quarantine quindi consente di evitare di essere aggiunti al elenco Bloccati da questi provider.

* La gestione delle scorte contribuirà anche a ridurre i costi di invio di SMS escludendo numeri di telefono errati dalle consegne.

## Doppio meccanismo di consenso {#double-opt-in}

Per evitare di inviare messaggi a indirizzi non validi, limitare le comunicazioni non corrette e migliorare la reputazione del mittente,  Adobe consiglia di implementare un meccanismo di doppio consenso per la conferma post-iscrizione. Questo aiuta a garantire che il destinatario si sia iscritto intenzionalmente.

I dettagli per l&#39;attuazione di questo meccanismo sono descritti in [questa sezione](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Per saperne di più, [iniziate a usare profili e audience](../../audiences/using/get-started-profiles-and-audiences.md).
