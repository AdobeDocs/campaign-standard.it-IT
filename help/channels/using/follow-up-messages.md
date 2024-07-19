---
title: Messaggi di follow-up
description: Scopri come creare, gestire e inviare un messaggio di completamento.
audience: channels
content-type: reference
topic-tags: transactional-messaging
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 0a05cf20-7c8f-406b-acfd-7aece2c5dd26
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 2%

---

# Messaggi di follow-up {#follow-up-messages}

Un messaggio di follow-up è un modello di consegna marketing predefinito che può essere utilizzato in un flusso di lavoro per inviare un’altra comunicazione ai destinatari di un messaggio transazionale specifico.

Riutilizziamo l’esempio descritto nella sezione [Principio operativo della messaggistica transazionale](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle): viene inviata un’e-mail di abbandono del carrello agli utenti del sito web che hanno aggiunto prodotti al carrello, ma hanno lasciato il sito senza procedere con gli acquisti.

Desideri inviare un promemoria amico a tutti i clienti che hanno ricevuto la notifica di abbandono del carrello ma che non l’hanno aperto dopo tre giorni. Riceveranno un messaggio di follow-up basato sugli stessi dati utilizzati nella prima e-mail inviata.

## Configurazione di un evento per l’invio di un messaggio di follow-up {#configuring-an-event-to-send-a-follow-up-message}

Per inviare un messaggio di follow-up, devi innanzitutto configurare di conseguenza l’evento corrispondente al messaggio transazionale già ricevuto.

1. Utilizza la stessa configurazione di evento creata per inviare un messaggio transazionale di evento. Vedi [Configurazione di un evento transazionale](../../channels/using/configuring-transactional-event.md).
1. Durante la configurazione dell&#39;evento, selezionare la casella **[!UICONTROL Create follow-up delivery template for this event]** prima di pubblicarlo.

   ![](assets/message-center_follow-up-checkbox.png)

