---
solution: Campaign Standard
product: campaign
title: Notifiche push transazionali
description: Scopri come inviare notifiche push transazionali con Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Messaggistica transazionale
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1341'
ht-degree: 4%

---


# Notifiche push transazionali{#transactional-push-notifications}

Puoi utilizzare Adobe Campaign per inviare notifiche push transazionali su dispositivi mobili iOS e Android. Questi messaggi vengono ricevuti sulle applicazioni mobili configurate in Adobe Campaign sfruttando l’SDK di Experience Cloud Mobile.

>[!NOTE]
>
>Il canale push è facoltativo. Controlla il contratto di licenza. Per ulteriori informazioni sulle notifiche push standard, consulta [Informazioni sulle notifiche push](../../channels/using/about-push-notifications.md).

Per poter inviare notifiche push transazionali, devi configurare Adobe Campaign di conseguenza. Consulta [Configurazione di un’app mobile](../../administration/using/configuring-a-mobile-application.md).

Puoi inviare due tipi di notifiche push transazionali:

* [Notifiche push transazionali destinate a un evento](#transactional-push-notifications-targeting-an-event)
* [Profili di targeting delle notifiche push transazionali ](#transactional-push-notifications-targeting-a-profile) dal database Adobe Campaign

## Notifiche push transazionali indirizzate a un evento {#transactional-push-notifications-targeting-an-event}

Puoi utilizzare Adobe Campaign per inviare **notifiche push transazionali anonime a tutti gli utenti** che hanno acconsentito alla ricezione di notifiche dalla tua app mobile.

In questo caso, solo **i dati contenuti nell&#39;evento stesso vengono utilizzati per definire la destinazione di consegna**. Non viene utilizzato alcun dato dal database di profili integrato di Adobe Campaign.

### Configurazione di una notifica transazionale basata su eventi {#configuring-event-based-transactional-push-notification}

Per inviare una notifica push transazionale a tutti gli utenti che hanno acconsentito alla ricezione di notifiche dalla tua app mobile, devi innanzitutto creare e configurare un evento che esegue il targeting dei dati contenuti nell’evento stesso.

>[!NOTE]
>
>Puoi ancora personalizzare il contenuto di una notifica transazionale basata su eventi utilizzando [attributi evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) (dati dall’evento) e [arricchimento evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) (dati dal database di Campaign). Vedi [l&#39;esempio seguente](#sending-event-based-transactional-push-notification).

L&#39;evento deve contenere i tre elementi seguenti:

* Un **token di registrazione**, che è l&#39;ID utente per una app mobile e un dispositivo. Potrebbe non corrispondere ad alcun profilo del database Adobe Campaign.
* A **nome dell&#39;applicazione mobile** (uno per tutti i dispositivi - Android e iOS). Questo è l’ID dell’app mobile configurata in Adobe Campaign che verrà utilizzato per ricevere notifiche push sui dispositivi degli utenti. Per ulteriori informazioni, consulta [Configurazione di un’app mobile](../../administration/using/configuring-a-mobile-application.md).
* Una **piattaforma push** (&quot;gcm&quot; per Android o &quot;apns&quot; per iOS).

Per configurare l’evento, segui i passaggi seguenti:

1. Durante la creazione della configurazione dell&#39;evento, seleziona il canale **[!UICONTROL Push notification]** e la dimensione di targeting **[!UICONTROL Real-time event]** (consulta [Creazione di un evento](../../channels/using/configuring-transactional-event.md#creating-an-event)).
1. Aggiungi campi all’evento. Questo ti consente di personalizzare il messaggio transazionale (consulta [Definizione degli attributi dell’evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)). In questo esempio, definire i campi &quot;gateNumber&quot;, &quot;lastname&quot; e &quot;firstname&quot;.
1. Puoi anche arricchire il contenuto del messaggio. A questo scopo, aggiungi i campi dalla tabella collegata alla configurazione dell’evento (consulta [Arricchimento dell’evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

   <!--Event-based transactional messaging is supposed to use only the data that are in the sent event to define the recipient and the message content personalization. However, you can enrich the content of your transactional message using information from the Adobe Campaign database.-->

1. [Visualizza l’anteprima e pubblica l’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Quando visualizzi l’anteprima dell’evento, l’API REST contiene gli attributi &quot;registrationToken&quot;, &quot;application&quot; e &quot;pushPlatform&quot; che verranno utilizzati per eseguire il targeting della consegna.

   ![](assets/message-center_push_api.png)

   Una volta pubblicato l’evento, viene automaticamente creata una notifica push transazionale collegata al nuovo evento. Ora puoi modificare e pubblicare il messaggio appena creato (consulta [questa sezione](#sending-event-based-transactional-push-notification)).

1. Integra l&#39;evento nel tuo sito web (consulta [Integrare l&#39;attivazione dell&#39;evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Invio di una notifica transazionale basata su eventi {#sending-event-based-transactional-push-notification}

Ad esempio, una compagnia aerea desidera invitare i propri utenti di applicazioni mobili a procedere al cancello di imbarco pertinente.

L’azienda invierà una notifica push transazionale per utente (identificata con un token di registrazione) utilizzando un’app mobile, tramite un singolo dispositivo.

1. Passa al messaggio transazionale creato per modificarlo. Consulta [Accesso ai messaggi transazionali](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

   ![](assets/message-center_push_message.png)

1. Fai clic sul blocco **[!UICONTROL Content]** per modificare il titolo e il corpo del messaggio.

1. Puoi inserire campi di personalizzazione per aggiungere elementi definiti al momento della creazione dell’evento (consulta [Definizione degli attributi dell’evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   ![](assets/message-center_push_content.png)

   Per trovare questi campi, fai clic sulla matita accanto a un elemento, quindi fai clic su **[!UICONTROL Insert personalization field]** e seleziona **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Per ulteriori informazioni sulla modifica di un contenuto di notifica push, consulta [Preparazione e invio di una notifica push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Puoi anche arricchire il contenuto dei messaggi transazionali se desideri utilizzare informazioni aggiuntive dal database Adobe Campaign (consulta [Arricchimento dell’evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

1. Salva le modifiche e pubblica il messaggio. Consulta [Pubblicazione di un messaggio transazionale](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

1. Utilizzando l’API REST di Adobe Campaign Standard, invia un evento a un token di registrazione (ABCDEF123456789), utilizzando un’app mobile (WeFlight), su Android (gcm), contenente i dati di imbarco:

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

   Per ulteriori informazioni sull&#39;integrazione dell&#39;attivazione di un evento in un sistema esterno, consulta [Integrare l&#39;attivazione dell&#39;evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

Se il token di registrazione esiste, l’utente corrispondente riceve una notifica push transazionale con il seguente contenuto:

*&quot;Ciao Jane Green, imbarco è appena iniziato! Procedere al cancello B18.&quot;*

## Notifiche push transazionali indirizzate a un profilo {#transactional-push-notifications-targeting-a-profile}

Puoi inviare una notifica push transazionale **ai profili Adobe Campaign abbonati alla tua app mobile**. Questa consegna può contenere [campi di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field), ad esempio il nome del destinatario, direttamente recuperati dal database Adobe Campaign.

In questo caso, l&#39;evento deve contenere alcuni campi **che consentono la riconciliazione con un profilo dal database Adobe Campaign**.

Quando esegui il targeting dei profili, viene inviata una notifica push transazionale per applicazione mobile e per dispositivo. Ad esempio, se un utente Adobe Campaign si è iscritto a due applicazioni, questo utente riceverà due notifiche. Se un utente si è iscritto alla stessa applicazione con due dispositivi diversi, riceverà una notifica su ciascun dispositivo.

Le applicazioni mobili a cui un profilo si è iscritto sono elencate nella scheda **[!UICONTROL Mobile App Subscriptions]** di questo profilo. Per accedere a questa scheda, seleziona un profilo e fai clic sul pulsante **[!UICONTROL Edit profile properties]** a destra.

![](assets/push_notif_subscriptions.png)

Per ulteriori informazioni sull’accesso e la modifica dei profili, consulta [Informazioni sui profili](../../audiences/using/about-profiles.md).

### Configurazione di una notifica transazionale basata su profilo {#configuring-profile-based-transactional-push-notification}

Per inviare una notifica push transazionale ai profili Adobe Campaign abbonati alla tua app mobile, devi innanzitutto creare e configurare un evento che esegue il targeting del database Adobe Campaign.

1. Durante la creazione della configurazione dell&#39;evento, seleziona il canale **[!UICONTROL Push notification]** e la dimensione di targeting **[!UICONTROL Profile]** (consulta [Creazione di un evento](../../channels/using/configuring-transactional-event.md#creating-an-event)).

   Per impostazione predefinita, la notifica push transazionale viene inviata a tutte le applicazioni mobili alle quali i destinatari si sono abbonati. Per inviare la notifica push a una specifica app mobile, selezionala nell’elenco. Le altre applicazioni mobili saranno oggetto del messaggio ma saranno escluse dall’invio.

   ![](assets/message-center_push_appfilter.png)

1. Aggiungi dei campi all’evento, se desideri personalizzare il messaggio sulle transazioni (consulta [Definizione degli attributi dell’evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >Per creare un arricchimento è necessario aggiungere almeno un campo. Non è necessario creare altri campi come **Nome** e **Cognome**, in quanto sarà possibile utilizzare campi di personalizzazione dal database Adobe Campaign.

1. Crea un arricchimento per collegare l’evento alla risorsa **[!UICONTROL Profile]** (consulta [Arricchimento dell’evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)) e seleziona questo arricchimento come **[!UICONTROL Targeting enrichment]**.

   >[!IMPORTANT]
   >
   >Questo passaggio è obbligatorio per gli eventi basati su profilo.

1. [Visualizza l’anteprima e pubblica l’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Quando visualizzi l’anteprima dell’evento, l’API REST non contiene un attributo che specifica il token di registrazione, il nome dell’applicazione e la piattaforma push, in quanto verranno recuperati dalla risorsa **[!UICONTROL Profile]**.

   Una volta pubblicato l’evento, viene automaticamente creata una notifica push transazionale collegata al nuovo evento. Ora puoi modificare e pubblicare il messaggio appena creato (consulta [questa sezione](#sending-profile-based-transactional-push-notification)).

1. Integra l&#39;evento nel tuo sito web (consulta [Integrare l&#39;attivazione dell&#39;evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Invio di una notifica transazionale basata su profilo {#sending-profile-based-transactional-push-notification}

Ad esempio, un’azienda aerea desidera inviare un’ultima chiamata per l’imbarco a tutti gli utenti Adobe Campaign che si sono abbonati alla propria app mobile.

1. Passa al messaggio transazionale creato per modificarlo. Consulta [Accesso ai messaggi transazionali](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Fai clic sul blocco **[!UICONTROL Content]** per modificare il titolo e il corpo del messaggio.

   A differenza delle configurazioni basate su eventi in tempo reale, puoi accedere direttamente a tutte le informazioni di profilo per personalizzare il messaggio. Consulta [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field).

   Per ulteriori informazioni sulla modifica di un contenuto di notifica push, consulta [Preparazione e invio di una notifica push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Salva le modifiche e pubblica il messaggio. Consulta [Pubblicazione di un messaggio transazionale](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).
1. Utilizzando l’API REST di Adobe Campaign Standard, invia un evento a un profilo:

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

Per ulteriori informazioni sull&#39;integrazione dell&#39;attivazione di un evento in un sistema esterno, consulta [Integrare l&#39;attivazione dell&#39;evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

L’utente corrispondente riceve una notifica push transazionale che include tutti gli elementi di personalizzazione recuperati dal database Adobe Campaign.

>[!NOTE]
>
>Non sono presenti campi token di registrazione, applicazioni e piattaforme push. In questo esempio, la riconciliazione viene eseguita con il campo e-mail.
