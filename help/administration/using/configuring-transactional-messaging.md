---
title: Configurazione dei messaggi transazionali
seo-title: Configurazione dei messaggi transazionali
description: Configurazione dei messaggi transazionali
seo-description: Scopri come configurare i messaggi transazionali.
page-status-flag: never-activated
uuid: 4 caeadbe-f 4 a 7-43 ce -986 d-e 99 fa 9 ca 0 d 0 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: riferimento
topic-tags: configuring-channels
discoiquuid: 3 f 968556-e 774-43 dc-a 0 b 8-7188 d 7665 fbc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8e2f947cce39ce08f233292d34cb4440aa48a2b5

---


# Configuring transactional messaging{#configuring-transactional-messaging}

Per inviare un messaggio di transazione con Adobe Campaign, devi prima descrivere la struttura dei dati dell'evento.

Event configuration must be performed by an **administrator** by following the steps below:

La configurazione può variare in base al tipo di messaggio transazionali da inviare. For more on this, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations)

Una volta pubblicato l'evento, viene automaticamente creato il messaggio transazionali corrispondente. For more on transactional messaging, refer to [this page](../../channels/using/about-transactional-messaging.md).

## Creating an event {#creating-an-event}

Iniziate creando l'evento in base alle vostre esigenze.

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Event configuration]**.
1. Click the **[!UICONTROL Create]** button.
1. Give a **[!UICONTROL Label]** and an **[!UICONTROL ID]** to the event. **[!UICONTROL ID]** Il campo è obbligatorio e deve iniziare con il prefisso "EVT". If you do not use this prefix, it is automatically added once you click **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

   >[!CAUTION]
   >
   >L'ID non deve superare i 64 caratteri, incluso il prefisso EVT.

1. Select the channel that will be used to send your transactional messages **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** or **[!UICONTROL Mobile application]** (push notification).

   >[!NOTE]
   >
   >Per ogni configurazione di evento è possibile utilizzare un solo canale. Una volta creato l'evento, non potete modificare il canale.

1. Select the targeting dimension corresponding to the desired event configuration and click **[!UICONTROL Create]**.

   I messaggi transazionali basati su evento contengono dati di destinazione contenuti nell'evento stesso, mentre i messaggi transazionali basati su profilo contengono dati di destinazione contenuti nel database Adobe Campaign. For more on this, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

## Defining the event attributes {#defining-the-event-attributes}

In the **[!UICONTROL Fields]** section, define the attributes that will be integrated into the event content and will then be able to be used to personalize the transactional message.

The steps for adding and modifying fields are the same as for [custom resources](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>If you want to create a multilingual transactional message, define an additional event attribute with the **[!UICONTROL AC_language]** ID. Ciò vale solo per i messaggi transazionali degli eventi. Una volta pubblicato l'evento, i passaggi per modificare il contenuto di un messaggio transazionale multilingue sono identici a quelli per un'e-mail standard multilingue. See [Creating a multilingual email](../../channels/using/creating-a-multilingual-email.md).

## Defining data collections {#defining-data-collections}

Potete aggiungere al contenuto dell'evento una raccolta di elementi, ogni elemento stesso compreso vari attributi.

This collection can be used in a transactional email to add product lists to the content of the message, for example a list of products - with the price, reference number, quantity, etc. per ciascun prodotto dell'elenco.

1. In the **[!UICONTROL Collections]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/message-center_collection_create.png)

1. Aggiungete un'etichetta e un ID per la raccolta.
1. Aggiungi tutti i campi da visualizzare nel messaggio di transazione per ogni prodotto dell'elenco.

   In questo esempio sono stati aggiunti i seguenti campi:

   ![](assets/message-center_collection_fields.png)

Una volta pubblicati l'evento e il messaggio, potrete utilizzare questa raccolta nel messaggio transazionali.

Di seguito viene illustrata l'anteprima API per questo esempio:

![](assets/message-center_collection_api-preview.png)

**Argomenti correlati:**

