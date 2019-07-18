---
title: Notifiche push transazionali
seo-title: Notifiche push transazionali
description: Notifiche push transazionali
seo-description: Scopri come creare e pubblicare una notifica push transazionale.
page-status-flag: never-activated
uuid: ef 31 c 1 b 6-9 ef 8-42 e 3-b 49 d -72 f 9 eac 8 ea 32
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: transactional-messaging
discoiquuid: e 645 d 4 b 9-001 f -47 d 9-8 a 0 f-b 4696 c 75 c 5 d 3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Transactional push notifications{#transactional-push-notifications}

Puoi utilizzare Adobe Campaign per inviare notifiche push transazionali sui dispositivi mobili iOS e Android. Questi messaggi vengono ricevuti sulle applicazioni mobili configurate in Adobe Campaign sfruttando l'SDK di Experience Cloud Mobile.

>[!NOTE]
>
>Il canale push è facoltativo. Controllate il contratto di licenza. For more information on standard push notifications, see [Push notifications](../../channels/using/about-push-notifications.md).

Potete inviare due tipi di notifiche push transazionali:

* Notifiche push transazionali mirate a un evento.
* Profili di targeting delle notifiche push transazionali dal database Adobe Campaign.

Once you have created and published an event (the cart abandonment explained in [this section](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), the corresponding transactional push notification is created automatically.

The configuration steps are presented in the [Configuring an event to send a transactional push notification](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.

Affinché l'evento attivi l'invio di un messaggio transazionale, dovete personalizzare il messaggio, quindi testarlo e pubblicarlo.

>[!NOTE]
>
>To access the transactional messages, you must have administration rights or appear in the **[!UICONTROL Message Center agents]** (mcExec) security group.

## Transactional push notifications targeting an event {#transactional-push-notifications-targeting-an-event}

Puoi inviare una notifica push transazionale anonima a tutti gli utenti che hanno acconsentito alla ricezione di notifiche dall'applicazione mobile.

In questo caso, solo i dati contenuti nell'evento stesso vengono utilizzati per definire la destinazione di consegna. Non vengono utilizzati dati provenienti dal database profilo integrato di Adobe Campaign.

### Sending a transactional push notification targeting an event {#sending-a-transactional-push-notification-targeting-an-----------event}

Ad esempio, una compagnia aerea vuole invitare i suoi utenti dell'applicazione mobile a passare al gate pertinente per l'imbarco.

L'azienda invierà una notifica push transazionale per utente (identificato con un token di registrazione) utilizzando un'applicazione mobile tramite un singolo dispositivo.

1. Passate il messaggio transazionali creato per modificarlo. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message.png)

1. Click the **[!UICONTROL Content]** block to modify your message's title and body.

   Potete inserire campi personalizzati per aggiungere elementi definiti al momento della creazione dell'evento.

   ![](assets/message-center_push_content.png)

   To find these fields, click the pencil next to an item, click **[!UICONTROL Insert personalization field]** and select **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   For more on editing a push notification content, see [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Salvate le modifiche e pubblicate il messaggio. See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
1. Utilizzando Adobe Campaign Standard REST API, inviate un evento a un token di registrazione (ABCDEF 123456789), utilizzando un'applicazione mobile (weflight), su Android (gcm), contenente i dati Boarding.

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

   For more on integrating the triggering of an event into an external system, see [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Se il token di registrazione esiste, l'utente corrispondente riceve una notifica push transazionale, compresi i seguenti contenuti:

" Hello Jane Green, Boarding è appena iniziata! Passate al gate B 18. "

## Transactional push notifications targeting a profile {#transactional-push-notifications-targeting-a-profile}

Puoi inviare una notifica push transazionale ai profili di Adobe Campaign che hanno effettuato la sottoscrizione all'applicazione mobile. This delivery can contain [personalization](../../designing/using/inserting-a-personalization-field.md) fields, such as the recipient's first name.

In questo caso, l'evento deve contenere alcuni campi che consentono la riconciliazione con un profilo dal database Adobe Campaign.

Quando si esegue il targeting dei profili, una notifica push transazionale viene inviata per applicazione mobile e per dispositivo. Ad esempio, se un utente Adobe Campaign ha effettuato la sottoscrizione a due applicazioni, questo utente riceverà due notifiche. Se un utente ha effettuato la sottoscrizione alla stessa applicazione con due dispositivi diversi, questo utente riceverà una notifica su ogni dispositivo.

The mobile applications a profile has subscribed to are listed in the **[!UICONTROL Mobile App Subscriptions]** tab of this profile. To access this tab, select a profile and click the **[!UICONTROL Edit profile properties]** button on the right.

![](assets/push_notif_subscriptions.png)

For more information on accessing and editing profiles, see [Profiles](../../audiences/using/creating-profiles.md).

### Sending a transactional push notification targeting a profile {#sending-a-transactional-push-notification-targeting-a-----------profile}

Ad esempio, una compagnia aerea vuole inviare un'ultima chiamata per l'imbarco a tutti gli utenti di Adobe Campaign che hanno sottoscritto la sua applicazione mobile.

1. Passate il messaggio transazionali creato per modificarlo. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message_profile.png)

1. Click the **[!UICONTROL Content]** block to modify your message's title and body.

   Invece di configurazioni basate su eventi in tempo reale, puoi accedere direttamente a tutte le informazioni di profilo per personalizzare il messaggio. See [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md).

   ![](assets/message-center_push_content_profile.png)

   Per ulteriori informazioni sulla modifica di un contenuto di notifica push. See [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Salvate le modifiche e pubblicate il messaggio. See [Publishing a transactional message](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
1. Utilizzando Adobe Campaign Standard REST API, invia un evento a un profilo.

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

   For more on integrating the triggering of an event into an external system, see [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   >[!NOTE]
   >
   >Non sono disponibili campi di registrazione, applicazioni e campi push. In questo esempio, la riconciliazione viene eseguita con il campo e-mail.

