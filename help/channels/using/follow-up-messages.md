---
solution: Campaign Standard
product: campaign
title: Messaggi di follow-up
description: Scopri come creare, gestire e inviare un messaggio di follow-up.
audience: channels
content-type: reference
topic-tags: transactional-messaging
feature: Messaggistica transazionale
role: User
level: Intermediate
exl-id: 0a05cf20-7c8f-406b-acfd-7aece2c5dd26
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 3%

---

# Messaggi di follow-up {#follow-up-messages}

Un messaggio di follow-up è un modello di consegna marketing predefinito che può essere utilizzato in un flusso di lavoro per inviare un’altra comunicazione ai destinatari di un messaggio transazionale specifico.

Riutilizziamo l’esempio descritto nella sezione [Principio operativo della messaggistica transazionale](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) : un messaggio e-mail di abbandono carrello viene inviato agli utenti del tuo sito web che hanno aggiunto prodotti al loro carrello, ma hanno lasciato il sito senza procedere con i loro acquisti.

Vuoi inviare un promemoria descrittivo a tutti i clienti che hanno ricevuto la notifica di abbandono del carrello ma che non l’hanno aperta dopo tre giorni. Riceveranno un messaggio di follow-up basato sugli stessi dati utilizzati nella prima e-mail inviata.

## Configurazione di un evento per l’invio di un messaggio di follow-up {#configuring-an-event-to-send-a-follow-up-message}

Per inviare un messaggio di follow-up, devi prima configurare di conseguenza l’evento corrispondente al messaggio transazionale già ricevuto.

1. Utilizza la stessa configurazione evento creata per inviare un messaggio transazionale di evento. Consulta [Configurazione di un evento transazionale](../../channels/using/configuring-transactional-event.md).
1. Durante la configurazione dell’evento, seleziona la casella **[!UICONTROL Create follow-up delivery template for this event]** prima di pubblicare l’evento.

   ![](assets/message-center_follow-up-checkbox.png)

