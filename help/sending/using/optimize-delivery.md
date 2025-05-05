---
title: Ottimizzare la consegna dei messaggi
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Scopri come proteggere e ottimizzare il processo di invio a monte.
feature: Deliverability
role: User
level: Intermediate
exl-id: 28b0cf6d-c1f1-4d55-b9bc-0d6bfb063471
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 4%

---

# Ottimizzare la consegna {#optimize-delivery}

Prima ancora di iniziare a creare le consegne, puoi intraprendere diverse azioni per proteggere e ottimizzare il processo di invio a monte.

La sezione seguente illustra le best practice e le procedure consigliate per la configurazione ottimale di Adobe Campaign. L’aderenza a queste procedure riduce al minimo i problemi che potresti riscontrare a valle.

## Prestazioni della piattaforma

Diversi fattori possono influire direttamente sulle prestazioni del server e rallentare la piattaforma:

* Il numero e il tipo di elementi di personalizzazione: la personalizzazione nelle e-mail estrae dati dal database per ogni destinatario. Se sono presenti molti elementi di personalizzazione, aumenta la quantità di dati necessari per preparare la consegna.  Ulteriori informazioni sulla personalizzazione delle e-mail in [questa sezione](../../designing/using/personalization.md)

* Caricamento del server: quando Campaign gestisce più attività diverse contemporaneamente, può rallentare le prestazioni. Il server deve coordinare tutti i dati in entrata e in uscita per tutte le consegne per garantire che i dati siano corretti e puntuali.

  **SUGGERIMENTO** - Per evitare questo problema, coordina la pianificazione delle consegne con gli altri membri del tuo team per garantire le migliori prestazioni.

* [esecuzione del flusso di lavoro](../../automating/using/about-workflow-execution.md): il monitoraggio dei flussi di lavoro è essenziale per evitare problemi di prestazioni della piattaforma. Segui le linee guida elencate [in questa pagina](../../automating/using/monitoring-workflow-execution.md). Ulteriori informazioni sono disponibili nella sezione [best practice per i flussi di lavoro](../../automating/using/best-practices-workflows.md).

* Puoi sfruttare le [funzionalità di Pannello di controllo Campaign di Campaign](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=it) per monitorare la piattaforma, utilizzando le [funzionalità di monitoraggio delle prestazioni](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=it).

## Verifica della configurazione di rete {#network-config}

Per ottimizzare la consegna quando gestisci le e-mail in grandi volumi ed evitare di essere scambiato per uno spammer, assicurati di disporre di una configurazione di rete legittima che non tenti di nascondere l’identità del server.

**Suggerimento**: utilizza un indirizzo mittente trasparente corrispondente al sito Web del tuo marchio. Ad esempio, la società TravelAgency gestisce la catena alberghiera Valentino. È il proprietario del dominio valentino.com per il suo sito web. Per promuovere l&#39;hotel Valentino a Parigi, utilizza il sottodominio paris.valentino.com. Pertanto, un indirizzo del mittente pertinente può essere hotel@paris.valentino.com.

## Gestione del recapito messaggi {#deliverability-management}

Per raggiungere la casella in entrata dei destinatari senza che vengano generati o contrassegnati come spam, devi migliorare il tasso di recapito dei messaggi.

* Che cos’è il recapito messaggi?

   * Si riferisce ai fattori di un’e-mail che determinano la sua capacità di essere accettata dal server di un destinatario. Gli ISP (Internet Service Provider) filtrano le e-mail che identificano come SPAM, oppure bloccano il download delle immagini. Se determinano che un determinato dominio sta inviando troppe e-mail, imposteranno un limite al numero di e-mail che accetteranno da quel mittente.

   * Durante il controllo della consegna delle e-mail, desideri concentrarti su quattro categorie principali: qualità dei dati, messaggio e contenuto, infrastruttura di invio e reputazione. Per ulteriori informazioni su questo argomento, consulta [questa sezione](../../sending/using/about-deliverability.md).

* All&#39;avvio di una nuova piattaforma, applica i consigli dettagliati in [questa pagina](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/switching-email-platforms.html?lang=it#transition-process).

* Contatta il rappresentante del tuo Adobe per assistenza.

## Gestione della quarantena {#quarantine-management}

È nel tuo interesse mantenere processi di gestione della quarantena efficaci.

Quando inizi a inviare e-mail su una nuova piattaforma, puoi utilizzare un elenco di indirizzi non completamente qualificati. Se invii a indirizzi non validi o a indirizzi honeypot (cassette postali create solo per ingannare gli spammer), questo comincerà a ridurre la reputazione della tua piattaforma. Una buona gestione della quarantena aiuta a: mantenere la qualità dell’indirizzo, evitare l’inserisco nell&#39;elenco Bloccati da parte dei provider di accesso a Internet e ridurre il tasso di errore, velocizzando le consegne e la velocità effettiva.

**Suggerimenti**

* I destinatari i cui indirizzi sono in quarantena sono esclusi per impostazione predefinita durante l’analisi della consegna: non sono oggetto di targeting. In questo modo le consegne saranno più rapide, poiché il tasso di errore ha un effetto significativo sulla velocità di consegna. Un indirizzo e-mail può essere messo in quarantena, ad esempio quando la casella in entrata è piena o se l’indirizzo non esiste. [Ulteriori informazioni](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

* Adobe Campaign gestisce gli indirizzi errati in base al tipo di errore restituito. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../sending/using/understanding-quarantine-management.md).

* Alcuni provider di accesso a Internet considerano automaticamente le e-mail come spam se il tasso di indirizzi non validi è troppo alto. La quarantena consente quindi di evitare che questi provider aggiungano altri elementi al elenco Bloccati del sistema di protezione.

* La gestione delle quarantene contribuirà inoltre a ridurre i costi di invio degli SMS escludendo numeri di telefono errati dalle consegne.

## Doppio meccanismo di consenso {#double-opt-in}

Per evitare l’invio di messaggi a indirizzi non validi, limitare le comunicazioni improprie e migliorare la reputazione del mittente, l’Adobe consiglia di implementare un doppio meccanismo di consenso per la conferma dopo l’abbonamento. Questo aiuta a garantire che un destinatario si sia iscritto intenzionalmente.

I dettagli relativi all&#39;implementazione di questo meccanismo sono descritti in [questa sezione](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Ulteriori informazioni in [Introduzione a profili e tipi di pubblico](../../audiences/using/get-started-profiles-and-audiences.md).
