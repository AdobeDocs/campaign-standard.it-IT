---
title: Informazioni sui messaggi transazionali
seo-title: Informazioni sui messaggi transazionali
description: Informazioni sui messaggi transazionali
seo-description: Scopri i diversi tipi di messaggi transazionali che puoi inviare e come vengono utilizzati in Adobe Campaign.
page-status-flag: never-activated
uuid: 8470 e 9 e 2-ee 17-456 f -9 e 4 c -460 e 69 c 78 a 2 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: transactional-messaging
discoiquuid: 71 a 4 d 5 d 5-fe 2 a -4 ce 5-b 22 b-a 4736 f 7 add 83
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d93c2600299a8d2ec3672b3d82222f423878034c

---


# About transactional messaging{#about-transactional-messaging}

Puoi creare e gestire messaggi transazionali personalizzati in Adobe Campaign.

Un messaggio transazionale è una comunicazione singola e univoca inviata a un utente da un fornitore quale un sito Web.

* Questo tipo di messaggio è particolarmente atteso, in quanto contiene informazioni che il destinatario desidera controllare o confermare. Potrebbe essere un messaggio di benvenuto dopo la creazione di un account, ad esempio un'attestazione ricevuta da un ordine, una bolletta o un messaggio che conferma la modifica della password.
* Si tratta di un messaggio importante che definisce la relazione client: l'utente deve essere inviato in tempo reale. Il ritardo tra l'attivazione dell'evento e l'invio del messaggio deve pertanto essere molto breve.
* In genere, i messaggi transazionali hanno tassi di apertura elevati.

Adobe Campaign consente di integrare questa funzionalità con un sistema di informazioni che invia eventi da trasformare in messaggi transazionali personalizzati.

>[!NOTE]
>
>I messaggi transazionali possono essere inviati tramite e-mail, SMS o notifica push, a seconda delle opzioni. Controllate il contratto di licenza.

In Adobe Campaign sono disponibili due tipi di messaggi transazionali:

* [Messaggi transazionali evento](../../channels/using/event-transactional-messages.md) destinati a un evento. I dati contenuti nell'evento vengono utilizzati per definire la destinazione di consegna.
* [Profili di targeting dei messaggi](../../channels/using/profile-transactional-messages.md) transazionali provenienti dal database di marketing di Adobe Campaign. Puoi utilizzare le informazioni del database Adobe Campaign per inviare un messaggio di transazione basato sui profili di marketing dei clienti.

Il tipo di messaggio viene definito durante la configurazione dell'evento che verrà trasformato in un messaggio transazionale. See [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign stabilisce la priorità dell'elaborazione dei messaggi transazionali attraverso qualsiasi altra consegna.

I messaggi transazionali sono disponibili anche dall'API standard di Adobe Campaign. For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#about-transactional-messaging).

## Transactional messaging operating principle {#transactional-messaging-operating-principle}

Prendiamo l'esempio di una società che dispone di un sito Web e in questo sito Web gli utenti possono acquistare prodotti.

Adobe Campaign consente di inviare un messaggio e-mail di notifica agli utenti del sito che hanno aggiunto prodotti al carrello: quando una di esse lascia il sito senza oltrepassarlo, viene automaticamente inviato un messaggio e-mail di abbandono al carrello.

I passaggi per posizionarlo sono:

