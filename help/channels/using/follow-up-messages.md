---
solution: Campaign Standard
product: campaign
title: Messaggi di follow-up
description: Scopri come creare e pubblicare un messaggio di follow-up.
audience: channels
content-type: reference
topic-tags: transactional-messaging
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '722'
ht-degree: 4%

---


# Messaggi di follow-up{#follow-up-messages}

Puoi inviare un messaggio di follow-up ai clienti che hanno ricevuto un messaggio transazionale specifico. A questo scopo, dovete impostare un flusso di lavoro per l&#39;evento corrispondente.

Riutilizziamo l&#39;esempio descritto nella sezione [Principio operativo dei messaggi transazionali](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle): un messaggio e-mail di abbandono del carrello viene inviato agli utenti del sito Web che hanno aggiunto prodotti al carrello, ma hanno lasciato il sito senza procedere con i loro acquisti.

Desiderate inviare un promemoria amichevole a tutti i clienti che hanno ricevuto la notifica di abbandono del carrello ma che non l&#39;hanno aperta dopo tre giorni.

Ogni cliente interessato riceverà quindi un messaggio di follow-up basato sugli stessi dati utilizzati nella prima e-mail inviata.

## Accesso ai messaggi di follow-up {#accessing-the-follow-up-messages}

Dopo aver creato e pubblicato un evento (l&#39;abbandono del carrello come da [esempio](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) sopra), il messaggio transazionale e il messaggio di follow-up corrispondenti vengono creati automaticamente.

I passaggi di configurazione sono descritti nella sezione [Configurazione di un evento per inviare un messaggio di follow-up](../../administration/using/configuring-transactional-messaging.md#configuring-an-event-to-send-a-follow-up-message).

Per gestire un evento in un flusso di lavoro, è necessario un modello di consegna. Tuttavia, quando si pubblica l&#39;evento, il [messaggio transazionale](../../channels/using/event-transactional-messages.md) creato non può essere utilizzato come modello. Pertanto, è necessario creare un modello di consegna di follow-up specifico progettato per supportare questo tipo di evento e da utilizzare come modello in un flusso di lavoro.

Per accedere a questo modello:

1. Fate clic sul logo **[!UICONTROL Adobe Campaign]**, nell&#39;angolo in alto a sinistra.
1. Seleziona **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Selezionare la casella **[!UICONTROL Follow-up messages]** nel riquadro a sinistra.

   ![](assets/message-center_follow-up-search.png)

Vengono visualizzati solo i messaggi di follow-up.

>[!NOTE]
>
>Per accedere ai messaggi transazionali, devi far parte del gruppo di sicurezza **[!UICONTROL Administrators (all units)]**.

## Invio di un messaggio di follow-up {#sending-a-follow-up-message}

Dopo aver creato il modello di consegna di follow-up, potete usarlo in un flusso di lavoro per inviare un messaggio di follow-up.

1. Accedi all&#39;elenco delle attività di marketing e crea un nuovo flusso di lavoro.

   Vedere [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Trascinate e rilasciate un&#39;attività **[!UICONTROL Scheduler]** nel flusso di lavoro per aprirla. Impostate la frequenza di esecuzione su una volta al giorno.

   L&#39;attività Scheduler viene presentata nella sezione [Scheduler](../../automating/using/scheduler.md).

1. Trascinate e rilasciate un&#39;attività **[!UICONTROL Query]** nel flusso di lavoro per aprirla.

   L&#39;attività Query viene presentata nella sezione [Query](../../automating/using/query.md).

1. Per eseguire la query su una risorsa diversa dalla risorsa del profilo, andate alla scheda **[!UICONTROL Properties]** dell&#39;attività e fate clic sull&#39;elenco a discesa **[!UICONTROL Resource]**.

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >Per impostazione predefinita l’attività è preconfigurata per ricercare profili.

1. Selezionate l’evento di cui desiderate eseguire il targeting in modo da poter accedere solo ai dati di questo evento.

   ![](assets/message-center_follow-up-query-resource.png)

1. Andate alla scheda **[!UICONTROL Target]** dell&#39;attività, quindi trascinate l&#39;elemento **[!UICONTROL Delivery logs (logs)]** dalla palette all&#39;area di lavoro.

   ![](assets/message-center_follow-up-delivery-logs.png)

   Selezionate **[!UICONTROL Exists]** per eseguire il targeting di tutti i clienti che hanno ricevuto l&#39;e-mail.

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. Spostate l&#39;elemento **[!UICONTROL Tracking logs (tracking)]** dalla palette all&#39;area di lavoro e selezionate **[!UICONTROL Does not exist]** per eseguire il targeting di tutti i clienti che non hanno aperto l&#39;e-mail.

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. Trascinare l&#39;evento di destinazione (**abbandono carrello** in questo esempio) dalla palette all&#39;area di lavoro. Definite quindi una regola per eseguire il targeting di tutti i messaggi inviati tre giorni fa.

   ![](assets/message-center_follow-up-created.png)

   Questo significa che tutti i destinatari che hanno ricevuto il messaggio transazionale tre giorni prima dell&#39;esecuzione del flusso di lavoro e che non l&#39;hanno ancora aperto, vengono assegnati al targeting.

   Fare clic su **[!UICONTROL Confirm]** per salvare la query.

1. Trascinate e rilasciate un&#39;attività **Invia per e-mail** nel flusso di lavoro.

   L&#39;attività di distribuzione e-mail viene presentata nella sezione [Invio e-mail](../../automating/using/email-delivery.md).

   ![](assets/message-center_follow-up-workflow.png)

   È inoltre possibile utilizzare un&#39;attività [invio di SMS](../../automating/using/sms-delivery.md) o [distribuzione di app mobili](../../automating/using/push-notification-delivery.md). In questo caso, accertatevi di selezionare il canale **[!UICONTROL Mobile (SMS)]** o **[!UICONTROL Mobile application]** al momento della creazione della configurazione dell&#39;evento. Vedi [Creazione di un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

1. Aprite l&#39;attività **Invio e-mail**. Nella procedura guidata di creazione, selezionate la casella **[!UICONTROL Follow-up messages]** e il modello di consegna di follow-up creato dopo la pubblicazione dell&#39;evento.

   ![](assets/message-center_follow-up-template.png)

1. Nel contenuto del messaggio di follow-up, potete sfruttare il contenuto dell&#39;evento aggiungendo campi di personalizzazione.

   ![](assets/message-center_follow-up-content.png)

1. Trovate i campi definiti al momento della creazione dell&#39;evento selezionando **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**. Vedere [Personalizzazione di un messaggio transazionale](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   Questo significa che potete sfruttare lo stesso contenuto, inclusi i dati arricchiti, utilizzato la prima volta che l’evento è stato inviato, per creare un promemoria personalizzato.

1. Salvate l&#39;attività e avviate il flusso di lavoro.

Una volta avviato il flusso di lavoro, ogni cliente che ha ricevuto la notifica di abbandono del carrello tre giorni fa ma non l&#39;ha aperta riceverà un messaggio di follow-up basato sugli stessi dati.

>[!NOTE]
>
>Se al momento della creazione della configurazione dell&#39;evento avete selezionato la dimensione di targeting **[!UICONTROL Profile]**, il messaggio di follow-up utilizzerà anche il database di marketing  Adobe Campaign. Vedi [Messaggi transazionali di profilo](../../channels/using/profile-transactional-messages.md).
