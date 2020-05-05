---
title: Introduzione a test e invio
description: Scopri i diversi passaggi per testare e inviare un messaggio.
page-status-flag: never-activated
uuid: 58666444-6e7c-4049-b2d2-8b26eabf5a82
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
discoiquuid: ae2eba1c-24ad-4839-afa9-5a2975570d9b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c1b7d2210647a87693d93e325a4c888cb23e5f3a

---


# Introduzione a test e invio {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">Preparare e testare</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">Invio, monitoraggio e tracciamento</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">Linee guida per la realizzazione</a></p></td></tr>
</table>

Dopo aver definito la destinazione e creato il contenuto di un messaggio, devi preparare e testare il contenuto, la personalizzazione, il rendering e la configurazione delle tue consegne. Questo consente di verificare che tutto sia corretto prima di inviare il messaggio alla destinazione principale. A questo scopo, sono disponibili diverse funzionalità come anteprima, prove di stampa, test dell&#39;oggetto dell&#39;e-mail o rendering dell&#39;e-mail.

Una volta che le campagne di marketing sono state eseguite e che i diversi messaggi sono stati inviati, monitorateli utilizzando i registri per verificare il successo della campagna e recuperare le informazioni di tracciamento sui destinatari.

Infine, puoi sfruttare le linee guida e gli strumenti per la recapito disponibili in Campaign Standard per migliorare il numero di messaggi consegnati e garantire il successo delle campagne di marketing.

## Preparare e testare {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

La preparazione **dei** messaggi di Campaign Standard analizza il target, la personalizzazione e la validità del messaggio. Gli errori rilevati durante questo passaggio devono essere corretti prima di poter procedere ulteriormente.

**Visualizza in anteprima e verifica** i messaggi utilizzando diverse funzionalità: inviate prove di stampa per verificare i profili o i profili di destinazione, verificate l&#39;oggetto delle e-mail e controllate il rendering dei messaggi per essere certi che verranno visualizzati in modo ottimale su una varietà di client Web, e-mail e dispositivi.

Sfruttare le funzionalità di pianificazione delle campagne $$ per definire quando i messaggi verranno inviati. Ad esempio, puoi adattare l&#39;invio al fuso orario del destinatario, ottimizzare l&#39;ora di invio o calcolare la data di invio.

Utilizzate **le tipologie** per verificare durante la preparazione se il messaggio è valido e soddisfa i criteri di qualità attraverso l&#39;affaticamento, il controllo e le regole di targeting. Ad esempio, per verificare che le e-mail contengano sempre un oggetto o per escludere utenti non iscritti dai destinatari del messaggio.

Ulteriori informazioni:

* [Preparazione dell’invio](../../sending/using/preparing-the-send.md)
* [Anteprima dei messaggi](../../sending/using/previewing-messages.md)
* [Invio di prove](../../sending/using/sending-proofs.md)
* [Rendering di e-mail](../../sending/using/email-rendering.md)
* [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md)
* [Informazioni su tipologie e regole di tipologia](../../sending/using/about-typology-rules.md)

## Invio, monitoraggio e tracciamento {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

Una volta che il messaggio è pronto, puoi confermare l’invio e accedere ai registri e ai rapporti per **monitorare la distribuzione** e misurare il successo della campagna. Adobe Campaign fornisce inoltre un sistema di avvisi e-mail per tenere traccia dei risultati ottenuti o degli errori di consegna, nonché delle capacità di gestione della quarantena.

**Monitora il comportamento** dei destinatari del messaggio utilizzando i cookie di sessione e permanenti per recuperare le informazioni di tracciamento (URL su cui è stato fatto clic, pagine mirror, messaggi aperti...).

Infine, puoi configurare Adobe Campaign per **conservare una copia dei messaggi e-mail** inviati dalla piattaforma tramite CCN e-mail. In particolare, se l&#39;azienda deve archiviare tutti i messaggi e-mail in uscita per garantire la conformità, è possibile abilitare questa funzionalità.

Ulteriori informazioni:

* [Conferma dell’invio](../../sending/using/confirming-the-send.md)
* [Tracciamento dei messaggi](../../sending/using/tracking-messages.md)
* [Archiviazione di e-mail con indirizzi Ccn](../../sending/using/archiving.md)
* [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)
* [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Riconoscimento della gestione della quarantena](../../sending/using/understanding-quarantine-management.md)

## Linee guida per la realizzazione {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

La possibilità di distribuire i dati consente di misurare il successo delle campagne che raggiungono la inbox dei destinatari senza rimbalzare o essere contrassegnate come spam.

Campaign Standard offre diversi strumenti **di** recapito che consentono di migliorare il numero di messaggi consegnati correttamente: report di analisi dei tempi di consegna, ottimizzazione dei tempi di invio, anteprima dei messaggi, rendering delle e-mail, gestione della quarantena, ecc.

Ulteriori informazioni:

* [Informazioni sul recapito messaggi](../../sending/using/about-deliverability.md)
* [Monitoraggio del recapito messaggi](../../sending/using/monitor-deliverability.md)
* [Crescita reputazione](../../sending/using/improving-reputation.md)
* [Raccomandazioni tecniche](../../sending/using/technical-recommendations.md)
* [Velocità di consegna controllata](../../reporting/using/delivery-throughput.md)

## Risorse aggiuntive

* [Progettazione di e-mail di test A/B](../../channels/using/designing-an-a-b-test-email.md)
* [Inviare un test, preparare e inviare un messaggio e-mail (video)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/sending-test-preparing-sending-email.html)
* [Rivedere la consegna e i rapporti tramite e-mail (video)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/reviewing-personalized-email-delivery-and-reports.html)
* [Guida introduttiva alle e-mail](https://helpx.adobe.com/campaign/kb/acs-get-started-with-emails.html)
* [Best practice di distribuzione](https://helpx.adobe.com/it/campaign/kb/delivery-best-practices.html)