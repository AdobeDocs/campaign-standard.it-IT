---
title: Modifica di un messaggio transazionale
description: Scopri come accedere a un messaggio transazionale, modificarlo e personalizzarlo.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: f5dcb715-7cbd-49f2-8713-7e16cfa04184
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 30%

---

# Modifica di un messaggio transazionale {#editing-transactional-message}

Dopo aver creato e pubblicato un evento<!--(the cart abandonment example as explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle))-->, il messaggio transazionale corrispondente viene creato automaticamente.

I passaggi per configurare e pubblicare l’evento sono descritti in [Configurazione di un evento transazionale](../../channels/using/configuring-transactional-event.md) e [Pubblicazione di un evento transazionale](../../channels/using/publishing-transactional-event.md) sezione.

Di seguito sono descritti i passaggi per accedere a questo messaggio, modificarlo e personalizzarlo.

>[!IMPORTANT]
>
>Solo gli utenti con [Amministrazione](../../administration/using/users-management.md#functional-administrators) Il ruolo può accedere e modificare i messaggi transazionali.

Quando il messaggio è pronto, può essere testato e pubblicato. Consulta [Verifica di un messaggio sulle transazioni](../../channels/using/testing-transactional-message.md) e [Ciclo di vita dei messaggi transazionali](../../channels/using/publishing-transactional-message.md).

## Accesso ai messaggi transazionali {#accessing-transactional-messages}

Per accedere al messaggio transazionale creato:

1. Fai clic su **Adobe** in alto a sinistra.
1. Seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Fai clic sul messaggio desiderato per modificarlo.

   ![](assets/message-center_message-board.png)

Puoi anche accedere direttamente a un messaggio transazionale tramite il collegamento che si trova nell’area a sinistra della schermata di configurazione dell’evento corrispondente. Consulta [Anteprima e pubblicazione di un evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)

## Personalizzazione di un messaggio sulle transazioni {#personalizing-a-transactional-message}

Per modificare e personalizzare un messaggio sulle transazioni, segui i passaggi indicati di seguito.

>[!NOTE]
>
>Questa sezione descrive come modificare una **basato su eventi** messaggio transazionale. Il **basato su profilo** le specificità dei messaggi transazionali sono dettagliate [sotto](#profile-transactional-message-specificities).
>
>I passaggi di configurazione per creare un messaggio transazionale basato su eventi sono descritti in [questa sezione](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).

Ad esempio, desideri inviare una notifica agli utenti del tuo sito web che hanno aggiunto prodotti al carrello e lasciano il sito senza procedere con gli acquisti. Questo esempio è presentato nel [Principio operativo della messaggistica transazionale](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) sezione.

1. Fai clic sul blocco **[!UICONTROL Content]** per modificare l’oggetto e il contenuto del messaggio. Ai fini del presente esempio, seleziona un modello contenente immagini e testo. Per ulteriori informazioni sui modelli di contenuto delle e-mail, consulta [Progettazione di e-mail tramite modelli](../../designing/using/using-reusable-content.md#designing-templates).

   ![](assets/message-center_6.png)

1. Aggiungi un oggetto e modifica il contenuto del messaggio in base alle tue esigenze.

   >[!NOTE]
   >
   >Il collegamento al carrello abbandonato porta a un URL esterno che reindirizzerà il consumatore al proprio carrello. Tale parametro non è gestito all’interno di Adobe Campaign.

1. Nell’esempio attuale, vuoi aggiungere tre campi precedentemente definiti durante la [creazione dell’evento](../../channels/using/configuring-transactional-event.md): nome, ultimo prodotto visionato, importo totale del carrello. A tal fine, [inserisci un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field) nel contenuto del messaggio.

1. Puoi accedere ai campi in questione tramite **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. Puoi anche arricchire il contenuto del messaggio. A questo scopo, aggiungi i campi dalla tabella collegata alla configurazione dell’evento (consulta [Arricchimento dell’evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)). In questo esempio, seleziona la **[!UICONTROL Title (salutation)]** campo da **[!UICONTROL Profile]** da tabella a **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7-enrichment.png)

1. Inserisci tutti i campi richiesti.

   ![](assets/message-center_8.png)

1. Per visualizzare l’anteprima del messaggio, seleziona il profilo definito per l’evento.

   La procedura per la visualizzazione dell’anteprima di un messaggio è spiegata nei dettagli nella sezione [Anteprima dei messaggi](../../sending/using/previewing-messages.md).

   ![](assets/message-center_9.png)

   Puoi verificare che i campi di personalizzazione corrispondano alle informazioni inserite nel profilo di test. Per ulteriori informazioni, consulta [Definizione di un profilo di test specifico](../../channels/using/testing-transactional-message.md#defining-specific-test-profile).

<!--## Using product listings in a transactional message {#using-product-listings-in-a-transactional-message}

When editing the content of a transactional email, you can create product listings referencing one or more data collections. For example, in a cart abandonment email, you can include a list of all products that were in the users' carts when they left your website, with an image, the price, and a link to each product.

>[!IMPORTANT]
>
>Product listings are only available for the email channel, when editing transactional email content through the [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface) interface.

To add a list of abandoned products in a transactional message, follow the steps below.

You can also watch [this set of videos](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/designing-content/product-listings-in-transactional-email.html#configure-product-listings-in-transactional-emails) explaining the steps that are required to configure product listings in a transactional email.

>[!NOTE]
>
>Adobe Campaign does not support nested product listings, meaning that you cannot include a product listing inside another one.

### Defining a product listing {#defining-a-product-listing}

Before being able to use a product listing in a transactional message, you need to define at the event level the list of products and the fields for each product of the list you want to display. For more on this, see [Defining data collections](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. In the transactional message, click the **[!UICONTROL Content]** block to modify the email content.
1. Drag and drop a structure component to the workspace. For more on this, see [Defining the email structure](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

   For example, select a one-column structure component and add a text component, an image component and a button component. For more on this, see [Using content components](../../designing/using/designing-from-scratch.md#about-content-components).

1. Select the structure component you just created and click the **[!UICONTROL Enable product listing]** icon from the contextual toolbar.

   ![](assets/message-center_loop_create.png)

   The structure component is highlighted with an orange frame and the **[!UICONTROL Product listing]** settings are displayed in the left palette.

   ![](assets/message-center_loop_palette.png)

1. Select how the elements of the collection will be displayed:

    * **[!UICONTROL Row]**: horizontally, meaning each element on one row under the other.
    * **[!UICONTROL Column]**: vertically, meaning each element next to the other on the same row.

   >[!NOTE]
   >
   >The **[!UICONTROL Column]** option is only available when using a multicolumn structure component ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** and **[!UICONTROL 4:4 column]** ). When editing the product listing, only fill in the first column: the other columns will not be taken into account. For more on selecting structure components, see [Defining the email structure](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Select the data collection you created when configuring the event related to the transactional message. You can find it under the **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** node.

   ![](assets/message-center_loop_selection.png)

   For more on configuring the event, see [Defining data collections](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Use the **[!UICONTROL First item]** drop-down list to select which element will start the list displayed in the email.

   For example, if you select 2, the first item of the collection will not be displayed in the email. The product listing will start on the second item.

1. Select the maximum number of items to display in the list.

   >[!NOTE]
   >
   >If you want the elements of your list to be displayed vertically ( **[!UICONTROL Column]** ), the maximum number of items is limited according to the selected structure component (2, 3 or 4 columns). For more on selecting structure components, see [Editing the email structure](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

### Populating the product listing {#populating-the-product-listing}

To display a list of products coming from the event linked to the transactional email, follow the steps below.

For more on creating a collection and related fields when configuring the event, see [Defining data collections](../../channels/using/configuring-transactional-event.md#defining-data-collections).

1. Select the image component you inserted, select **[!UICONTROL Enable personalization]** and click the pencil in the Settings pane.

   ![](assets/message-center_loop_image.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Image source URL]** window that opens.

   From the **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the image field that you defined (here **[!UICONTROL Product image]** ). Click **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   The personalization field that you selected is now displayed in the Settings pane.

1. At the desired position, select **[!UICONTROL Insert personalization field]** from the contextual toolbar.

   ![](assets/message-center_loop_product.png)

1. From the **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the field that you created (here **[!UICONTROL Product name]** ). Click **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   The personalization field that you selected is now displayed at the desired position in the email content.

1. Proceed similarly to insert the price.
1. Select some text and select **[!UICONTROL Insert link]** from the contextual toolbar.

   ![](assets/message-center_loop_link_insert.png)

1. Select **[!UICONTROL Add personalization field]** in the **[!UICONTROL Insert link]** window that opens.

   From the **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** node, open the node corresponding to the collection that you created (here **[!UICONTROL Product list]** ) and select the URL field that you created (here **[!UICONTROL Product URL]** ). Click **[!UICONTROL Save]**.

   >[!IMPORTANT]
   >
   >For security reasons, make sure you insert the personalization field inside a link starting with a proper static domain name.

   ![](assets/message-center_loop_link_select.png)

   The personalization field that you selected is now displayed in the Settings pane.

1. Select the structure component on which the product listing is applied and select **[!UICONTROL Show fallback]** to define a default content.

   ![](assets/message-center_loop_fallback_show.png)

1. Drag one or more content components and edit them as needed.

   ![](assets/message-center_loop_fallback.png)

   The fallback content will be displayed if the collection is empty when the event is triggered, for example if a customer has nothing in his cart.

1. From the Settings pane, edit the styles for the product listing. For more on this, see [Managing email styles](../../designing/using/styles.md).
1. Preview the email using a test profile linked to the relevant transactional event and for which you defined collection data. For example, add the following information in the **[!UICONTROL Event data]** section for the test profile you want to use:

   ![](assets/message-center_loop_test-profile_payload.png)

   For more on defining a test profile in a transactional message, see [this section](../../channels/using/testing-transactional-message.md#defining-specific-test-profile).-->

## Specificità dei messaggi transazionali basati su profili {#profile-transactional-message-specificities}

Puoi inviare messaggi transazionali basati sui profili di marketing dei clienti, che ti consentono di sfruttare tutte le informazioni di profilo per personalizzare il contenuto del messaggio, utilizzare il collegamento di annullamento dell’abbonamento e applicare regole di tipologia di marketing come [regole di fatica](../../sending/using/fatigue-rules.md).

* Per ulteriori informazioni sulle differenze tra i messaggi transazionali basati su eventi e quelli basati su profili, consulta [questa sezione](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types).

* I passaggi di configurazione per creare un messaggio transazionale basato su profilo sono descritti in [questa sezione](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

I passaggi per creare, modificare e personalizzare un messaggio transazionale di profilo sono per lo più gli stessi di un messaggio transazionale di evento.

Le differenze sono elencate di seguito.

1. [Passa al messaggio transazionale creato per modificarlo.](#accessing-transactional-messages)
1. Nel messaggio transazionale, fai clic sulla sezione **[!UICONTROL Content]**. Oltre ai modelli e-mail transazionali, puoi anche scegliere qualsiasi modello e-mail destinato a **[!UICONTROL Profile]** risorsa.

   ![](assets/message-center_marketing_templates.png)

1. Seleziona il modello di e-mail predefinito. Simile a tutte le e-mail di marketing, include una **collegamento per annullare l’abbonamento**.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Per ulteriori informazioni sui modelli, consulta [questa sezione](../../designing/using/using-reusable-content.md#content-templates).

1. Inoltre, a differenza delle configurazioni basate su eventi in tempo reale, **accesso diretto a tutte le informazioni del profilo** per personalizzare il messaggio. Puoi aggiungere [campi di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field) come faresti per qualsiasi altra e-mail di marketing standard.

1. Salva le modifiche prima di pubblicare il messaggio. Per ulteriori informazioni, consulta [Pubblicazione di un messaggio sulle transazioni](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

<!--### Monitoring a profile transactional message delivery {#monitoring-a-profile-transactional-message-delivery}

Once the message is published and your site integration is done, you can monitor the delivery.

1. To view the message delivery log, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

1. Click the **[!UICONTROL Execution list]** tab.

   ![](assets/message-center_execution_tab.png)

1. Select the latest execution delivery.

   An **execution delivery** is a non-actionable and non-functional technical message created once a month for each transactional message, and each time a transactional message is edited and published again

1. Select the **[!UICONTROL Sending logs]** tab. In the **[!UICONTROL Status]** column, **[!UICONTROL Sent]** indicates that a profile has opted in.

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as addresses on denylist.

   ![](assets/message-center_marketing_exclusion_logs.png)

>[!NOTE]
>
>For more information on accessing and using the logs, see [Monitoring a delivery](../../sending/using/monitoring-a-delivery.md).

For any profile that has opted out, the **[!UICONTROL Address on denylist]** typology rule excluded the corresponding recipient.

This rule is part of a specific typology that applies to all transactional messages based on the **[!UICONTROL Profile]** table.

![](assets/message-center_marketing_typology.png)

**Related topics**:

* [Integrate the event triggering](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)
* [About typologies and typology rules](../../sending/using/about-typology-rules.md)-->