1. Configurate un evento che verrà denominato "abbandono del carrello" e pubblicate la configurazione dell'evento, che crea automaticamente un messaggio transazionale. Creating and publishing an event are presented in the [Configuring an event to send an event transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.
1. Il messaggio transazionali deve essere personalizzato, testato e pubblicato. See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. Inoltre, per attivare l'evento quando un client abbandona il carrello, questo evento deve essere inviato dal sito Web della società utilizzando l'API REST di Adobe Campaign Standard. See [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Una volta eseguiti tutti questi passaggi, non appena un utente lascia il sito senza ordinare i prodotti nel carrello, ricevono automaticamente un messaggio e-mail di notifica.

## Transactional messaging limitations {#transactional-messaging-limitations}

### Design and publication {#design-and-publication}

Mentre progettate e pubblicate messaggi transazionali, alcuni dei passaggi da eseguire non possono essere ripristinati. È necessario conoscere i seguenti limiti:

* Per ogni configurazione di evento è possibile utilizzare un solo canale. See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Una volta creato l'evento, non potete modificare il canale. Pertanto, se un messaggio non viene inviato correttamente, è necessario progettare il meccanismo per inviarlo da un altro canale utilizzando un flusso di lavoro. See [Workflow data and processes](../../automating/using/workflow-data-and-processes.md).
* You cannot change the targeting dimension ( **[!UICONTROL Real-time event]** or **[!UICONTROL Profile]** ) after the event is created. See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Non è possibile ripristinare una pubblicazione, ma potete annullare la pubblicazione di un evento: questa operazione rende inaccessibile l'evento e il messaggio transazionali associato. See [Unpublishing an event](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* L'unico messaggio transazionale che può essere associato a un evento è il messaggio che viene creato automaticamente al momento della pubblicazione dell'evento. See [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalization {#personalization}

Il modo in cui potete personalizzare il contenuto di un messaggio dipende dal tipo di messaggio transazionale. Le specificità sono elencate di seguito:

**Messaggi transazionali basati su evento**:

* Le informazioni di personalizzazione provengono dai dati contenuti nell'evento stesso. See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* You cannot use **Unsubscription link** content blocks in an event transactional message.
* La messaggistica transazionale basata su evento dovrebbe utilizzare solo i dati presenti nell'evento inviato per definire il destinatario e la personalizzazione dei contenuti dei messaggi. Tuttavia, puoi arricchire il contenuto del messaggio transazionale utilizzando informazioni provenienti dal database Adobe Campaign. See [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Poiché i messaggi transazionali degli eventi non contengono informazioni sul profilo, non sono compatibili con le regole di affaticamento, anche nel caso di un arricchimento con profili. See [Fatigue rules](../../administration/using/fatigue-rules.md).

**Messaggi transazionali basati su profilo**:

* Le informazioni di personalizzazione possono provenire dai dati contenuti nell'evento o dal record di profilo riconciliato. See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* You can use **Unsubscription link** content blocks in a profile transactional message. See [Adding a content block](../../designing/using/adding-a-content-block.md).
* Le regole di fatigue sono compatibili con i messaggi transazionali del profilo. See [Fatigue rules](../../administration/using/fatigue-rules.md).

I prodotti sono disponibili solo nei messaggi e-mail transazionali. See [Using product listings in a transactional message](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Permissions and branding {#permissions-and-branding}

When it comes to [branding](../../administration/using/branding.md) management, transactional messaging enables less flexibility than standard messaging. Adobe recommends linking all brands used in transactional messages to the **[!UICONTROL All]** organizational unit. Per ulteriori informazioni, leggi la descrizione dettagliata di seguito.

Quando si modifica un messaggio transazionale, è possibile collegarlo a un marchio per applicare automaticamente alcuni parametri quali il marchio o il logo del marchio. The **[!UICONTROL Default brand]** is selected by default in the transactional message properties.

![](assets/message-center_branding.png)

To access the transactional messages, you must be part of the **[!UICONTROL Message Center agents]** (mcExec) security group, which is linked to the **[!UICONTROL Message Center]** [organizational unit](../../administration/using/organizational-units.md). Therefore, all objects (including branding) used in a transactional message must be visible from the **[!UICONTROL Message Center]** organizational unit, meaning that these objects must be in the **[!UICONTROL Message Center]** or **[!UICONTROL All]** organizational units.

However, if the brand selected in the message properties is linked to an organizational unit which is different from **[!UICONTROL Message Center]** or **[!UICONTROL All]**, this will cause an error and you will not be able to send the transactional message.

Therefore, if you want to use multi-branding in the context of transactional messaging, you should link all brands either to the **[!UICONTROL Message Center]** organizational unit or to the **[!UICONTROL All]** organizational unit.

### Exporting and importing transactional messages {#exporting-and-importing-transactional-messages}

* To export a transactional message, you need to include the corresponding event configuration when [creating the package export](../../automating/using/managing-packages.md#creating-a-package).
* Once the transactional message is [imported through a package](../../automating/using/managing-packages.md#importing-a-package), it is not displayed in the transactional message list. You need to [publish](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) the event configuration in order to make the associated transactional message available.

