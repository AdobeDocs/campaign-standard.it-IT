---
title: Notifiche push transazionali
seo-title: Notifiche push transazionali
description: Notifiche push transazionali
seo-description: Scoprite come creare e pubblicare una notifica push transazionale.
page-status-flag: mai attivato
uuid: ef31c1b6-9ef8-42e3-b49d-72f9eac8ea32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: messaggistica transazionale
discoiquuid: e645d4b9-001f-47d9-8a0f-b4696c75c5d3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d9357481a567cb0d11eea43211abf08a6dcb07d6

---


# Notifiche push transazionali{#transactional-push-notifications}

Puoi utilizzare Adobe Campaign per inviare notifiche push transazionali su dispositivi mobili iOS e Android. Questi messaggi vengono ricevuti sulle applicazioni mobili configurate in Adobe Campaign sfruttando l'SDK di Experience Cloud Mobile.

>[!NOTE]
>
>Il canale push è opzionale. Controllare il contratto di licenza. Per ulteriori informazioni sulle notifiche push standard, consultate Notifiche [](../../channels/using/about-push-notifications.md)push.

Potete inviare due tipi di notifiche push transazionali:

* Notifiche push transazionali indirizzate a un evento.
* Notifiche push transazionali profili di targeting dal database di Adobe Campaign.

Dopo aver creato e pubblicato un evento (l'abbandono del carrello descritto in [questa sezione](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), la notifica push transazionale corrispondente viene creata automaticamente.

I passaggi di configurazione sono descritti nella sezione [Configurazione di un evento per inviare una sezione di notifica](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) push transazionale.

Affinché l'evento attivi l'invio di un messaggio transazionale, è necessario personalizzare il messaggio, testarlo e pubblicarlo.

>[!NOTE]
>
>Per accedere ai messaggi transazionali, è necessario disporre dei diritti di amministrazione o essere visualizzati nel gruppo di sicurezza **[!UICONTROL Message Center agents]** (mcExec).

## Notifiche push transazionali indirizzate a un evento {#transactional-push-notifications-targeting-an-event}

Puoi inviare una notifica push transazionale anonima a tutti gli utenti che hanno acconsentito alla ricezione di notifiche dall’applicazione mobile.

In questo caso, solo i dati contenuti nell'evento stesso vengono utilizzati per definire il target di consegna. Nessun dato proveniente dal database dei profili integrato di Adobe Campaign viene sfruttato.

### Invio di una notifica push transazionale per l'impostazione di un evento {#sending-a-transactional-push-notification-targeting-an-----------event}

Ad esempio, una compagnia aerea desidera invitare i propri utenti di applicazioni mobili a passare alla porta d'imbarco pertinente.

L'azienda invierà una notifica push transazionale per utente (identificata con un token di registrazione), utilizzando un'applicazione mobile, tramite un singolo dispositivo.

1. Vai al messaggio transazionale creato per modificarlo. Consultate Messaggi transazionali [evento](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message.png)

1. Fai clic sul **[!UICONTROL Content]** blocco per modificare il titolo e il corpo del messaggio.

   Potete inserire campi di personalizzazione per aggiungere gli elementi definiti al momento della creazione dell'evento.

   ![](assets/message-center_push_content.png)

   Per trovare questi campi, fate clic sulla matita accanto a un elemento, quindi selezionate **[!UICONTROL Insert personalization field]** &gt; **[!UICONTROL Context]** &gt; **[!UICONTROL Real-time event]** **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Per ulteriori informazioni sulla modifica di un contenuto di notifica push, consultate [Creazione di una notifica](../../channels/using/preparing-and-sending-a-push-notification.md)push.

1. Salva le modifiche e pubblica il messaggio. Consultate [Pubblicazione di un messaggio](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)transazionale.
1. Utilizzando l'API REST standard di Adobe Campaign, inviate un evento a un token di registrazione (ABCDEF123456789), utilizzando un'applicazione mobile (WeFlight), su Android (gcm), contenente i dati di imbarco.

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

   Per ulteriori informazioni sull'integrazione dell'attivazione di un evento in un sistema esterno, vedere Integrazione [](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)del sito.

Se il token di registrazione esiste, l'utente corrispondente riceve una notifica push transazionale con il seguente contenuto:

"Ciao Jane Green, imbarco è appena iniziato! Procedere al cancello B18."

## Notifiche push transazionali per un profilo {#transactional-push-notifications-targeting-a-profile}

Puoi inviare una notifica push transazionale ai profili di Adobe Campaign per i quali hai effettuato la sottoscrizione all'applicazione mobile. Questa consegna può contenere campi di [personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field) , ad esempio il nome del destinatario.

In questo caso, l'evento deve contenere alcuni campi che consentono la riconciliazione con un profilo presente nel database di Adobe Campaign.

Quando si esegue il targeting dei profili, viene inviata una notifica push transazionale per applicazione mobile e per dispositivo. Ad esempio, se un utente di Adobe Campaign ha effettuato la sottoscrizione a due applicazioni, questo utente riceverà due notifiche. Se un utente si è iscritto alla stessa applicazione con due dispositivi diversi, riceverà una notifica su ciascun dispositivo.

Le applicazioni mobili a cui un profilo ha effettuato la sottoscrizione sono elencate nella **[!UICONTROL Mobile App Subscriptions]** scheda di questo profilo. Per accedere a questa scheda, seleziona un profilo e fai clic sul **[!UICONTROL Edit profile properties]** pulsante a destra.

![](assets/push_notif_subscriptions.png)

Per ulteriori informazioni sull'accesso e la modifica dei profili, vedere [Profili](../../audiences/using/creating-profiles.md).

### Invio di una notifica push transazionale per un profilo {#sending-a-transactional-push-notification-targeting-a-----------profile}

Ad esempio, un'azienda aerea desidera inviare un'ultima chiamata per l'imbarco a tutti gli utenti di Adobe Campaign che si sono abbonati alla sua applicazione mobile.

1. Vai al messaggio transazionale creato per modificarlo. Consultate Messaggi transazionali [evento](../../channels/using/event-transactional-messages.md).

   <!--![](assets/message-center_push_message_profile.png)-->

1. Fai clic sul **[!UICONTROL Content]** blocco per modificare il titolo e il corpo del messaggio.

   A differenza delle configurazioni basate su eventi in tempo reale, puoi accedere direttamente a tutte le informazioni sul profilo per personalizzare il messaggio. Consultate [Inserimento di un campo](../../designing/using/personalization.md#inserting-a-personalization-field)di personalizzazione.

   <!--![](assets/message-center_push_content_profile.png)-->

   Per ulteriori informazioni sulla modifica di un contenuto di notifica push. Consultate [Creazione di una notifica](../../channels/using/preparing-and-sending-a-push-notification.md)push.

1. Salva le modifiche e pubblica il messaggio. Consultate [Pubblicazione di un messaggio](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)transazionale.
1. Utilizzando l'API REST di Adobe Campaign Standard, inviate un evento a un profilo.

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

   Per ulteriori informazioni sull'integrazione dell'attivazione di un evento in un sistema esterno, vedere Integrazione [](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)del sito.

   >[!NOTE]
   >
   >Nessun token di registrazione, campi applicazione e piattaforma push. In questo esempio, la riconciliazione viene eseguita con il campo e-mail.

