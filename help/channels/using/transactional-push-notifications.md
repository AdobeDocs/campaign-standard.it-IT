---
title: Notifiche push transazionali
description: Scoprite come creare e pubblicare una notifica push transazionale.
page-status-flag: never-activated
uuid: ef31c1b6-9ef8-42e3-b49d-72f9eac8ea32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: e645d4b9-001f-47d9-8a0f-b4696c75c5d3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 13%

---


# Notifiche push transazionali{#transactional-push-notifications}

Potete utilizzare  Adobe Campaign per inviare notifiche push transazionali su dispositivi mobili iOS e Android. Questi messaggi vengono ricevuti sulle applicazioni mobili configurate in  Adobe Campaign sfruttando l&#39;SDK per dispositivi mobili  Experience Cloud.

>[!NOTE]
>
>Il canale push è opzionale. Controlla il contratto di licenza. Per ulteriori informazioni sulle notifiche push standard, consultate Notifiche [](../../channels/using/about-push-notifications.md)push.

Potete inviare due tipi di notifiche push transazionali:

* Notifiche push transazionali indirizzate a un evento.
* Notifiche push transazionali con profili di targeting dal database Adobe Campaign .

Once you have created and published an event (the cart abandonment explained in [this section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)), the corresponding transactional push notification is created automatically.

The configuration steps are presented in the [Configuring an event to send a transactional push notification](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

Per fare in modo che l’evento attivi l’invio di un messaggio transazionale, devi personalizzare il messaggio, verificarlo e pubblicarlo.

>[!NOTE]
>
>Per accedere ai messaggi transazionali, devi far parte del gruppo di sicurezza **[!UICONTROL Administrators (all units)]**.

## Notifiche push transazionali indirizzate a un evento {#transactional-push-notifications-targeting-an-event}

Puoi inviare una notifica push transazionale anonima a tutti gli utenti che hanno acconsentito alla ricezione di notifiche dall’applicazione mobile.

In questo caso, solo i dati contenuti nell&#39;evento stesso vengono utilizzati per definire il target di consegna. Nessun dato dal database del profilo integrato  Adobe Campaign viene utilizzato.

### Invio di una notifica push transazionale per l&#39;impostazione di un evento {#sending-a-transactional-push-notification-targeting-an-----------event}

Ad esempio, una compagnia aerea desidera invitare i propri utenti di applicazioni mobili a passare alla porta d&#39;imbarco pertinente.

L&#39;azienda invierà una notifica push transazionale per utente (identificata con un token di registrazione), utilizzando un&#39;applicazione mobile, tramite un singolo dispositivo.

1. Passa al messaggio transazionale creato per modificarlo. Vedi [Messaggi transazionali di evento](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message.png)

1. Click the **[!UICONTROL Content]** block to modify your message&#39;s title and body.

   Potete inserire campi di personalizzazione per aggiungere gli elementi definiti al momento della creazione dell&#39;evento.

   ![](assets/message-center_push_content.png)

   Per trovare questi campi, fare clic sulla matita accanto a un elemento, quindi selezionare **[!UICONTROL Insert personalization field]** > **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Per ulteriori informazioni sulla modifica di un contenuto di notifica push, consultate [Creazione di una notifica](../../channels/using/preparing-and-sending-a-push-notification.md)push.

1. Salva le modifiche e pubblica il messaggio. Consulta [Pubblicazione di un messaggio transazionale](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

1. Utilizzando l&#39;API REST di Adobe Campaign Standard , inviate un evento a un token di registrazione (ABCDEF123456789), utilizzando un&#39;applicazione mobile (WeFlight), su Android (gcm), contenente i dati di imbarco.

   ```
   {
     "registrationToken":"ABCDEF123456789",
     "application":"WeFlight",
     "pushPlatform":"gcm",
     "ctx":
     {
       "gateNumber":"Gate B18",
       "lastname":"Green",
       "firstname":"Jane"
     }
   }
   ```

   Per ulteriori informazioni sull&#39;integrazione dell&#39;attivazione di un evento in un sistema esterno, vedere Integrazione [](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)del sito.

Se il token di registrazione esiste, l&#39;utente corrispondente riceve una notifica push transazionale con il seguente contenuto:

&quot;Ciao Jane Green, imbarco è appena iniziato! Procedere al cancello B18.&quot;

## Notifiche push transazionali per un profilo {#transactional-push-notifications-targeting-a-profile}

Potete inviare una notifica push transazionale ai profili Adobe Campaign  che hanno effettuato la sottoscrizione all’applicazione mobile. Questa consegna può contenere campi di [personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field) , ad esempio il nome del destinatario.

In questo caso, l&#39;evento deve contenere alcuni campi che consentano la riconciliazione con un profilo del database Adobe Campaign .

Quando si esegue il targeting dei profili, viene inviata una notifica push transazionale per applicazione mobile e per dispositivo. Ad esempio, se un utente Adobe Campaign  ha effettuato la sottoscrizione a due applicazioni, questo utente riceverà due notifiche. Se un utente si è iscritto alla stessa applicazione con due dispositivi diversi, riceverà una notifica su ciascun dispositivo.

Le applicazioni mobili a cui un profilo ha effettuato la sottoscrizione sono elencate nella **[!UICONTROL Mobile App Subscriptions]** scheda di questo profilo. Per accedere a questa scheda, seleziona un profilo e fai clic sul **[!UICONTROL Edit profile properties]** pulsante a destra.

![](assets/push_notif_subscriptions.png)

Per ulteriori informazioni sull&#39;accesso e la modifica dei profili, vedere [Profili](../../audiences/using/creating-profiles.md).

### Invio di una notifica push transazionale per un profilo {#sending-a-transactional-push-notification-targeting-a-----------profile}

Ad esempio, un&#39;azienda aerea desidera inviare un&#39;ultima chiamata per l&#39;imbarco a tutti  utenti Adobe Campaign che hanno effettuato l&#39;iscrizione alla propria applicazione mobile.

1. Passa al messaggio transazionale creato per modificarlo. Vedi [Messaggi transazionali di evento](../../channels/using/event-transactional-messages.md).

1. Click the **[!UICONTROL Content]** block to modify your message&#39;s title and body.

   A differenza delle configurazioni basate su eventi in tempo reale, puoi accedere direttamente a tutte le informazioni sul profilo per personalizzare il messaggio. Consulta [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field).

   Per ulteriori informazioni sulla modifica di un contenuto di notifica push. Consultate [Creazione di una notifica](../../channels/using/preparing-and-sending-a-push-notification.md)push.

1. Salva le modifiche e pubblica il messaggio. Consulta [Pubblicazione di un messaggio transazionale](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
1. Utilizzando l&#39;API REST di Adobe Campaign Standard , inviate un evento a un profilo.

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

   Per ulteriori informazioni sull&#39;integrazione dell&#39;attivazione di un evento in un sistema esterno, vedere Integrazione [](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)del sito.

   >[!NOTE]
   >
   >Nessun token di registrazione, campo applicazione e campi piattaforma push. In questo esempio, la riconciliazione viene eseguita con il campo e-mail.
