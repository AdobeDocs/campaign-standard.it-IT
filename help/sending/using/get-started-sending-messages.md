---
solution: Campaign Standard
product: campaign
title: Guida introduttiva alla verifica e all’invio
description: Prepara, testa, pianifica, invia e monitora i messaggi.
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 15%

---


# Guida introduttiva alla verifica e all’invio {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">Preparare e testare</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">Invio, monitoraggio e tracciamento</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">Linee guida sul recapito messaggi</a></p></td></tr>
</table>

Una volta definito il target e creato il contenuto di un messaggio, devi preparare e testare il contenuto, la personalizzazione, il rendering e la configurazione delle consegne. Questo ti consente di verificare che tutto sia corretto prima di inviare il messaggio al target principale. A questo scopo, sono disponibili più funzionalità come anteprima, bozze, test dell’oggetto dell’e-mail o rendering di e-mail.

Dopo aver eseguito le campagne di marketing e aver inviato i diversi messaggi, monitorali utilizzando i registri per verificare il successo della campagna e recuperare le informazioni di tracciamento sui destinatari.

Infine, sfrutta le linee guida sul recapito messaggi e gli strumenti disponibili in Campaign Standard per migliorare il numero di messaggi consegnati e garantire il successo delle campagne di marketing.

![](assets/do-not-localize/how-to-video.png) [Scopri come inviare un’e-mail di test, preparare e inviare una consegna e-mail in video](#video)

## Preparare e testare {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

Campaign Standard **message preparation** analizza il target, la personalizzazione e la validità del messaggio. Gli errori rilevati durante questo passaggio devono essere corretti prima di poter procedere oltre.

**Visualizza in anteprima e** verifica i messaggi utilizzando varie funzionalità: invia bozze per testare profili o profili di destinazione, verifica la riga dell’oggetto delle e-mail e controlla il rendering dei messaggi per assicurarti che vengano visualizzati in modo ottimale su una varietà di client web, e-mail web e dispositivi.

Sfrutta le funzionalità di pianificazione di Campaign per definire quando verranno inviati i messaggi. Ad esempio, puoi adattare l’invio al fuso orario del destinatario, ottimizzare l’ora di invio o calcolare la data di invio.

Utilizza le **tipologie** per verificare durante la preparazione se il messaggio è valido e soddisfa i criteri di qualità tramite regole di affaticamento, controllo e targeting. Ad esempio, per verificare che le e-mail contengano sempre un oggetto o per escludere i non abbonati dai destinatari del messaggio.

Leggi tutto:

* [Preparazione dell’invio](../../sending/using/preparing-the-send.md)
* [Anteprima dei messaggi](../../sending/using/previewing-messages.md)
* [Invio di bozze](../../sending/using/sending-proofs.md)
* [Rendering di e-mail](../../sending/using/email-rendering.md)
* [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md)
* [Informazioni su tipologie e regole di tipologia](../../sending/using/about-typology-rules.md)

## Invio, monitoraggio e tracciamento {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

Quando il messaggio è pronto, puoi confermare l’invio e accedere ai registri e ai rapporti su **monitorare la consegna** e misurare il successo della campagna. Adobe Campaign fornisce inoltre un sistema di avvisi e-mail per tenere traccia dei successi o degli errori di consegna e delle funzionalità di gestione della quarantena.

**Monitora il** comportamento dei destinatari del messaggio utilizzando sessioni e cookie permanenti per recuperare informazioni di tracciamento (URL su cui è stato fatto clic, pagine mirror, messaggi aperti..).

Infine, puoi configurare Adobe Campaign per **conservare una copia delle e-mail** inviate dalla piattaforma tramite CCN e-mail. In particolare, se la tua organizzazione deve archiviare tutti i messaggi e-mail in uscita per garantire la conformità, puoi abilitare questa funzionalità.

Leggi tutto:

* [Conferma dell’invio](../../sending/using/confirming-the-send.md)
* [Tracciamento dei messaggi](../../sending/using/tracking-messages.md)
* [Archiviazione di e-mail con indirizzi Ccn](../../sending/using/archiving.md)
* [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)
* [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Informazioni sulla gestione della quarantena](../../sending/using/understanding-quarantine-management.md)

## Linee guida sul recapito messaggi {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

Il recapito messaggi consente di misurare il successo delle campagne che raggiungono la casella in entrata dei destinatari senza rimbalzare o contrassegnare come spam.

Campaign Standard fornisce diversi **strumenti di recapito** per aiutarti a migliorare il numero di messaggi consegnati correttamente: rapporti di valutazione della consegna, ottimizzazione del tempo di invio, anteprima dei messaggi, rendering di e-mail, gestione della quarantena, ecc.

Leggi tutto:

* [Informazioni sul recapito messaggi](../../sending/using/about-deliverability.md)
* [Monitoraggio della consegna messaggi](../../sending/using/monitor-deliverability.md)
* [Crescita reputazione](../../sending/using/improving-reputation.md)
* [Raccomandazioni tecniche](../../sending/using/technical-recommendations.md)
* [Controllo della velocità effettiva di consegna](../../reporting/using/delivery-throughput.md)

## Risorse aggiuntive

* [Progettazione di e-mail per test A/B](../../channels/using/designing-an-a-b-test-email.md)
* [Guida introduttiva alle e-mail](https://helpx.adobe.com/it/campaign/kb/acs-get-started-with-emails.html)
* [Best practice di consegna](../../sending/using/delivery-best-practices.md)
* [Aggiunta di un gruppo di controllo](../../sending/using/control-group.md)

## Video tutorial {#video}

Questo video mostra come inviare un’e-mail di prova, preparare e quindi inviare una consegna e-mail in Campaign Standard.

>[!VIDEO](https://video.tv.adobe.com/v/24013/)

Sono disponibili ulteriori video dimostrativi su Campaign Standard [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
