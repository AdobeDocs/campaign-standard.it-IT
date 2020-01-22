---
title: Informazioni sulla recapito in Adobe Campaign Standard
description: Scopri i concetti e le best practice relativi alla recapito dei prodotti e gli strumenti offerti da Adobe Campaign Standard per ottimizzare l'invio delle consegne.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 02b8d847d4506eca96abfa27db1e2efadc2a68d2

---


# Informazioni sul recapito{#about-deliverability}

La possibilità di distribuire i dati consente di misurare il successo delle campagne che raggiungono la inbox dei destinatari senza rimbalzare o essere contrassegnate come spam.

Il tasso di recapito dipende da numerosi fattori, in particolare:

* Configurazione corretta delle istanze
* La reputazione del tuo indirizzo IP
* Qualità degli indirizzi interessati
* Bassi reclami e tassi di rimbalzo
* Contenuto del messaggio
* Autenticazione dei messaggi (SPF, DKIM, DMARC)
* reputazione mittente

## Punti chiave da controllare {#deliverability-key-points}

Per ottimizzare la recapito dei messaggi e-mail di Adobe Campaign, consigliamo di utilizzare le best practice elencate di seguito. I problemi di recapito sono generalmente legati alle misure di protezione contro lo spam attuate dai provider di servizi Internet e dagli amministratori dei server di posta elettronica.

Per &quot;recapito e-mail&quot; si intende il set di caratteristiche che determinano la capacità di un messaggio di raggiungere la destinazione, tramite un indirizzo e-mail personale, entro un breve periodo di tempo e con la qualità prevista in termini di contenuto e formato. Queste caratteristiche sono suddivise in quattro categorie principali: qualità dei dati, messaggi e contenuti, infrastruttura di invio e reputazione. Insieme, costituiscono la base di un programma di recapito e-mail di successo.

Il tasso di recapito corrisponde al numero di e-mail inviate correttamente ai destinatari.
Di seguito è riportato un elenco dei punti chiave da verificare per garantire una buona consegna.

## Strumenti di distribuzione {#deliverability-tools}

Innanzitutto, consultare la documentazione sugli strumenti di recapito forniti con Campaign Standard:
* [Best practice di distribuzione](https://helpx.adobe.com/campaign/kb/delivery-best-practices.html)
* [Personalizzazione del nome del mittente](../../designing/using/personalization.md#personalizing-the-sender)
* [Verifica dell’oggetto di un messaggio e-mail](../../sending/using/testing-subject-line-email.md)
* [Ottimizzazione del tempo di invio](../../sending/using/optimizing-the-sending-time.md)
* [Anteprima dei messaggi](../../sending/using/previewing-messages.md)
* [Rendering di e-mail](../../sending/using/email-rendering.md)
* [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)
* [Ricezione degli avvisi in caso di errori](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Riconoscimento della gestione della quarantena](../../sending/using/understanding-quarantine-management.md)
* [Quarantena e blacklist](../../sending/using/understanding-quarantine-management.md#quarantine-vs-blacklisting)
* [Report dinamici](../../reporting/using/about-dynamic-reports.md)

## Verifica della configurazione di rete {#network-configuration}

Gli spammer cercano di nascondere la loro identità reale e di conseguenza rendono i loro server difficili da identificare. Una configurazione di rete legittima che non tenti di nascondere l&#39;identità del server è essenziale per inviare e-mail in grandi volumi.

## Invio a indirizzi validi {#valid-addresses}

Gli spammer usano spesso generatori di indirizzi basati su elenchi di nomi e nomi frequenti; inoltre, raramente elaborano le notifiche tecniche inviate dai server di posta. Un elevato numero di indirizzi non validi viene spesso interpretato come un segno di spam. I meccanismi di doppio consenso e l&#39;efficace gestione dei messaggi tecnici di rimbalzo consentono di evitare questo problema.

## Riduzione del tasso di reclamo {#reduce-complaint-rate}

Gli ISP solitamente dispongono di uno strumento importante per segnalare un messaggio ricevuto come spam. Questo permette di identificare fonti inaffidabili. Soddisfacendo rapidamente le richieste di rifiuto, utilizzando regolarmente un determinato elenco, verificando il consenso tramite un sistema di doppio consenso e implementando i cicli di feedback, potete ridurre le tariffe dei reclami.

## Invio agli indirizzi delle melanzane {#honeypot-addresses}

I provider di servizi Internet e altre organizzazioni (fare riferimento a https://www.projecthoneypot.org/) utilizzano caselle di posta che non corrispondono a persone fisiche ma sono create semplicemente per ingannare gli spammer. Questi cosiddetti indirizzi &quot;vaso di miele&quot; sono pubblicati sul Web per essere raccolti dagli spambots e quindi catturare mittenti illegittimi. L&#39;uso di un doppio meccanismo di opt-in impedisce l&#39;aggiunta di questo tipo di indirizzo a un elenco. Quando si utilizza un elenco di terze parti, è necessario essere certi dei metodi utilizzati dal relativo manutentore.

## Adattamento del contenuto dei messaggi {#adapt-message-content}

In misura minore, il contenuto di alcuni messaggi può portare alcuni filtri per rilevarlo come spam. L&#39;uso di determinate parole, l&#39;uso di punti esclamativi nella riga dell&#39;oggetto e all&#39;interno dei messaggi sono letti come segni di spam. È noto che gli spammers sostituiscono il testo con le immagini per evitare che il testo offensivo venga analizzato automaticamente dai filtri anti-spam. In risposta a ciò, un messaggio (in formato HTML) con un&#39;elevata percentuale di immagini o immagini come allegati potrebbe finire per essere bloccato.

## Invio regolare {#regular-deliveries}

Gli spammer fanno consegne programmate per mantenere la loro reputazione nel tempo. A volte devono adattare il piano di marketing per soddisfare le migliori pratiche imposte dai provider di servizi Internet e quindi, dopo un picco di reputazione (accelerazione), configurano consegne regolari.