1. [Anteprima e pubblicazione dell&#39;evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

Dopo la pubblicazione dell’evento, vengono creati automaticamente un messaggio transazionale e un modello di consegna successivo collegati al nuovo evento. I passaggi per inviare il messaggio di follow-up sono descritti in [questa sezione](#sending-a-follow-up-message).

## Accesso ai messaggi di follow-up {#accessing-the-follow-up-messages}

Per gestire un evento in un flusso di lavoro, è necessario un modello di consegna. Tuttavia, durante la pubblicazione dell&#39;evento, il [messaggio transazionale](../../channels/using/editing-transactional-message.md) creato non può essere utilizzato come modello. Pertanto, devi creare un modello di consegna di follow-up specifico progettato per supportare questo tipo di evento e per essere utilizzato come modello in un flusso di lavoro.

Per accedere a questo modello:

1. Fai clic sul logo **Adobe** nell&#39;angolo in alto a sinistra.
1. Selezionare **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Selezionare la casella **[!UICONTROL Follow-up messages]** nel riquadro a sinistra.

   ![](assets/message-center_follow-up-search.png)

Vengono visualizzati solo i messaggi di follow-up.

>[!IMPORTANT]
>
>Solo gli utenti con il ruolo [Amministrazione](../../administration/using/users-management.md#functional-administrators) possono accedere ai messaggi transazionali e modificarli.

## Invio di un messaggio di completamento {#sending-a-follow-up-message}

Dopo aver creato il modello di consegna di follow-up, puoi utilizzarlo in un flusso di lavoro per inviare un messaggio di follow-up.

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. Accedi all’elenco delle attività di marketing e crea un nuovo flusso di lavoro.

   Consulta [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Trascina e rilascia un&#39;attività **[!UICONTROL Scheduler]** nel flusso di lavoro e aprila. Imposta la frequenza di esecuzione su una volta al giorno.

   L&#39;attività Scheduler è presentata nella sezione [Scheduler](../../automating/using/scheduler.md).

1. Trascina e rilascia un&#39;attività **[!UICONTROL Query]** nel flusso di lavoro e aprila.

   L&#39;attività Query è presentata nella sezione [Query](../../automating/using/query.md).

1. Per eseguire la query su una risorsa diversa da quella del profilo, passare alla scheda **[!UICONTROL Properties]** dell&#39;attività e fare clic sull&#39;elenco a discesa **[!UICONTROL Resource]**.

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >Per impostazione predefinita l’attività è preconfigurata per ricercare profili.

1. Seleziona l’evento di destinazione in modo da accedere solo ai dati di questo evento.

   ![](assets/message-center_follow-up-query-resource.png)

1. Passa alla scheda **[!UICONTROL Target]** dell&#39;attività e trascina l&#39;elemento **[!UICONTROL Delivery logs (logs)]** dalla palette nell&#39;area di lavoro.

   ![](assets/message-center_follow-up-delivery-logs.png)

   Selezionare **[!UICONTROL Exists]** per eseguire il targeting di tutti i clienti che hanno ricevuto l&#39;e-mail.

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. Sposta l&#39;elemento **[!UICONTROL Tracking logs (tracking)]** dalla palette all&#39;area di lavoro e seleziona **[!UICONTROL Does not exist]** per eseguire il targeting di tutti i clienti che non hanno aperto l&#39;e-mail.

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. Trascina e rilascia l&#39;evento di destinazione (**Abbandono carrello** in questo esempio) dalla palette nell&#39;area di lavoro. Quindi definisci una regola per eseguire il targeting di tutti i messaggi inviati tre giorni fa.

   ![](assets/message-center_follow-up-created.png)

   Ciò significa che viene eseguito il targeting per tutti i destinatari che hanno ricevuto il messaggio sulle transazioni tre giorni prima dell’esecuzione del flusso di lavoro e che non lo hanno ancora aperto.

   Fare clic su **[!UICONTROL Confirm]** per salvare la query.

1. Trascina e rilascia un&#39;attività **Email delivery** nel flusso di lavoro.

   L&#39;attività Email delivery è presentata nella sezione [Email delivery](../../automating/using/email-delivery.md).

   ![](assets/message-center_follow-up-workflow.png)

   Puoi anche utilizzare un&#39;attività [SMS delivery](../../automating/using/sms-delivery.md) o [Push notification delivery](../../automating/using/push-notification-delivery.md). In questo caso, assicurati di selezionare il canale **[!UICONTROL Mobile (SMS)]** o **[!UICONTROL Mobile application]** durante la creazione della configurazione dell&#39;evento. Vedi [Creazione di un evento](../../channels/using/configuring-transactional-event.md#creating-an-event).

1. Apri l&#39;attività **Email delivery**. Nella procedura guidata di creazione, selezionare la casella **[!UICONTROL Follow-up messages]** e selezionare il modello di consegna di follow-up creato dopo la pubblicazione dell&#39;evento.

   ![](assets/message-center_follow-up-template.png)

1. Nel contenuto del messaggio di follow-up, puoi sfruttare il contenuto dell’evento aggiungendo campi di personalizzazione.

   ![](assets/message-center_follow-up-content.png)

1. Trovare i campi definiti durante la creazione dell&#39;evento selezionando **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**. Vedi [Personalizzazione di un messaggio sulle transazioni](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   Ciò significa che puoi sfruttare lo stesso contenuto, inclusi i dati arricchiti, utilizzato la prima volta che l’evento è stato inviato, per creare un promemoria descrittivo personalizzato.

1. Salva l’attività e avvia il flusso di lavoro.

Una volta avviato il flusso di lavoro, ogni cliente che ha ricevuto la notifica di abbandono del carrello tre giorni fa ma non l’ha aperto riceverà un messaggio di follow-up basato sugli stessi dati.

>[!NOTE]
>
>Se hai selezionato la dimensione di targeting **[!UICONTROL Profile]** durante la creazione della configurazione dell&#39;evento, il messaggio di follow-up sfrutterà anche il database di marketing di Adobe Campaign. Vedi [Messaggi transazionali di profilo](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
