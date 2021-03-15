---
solution: Campaign Standard
product: campaign
title: Informazioni sul recapito messaggi in Adobe Campaign Standard
description: Scopri i concetti e le best practice relativi al recapito messaggi e gli strumenti offerti da Adobe Campaign Standard per ottimizzare l’invio delle consegne.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Consegna
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 5%

---


# Informazioni sul recapito messaggi{#about-deliverability}

Il recapito messaggi consente di misurare il successo delle campagne che raggiungono la casella in entrata dei destinatari senza rimbalzare o contrassegnare come spam.

Il tasso di consegna dipende da numerosi fattori, in particolare:

* Configurazione corretta delle istanze
* La reputazione del tuo indirizzo IP
* Qualità degli indirizzi interessati
* Bassi reclami e tassi di mancato recapito
* Contenuto del messaggio
* Autenticazione dei messaggi (SPF, DKIM, DMARC)
* reputazione del mittente

## Punti chiave da verificare {#deliverability-key-points}

Per ottimizzare il recapito messaggi delle e-mail di Adobe Campaign, si consiglia di utilizzare le best practice elencate di seguito. I problemi di recapito sono generalmente collegati a misure di protezione contro lo spam implementate dai fornitori di servizi Internet e dagli amministratori dei server di posta.

Il recapito messaggi e-mail si riferisce al set di caratteristiche che determinano la capacità di un messaggio di raggiungere la destinazione, tramite un indirizzo e-mail personale, in un breve periodo di tempo e con la qualità prevista in termini di contenuto e formato. Queste caratteristiche rientrano in quattro categorie principali: qualità dei dati, messaggi e contenuti, infrastruttura di invio e reputazione. Insieme, costituiscono la base di un programma di recapito messaggi e-mail di successo.

Il tasso di recapito messaggi è il numero di e-mail inviate correttamente ai destinatari.
Elenco dei punti chiave da verificare per garantire un buon recapito messaggi.

## Strumenti di recapito {#deliverability-tools}

Innanzitutto, consulta la documentazione sugli strumenti di recapito messaggi forniti con Campaign Standard:
* [Best practice di consegna](../../sending/using/delivery-best-practices.md)
* [Personalizzazione del nome del mittente](../../designing/using/personalization.md#personalizing-the-sender)
* [Ottimizzazione del tempo di invio](../../sending/using/optimizing-the-sending-time.md)
* [Anteprima dei messaggi](../../sending/using/previewing-messages.md)
* [Rendering di e-mail](../../sending/using/email-rendering.md)
* [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)
* [Ricezione degli avvisi in caso di errori](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Informazioni sulla gestione della quarantena](../../sending/using/understanding-quarantine-management.md)
* [Quarantena rispetto elenco Bloccati](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)
* [Rapporti dinamici](../../reporting/using/about-dynamic-reports.md)

## Verifica della configurazione di rete {#network-configuration}

Gli spammer cercano di nascondere la loro identità reale e di conseguenza rendono i loro server difficili da identificare. Una configurazione di rete legittima che non tenti di nascondere l&#39;identità del server è essenziale per l&#39;invio di e-mail in grandi volumi.

## Invio a indirizzi validi {#valid-addresses}

Gli spammer utilizzano spesso generatori di indirizzi basati su elenchi di nomi frequenti e di nomi di battesimo; inoltre, raramente elaborano le notifiche tecniche inviate dai server di posta. Un elevato numero di indirizzi non validi viene spesso interpretato come un segno di spam. I meccanismi di doppio consenso e l&#39;efficace gestione dei messaggi di rimbalzo tecnici consentono di evitarlo.

## Riduzione del tasso di reclamo {#reduce-complaint-rate}

Gli ISP di solito hanno un modo prominente di segnalare un messaggio ricevuto come spam. Questo permette di identificare fonti inaffidabili. Soddisfacendo rapidamente le richieste di rinuncia, utilizzando regolarmente una determinata lista, verificando il consenso tramite un doppio sistema di consenso e implementando cicli di feedback, puoi ridurre i tassi di reclamo.

## Invio agli indirizzi della stazione di miele {#honeypot-addresses}

Gli ISP e altre organizzazioni (fare riferimento a https://www.projecthoneypot.org/) fanno uso di cassette postali che non corrispondono a persone fisiche ma sono create semplicemente per ingannare gli spammer. Questi cosiddetti indirizzi &quot;pentola di miele&quot; sono pubblicati sul web per essere raccolti da spambots e quindi catturare mittenti illegittimi. L&#39;uso di un doppio meccanismo di consenso impedisce l&#39;aggiunta di questo tipo di indirizzo a un elenco. Quando si utilizza un elenco di terze parti, è necessario assicurarsi dei metodi utilizzati dal relativo manutentore.

## Adattamento del contenuto del messaggio {#adapt-message-content}

In misura minore, il contenuto di alcuni messaggi può portare alcuni filtri a rilevarlo come spam. L&#39;uso di determinate parole, l&#39;uso di punti esclamativi nella riga dell&#39;oggetto e all&#39;interno dei messaggi sono letti come segni di spam. Gli spammer sono anche noti per sostituire il testo con immagini per impedire che il testo offensivo venga analizzato automaticamente dai filtri anti-spam. In risposta a ciò, un messaggio (in formato HTML) con un&#39;alta proporzione di immagini, o immagini come allegati, potrebbe finire per essere bloccato.

## Invio regolare {#regular-deliveries}

Gli spammer fanno consegne programmate per mantenere la loro reputazione nel tempo. A volte hanno bisogno di adattare il loro piano di marketing per soddisfare le best practice imposte dagli ISP e quindi, dopo un picco di reputazione (ramp-up), configurano consegne regolari.
