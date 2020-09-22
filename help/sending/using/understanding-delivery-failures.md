---
title: Informazioni sugli errori di consegna
description: Scopri come gestire gli errori di consegna con Campaign.
page-status-flag: never-activated
uuid: 2735aa05-7b6f-47c9-98c4-a15cc33be39d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 38452841-4cd4-4f92-a5c3-1dfdd54ff6f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '1285'
ht-degree: 81%

---


# Informazioni sugli errori di consegna{#understanding-delivery-failures}

## Informazioni sugli errori di consegna {#about-delivery-failures}

Quando una consegna non può essere inviata a un profilo, il server remoto invia automaticamente un messaggio di errore, rilevato dalla piattaforma Adobe Campaign e qualificato per determinare se l’indirizzo e-mail o il numero di telefono devono essere posti in quarantena o meno. Consulta [Qualificazione di mail non recapitate](#bounce-mail-qualification).

>[!NOTE]
>
>I messaggi di errore **E-mail** (o &quot;mancati recapiti&quot;) sono qualificati dall’MTA avanzato (mancati recapiti sincroni) o dal processo inMail (mancati recapiti asincroni).
>
>I messaggi di errore **SMS** (o &quot;SR&quot; per &quot;Report di stato&quot;) sono qualificati dal processo MTA.

I messaggi possono essere esclusi anche durante la preparazione della consegna se un indirizzo viene messo in quarantena o se un profilo è sul elenco Bloccati. I messaggi esclusi sono elencati nella scheda **[!UICONTROL Exclusion logs]** del dashboard di consegna (consulta [questa sezione](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Argomenti correlati:**

* [Informazioni sulla gestione della quarantena](../../sending/using/understanding-quarantine-management.md)
* [Informazioni sul consenso e diniego in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identificazione degli errori di consegna per un messaggio {#identifying-delivery-failures-for-a-message}

Una volta inviata la consegna, la scheda **[!UICONTROL Sending logs]** (consulta [questa sezione](../../sending/using/monitoring-a-delivery.md#sending-logs)) ti consente di visualizzare lo stato della consegna per ciascun profilo e il tipo e il motivo dell’errore associati (consulta [Tipi e motivi di errori di consegna](#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

È inoltre disponibile un report preconfigurato. Questo report descrive gli errori rigidi e morbidi riscontrati durante le consegne nonché l’elaborazione automatica dei mancati recapiti. Per ulteriori informazioni, consulta [questa sezione](../../reporting/using/bounce-summary.md).

## Tipi e motivi di errori di consegna {#delivery-failure-types-and-reasons}

Se una consegna non riesce, possono verificarsi tre tipi di errori:

* **Rigido**: un errore &quot;rigido&quot; indica un indirizzo non valido. Ciò comporta un messaggio di errore che indica esplicitamente che l’indirizzo non è valido, ad esempio: &quot;Utente sconosciuto&quot;.
* **Morbido**: potrebbe trattarsi di un errore temporaneo o di un errore che non è stato possibile classificare, ad esempio: &quot;Dominio non valido&quot; o &quot;Casella in entrata piena&quot;.
* **Ignorato**: si tratta di un errore che è noto come temporaneo, ad esempio &quot;Fuori sede&quot;, o di un errore tecnico, ad esempio se il tipo di mittente è &quot;postmaster&quot;.

I possibili motivi di un errore di consegna sono:

| Etichetta errore | Tipo errore | Descrizione |
---------|----------|---------
| **[!UICONTROL User unknown]** | Rigido | L&#39;indirizzo non esiste. Per questo profilo non verranno tentate ulteriori consegne. |
| **[!UICONTROL Quarantined address]** | Rigido | L&#39;indirizzo è stato messo in quarantena. |
| **[!UICONTROL Unreachable]** | Soft/Hard | Si è verificato un errore nella catena di distribuzione dei messaggi (ad esempio, dominio temporaneamente non raggiungibile). In base all’errore restituito dal provider, l’indirizzo verrà posto direttamente in quarantena o la consegna verrà ritentata finché Campaign non riceve un errore che giustifica lo stato di quarantena o finché non vengono raggiunti 5 errori. |
| **[!UICONTROL Address empty]** | Rigido | Indirizzo non definito. |
| **[!UICONTROL Mailbox full]** | Morbido | La cassetta postale di questo utente è piena e non può accettare altri messaggi. Questo indirizzo può essere rimosso dall’elenco di quarantena per effettuare un altro tentativo. Viene rimosso automaticamente dopo 30 giorni. Per consentire la rimozione automatica dell’indirizzo dall’elenco degli indirizzi in quarantena, è necessario avviare il flusso di lavoro tecnico **[!UICONTROL Database cleanup]**. |
| **[!UICONTROL Refused]** | Soft/Hard | L&#39;indirizzo è stato messo in quarantena a causa di un feedback sulla sicurezza come rapporto di spam. In base all’errore restituito dal provider, l’indirizzo verrà posto direttamente in quarantena o la consegna verrà ritentata finché Campaign non riceve un errore che giustifica lo stato di quarantena o finché non vengono raggiunti 5 errori. |
| **[!UICONTROL Duplicate]** | Ignorato | L&#39;indirizzo è già stato rilevato nella segmentazione. |
| **[!UICONTROL Not defined]** | Morbido | l&#39;indirizzo è nella qualifica perché gli errori non sono ancora stati incrementati. Questo tipo di errore si verifica quando un nuovo messaggio di errore viene inviato dal server: può essere un errore isolato, ma se si verifica di nuovo, il contatore degli errori aumenta, avvisando i team tecnici. |
| **[!UICONTROL Error ignored]** | Ignorato | L&#39;indirizzo è  inserire nell&#39;elenco Consentiti e gli verrà inviata un&#39;e-mail in ogni caso. |
| **[!UICONTROL Address on denylist]** | Rigido | L&#39;indirizzo è stato aggiunto al elenco Bloccati al momento dell&#39;invio. |
| **[!UICONTROL Account disabled]** | Soft/Hard | Quando Internet Access Provider (IAP) rileva un lungo periodo di inattività, può chiudere l&#39;account dell&#39;utente: le consegne all&#39;indirizzo dell&#39;utente saranno quindi impossibili. Il tipo morbido o rigido dipende dal tipo di errore ricevuto: se l’account è temporaneamente disattivato a causa di sei mesi di inattività e può ancora essere attivato, verrà assegnato lo stato **[!UICONTROL Erroneous]** e la consegna verrà ritentata. Se l’errore ricevuto segnala che l’account è disattivato in modo permanente, verrà posto direttamente in quarantena. |
| **[!UICONTROL Not connected]** | Ignorato | Il telefono cellulare del profilo viene spento o non è connesso alla rete quando il messaggio viene inviato. |
| **[!UICONTROL Invalid domain]** | Morbido | Il dominio dell&#39;indirizzo e-mail non è corretto o non esiste più. Questo profilo sarà nuovamente oggetto di targeting fino a raggiungere 5 errori. Successivamente, il record verrà impostato sullo stato di quarantena e non verrà eseguito alcun nuovo tentativo. |
| **[!UICONTROL Text too long]** | Ignorato | Il numero di caratteri nel messaggio SMS supera il limite. Per ulteriori informazioni, consulta [Codifica, lunghezza e traslitterazione degli SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration). |
| **[!UICONTROL Character not supported by encoding]** | Ignorato | Il messaggio SMS contiene uno o più caratteri non supportati dalla codifica. &amp;Per ulteriori informazioni, consulta [Tabella dei caratteri: standard GSM](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard). |

## Tentativi dopo un errore temporaneo di consegna {#retries-after-a-delivery-temporary-failure}

Se un messaggio non riesce a causa di un errore temporaneo del tipo **Ignorato**, verranno eseguiti nuovi tentativi per la durata della consegna. Per ulteriori informazioni sui tipi di errori, consulta [Tipi e motivi di errori di consegna](#delivery-failure-types-and-reasons).

Il numero di nuovi tentativi (numero di tentativi da eseguire il giorno successivo all’inizio dell’invio) e il ritardo minimo tra nuovi tentativi sono ora gestiti dall’MTA avanzato di Adobe Campaign, in base alle prestazioni di un IP sia storicamente sia attualmente in un determinato dominio. Le impostazioni **Nuovi tentativi** in Campaign vengono ignorate.

Per modificare la durata di una consegna, passa ai parametri avanzati della consegna o del modello di consegna e modifica il campo **[!UICONTROL Delivery duration]** della sezione [Periodo di validità](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!IMPORTANT]
>
>**Il parametro **[!UICONTROL Delivery duration]**nelle consegne di Campaign viene ora utilizzato soltanto se impostato su 3,5 giorni o meno.** Se definisci un valore superiore a 3,5 giorni, non verrà preso in considerazione in quanto ora è gestito dall’MTA avanzato di Adobe Campaign.

Ad esempio, se desideri che i nuovi tentativi per una consegna si interrompano dopo un giorno, puoi impostare la durata della consegna su **1d**, e l’MTA avanzato rispetterà tale impostazione rimuovendo i messaggi nella coda dei nuovi tentativi dopo un giorno.

>[!NOTE]
>
>Una volta che un messaggio è rimasto nella coda dell’MTA avanzato per 3,5 giorni e la consegna non è riuscita, si verificherà un timeout e il suo stato verrà aggiornato da **[!UICONTROL Sent]** a **[!UICONTROL Failed]** nei [log di consegna](../../sending/using/monitoring-a-delivery.md#delivery-logs).

<!--The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## Errori sincroni e asincroni {#synchronous-and-asynchronous-errors}

Una consegna può non riuscire immediatamente (errore sincrono) oppure in seguito, dopo che è stata inviata (errore asincrono).

* **Errore sincrono**: il server remoto contattato dal server di consegna di Adobe Campaign ha restituito immediatamente un messaggio di errore. La consegna non può essere inviata al server del profilo.
* **Errore asincrono**: una mail non recapitata o un SR è stato inviato in seguito dal server ricevente. Gli errori asincroni possono verificarsi fino a una settimana dopo l’invio di una consegna.

## Qualificazione di mail non recapitate {#bounce-mail-qualification}

Per i messaggi di errore di consegna sincrono, l’MTA avanzato determina il tipo di mancata consegna e la qualificazione e invia tali informazioni a Campaign.

Le mancate consegne asincrone vengono comunque qualificate dal processo inMail attraverso le regole **[!UICONTROL Inbound email]**. Per accedere a queste regole, fai clic sul logo **[!UICONTROL Adobe Campaign]**, in alto a sinistra, quindi seleziona **[!UICONTROL Administration > Channels > Email > Email processing rules]** e seleziona **[!UICONTROL Bounce mails]**. Per ulteriori informazioni su questa regola, consulta questa [sezione](../../administration/using/configuring-email-channel.md#email-processing-rules).

>[!NOTE]
>
>La qualificazione delle mail non recapitate viene ora gestita dall’MTA avanzato di Adobe Campaign. Le qualifiche di mancato recapito nella tabella **[!UICONTROL Message qualification]** di Campaign non vengono più utilizzate.

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## Ottimizzazione della consegna dei messaggi con il doppio meccanismo di consenso {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

Il doppio meccanismo di consenso è una best practice per l’invio di e-mail. Esso protegge la piattaforma da indirizzi e-mail errati o non validi, da spambot e impedisce possibili reclami di spam.

Il principio consiste nell’inviare un’e-mail per confermare il consenso del visitatore prima di memorizzarlo tra i “profili” nel database di Campaign: il visitatore compila una pagina di destinazione online, quindi riceve un messaggio e-mail e deve fare clic sul collegamento di conferma per finalizzare l’abbonamento.

Per ulteriori informazioni, consulta [questa sezione](../../channels/using/setting-up-a-double-opt-in-process.md).
