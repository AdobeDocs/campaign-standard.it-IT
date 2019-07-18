---
title: Messaggi transazionali profilo
seo-title: Messaggi transazionali profilo
description: Messaggi transazionali profilo
seo-description: Scopri come creare e pubblicare un messaggio transazionale profilo.
page-status-flag: never-activated
uuid: a 8 efe 979-74 ae -46 ff-a 305-b 86 a 90679581
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: transactional-messaging
discoiquuid: dcb 90 afc -42 c 3-419 e -8345-79 cddf 969 e 41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Profile transactional messages{#profile-transactional-messages}

Puoi inviare messaggi transazionali basati sui profili di marketing dei clienti, che permettono di:

* Apply marketing typology rules such as **[!UICONTROL Blacklisted address]** or [fatigue rules](../../administration/using/fatigue-rules.md).
* Includi il collegamento di annullamento iscrizione all'interno dei messaggi.
* Aggiungete i messaggi transazionali al reporting globale della distribuzione.
* Sfrutta i messaggi transazionali nel percorso del cliente.

Once you have created and published an event (the cart abandonment as per the [example](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) above), the corresponding transactional message is created automatically.

The configuration steps are presented in the [Configuring an event to send a profile transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

Affinché l'evento attivi l'invio di un messaggio transazionale, dovete personalizzare il messaggio, quindi testarlo e pubblicarlo.

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group. Le regole di fatigue sono compatibili con i messaggi transazionali del profilo. See [Fatigue rules](../../administration/using/fatigue-rules.md).

## Sending a profile transactional message {#sending-a-profile-transactional-message}

I passaggi per creare, personalizzare e pubblicare un messaggio transazionale di profilo sono identici a quelli di un messaggio transazionale dell'evento. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

Le differenze sono elencate di seguito.

1. Passate il messaggio transazionali creato per modificarlo.
1. In the transactional message, click the **[!UICONTROL Content]** section. In addition to the transactional template, you can also choose the default email template, which targets **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Selezionate il modello e-mail predefinito.

   Simili a tutte le e-mail di marketing, include un collegamento non sottoscrizione.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Inoltre, invece di configurazioni basate su eventi in tempo reale, hai accesso diretto a tutte le informazioni sul profilo per personalizzare il messaggio. See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md).

1. Salvate le modifiche e pubblicate il messaggio. See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Monitoring a profile transactional message delivery {#monitoring-a-profile-transactional-message-delivery}

Una volta pubblicato il messaggio e l'integrazione del sito, potete monitorare la consegna.

1. To view the message delivery log, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   For more information on accessing the logs, see [Monitoring the delivery](../../sending/using/monitoring-a-delivery.md).

1. Select the **[!UICONTROL Sending logs]** tab. In the **[!UICONTROL Status]** column, **[!UICONTROL Sent]** indicates that a profile has opted in.

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as blacklisted addresses.

   ![](assets/message-center_marketing_exclusion_logs.png)

For any profile that has opted out, the **[!UICONTROL Blacklisted address]** typology rule excluded the corresponding recipient.

This rule is part of a specific typology that applies to all transactional messages based on the **[!UICONTROL Profile]** table.

![](assets/message-center_marketing_typology.png)

**Argomenti correlati**:

* [Integrazione del sito](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Typolgies](../../administration/using/about-typology-rules.md)

