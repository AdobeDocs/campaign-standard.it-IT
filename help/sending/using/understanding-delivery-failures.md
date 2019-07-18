---
title: Informazioni sugli errori di consegna
seo-title: Informazioni sugli errori di consegna
description: Informazioni sugli errori di consegna
seo-description: Scopri come gestire gli errori di distribuzione con Campaign.
page-status-flag: never-activated
uuid: 2735 aa 05-7 b 6 f -47 c 9-98 c 4-a 15 cc 33 be 39 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: invio
content-type: riferimento
topic-tags: monitoring-messages
discoiquuid: 38452841-4 cd 4-4 f 92-a 5 c 3-1 dfdd 54 ff 6 f 4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Understanding delivery failures{#understanding-delivery-failures}

## About delivery failures {#about-delivery-failures}

Quando una consegna non può essere inviata a un profilo, il server remoto invia automaticamente un messaggio di errore, prelevato dalla piattaforma Adobe Campaign, per determinare se l'indirizzo e-mail o il numero di telefono deve essere messo in quarantena. See [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

>[!NOTE]
>
>**I messaggi** di errore e-mail (o «bounce») sono qualificati dal processo inmail. **I messaggi** di errore SMS ("SR" per "Report Status") sono qualificati dal processo MTA.

I messaggi possono essere anche esclusi durante la preparazione della consegna se un indirizzo viene messo in quarantena o se un profilo è in lista nera. Excluded messages are listed in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Argomenti correlati:**

* [Gestione della gestione della quarantena](../../sending/using/understanding-quarantine-management.md)
* [Gestione della blacklist in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identifying delivery failures for a message {#identifying-delivery-failures-for-a-message}

Once a delivery is sent, the **[!UICONTROL Sending logs]** tab (see [this section](../../sending/using/monitoring-a-delivery.md#sending-logs)) allows you to view the delivery status for each profile and the associated failure type and reason (see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

È disponibile anche un rapporto dedicato. Questo rapporto illustra gli errori complessivi e netti riscontrati durante le consegne nonché l'elaborazione automatica degli sbalzi. For more on this, refer to [this section](../../reporting/using/bounce-summary.md).

## Delivery failure types and reasons {#delivery-failure-types-and-reasons}

Quando una consegna non riesce, si verificano tre tipi di errori:

* **Hard**: Un errore "hard" indica un indirizzo non valido. Si tratta di un messaggio di errore che indica esplicitamente che l'indirizzo non è valido, ad esempio: " User user ".
* **Soft**: Potrebbe trattarsi di un errore temporaneo o di uno che non può essere categorizzato, ad esempio: " Dominio non valido "o" Casella di posta completa ".
* **Ignorato**: Si tratta di un errore noto come temporanea, ad esempio «Non Office», o un errore tecnico, ad esempio se il tipo di mittente è «postmaster».

I motivi possibili per un errore di consegna sono:

* **[!UICONTROL User unknown]** (Tipo hardtype): l'indirizzo non esiste. Per questo profilo non verranno tentate ulteriori consegne.
* **[!UICONTROL Quarantined address]** (Tipo hardtype): l'indirizzo è stato posizionato in quarantena.
* **[!UICONTROL Unreachable]** (Tipo morbido/hardtype): si è verificato un errore nella catena di consegna dei messaggi (incidente su relay SMTP, dominio temporaneamente non raggiungibile, ecc.). In base all'errore restituito dal fornitore, l'indirizzo verrà inviato direttamente oppure la consegna viene riprovata finché Campaign non riceve un errore che giustifica lo stato di quarantena o finché il numero di errori non raggiunge il 5.
* **[!UICONTROL Address empty]** (Tipo hardtype): l'indirizzo non è definito.
* **[!UICONTROL Mailbox full]** (Tipo di morbido): the mailbox di questo utente è piena e non può accettare più messaggi. Questo indirizzo può essere rimosso dall'elenco di quarantena per effettuare un altro tentativo. Viene rimosso automaticamente dopo 30 giorni.

   Per consentire la rimozione automatica dell’indirizzo dall’elenco degli indirizzi in quarantena, è necessario avviare il flusso di lavoro tecnico **[!UICONTROL Database cleanup]**.

* **[!UICONTROL Refused]** (Tipo morbido/hardtype): l'indirizzo è stato posizionato in quarantena a causa di un feedback di sicurezza come rapporto spam. In base all'errore restituito dal fornitore, l'indirizzo verrà inviato direttamente oppure la consegna viene riprovata finché Campaign non riceve un errore che giustifica lo stato di quarantena o finché il numero di errori non raggiunge il 5.
* **[!UICONTROL Duplicate]**: l'indirizzo è già stato rilevato nella segmentazione.
* **[!UICONTROL Not defined]** (Tipo di morbido): l'indirizzo è in qualifica perché gli errori non sono ancora stati incrementati.

   Questo tipo di errore si verifica quando un nuovo messaggio di errore viene inviato dal server: può essere un errore isolato, ma se si verifica di nuovo, il contatore di errore aumenta, che avverte i team tecnici.

* **[!UICONTROL Error ignored]**: l'indirizzo è nella whitelist e in ogni caso viene inviato un messaggio e-mail.
* **[!UICONTROL Blacklisted address]**: l'indirizzo è stato inserito in blacklist al momento dell'invio.
* **[!UICONTROL Account disabled]** (Tipo morbido/hardtype): quando l'IAP (Internet Access Provider) rileva un periodo di inattività lungo, può chiudere l'account dell'utente: le consegne all'indirizzo dell'utente saranno quindi impossibili. The Soft or Hard type depends upon the type of error received: if the account is temporarily disabled due to six months of inactivity and can still be activated, the status **[!UICONTROL Erroneous]** will be assigned and the delivery will be tried again. Se l'errore ricevuto segnala che l'account è disattivato permanentemente, verrà inviato direttamente a Quarantena.
* **[!UICONTROL Not connected]**: il cellulare del profilo viene spento o non connesso alla rete quando viene inviato il messaggio.
* **[!UICONTROL Invalid domain]** (Tipo di morbido): il dominio dell'indirizzo e-mail è errato o non esiste più. Questo profilo sarà di nuovo impostato come destinazione fino a raggiungere il 5. In seguito, il record sarà impostato sullo stato Quarantena e non verrà eseguito alcun tentativo.
* **[!UICONTROL Text too long]**: il numero di caratteri nel messaggio SMS supera il limite. For more on this, see [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).
* **[!UICONTROL Character not supported by encoding]**: il messaggio SMS contiene uno o più caratteri non supportati dalla codifica. &amp;For more on this, see [Table of characters - GSM Standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard).

## Retries after a delivery temporary failure {#retries-after-a-delivery-temporary-failure}

If a message fails due to a temporary error of the **Ignored** type, retries will be performed during the delivery duration. For more on the types of errors, see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

Per modificare la durata di una consegna, accedete ai parametri avanzati del modello di consegna o di consegna e specificate la durata desiderata nel campo corrispondente. The advanced delivery properties are presented in [this section](../../administration/using/configuring-email-channel.md#validity-period-parameters).

La configurazione predefinita consente cinque tentativi a intervalli di un'ora, seguiti da un ritry al giorno per quattro giorni. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).

## Synchronous and asynchronous errors {#synchronous-and-asynchronous-errors}

Una consegna può non riuscire immediatamente (errore sincrono) o successivo dopo l'invio (errore asincrono).

* **Errore sincrono**: il server remoto contattato dal server di consegna di Adobe Campaign restituiva immediatamente un messaggio di errore, non è possibile inviare la consegna al server del profilo.
* **Errore asincrono**: un messaggio di rimbalzo o un SR è stato inviato successivamente dal server ricevente. Possono verificarsi errori asincroni fino a una settimana dopo l'invio della distribuzione.

## Bounce mail qualification {#bounce-mail-qualification}

I messaggi di errore non riusciti (o «bounce») vengono prelevati dalla piattaforma Adobe Campaign e sono qualificati dal processo inmail per arricchire l'elenco delle regole di gestione e-mail.

Questo elenco è disponibile solo per gli amministratori e contiene tutte le regole utilizzate da Adobe Campaign per qualificare gli errori di consegna.

To access it, click the **[!UICONTROL Adobe Campaign]** logo, at the top left, then select **[!UICONTROL Administration > Channels > Email > Email processing rules]**.

For more on this, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

Gli bounce possono avere i seguenti stati di qualifica:

* **[!UICONTROL To qualify]**: il messaggio di rimbalzo deve essere qualificato. La qualifica deve essere realizzata dal team di Deliverability per garantire che le funzioni di prestazioni della piattaforma siano corrette. Se non è qualificato, il messaggio di rimbalzo non viene usato per arricchire l'elenco delle regole di elaborazione e-mail.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by **the Update for deliverability** workflow to be confrontati with existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: il messaggio bounce è stato qualificato ma non verrà utilizzato dall' **aggiornamento per** il flusso di lavoro di recapito. Pertanto, non verrà inviato alle istanze client.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)

## Optimizing mail deliverability with double opt-in mechanism {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

Il duplice meccanismo di consenso è una procedura consigliata per l'invio di e-mail. Protegge la piattaforma da indirizzi e-mail errati o non validi, oltre a possibili reclami di spam.

Il principio consiste nell'inviare un messaggio e-mail per confermare il contratto del visitatore prima di memorizzarlo come «profili» nel database campagna: il visitatore compila una pagina di destinazione online, quindi riceve un messaggio e-mail e deve fare clic sul collegamento di conferma per finalizzarne l'iscrizione.

For more on this, refer to [this section](../../channels/using/setting-up-a-double-opt-in-process.md).
