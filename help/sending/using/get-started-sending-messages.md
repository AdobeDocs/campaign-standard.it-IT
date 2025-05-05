---
title: Introduzione alla verifica e all’invio
description: Prepara, testa, pianifica, invia e monitora i messaggi.
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
role: User
level: Intermediate
exl-id: bcb28ef5-5cad-43c1-b11b-080abc791a72
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 11%

---

# Introduzione alla verifica e all’invio {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">Preparare e testare</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">Invio, monitoraggio e tracciamento</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">Linee guida per il recapito messaggi</a></p></td></tr>
</table>

Dopo aver definito il target e creato il contenuto di un messaggio, devi preparare e testare il contenuto, la personalizzazione, il rendering e la configurazione delle consegne. Questo ti consente di verificare che tutto sia corretto prima di inviare il messaggio al target principale. A questo scopo, sono disponibili più funzionalità come anteprima, bozze, test dell’oggetto dell’e-mail o rendering di e-mail.

Dopo aver eseguito le campagne di marketing e inviato i diversi messaggi, monitorali utilizzando i registri per verificare il successo della campagna e recuperare le informazioni di tracciamento sui destinatari.

Infine, sfrutta le linee guida e gli strumenti disponibili in Campaign Standard per il recapito dei messaggi al fine di migliorare il numero di messaggi consegnati e garantire il successo delle campagne di marketing.

![](assets/do-not-localize/how-to-video.png) [Scopri come inviare un&#39;e-mail di test, preparare e inviare una consegna e-mail in un video](#video)

## Preparare e testare {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

La **preparazione dei messaggi** di Campaign Standard analizza il target, la personalizzazione e la validità del messaggio. Gli errori rilevati durante questo passaggio devono essere corretti prima di poter procedere ulteriormente.

**Anteprima e verifica** i messaggi utilizzando varie funzionalità: invia bozze a profili di test o di destinazione, verifica l&#39;oggetto delle e-mail e controlla il rendering dei messaggi per assicurarti che vengano visualizzati in modo ottimale su diversi client web, web mail e dispositivi.

Sfrutta le funzionalità di pianificazione di Campaign per definire quando verranno inviati i messaggi. Ad esempio, puoi adattare l’invio al fuso orario del destinatario, ottimizzare l’ora di invio o calcolare la data di invio.

Utilizza **tipologie** per verificare durante la preparazione se il messaggio è valido e soddisfa i criteri di qualità tramite regole di affaticamento, controllo e targeting. Ad esempio, per verificare che le e-mail contengano sempre un oggetto o per escludere gli utenti non abbonati dai destinatari del messaggio.

Ulteriori informazioni:

* [Preparazione dell’invio](../../sending/using/preparing-the-send.md)
* [Anteprima dei messaggi](../../sending/using/previewing-messages.md)
* [Invio di bozze](../../sending/using/sending-proofs.md)
* [Rendering di e-mail](../../sending/using/email-rendering.md)
* [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md)
* [Informazioni su tipologie e regole di tipologia](../../sending/using/about-typology-rules.md)

## Invio, monitoraggio e tracciamento {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

Quando il messaggio è pronto, puoi confermare i registri di invio e di accesso e i rapporti per **monitorare la consegna** e misurare il successo della campagna. Adobe Campaign fornisce anche un sistema di avvisi e-mail per tenere traccia dei successi o degli errori di consegna, nonché funzionalità di gestione della quarantena.

**Monitora il comportamento** dei destinatari del messaggio utilizzando cookie di sessione e permanenti per recuperare le informazioni di tracciamento (URL su cui è stato fatto clic, pagine mirror, messaggi aperti...).

Infine, puoi configurare Adobe Campaign per **conservare una copia delle e-mail** inviate dalla piattaforma tramite E-mail in Ccn. In particolare, se la tua organizzazione deve archiviare tutti i messaggi e-mail in uscita per motivi di conformità, puoi abilitare questa funzionalità.

Ulteriori informazioni:

* [Conferma dell’invio](../../sending/using/confirming-the-send.md)
* [Tracciamento dei messaggi](../../sending/using/tracking-messages.md)
* [Archiviazione di e-mail con indirizzi in Ccn](../../sending/using/archiving.md)
* [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)
* [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)
* [Informazioni sulla gestione della quarantena](../../sending/using/understanding-quarantine-management.md)

## Linee guida per il recapito messaggi {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

Il recapito messaggi consente di misurare il successo delle campagne che raggiungono la casella in entrata dei destinatari senza che questi vengano recapitati o contrassegnati come spam.

Campaign Standard fornisce diversi **strumenti di recapito messaggi** per aiutarti a migliorare il numero di messaggi recapitati correttamente: rapporti sulla velocità effettiva di consegna, ottimizzazione del tempo di invio, anteprima dei messaggi, rendering delle e-mail, gestione della quarantena, ecc.

Ulteriori informazioni:

* [Informazioni sul recapito messaggi](../../sending/using/about-deliverability.md)
* [Monitoraggio del recapito messaggi](../../sending/using/monitor-deliverability.md)
* [Guida alle procedure consigliate per la consegna dei messaggi di Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=it)
* [Controllo della velocità effettiva di consegna](../../reporting/using/delivery-throughput.md)

## Risorse aggiuntive

* [Progettazione di e-mail per test A/B](../../channels/using/designing-an-a-b-test-email.md)
* [Guida introduttiva ai messaggi](../../channels/using/key-steps-to-send-a-message.md)
* [Best practice per la consegna](../../sending/using/delivery-best-practices.md)
* [Aggiunta di un gruppo di controllo](../../sending/using/control-group.md)

## Video tutorial {#video}

Questo video mostra come inviare un’e-mail di test, preparare e quindi inviare una consegna e-mail in Campaign Standard.

>[!VIDEO](https://video.tv.adobe.com/v/329658?captions=ita)

Sono disponibili altri video dimostrativi di Campaign Standard [qui](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=it).
