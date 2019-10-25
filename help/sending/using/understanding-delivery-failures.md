---
title: Informazioni sugli errori di consegna
seo-title: Informazioni sugli errori di consegna
description: Informazioni sugli errori di consegna
seo-description: Scopri come gestire gli errori di consegna con Campaign.
page-status-flag: mai attivato
uuid: 2735aa05-7b6f-47c9-98c4-a15cc33be39d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: invio
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 38452841-4cd4-4f92-a5c3-1dfdd54ff6f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Informazioni sugli errori di consegna{#understanding-delivery-failures}

## Errori di consegna {#about-delivery-failures}

Quando una consegna non può essere inviata a un profilo, il server remoto invia automaticamente un messaggio di errore, prelevato dalla piattaforma Adobe Campaign e qualificato per determinare se l'indirizzo e-mail o il numero di telefono devono essere posti in quarantena. Consultate Qualificazione [della posta](#bounce-mail-qualification)Bounce.

>[!NOTE]
>
>**I messaggi di errore e-mail** (o "rimbalzi") sono qualificati dal processo inMail. **I messaggi di errore SMS** (o "SR" per "Report di stato") sono qualificati dal processo MTA.

I messaggi possono essere esclusi durante la preparazione del recapito se un indirizzo viene messo in quarantena o se un profilo viene inserito in una blacklist. I messaggi esclusi sono elencati nella **[!UICONTROL Exclusion logs]** scheda del dashboard di distribuzione (vedere [questa sezione](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Argomenti correlati:**

* [Gestione della quarantena](../../sending/using/understanding-quarantine-management.md)
* [Gestione della blacklist in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identificazione degli errori di consegna per un messaggio {#identifying-delivery-failures-for-a-message}

Una volta inviata la consegna, la **[!UICONTROL Sending logs]** scheda (vedere [questa sezione](../../sending/using/monitoring-a-delivery.md#sending-logs)) consente di visualizzare lo stato della consegna per ciascun profilo e il tipo e il motivo di errore associati (vedere Tipi e motivi [di](#delivery-failure-types-and-reasons)consegna non riuscita).

![](assets/sending_logs.png)

È inoltre disponibile un rapporto specifico. Questo rapporto descrive gli errori rigidi e morbidi riscontrati durante le consegne e l'elaborazione automatica dei rimbalzi. For more on this, refer to [this section](../../reporting/using/bounce-summary.md).

## Tipi e motivi di mancata consegna {#delivery-failure-types-and-reasons}

Se una consegna non riesce, si verificano tre tipi di errori:

* **Duro**: Un errore "hard" indica un indirizzo non valido. Ciò comporta un messaggio di errore che indica esplicitamente che l'indirizzo non è valido, ad esempio: "Utente sconosciuto".
* **Soft**: Potrebbe trattarsi di un errore temporaneo o di un errore che non è stato possibile classificare, ad esempio: "Dominio non valido" o "Cassetta postale completa".
* **Ignorato**: Si tratta di un errore che è noto come temporaneo, ad esempio "Fuori sede" o un errore tecnico, ad esempio se il tipo di mittente è "postmaster".

I possibili motivi di un mancato recapito sono:

* **[!UICONTROL User unknown]** (tipo rigido): l'indirizzo non esiste. Per questo profilo non verranno tentate ulteriori consegne.
* **[!UICONTROL Quarantined address]** (tipo rigido): l'indirizzo è stato messo in quarantena.
* **[!UICONTROL Unreachable]** (tipo morbido/rigido): si è verificato un errore nella catena di distribuzione dei messaggi (incidente sul relay SMTP, dominio temporaneamente irraggiungibile, ecc.). In base all'errore restituito dal provider, l'indirizzo verrà inviato direttamente alla quarantena o la consegna verrà ritentata finché Campaign non riceve un errore che giustifica lo stato della quarantena o finché il numero di errori non raggiunge 5.
* **[!UICONTROL Address empty]** (tipo rigido): l'indirizzo non è definito.
* **[!UICONTROL Mailbox full]** (tipo morbido): la cassetta postale di questo utente è piena e non può accettare altri messaggi. Questo indirizzo può essere rimosso dall'elenco di quarantena per effettuare un altro tentativo. Viene rimosso automaticamente dopo 30 giorni.

   Per consentire la rimozione automatica dell’indirizzo dall’elenco degli indirizzi in quarantena, è necessario avviare il flusso di lavoro tecnico **[!UICONTROL Database cleanup]**.

* **[!UICONTROL Refused]** (tipo morbido/rigido): l'indirizzo è stato messo in quarantena a causa di un feedback di sicurezza come rapporto di spam. In base all'errore restituito dal provider, l'indirizzo verrà inviato direttamente alla quarantena o la consegna verrà ritentata finché Campaign non riceve un errore che giustifica lo stato della quarantena o finché il numero di errori non raggiunge 5.
* **[!UICONTROL Duplicate]**: l'indirizzo è già stato rilevato nella segmentazione.
* **[!UICONTROL Not defined]** (tipo morbido): l'indirizzo è nella qualifica perché gli errori non sono ancora stati incrementati.

   Questo tipo di errore si verifica quando un nuovo messaggio di errore viene inviato dal server: può essere un errore isolato, ma se si verifica di nuovo, il contatore di errori aumenta, che avviserà i team tecnici.

* **[!UICONTROL Error ignored]**: l'indirizzo è nella whitelist e in ogni caso vi verrà inviato un messaggio e-mail.
* **[!UICONTROL Blacklisted address]**: l'indirizzo è stato inserito in una blacklist al momento dell'invio.
* **[!UICONTROL Account disabled]** (tipo morbido/rigido): quando Internet Access Provider (IAP) rileva un lungo periodo di inattività, può chiudere l'account dell'utente: le consegne all'indirizzo dell'utente saranno quindi impossibili. Il tipo Soft o Hard dipende dal tipo di errore ricevuto: se l'account è temporaneamente disattivato a causa di sei mesi di inattività e può essere ancora attivato, lo stato **[!UICONTROL Erroneous]** verrà assegnato e la consegna verrà ritentata. Se l'errore ricevuto segnala che l'account è disattivato in modo permanente, verrà inviato direttamente a Quarantine.
* **[!UICONTROL Not connected]**: il telefono cellulare del profilo viene spento o non è connesso alla rete quando il messaggio viene inviato.
* **[!UICONTROL Invalid domain]** (tipo morbido): il dominio dell'indirizzo e-mail non è corretto o non esiste più. Questo profilo verrà nuovamente eseguito il targeting fino a raggiungere 5. Successivamente, il record verrà impostato sullo stato Quarantine e non verrà seguito alcun nuovo tentativo.
* **[!UICONTROL Text too long]**: il numero di caratteri nel messaggio SMS supera il limite. Per ulteriori informazioni, consulta Codifica [SMS, lunghezza e traslitterazione](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).
* **[!UICONTROL Character not supported by encoding]**: il messaggio SMS contiene uno o più caratteri non supportati dalla codifica. &amp;Per ulteriori informazioni, vedere [Tabella di caratteri - GSM Standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard).

## Tentativi dopo un errore temporaneo di consegna {#retries-after-a-delivery-temporary-failure}

Se un messaggio non riesce a causa di un errore temporaneo del tipo **Ignorato** , i tentativi verranno eseguiti durante la durata del recapito. Per ulteriori informazioni sui tipi di errori, consulta Tipi di errori di [consegna e motivi](#delivery-failure-types-and-reasons).

Per modificare la durata di una consegna, passate ai parametri avanzati del modello di consegna o consegna e specificate la durata desiderata nel campo corrispondente. Le proprietà di consegna avanzate sono presentate in [questa sezione](../../administration/using/configuring-email-channel.md#validity-period-parameters).

La configurazione predefinita consente cinque tentativi a intervalli di un'ora, seguiti da un nuovo tentativo al giorno per quattro giorni. Il numero di tentativi può essere modificato a livello globale (rivolgetevi al vostro amministratore tecnico Adobe) o per ogni modello di consegna o consegna (consultate [questa sezione](../../administration/using/configuring-email-channel.md#sending-parameters)).

## Errori sincroni e asincroni {#synchronous-and-asynchronous-errors}

Una consegna può non riuscire immediatamente (errore sincrono), o successivamente, dopo che è stata inviata (errore asincrono).

* **Errore** sincrono: il server remoto contattato dal server di distribuzione di Adobe Campaign ha immediatamente restituito un messaggio di errore. La consegna non può essere inviata al server del profilo.
* **Errore** asincrono: un messaggio di rimbalzo o un SR veniva inviato successivamente dal server ricevente. Gli errori asincroni possono verificarsi fino a una settimana dopo l'invio di una consegna.

## Qualificazione della posta {#bounce-mail-qualification}

I messaggi di errore relativi alla distribuzione (o "rimbalzi") vengono raccolti dalla piattaforma Adobe Campaign e qualificati dal processo inMail per arricchire l'elenco delle regole di gestione delle e-mail.

Questo elenco è disponibile solo per gli amministratori e contiene tutte le regole utilizzate da Adobe Campaign per qualificare gli errori di consegna.

Per accedervi, fate clic sul **[!UICONTROL Adobe Campaign]** logo, in alto a sinistra, quindi selezionate **[!UICONTROL Administration > Channels > Email > Email processing rules]**.

For more on this, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

Gli oggetti Bounce possono avere i seguenti stati di qualifica:

* **[!UICONTROL To qualify]**: il messaggio deve essere qualificato. La qualifica deve essere fornita dal team Deliverability per garantire il corretto funzionamento della piattaforma. Fintanto che non è qualificato, il messaggio di rimbalzo non viene utilizzato per arricchire l'elenco delle regole di elaborazione e-mail.
* **[!UICONTROL Keep]**: il messaggio di rimbalzo è qualificato e verrà utilizzato dal flusso di lavoro **Aggiorna per la recapito** , per essere confrontato con le regole di elaborazione e-mail esistenti e arricchire l'elenco.
* **[!UICONTROL Ignore]**: il messaggio di rimbalzo era qualificato ma non verrà utilizzato dal flusso di lavoro **Aggiorna per la recapito** . Pertanto, non verrà inviato alle istanze client.

Per elencare i vari rimbalzi e i relativi tipi di errori e motivi, fare clic sul **[!UICONTROL Adobe Campaign]** logo, in alto a sinistra, quindi selezionare **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)

## Ottimizzazione della recapito della posta con il meccanismo di doppio consenso {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

Il doppio meccanismo di consenso è una procedura consigliata per l'invio di e-mail. Protegge la piattaforma da indirizzi e-mail errati o non validi, spambots e impedisce possibili reclami di spam.

Il principio consiste nell'inviare un'e-mail per confermare l'accordo del visitatore prima di memorizzarlo come "profili" nel database Campaign: il visitatore compila una pagina di destinazione online, quindi riceve un messaggio e-mail e deve fare clic sul collegamento di conferma per finalizzare l’iscrizione.

For more on this, refer to [this section](../../channels/using/setting-up-a-double-opt-in-process.md).