* [Anteprima e pubblicazione dell'evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)
* [Uso degli elenchi di prodotti in un messaggio transazionale](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## Enriching the transactional message content {#enriching-the-transactional-message-content}

L'arricchimento del contenuto dei messaggi transazionali con informazioni dal database Adobe Campaign consente di personalizzare i messaggi. Dal cognome o dall'ID CRM di ciascun destinatario, ad esempio, puoi recuperare dati quali indirizzo o data di nascita o qualsiasi altro campo personalizzato aggiunto nella tabella Profilo, per personalizzare le informazioni che sono state loro inviate.

It is possible to enrich the transactional message content with information from extended **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources.

Queste informazioni possono essere memorizzate anche in nuove risorse. In that case, the resource must be linked to the **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources either directly, or via another table. For example, in the configuration below, it is possible to enrich the transactional message content with information from the **[!UICONTROL Product]** resource like the product category or ID, if the **[!UICONTROL Product]** resource is linked to the **[!UICONTROL Profile]** resource.

![](assets/message-center_usecaseschema.png)

For more on resource creation and publishing, refer to [this page](../../developing/using/key-steps-to-add-a-resource.md).

1. In the **[!UICONTROL Enrichment]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/message-center_addenrichment.png)

1. Selezionate la risorsa con la quale desiderate collegare il messaggio. In this case, choose the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_new-enrichment.png)

1. Use the **[!UICONTROL Create element]** button to link a field from the selected resource to one of the fields you previously added to the event (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. In this example, we reconcile the **[!UICONTROL Last name]** and the **[!UICONTROL First name]** fields with the corresponding fields in the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_enrichment-join-fields.png)

1. In the **[!UICONTROL Targeting enrichment]** section, select the enrichment that will be used as the message target during the delivery execution. In this example, select **[!UICONTROL Profile]**. La selezione di un arricchimento di targeting è obbligatoria per gli eventi basati su profilo.

   ![](assets/message-center_marketing_targeting_enrichment.png)

Once the event and the message are published, the link with the **[!UICONTROL Profile]** resource will allow you to enrich the content of the transactional message.

**Argomenti correlati:**

