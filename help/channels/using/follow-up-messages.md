---
title: Messaggi di follow-up
description: Scopri come creare, gestire e inviare un messaggio di follow-up.
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

Riutilizziamo l’esempio descritto in [Principio operativo della messaggistica transazionale](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) sezione: un messaggio e-mail di abbandono carrello viene inviato agli utenti del tuo sito web che hanno aggiunto prodotti al loro carrello, ma hanno lasciato il sito senza procedere con i loro acquisti.

Vuoi inviare un promemoria descrittivo a tutti i clienti che hanno ricevuto la notifica di abbandono del carrello ma che non l’hanno aperta dopo tre giorni. Riceveranno un messaggio di follow-up basato sugli stessi dati utilizzati nella prima e-mail inviata.

## Configurazione di un evento per l’invio di un messaggio di follow-up {#configuring-an-event-to-send-a-follow-up-message}

Per inviare un messaggio di follow-up, devi prima configurare di conseguenza l’evento corrispondente al messaggio transazionale già ricevuto.

1. Utilizza la stessa configurazione evento creata per inviare un messaggio transazionale di evento. Vedi [Configurazione di un evento sulle transazioni](../../channels/using/configuring-transactional-event.md).
1. Durante la configurazione dell’evento, controlla la **[!UICONTROL Create follow-up delivery template for this event]** prima della pubblicazione dell’evento.

   ![](assets/message-center_follow-up-checkbox.png)

1. [Anteprima e pubblicazione dell’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

Una volta pubblicato l’evento, vengono automaticamente creati un messaggio transazionale e un modello di consegna di follow-up collegato al nuovo evento. I passaggi per inviare il messaggio di follow-up sono descritti in [questa sezione](#sending-a-follow-up-message).

## Accesso ai messaggi di follow-up {#accessing-the-follow-up-messages}

Per gestire un evento in un flusso di lavoro, è necessario un modello di consegna. Tuttavia, quando pubblichi l’evento, la [messaggio sulle transazioni](../../channels/using/editing-transactional-message.md) non può essere utilizzato come modello. Pertanto, devi creare un modello di consegna di follow-up specifico progettato per supportare questo tipo di evento e da utilizzare come modello in un flusso di lavoro.

Per accedere a questo modello:

1. Fai clic sul pulsante **Adobe** nell&#39;angolo in alto a sinistra.
1. Seleziona **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Controlla la **[!UICONTROL Follow-up messages]** nel riquadro a sinistra.

   ![](assets/message-center_follow-up-search.png)

Vengono visualizzati solo i messaggi di follow-up.

>[!IMPORTANT]
>
>Solo gli utenti con [Amministrazione](../../administration/using/users-management.md#functional-administrators) Il ruolo può accedere ai messaggi transazionali e modificarli.

## Invio di un messaggio di follow-up {#sending-a-follow-up-message}

Una volta creato il modello di consegna di follow-up, puoi utilizzarlo in un flusso di lavoro per inviare un messaggio di follow-up.

<!--You need to set up a workflow targeting the event corresponding to the transactional message that was already received.-->

1. Accedi all’elenco delle attività di marketing e crea un nuovo flusso di lavoro.

   Vedi [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Trascina e rilascia una **[!UICONTROL Scheduler]** nel flusso di lavoro e aprilo. Imposta la frequenza di esecuzione su una volta al giorno.

   L’attività Scheduler viene presentata nel [Scheduler](../../automating/using/scheduler.md) sezione .

1. Trascina e rilascia una **[!UICONTROL Query]** nel flusso di lavoro e aprilo.

   L’attività Query viene presentata nel [Query](../../automating/using/query.md) sezione .

1. Per eseguire la query su una risorsa diversa dalla risorsa del profilo, passa a **[!UICONTROL Properties]** e fai clic su **[!UICONTROL Resource]** elenco a discesa.

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >Per impostazione predefinita l’attività è preconfigurata per ricercare profili.

1. Seleziona l’evento di cui desideri eseguire il targeting in modo da poter accedere solo ai dati di questo evento.

   ![](assets/message-center_follow-up-query-resource.png)

1. Vai a **[!UICONTROL Target]** e trascina e rilascia la **[!UICONTROL Delivery logs (logs)]** dalla palette nell’area di lavoro.

   ![](assets/message-center_follow-up-delivery-logs.png)

   Seleziona **[!UICONTROL Exists]** per eseguire il targeting di tutti i clienti che hanno ricevuto l’e-mail.

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. Sposta la **[!UICONTROL Tracking logs (tracking)]** dalla palette all’area di lavoro e seleziona **[!UICONTROL Does not exist]** per eseguire il targeting di tutti i clienti che non hanno aperto l’e-mail.

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. Trascina e rilascia l’evento di destinazione (**Abbandono del carrello** in questo esempio) dalla palette all’area di lavoro. Quindi definisci una regola per eseguire il targeting di tutti i messaggi inviati tre giorni fa.

   ![](assets/message-center_follow-up-created.png)

   Ciò significa che vengono targetizzati tutti i destinatari che hanno ricevuto il messaggio sulle transazioni tre giorni prima dell’esecuzione del flusso di lavoro e che non lo hanno ancora aperto.

   Fai clic su **[!UICONTROL Confirm]** per salvare la query.

1. Trascina e rilascia una **Email delivery** nel flusso di lavoro.

   L’attività Email delivery viene presentata nel [Email delivery](../../automating/using/email-delivery.md) sezione .

   ![](assets/message-center_follow-up-workflow.png)

   È inoltre possibile utilizzare un [SMS delivery](../../automating/using/sms-delivery.md) o [Consegna notifiche push](../../automating/using/push-notification-delivery.md) attività. In questo caso, assicurati di selezionare la **[!UICONTROL Mobile (SMS)]** o **[!UICONTROL Mobile application]** canale durante la creazione della configurazione dell’evento. Vedi [Creazione di un evento](../../channels/using/configuring-transactional-event.md#creating-an-event).

1. Apri **Email delivery** attività. Nella procedura guidata di creazione, seleziona la **[!UICONTROL Follow-up messages]** e seleziona il modello di consegna di follow-up creato dopo la pubblicazione dell’evento.

   ![](assets/message-center_follow-up-template.png)

1. Nel contenuto del messaggio di follow-up, puoi sfruttare il contenuto dell’evento aggiungendo campi di personalizzazione.

   ![](assets/message-center_follow-up-content.png)

1. Trova i campi definiti durante la creazione dell’evento selezionando **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**. Vedi [Personalizzazione di un messaggio sulle transazioni](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   Ciò significa che puoi sfruttare lo stesso contenuto, inclusi i dati arricchiti, utilizzato la prima volta che l’evento è stato inviato, per creare un promemoria personalizzato.

1. Salva l’attività e avvia il flusso di lavoro.

Una volta avviato il flusso di lavoro, ogni cliente che ha ricevuto la notifica di abbandono del carrello tre giorni fa ma non l’ha aperta riceverà un messaggio di follow-up basato sugli stessi dati.

>[!NOTE]
>
>Se hai selezionato la **[!UICONTROL Profile]** dimensione di targeting durante la creazione della configurazione dell’evento, il messaggio di follow-up sfrutterà anche il database di marketing di Adobe Campaign. Vedi [Messaggi transazionali di profilo](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
