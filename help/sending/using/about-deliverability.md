---
solution: Campaign Standard
product: campaign
title: Informazioni sul recapito messaggi in Adobe Campaign Standard
description: Scopri i concetti e le best practice relativi al recapito messaggi e gli strumenti offerti da Adobe Campaign Standard per ottimizzare l’invio delle consegne.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Recapito messaggi
role: User
level: Intermediate
exl-id: 5e523519-7192-4031-9d96-559af23074d9
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 8%

---

# Che cos’è il recapito messaggi{#about-deliverability}

Il recapito messaggi consente di misurare il successo delle campagne che raggiungono la casella in entrata dei destinatari senza rimbalzare o contrassegnare come spam. [Scopri perché il recapito messaggi è importante](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html#why-deliverability-matters).

Più precisamente, il recapito messaggi e-mail si riferisce al set di caratteristiche che determinano la capacità di un messaggio di raggiungere la sua destinazione, tramite un indirizzo e-mail personale, in un breve periodo di tempo e con la qualità prevista in termini di contenuto e formato. <!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

Per informazioni più approfondite sul recapito messaggi e per ulteriori informazioni su termini, concetti e approcci chiave per il recapito messaggi, consulta la [Guida alle best practice per il recapito messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it).

## Come migliorare il recapito messaggi {#deliverability-key-points}

I problemi di recapito sono solitamente collegati a misure di protezione contro lo spam implementate da fornitori di servizi Internet e amministratori di server di posta.

* Per raccomandazioni generali su come progettare campagne di marketing e-mail di successo, consulta [Strategia di recapito messaggi e definizione](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html).

* Per consigli più specifici su come ottimizzare il recapito messaggi delle e-mail di Adobe Campaign, si consiglia di utilizzare le best practice elencate in questa sezione.

>[!NOTE]
>
>Poiché gli ISP sono obbligati a sviluppare continuamente nuove tecniche di filtraggio sofisticate per proteggere i loro clienti dagli spammer, la consegna delle e-mail è caratterizzata da criteri e regole in continua evoluzione. Assicurati di fare riferimento alla [Guida alle best practice per il recapito messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html) che viene aggiornata regolarmente.

### Tasso di consegna

Il tasso di recapito messaggi è il numero di messaggi che hanno colpito le caselle in entrata dei destinatari rispetto al numero di messaggi inviati. Per migliorare il recapito messaggi, puoi lavorare per aumentare questo tasso.

Con Adobe Campaign, il tasso di consegna dipende da numerosi fattori, in particolare:

* Configurazione corretta delle istanze: contatta il tuo rappresentante Adobe per assistenza.
* Configurazione di rete legittima: consulta [questa sezione](../../sending/using/optimize-delivery.md#network-config) e [Configurazione e strategia del dominio](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#domain-setup-and-strategy).
* La reputazione del tuo indirizzo IP: consulta [Strategia IP](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#ip-strategy).
* Qualità degli indirizzi interessati: consulta [Gestione della quarantena](../../sending/using/optimize-delivery.md#quarantine-management).
* Percentuali basse [reclami](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html) e [mancate consegne](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces).
* Contenuto del messaggio: consulta [Controllo del contenuto delle e-mail](../../sending/using/control-email-content.md).
* Autenticazione dei messaggi (SPF, DKIM, DMARC): vedere [questa sezione](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).
* reputazione del mittente: per scoprire come gli ISP principali valutano la reputazione di un mittente, consulta [questa sezione](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html).

## Strumenti per il recapito messaggi di Campaign {#deliverability-tools}

Adobe Campaign fornisce una serie di strumenti per monitorare e migliorare le prestazioni di recapito messaggi della piattaforma. Questa pagina evidenzia anche i principi principali che dovresti tenere a mente per ottimizzare il recapito messaggi durante l’utilizzo di Campaign.

### Crea il messaggio con attenzione

Durante la configurazione, la progettazione e il test del messaggio, assicurati di seguire le best practice menzionate nelle sezioni elencate di seguito. Sfruttando tutte le funzioni fornite da Adobe Campaign potrai migliorare il recapito messaggi.

* [Best practice per la consegna](../../sending/using/delivery-best-practices.md)
* [Controllo dei contenuti dell’e-mail](../../sending/using/control-email-content.md)
* [Anteprima dei messaggi](../../sending/using/previewing-messages.md)
* [Invio di bozze](../../sending/using/sending-proofs.md)

### Verifica il consenso tramite doppio consenso {#double-opt-in}

Per evitare l’invio di messaggi a indirizzi non validi, limitare le comunicazioni non corrette e migliorare la reputazione del mittente, l’Adobe consiglia di implementare un doppio meccanismo di consenso. Questo ti consente di garantire che i destinatari si siano abbonati intenzionalmente.

Per ulteriori informazioni, consulta [Informazioni su consenso e rinuncia in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Per ulteriori informazioni sulle best practice per la raccolta di dati dai clienti, consulta la [Guida alle best practice per il recapito messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html#data-quality-and-hygiene).

### Gestione della quarantena

Adobe Campaign gestisce un elenco che raccoglie reclami di spam, rimbalzi duri e mancati rimbalzi morbidi che si verificano in modo coerente.

Per proteggere il recapito messaggi, i destinatari i cui indirizzi si trovano in tale elenco vengono esclusi per impostazione predefinita da tutte le consegne future, in quanto l’invio a tali contatti potrebbe danneggiare la reputazione dell’invio.

Alcuni provider di accesso a Internet considerano automaticamente le e-mail come spam se il tasso di indirizzi non validi è troppo alto. La quarantena ti consente quindi di evitare di essere aggiunta al elenco Bloccati da questi provider.

Per ulteriori informazioni, consulta le sezioni seguenti:

* [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Informazioni sulla gestione della quarantena](../../sending/using/understanding-quarantine-management.md)
* [Quarantena rispetto elenco Bloccati](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### Utilizzare strumenti di monitoraggio e reporting

Utilizza le funzioni offerte da Adobe Campaign per monitorare il recapito messaggi.

Adobe Campaign ti consente di controllare le prestazioni delle consegne tramite un set di indicatori in tempo reale incorporati. <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->Puoi anche creare rapporti completamente personalizzabili e in tempo reale per ottenere informazioni approfondite sulle consegne.

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