* [Anteprima e pubblicazione dell'evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).
* [Personalizzazione di un messaggio transazionale](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

## Previewing and publishing the event {#previewing-and-publishing-the-event}

Prima di poter utilizzare l'evento, è necessario visualizzarlo in anteprima e pubblicarlo.

1. Click the **[!UICONTROL API preview]** button to see a simulation of the REST API that will be used by your website developer before it is published. Una volta pubblicato l'evento, questo pulsante consente anche di visualizzare un'anteprima dell'API in produzione. See [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >La REST API varia a seconda del canale selezionato e della dimensione di targeting selezionata. For more details on the various configurations, refer to [Transactional event specific configurations](../../administration/using/configuring-transactional-messaging.md#transactional-event-specific-configurations).

1. Click **[!UICONTROL Publish]** to start publication.

   ![](assets/message-center_pub.png)

1. Potete visualizzare i registri di pubblicazione selezionando la scheda corrispondente.

   ![](assets/message-center_logs.png)

   Potete inoltre consultare le pubblicazioni precedenti selezionando la scheda.

>[!NOTE]
>
>Each time you modify the event, you must click **[!UICONTROL Publish]** again to generate the updated REST API that will be used by your website developer.

Una volta pubblicato l'evento, viene automaticamente creato un messaggio transazionale collegato al nuovo evento. Affinché questo evento attivi l'invio di un messaggio transazionale, è necessario modificare e pubblicare il messaggio appena creato. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

Potete accedere al messaggio transazionali creato direttamente dal collegamento nell'area lato sinistro.

![](assets/message-center_messagegeneration.png)

Dovete anche integrare questo evento di attivazione nel sito Web. See [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Unpublishing an event {#unpublishing-an-event}

**[!UICONTROL Unpublish]** Il pulsante consente di annullare la pubblicazione dell'evento, che elimina dalla REST API la risorsa corrispondente all'evento creato in precedenza. Ora, anche se l'evento viene attivato attraverso il sito Web, i messaggi corrispondenti non vengono più inviati e non vengono memorizzati nel database.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Se avete già pubblicato il messaggio transazionali corrispondente, viene annullata anche la pubblicazione dei messaggi transazionali. See [Unpublishing a transactional message](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

Click the **[!UICONTROL Publish]** button to generate a new REST API.

## Integrating the triggering of the event in a website {#integrating-the-triggering-of-the-event-in-a-website}

Dopo aver creato un evento, dovrete integrare l'attivazione di questo evento nel sito Web.

In the example described in the [Transactional messaging operating principle](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) section, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart. A tal fine, lo sviluppatore Web del sito Web deve utilizzare l'API REST di Adobe Campaign Standard.

See the [REST API Documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#transactional-messages-api) .

## Transactional event specific configurations {#transactional-event-specific-configurations}

La configurazione dell'evento transazionali può variare a seconda del tipo di messaggio transazionale da inviare (evento o profilo) e del canale che verrà utilizzato.

Nelle sezioni seguenti viene descritto quale configurazione specifica deve essere impostata in base al messaggio transazionale desiderato. For more on the general steps to configure an event, refer to [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

### Event-based transactional messages {#event-based-transactional-messages}

Per inviare un messaggio transazionali basato su eventi, occorre innanzitutto creare e configurare un evento con i dati contenuti nell'evento stesso.

1. When creating the event configuration, select the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enrich the transactional message content if you want to use additional information from the Adobe Campaign database (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >La messaggistica transazionale basata su evento dovrebbe utilizzare solo i dati presenti nell'evento inviato per definire il destinatario e la personalizzazione dei contenuti dei messaggi. Tuttavia, puoi arricchire il contenuto del messaggio transazionale utilizzando informazioni provenienti dal database Adobe Campaign.

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Quando si visualizza l'anteprima dell'evento, l'API REST contiene un attributo che specifica l'indirizzo e-mail o il cellulare in base al canale selezionato.

   Una volta pubblicato l'evento, viene automaticamente creato un messaggio transazionale collegato al nuovo evento. In order for the event to trigger sending a transactional message, you must modify and publish the message that was just created, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Profile-based transactional messages {#profile-based-transactional-messages}

Per inviare un messaggio transazionale basato su profilo, devi prima creare e configurare i dati di targeting degli eventi contenuti nel database Adobe Campaign.

1. When creating the event configuration, select the **[!UICONTROL Profile event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)). È necessario aggiungere almeno un campo per creare un arricchimento. You do not need to create other fields such as **First name** and **Last name** as you will be able to use personalization fields from the Adobe Campaign database.
1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). Creating an enrichment is mandatory when using a **[!UICONTROL Profile]** targeting dimension.
1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the email address or the mobile phone as it will be retrieved from the **[!UICONTROL Profile]** resource.

   Una volta pubblicato l'evento, viene automaticamente creato un messaggio transazionale collegato al nuovo evento. In order for the event to trigger sending a transactional message, you must modify and publish the message that was just created, see [Sending a profile transactional message](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Event-based transactional push notifications {#event-based-transactional-push-notifications}

Per poter inviare notifiche push transazionali, devi configurare di conseguenza Adobe Campaign. See [Push configuration](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Per inviare una notifica push transazionale a tutti gli utenti che hanno acconsentito alla ricezione di notifiche dall'applicazione mobile, occorre innanzitutto creare e configurare un evento con i dati contenuti nell'evento stesso. I passaggi corrispondenti sono indicati di seguito.

L'evento deve contenere i tre elementi seguenti:

* A **registration token**, which is the user ID for one mobile application and one device. Potrebbe non corrispondere ad alcun profilo dal database Adobe Campaign.
* A **mobile application name** (one for all devices - Android and iOS). Si tratta dell'ID dell'applicazione mobile configurata in Adobe Campaign che verrà utilizzata per ricevere notifiche push sui dispositivi degli utenti. For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* A **push platform** ("gcm" for Android or "apns" for iOS).

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Add fields to the event, in order to be able to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).
1. Enrich the transactional message content if you want to use additional information from Adobe Campaign database (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >La messaggistica transazionale basata su evento dovrebbe utilizzare solo i dati presenti nell'evento inviato per definire il destinatario e la personalizzazione dei contenuti dei messaggi. Tuttavia, puoi arricchire il contenuto del messaggio transazionale utilizzando informazioni provenienti dal database Adobe Campaign.

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Quando si visualizza l'anteprima dell'evento, l'API REST contiene gli attributi "registrationtoken", "application" e "pushplatform" che verranno utilizzati per eseguire il targeting della distribuzione.

   ![](assets/message-center_push_api.png)

   Una volta che l'evento è stato pubblicato, viene automaticamente creata una notifica push transazionale collegata al nuovo evento. To modify and publish the message that was just created, see [Sending a transactional push notification targeting an event](/channels/using/transactional-push-notifications.html#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event#sending-a-transactional-push-notification-targeting-an
----------event).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Profile-based transactional push notifications {#profile-based-transactional-push-notifications}

Per inviare una notifica push transazionale ai profili di Adobe Campaign che hanno effettuato la sottoscrizione all'applicazione mobile, devi prima creare e configurare un evento con il database Adobe Campaign.

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Profile]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).

   Per impostazione predefinita, la notifica push transazionale viene inviata a tutte le applicazioni mobili a cui sono iscritti i destinatari. Per inviare la notifica push a un'applicazione mobile specifica, selezionala nell'elenco. Le altre applicazioni mobili verranno eseguite in base al messaggio, ma saranno escluse dall'invio.

   ![](assets/message-center_push_appfilter.png)

1. Add fields to the event, if you want to personalize the transactional message (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >È necessario aggiungere almeno un campo per creare un arricchimento. You do not need to create other fields such as **First name** and **Last name** as you will be able to use personalization fields from the Adobe Campaign database.

1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)). Creating an enrichment is mandatory when using a **[!UICONTROL Profile]** targeting dimension.
1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the registration token, the application name and the push platform as they will be retrieved from the **[!UICONTROL Profile]** resource.

   Una volta che l'evento è stato pubblicato, viene automaticamente creata una notifica push transazionale collegata al nuovo evento. To modify and publish the message that was just created, see [Sending a transactional push notification targeting a profile](/channels/using/transactional-push-notifications.html#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile#sending-a-transactional-push-notification-targeting-a
----------profile).

1. Integrate the event into your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

### Configuring an event to send a follow-up message {#configuring-an-event-to-send-a-follow-up-message}

Un messaggio di follow-up è un modello di consegna di marketing predefinito che può essere utilizzato in un flusso di lavoro per inviare messaggi ai destinatari di un messaggio transazionali specifico. For more on this, see [Follow-up messages](../../channels/using/follow-up-messages.md).

1. Utilizzate la stessa configurazione evento creata per inviare un messaggio transazionale evento. See [Event-based transactional messages](../../administration/using/configuring-transactional-messaging.md#event-based-transactional-messages).
1. When configuring your event, check the **[!UICONTROL Create follow-up delivery template for this event]** box before publishing the event.

   ![](assets/message-center_follow-up-checkbox.png)

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).

   Una volta pubblicato l'evento, viene automaticamente creato un messaggio di transazione e un modello di consegna successivo collegato al nuovo evento. For more on using follow-up messages, see [Sending a follow-up message](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).

## Use case: configuring an event to send a transactional message {#use-case--configuring-an-event-to-send-a-transactional-message}

In questo esempio, desideriamo configurare un evento per inviare messaggi di conferma dopo ogni acquisto sul nostro sito Web con i seguenti prerequisiti:

As we want to identify our client via his CRM ID, first make sure that the **[!UICONTROL Profile]** resource has been extended with this new field.

In the same way, a custom resource corresponding to purchases must have been created and published, and must be linked to the **[!UICONTROL Profile]** resource. In questo modo potrete ottenere informazioni da questa risorsa per arricchire il contenuto dei messaggi.

For more on resource creation and publishing, refer to [this page](../../developing/using/key-steps-to-add-a-resource.md).

1. Create a new event using the **[!UICONTROL Email]** channel and the **[!UICONTROL Profile]** targeting dimension (see [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event)).
1. Definite gli attributi che saranno disponibili per personalizzare il messaggio transazionale. In our case, add the "CRM ID" and the "Product identifier" fields (see [Defining the event attributes](../../administration/using/configuring-transactional-messaging.md#defining-the-event-attributes)).

   ![](assets/message-center_usecase1.png)

1. To enrich the message content with information regarding the client's previous purchases, create an enrichment targeting the **[!UICONTROL Purchase]** resource (see [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Create a join condition between the "Product identifier" field that was previously added to the message, and the corresponding field from the **[!UICONTROL Purchase]** resource

   ![](assets/message-center_usecase3.png)

1. Preview and publish the event (see [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event)).
1. Integrate the event in your website (see [Integrating the triggering of the event in a website](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)).

