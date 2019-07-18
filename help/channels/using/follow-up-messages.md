---
title: Messaggi di follow-up
seo-title: Messaggi di follow-up
description: Messaggi di follow-up
seo-description: Scopri come creare e pubblicare un messaggio di follow-up.
page-status-flag: never-activated
uuid: d 2 a 17 da 2-e 935-420 a -8531-78 ed 6 a 1 fe 68 b
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: transactional-messaging
discoiquuid: 9615 e 369-754 f -4 f 6 a-a 1 b 1-14462 f 946666
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Follow-up messages{#follow-up-messages}

Potete inviare un messaggio di follow-up ai clienti che hanno ricevuto un messaggio transazionale specifico. A tal fine, dovete impostare un flusso di lavoro per l'evento corrispondente.

Let's reuse the example described in the [Transactional messaging operating principle](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) section: a cart abandonment email is sent to your website users who added products to their cart, but left the site without going through with their purchases.

Desiderate inviare un promemoria descrittivo a tutti i clienti che hanno ricevuto la notifica di abbandono del carrello, ma che non lo hanno aperto dopo tre giorni.

Ogni cliente interessato riceverà quindi un messaggio di follow-up in base agli stessi dati utilizzati nella prima e-mail inviata.

## Accessing the follow-up messages {#accessing-the-follow-up-messages}

Once you have created and published an event (the cart abandonment as per the [example](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) above), the corresponding transactional message and follow-up message are created automatically.

The configuration steps are presented in the [Configuring an event to send a follow-up message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

Per gestire un evento in un flusso di lavoro, è necessario un modello di consegna. However, when publishing the event, the [transactional message](../../channels/using/event-transactional-messages.md) that is created cannot be used as a template. Pertanto, è necessario creare un modello di consegna follow-up specifico progettato per supportare questo tipo di evento e essere utilizzato come modello in un flusso di lavoro.

Per accedere a questo modello:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]**.
1. Check the **[!UICONTROL Follow-up messages]** box in the left pane.

   ![](assets/message-center_follow-up-search.png)

Vengono visualizzati solo i messaggi di follow-up.

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group.

## Sending a follow-up message {#sending-a-follow-up-message}

Una volta creato il modello di consegna successivo, potete utilizzarlo in un flusso di lavoro per inviare un messaggio di follow-up.

1. Accedi all'elenco delle attività di marketing e crea un nuovo flusso di lavoro.

   See [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Drag and drop a **[!UICONTROL Scheduler]** activity into your workflow and open it. Impostate la frequenza di esecuzione su una volta al giorno.

   The Scheduler activity is presented in the [Scheduler](../../automating/using/scheduler.md) section.

1. Drag and drop a **[!UICONTROL Query]** activity into your workflow and open it.

   The Query activity is presented in the [Query](../../automating/using/query.md) section.

1. To run the query on a resource other than the profile resource, go to the activity's **[!UICONTROL Properties]** tab and click the **[!UICONTROL Resource]** drop-down list.

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >Per impostazione predefinita, l'attività è predefinita per la ricerca dei profili.

1. Selezionate l'evento di destinazione per poter accedere ai dati di questo evento.

   ![](assets/message-center_follow-up-query-resource.png)

1. Go to the activity's **[!UICONTROL Target]** tab and drag and drop the **[!UICONTROL Delivery logs (logs)]** element from the **[!UICONTROL Email]** section into the workspace.

   ![](assets/message-center_follow-up-delivery-logs.png)

   Select **[!UICONTROL Exists]** to target all of the customers who received the email.

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. Move the **[!UICONTROL Tracking logs (tracking)]** element from the palette to the workspace and select **[!UICONTROL Does not exist]** to target all of the customers who did not open the email.

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. Drag and drop the event that you are targeting (**Cart abandonment** in this example) from the **[!UICONTROL Email]** section into the workspace. Quindi definite una regola per eseguire il targeting di tutti i messaggi inviati tre giorni fa.

   ![](assets/message-center_follow-up-created.png)

   Ciò significa che tutti i destinatari che hanno ricevuto il messaggio transazionale tre giorni prima dell'esecuzione del flusso di lavoro non potranno comunque accedervi.

   Click **[!UICONTROL Confirm]** to save the query.

1. Drag and drop an **Email delivery** activity into your workflow.

   The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.

   ![](assets/message-center_follow-up-workflow.png)

   You can also use an [SMS delivery](../../automating/using/sms-delivery.md) or a [Mobile app delivery](../../automating/using/push-notification-delivery.md) activity. In this case, make sure you select the **[!UICONTROL Mobile (SMS)]** or **[!UICONTROL Mobile application]** channel when creating your event configuration. See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

1. Open the **Email delivery** activity. In the creation wizard, check the **[!UICONTROL Follow-up messages]** box and select the follow-up delivery template that was created after publishing the event.

   ![](assets/message-center_follow-up-template.png)

1. Nel contenuto di follow-up, potete sfruttare il contenuto dell'evento aggiungendo campi personalizzati.

   ![](assets/message-center_follow-up-content.png)

1. Find the fields that you defined when creating your event by selecting **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]**. See [Personalizing a transactional message](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   Questo significa che potete sfruttare lo stesso contenuto, inclusi i dati arricchiti, utilizzati la prima volta che l'evento è stato inviato, per creare un promemoria descrittivo personalizzato.

1. Salvate l'attività e avviate il flusso di lavoro.

Una volta iniziato il flusso di lavoro, ogni cliente che ha ricevuto la notifica di abbandono del carrello tre giorni fa ma non lo ha aperto riceverà un messaggio di follow-up basato sugli stessi dati.

>[!NOTE]
>
>If you selected the **[!UICONTROL Profile]** targeting dimension when creating the event configuration, the follow-up message will also leverage the Adobe Campaign marketing database. See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).

