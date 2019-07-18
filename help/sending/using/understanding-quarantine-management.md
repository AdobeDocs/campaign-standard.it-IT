---
title: Gestione della gestione della quarantena
seo-title: Gestione della gestione della quarantena
description: Gestione della gestione della quarantena
seo-description: Scopri come ottimizzare il rendimento con la gestione della quarantena.
page-status-flag: never-activated
uuid: 3 c 287865-1 ada -4351-b 205-51807 ff 9 f 7 ed
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: invio
content-type: riferimento
topic-tags: monitoring-messages
discoiquuid: de 3 a 50 b 6-ea 8 f -4521-996 b-c 49 cc 1 f 3 c 946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5b3ea982f08e1198e8c88f78a5faf8a80b935db4

---


# Understanding quarantine management{#understanding-quarantine-management}

## About quarantines {#about-quarantines}

Un indirizzo e-mail o un numero di telefono può essere messo in quarantena, ad esempio quando la casella postale è piena o se l'indirizzo non esiste.

In any case, the quarantine procedure complies with specific rules described in this [section](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).

### Optimizing your delivery through quarantines {#optimizing-your-delivery-through-quarantines}

The profiles whose email addresses or phone number are in quarantine are automatically excluded during message preparation (see [Identifying quarantined addresses for a delivery](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-a-delivery)). Questo consente di velocizzare le consegne, in quanto il tasso di errore incide sulla velocità di consegna.

Alcuni provider di accesso a Internet considerano automaticamente le e-mail se la velocità degli indirizzi non validi è troppo alta. La quarantena, pertanto, consente di evitare di inserire in blacklist i fornitori.

Inoltre, le lettine contribuiscono a ridurre i costi di invio SMS escludendo quelli erronei dalle consegne.

For more on best practices to secure and optimize your deliveries, refer to [this page](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Quarantine vs blacklisting {#quarantine-vs-blacklisting}

**La quarantena** si applica solo a un indirizzo, non al profilo stesso. Ciò significa che, se due profili hanno lo stesso indirizzo e-mail, verranno entrambi modificati se l'indirizzo viene messo in quarantena.

Analogamente, un profilo il cui indirizzo e-mail viene messo in quarantena può aggiornare il proprio profilo e immettere un nuovo indirizzo, e quindi essere indirizzato di nuovo dalle azioni di consegna.

**L'Elenco in blacklist**, ad esempio, darà luogo al profilo non più destinato ad alcun tipo di consegna, ad esempio dopo un'iscrizione (opt-out). For more on the blacklisting process, refer to [Managing blacklisting in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>Quando un utente risponde a un messaggio SMS con una parola chiave come "STOP" per rifiutare le consegne SMS, il profilo non viene elencato come nel processo di rinuncia e-mail. The profile phone number is sent to quarantine with the **[!UICONTROL Blacklisted]** status. Questo stato fa riferimento solo al numero di telefono, il profilo non viene inserito in lista nera in modo che l'utente continui a ricevere messaggi e-mail. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identifying quarantined addresses {#identifying-quarantined-addresses}

Gli indirizzi in quarantena possono essere elencati per una distribuzione specifica o per l'intera piattaforma.

>[!NOTE]
>
>Se devi rimuovere un indirizzo dalla quarantena, contatta l'amministratore tecnico.

### Identifying quarantined addresses for a delivery {#identifying-quarantined-addresses-for-a-delivery}

Quarantined addresses for a specific delivery are listed during the delivery preparation phase, in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identifying quarantined addresses for the entire platform {#identifying-quarantined-addresses-for-the-entire-platform}

Administrators can list the addresses in quarantine for the entire platform from the **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menu.

>[!NOTE]
>
>This menu lists quarantined elements for **email**, **SMS** and **Push notification** channels.

![](assets/quarantines1.png)

>[!NOTE]
>
>L'incremento in termini di quarantena è un effetto normale, correlato alla "usura" del database. Ad esempio, se la durata di un indirizzo e-mail è considerata di tre anni e la tabella destinatario aumenta di 50% ogni anno, l'aumento delle entrate può essere calcolato come segue: Fine anno 1: (1 * 0.33)/(1+0.5) = 22%. Fine anno 2: ((1.22 * 0.33) +0.33)/(1.5+0.75) = 32.5%.

## Conditions for sending an address to quarantine {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign manages quarantine according to the delivery failure type and the reason assigned during error messages qualification (see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) and [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Errore ignorato**: gli errori ignorati non inviano un indirizzo alla quarantena.
* **Errore grave**: l'indirizzo e-mail corrispondente viene inviato immediatamente alla quarantena.
* **Errore leggero**: gli errori software non inviano immediatamente un indirizzo alla quarantena, ma aumentano un contatore di errore. Quando il contatore di errore raggiunge la soglia di limite, l'indirizzo entra in quarantena. Nella configurazione predefinita, la soglia è impostata su cinque errori, in cui due errori sono significativi se si verificano almeno 24 ore. L'indirizzo viene posizionato in quarantena al sesto errore. La soglia del contatore di errore può essere modificata. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   Quando una consegna viene eseguita dopo un tentativo, il contatore di errore dell'indirizzo precedente alla quarantena viene riinizializzato. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.

If a user qualifies an email as a spam (**Feedback loop**), the message is automatically redirected towards a technical mailbox managed by Campaign. The user's email address is then automatically sent to quarantine with the **[!UICONTROL Blacklisted]** status. Questo stato fa riferimento solo all'indirizzo, il profilo non viene elencato in lista nera, per cui l'utente continua a ricevere messaggi SMS e notifiche push.

>[!NOTE]
La quarantena in Adobe Campaign fa distinzione tra maiuscole e minuscole. Accertatevi di importare gli indirizzi e-mail nel caso inferiore, in modo che non vengano reindirizzati successivamente.

In the list of quarantined addresses (see [Identifying quarantined addresses for the entire platform](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)), the **[!UICONTROL Error reason]** field indicates why the selected address was placed in quarantine.

![](assets/quarantines2.png)

