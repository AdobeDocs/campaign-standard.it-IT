---
title: Informazioni sul recapito messaggi in Adobe Campaign Standard
description: Scopri i concetti e le best practice relativi al recapito messaggi, nonché gli strumenti offerti da Adobe Campaign Standard per ottimizzare l’invio delle consegne.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 5e523519-7192-4031-9d96-559af23074d9
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '676'
ht-degree: 6%

---

# Che cos’è il recapito messaggi{#about-deliverability}

Il recapito messaggi consente di misurare il successo delle campagne che raggiungono la casella in entrata dei destinatari senza che questi vengano recapitati o contrassegnati come spam. [Scopri perché il recapito messaggi è importante](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html#why-deliverability-matters).

Più precisamente, il recapito messaggi e-mail si riferisce all’insieme di caratteristiche che determinano la capacità di un messaggio di raggiungere la sua destinazione, tramite un indirizzo e-mail personale, in un breve lasso di tempo e con la qualità prevista in termini di contenuto e formato. <!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

Per informazioni più approfondite sulla consegna dei messaggi e per ulteriori informazioni sui termini, i concetti e gli approcci chiave, consulta [Guida alle procedure consigliate per la consegna dei messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it).

## Come migliorare il recapito messaggi {#deliverability-key-points}

I problemi di recapito dei messaggi sono solitamente legati a misure di protezione contro lo spam implementate dai provider di servizi Internet e dagli amministratori del server di posta.

* Per raccomandazioni generali su come progettare campagne di e-mail marketing di successo, consulta [Strategia e definizione di consegna](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html).

* Per raccomandazioni più specifiche su come ottimizzare il recapito dei messaggi e-mail in Adobe Campaign, si consiglia di utilizzare le best practice elencate in questa sezione.

>[!NOTE]
>
>Poiché gli ISP sono obbligati a sviluppare continuamente nuove sofisticate tecniche di filtro per proteggere i propri clienti dagli spammer, la consegna delle e-mail è caratterizzata da criteri e regole in continua evoluzione. Assicurati di fare riferimento a [Guida alle procedure consigliate per la consegna dei messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it) che viene regolarmente aggiornato.

### Percentuale di consegna

Il tasso di recapito messaggi è il numero di messaggi che raggiungono le caselle in entrata dei destinatari rispetto al numero di messaggi consegnati. Per migliorare il recapito messaggi, puoi aumentare questo tasso.

Con Adobe Campaign, il tasso di consegna dipende da numerosi fattori, in particolare:

* Corretta configurazione delle istanze: contatta il rappresentante dell’Adobe per assistenza.
* Configurazione di rete legittima: vedi [questa sezione](../../sending/using/optimize-delivery.md#network-config) e [Configurazione e strategia del dominio](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#domain-setup-and-strategy).
* La reputazione del tuo indirizzo IP: vedi [Strategia IP](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#ip-strategy).
* Qualità degli indirizzi target: vedi [Gestione della quarantena](../../sending/using/optimize-delivery.md#quarantine-management).
* Basso [reclami](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html) e [mancato recapito permanente](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces) tariffe.
* Contenuto del messaggio: vedi [Controllo del contenuto delle e-mail](../../sending/using/control-email-content.md).
* Autenticazione dei messaggi (SPF, DKIM, DMARC): vedi [questa sezione](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).
* Reputazione del mittente: per informazioni sulla valutazione della reputazione di un mittente da parte degli ISP principali, consulta [questa sezione](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html).

## Strumenti di recapito messaggi della campagna {#deliverability-tools}

Adobe Campaign fornisce una serie di strumenti per monitorare e migliorare le prestazioni di consegna dei messaggi della piattaforma. Questa pagina evidenzia anche i principi principali da tenere presenti per ottimizzare il recapito dei messaggi durante l’utilizzo di Campaign.

### Crea il messaggio con attenzione

Durante la configurazione, la progettazione e il test del messaggio, assicurati di seguire le best practice indicate nelle sezioni elencate di seguito. L’utilizzo di tutte le funzioni fornite da Adobe Campaign consente di migliorare il recapito messaggi.

* [Best practice per la consegna](../../sending/using/delivery-best-practices.md)
* [Controllo dei contenuti dell’e-mail](../../sending/using/control-email-content.md)
* [Anteprima dei messaggi](../../sending/using/previewing-messages.md)
* [Invio di bozze](../../sending/using/sending-proofs.md)

### Verificare il consenso tramite il doppio consenso {#double-opt-in}

Per evitare l’invio di messaggi a indirizzi non validi, limitare le comunicazioni improprie e migliorare la reputazione del mittente, l’Adobe consiglia di implementare un doppio meccanismo di consenso. Questo ti consente di garantire che i destinatari si siano abbonati intenzionalmente.

Per ulteriori informazioni, consulta [Informazioni su consenso e rinuncia in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Per ulteriori informazioni sulle best practice per la raccolta di dati dai clienti, consulta [Guida alle procedure consigliate per la consegna dei messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html#data-quality-and-hygiene).

### Gestione della quarantena

Adobe Campaign gestisce un elenco che raccoglie i reclami e i mancati recapiti non recapitati di posta indesiderata, i mancati recapiti permanenti e i mancati recapiti non permanenti che si verificano in modo coerente.

Per proteggere il recapito messaggi, i destinatari i cui indirizzi sono in tale elenco sono esclusi per impostazione predefinita da tutte le consegne future, perché l’invio a questi contatti potrebbe danneggiare la reputazione del mittente.

Alcuni provider di accesso a Internet considerano automaticamente le e-mail come spam se il tasso di indirizzi non validi è troppo alto. La quarantena consente quindi di evitare di essere aggiunti al elenco Bloccati da parte di questi provider.

Per ulteriori informazioni, consulta le sezioni seguenti:

* [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Informazioni sulla gestione della quarantena](../../sending/using/understanding-quarantine-management.md)
* [Quarantena e inserisco nell&#39;elenco Bloccati di](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### Utilizzare strumenti di monitoraggio e reporting

Utilizza le funzioni offerte da Adobe Campaign per monitorare il recapito messaggi.

Adobe Campaign consente di controllare le prestazioni delle consegne tramite una serie di indicatori in tempo reale incorporati. <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->Puoi anche creare rapporti completamente personalizzabili e in tempo reale per ottenere informazioni approfondite sulle consegne.

Per ulteriori informazioni, consulta le sezioni seguenti:

* [Monitoraggio del recapito messaggi](../../sending/using/monitor-deliverability.md)
  <!--[Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)-->
* [Ricezione degli avvisi in caso di errori](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporti dinamici](../../reporting/using/about-dynamic-reports.md)

<!--## General recommendations

NOT SURE TO KEEP

Here are a few additional recommendations when it comes to deliverability.

### Send to valid addresses {#valid-addresses}

Spammers often use address generators based on lists of frequent names and first names; in addition, they rarely process technical notifications sent back by mail servers. A high rate of invalid addresses is often interpreted as a sign of spam.

Double opt-in mechanisms and effective handling of technical bounce messages make it possible to avoid this.

### Reduce complaint rate {#reduce-complaint-rate}

ISPs usually have a prominent means of reporting a received message as spam. This makes it possible to identify unreliable sources. By rapidly honoring opt-out requests, making regular use of a given list, verifying consent through a double opt-in system, and implementing feedback loops, you can reduce complaint rates.

<!--Sending to honeypot addresses {#honeypot-addresses}
ISPs and other organizations (refer to https://www.projecthoneypot.org/) make use of mailboxes that do not correspond to physical persons but are created simply to trick spammers. These so-called "honey pot" addresses are published on the Web in order to be collected by spambots and thus catch illegitimate senders. The use of a double opt-in mechanism precludes this sort of address being added to a list. When using a third-party list, you must be sure of the methods employed by its maintainer.-->

<!--## Sending on a regular basis {#regular-deliveries}

Spammers make programmed deliveries to maintain their reputation over time. They sometimes need to adapt their marketing plan to meet the best practices imposed by the ISPs and so, after a peak in reputation (ramp-up), they configure regular deliveries.-->