1. [Visualizza l’anteprima e pubblica l’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

Una volta pubblicato l’evento, vengono automaticamente creati un messaggio transazionale e un modello di consegna di follow-up collegato al nuovo evento. I passaggi per inviare il messaggio di follow-up sono descritti in [questa sezione](#sending-a-follow-up-message).

## Accesso ai messaggi di follow-up {#accessing-the-follow-up-messages}

Per gestire un evento in un flusso di lavoro, è necessario un modello di consegna. Tuttavia, quando si pubblica l’evento, il [messaggio transazionale](../../channels/using/editing-transactional-message.md) creato non può essere utilizzato come modello. Pertanto, devi creare un modello di consegna di follow-up specifico progettato per supportare questo tipo di evento e da utilizzare come modello in un flusso di lavoro.

Per accedere a questo modello:

1. Fai clic sul logo **[!UICONTROL Adobe Campaign]** nell’angolo in alto a sinistra.
1. Seleziona **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Seleziona la casella **[!UICONTROL Follow-up messages]** nel riquadro a sinistra.

   ![](assets/message-center_follow-up-search.png)

Vengono visualizzati solo i messaggi di follow-up.

>[!IMPORTANT]
>
>Solo gli utenti con il ruolo [Amministrazione](../../administration/using/users-management.md#functional-administrators) possono accedere e modificare i messaggi transazionali.

## Invio di un messaggio di follow-up {#sending-a-follow-up-message}

Una volta creato il modello di consegna di follow-up, puoi utilizzarlo in un flusso di lavoro per inviare un messaggio di follow-up.

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. Accedi all’elenco delle attività di marketing e crea un nuovo flusso di lavoro.

   Consulta [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Trascina e rilascia un’attività **[!UICONTROL Scheduler]** nel flusso di lavoro e aprila. Imposta la frequenza di esecuzione su una volta al giorno.

   L’attività Scheduler è presentata nella sezione [Scheduler](../../automating/using/scheduler.md) .

1. Trascina e rilascia un’attività **[!UICONTROL Query]** nel flusso di lavoro e aprila.

   L’attività Query viene presentata nella sezione [Query](../../automating/using/query.md) .

1. Per eseguire la query su una risorsa diversa dalla risorsa profilo, passa alla scheda **[!UICONTROL Properties]** dell’attività e fai clic sull’elenco a discesa **[!UICONTROL Resource]** .

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >Per impostazione predefinita l’attività è preconfigurata per ricercare profili.

1. Seleziona l’evento di cui desideri eseguire il targeting in modo da poter accedere solo ai dati di questo evento.

   ![](assets/message-center_follow-up-query-resource.png)

1. Vai alla scheda **[!UICONTROL Target]** dell’attività e trascina l’elemento **[!UICONTROL Delivery logs (logs)]** dalla palette nell’area di lavoro.

   ![](assets/message-center_follow-up-delivery-logs.png)

   Seleziona **[!UICONTROL Exists]** per eseguire il targeting di tutti i clienti che hanno ricevuto l’e-mail.

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. Sposta l’elemento **[!UICONTROL Tracking logs (tracking)]** dalla palette nell’area di lavoro e seleziona **[!UICONTROL Does not exist]** per eseguire il targeting di tutti i clienti che non hanno aperto l’e-mail.

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. Trascina l’evento di destinazione (**Abbandono carrello** in questo esempio) dalla palette nell’area di lavoro. Quindi definisci una regola per eseguire il targeting di tutti i messaggi inviati tre giorni fa.

   ![](assets/message-center_follow-up-created.png)

   Ciò significa che vengono targetizzati tutti i destinatari che hanno ricevuto il messaggio sulle transazioni tre giorni prima dell’esecuzione del flusso di lavoro e che non lo hanno ancora aperto.

   Fai clic su **[!UICONTROL Confirm]** per salvare la query.

1. Trascina e rilascia un’attività **Email delivery** nel flusso di lavoro.

   L’attività Email delivery è presentata nella sezione [Email delivery](../../automating/using/email-delivery.md) .

   ![](assets/message-center_follow-up-workflow.png)

   Puoi anche utilizzare un&#39;attività [SMS delivery](../../automating/using/sms-delivery.md) o [Push notification delivery](../../automating/using/push-notification-delivery.md) . In questo caso, assicurati di selezionare il canale **[!UICONTROL Mobile (SMS)]** o **[!UICONTROL Mobile application]** durante la creazione della configurazione dell’evento. Vedi [Creazione di un evento](../../channels/using/configuring-transactional-event.md#creating-an-event).

1. Apri l’attività **Email delivery** . Nella procedura guidata di creazione, seleziona la casella **[!UICONTROL Follow-up messages]** e seleziona il modello di consegna di follow-up creato dopo la pubblicazione dell’evento.

   ![](assets/message-center_follow-up-template.png)

1. Nel contenuto del messaggio di follow-up, puoi sfruttare il contenuto dell’evento aggiungendo campi di personalizzazione.

   ![](assets/message-center_follow-up-content.png)

1. Trova i campi definiti durante la creazione dell’evento selezionando **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**. Consulta [Personalizzazione di un messaggio transazionale](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   Ciò significa che puoi sfruttare lo stesso contenuto, inclusi i dati arricchiti, utilizzato la prima volta che l’evento è stato inviato, per creare un promemoria personalizzato.

1. Salva l’attività e avvia il flusso di lavoro.

Una volta avviato il flusso di lavoro, ogni cliente che ha ricevuto la notifica di abbandono del carrello tre giorni fa ma non l’ha aperta riceverà un messaggio di follow-up basato sugli stessi dati.

>[!NOTE]
>
>Se hai selezionato la dimensione di targeting **[!UICONTROL Profile]** durante la creazione della configurazione dell’evento, il messaggio di follow-up sfrutterà anche il database di marketing di Adobe Campaign. Vedi [Messaggi transazionali di profilo](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
