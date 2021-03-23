---
solution: Campaign Standard
product: campaign
title: Ottimizzare la consegna dei messaggi
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Scopri come proteggere e ottimizzare il processo di invio a monte.
feature: Consegna
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 6%

---


# Ottimizzare la consegna {#optimize-delivery}

Prima ancora di iniziare la creazione delle consegne, puoi intraprendere diverse azioni per proteggere e ottimizzare il processo di invio a monte.

La sezione seguente illustra le best practice e le procedure consigliate per una configurazione ottimale di Adobe Campaign. Seguendo queste pratiche, i problemi che potresti riscontrare a valle verranno ridotti al minimo.

## Prestazioni della piattaforma

Diversi fattori possono influenzare direttamente le prestazioni del server e rallentare la piattaforma:

* Numero e tipo di elementi di personalizzazione: la personalizzazione nelle e-mail estrae i dati dal database per ciascun destinatario. Se sono presenti molti elementi di personalizzazione, ciò aumenta la quantità di dati necessari per preparare la consegna.  Ulteriori informazioni sulla personalizzazione delle e-mail in [questa sezione](../../designing/using/personalization.md)

* Caricamento server: quando Campaign gestisce contemporaneamente diverse attività, può rallentare le prestazioni. Il server deve coordinare tutti i dati in entrata e in uscita per tutte le consegne, in modo da garantire che i dati siano corretti e puntuali.

   **SUGGERIMENTO** : per evitare questo problema, coordina la pianificazione delle consegne con gli altri membri del team per garantire le migliori prestazioni.

* L&#39; [esecuzione del flusso di lavoro](../../automating/using/about-workflow-execution.md): il monitoraggio dei flussi di lavoro è essenziale per evitare problemi di prestazioni della piattaforma. Segui le linee guida elencate [in questa pagina](../../automating/using/monitoring-workflow-execution.md). Ulteriori informazioni sono disponibili nella sezione [best practice per i flussi di lavoro](../../automating/using/best-practices-workflows.md) .

* Puoi sfruttare le funzionalità [Pannello di controllo Campaign](https://docs.adobe.com/content/help/en/control-panel/using/discover-control-panel/key-features.html) per monitorare la piattaforma, utilizzando le funzionalità [monitoraggio delle prestazioni](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/about-performance-monitoring.html).

## Verifica della configurazione di rete {#network-config}

Per ottimizzare la consegna quando gestisci le e-mail in grandi volumi ed evitare errori per uno spammer, assicurati di disporre di una configurazione di rete legittima che non tenti di nascondere l’identità del server.

**Suggerimento**: Utilizza un indirizzo mittente trasparente corrispondente al sito web del tuo marchio. Ad esempio, la società TravelAgency gestisce la catena alberghiera Valentino. Possiede il dominio valentino.com per il suo sito web. Per promuovere il Valentino hotel a Parigi, utilizza il sottodominio paris.valentino.com. Pertanto, un indirizzo del mittente pertinente può essere hotel@paris.valentino.com.

## Gestione del recapito messaggi {#deliverability-management}

Per raggiungere la casella in entrata dei destinatari senza rimbalzare o contrassegnare come spam, devi migliorare il tasso di recapito dei messaggi.

* Che cos’è il recapito messaggi?

   * Si riferisce ai fattori di un’e-mail che determinano la sua capacità di essere accettata dal server di un destinatario. Gli ISP (Internet Service Provider) filtrano le e-mail che identificano come SPAM o impediscono il download delle immagini. Se determinano che un determinato dominio sta inviando troppe e-mail, imposteranno un limite al numero di e-mail che accetteranno da quel mittente.

   * Quando controlli l&#39;e-mail per il recapito messaggi, vuoi concentrarti su quattro categorie principali: qualità dei dati, messaggi e contenuti, infrastruttura di invio e reputazione. Per informazioni più approfondite su questo argomento, consulta [questa sezione](../../sending/using/about-deliverability.md).

* Quando avvii una nuova piattaforma, applica le raccomandazioni dettagliate in [questa pagina](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/switching-email-platforms.html#transition-process).

* Contatta il tuo rappresentante Adobe per assistenza.

## Gestione della quarantena {#quarantine-management}

È nel tuo interesse mantenere buoni processi di gestione della quarantena.

Quando inizi a inviare e-mail su una nuova piattaforma, puoi utilizzare un elenco di indirizzi non completamente qualificati. Se invii a indirizzi non validi o a indirizzi di articoli da miele (caselle di posta create solo per gli spammer ingannatori), questo inizierà a diminuire la reputazione della tua piattaforma. I buoni processi di gestione della quarantena aiutano a: mantenere la qualità degli indirizzi, evitare elenchi Bloccati da parte dei provider di accesso a Internet e ridurre il tasso di errore, velocizzando le consegne e il throughput.

**Suggerimenti**

* I destinatari i cui indirizzi sono messi in quarantena sono esclusi per impostazione predefinita durante l’analisi della consegna: non sono mirati. In questo modo le consegne sono più rapide, poiché il tasso di errore ha un effetto significativo sulla velocità di consegna. È possibile mettere in quarantena un indirizzo e-mail, ad esempio se la casella in entrata è piena o se l’indirizzo non esiste. [Ulteriori informazioni](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

* Adobe Campaign gestisce gli indirizzi errati in base al tipo di errore restituito. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../sending/using/understanding-quarantine-management.md).

* Alcuni provider di accesso a Internet considerano automaticamente le e-mail come spam se il tasso di indirizzi non validi è troppo alto. La quarantena ti consente quindi di evitare di essere aggiunta al elenco Bloccati da questi provider.

* La gestione delle quarantena aiuterà anche a ridurre i costi di invio degli SMS escludendo numeri di telefono errati dalle consegne.

## Doppio meccanismo di consenso {#double-opt-in}

Per evitare l’invio di messaggi a indirizzi non validi, limitare le comunicazioni non corrette e migliorare la reputazione del mittente, l’Adobe consiglia di implementare un doppio meccanismo di consenso per la conferma post-abbonamento. In questo modo il destinatario si è iscritto intenzionalmente.

I dettagli sull&#39;implementazione di questo meccanismo sono descritti in [questa sezione](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Ulteriori informazioni in [Guida introduttiva a profili e tipi di pubblico](../../audiences/using/get-started-profiles-and-audiences.md).
