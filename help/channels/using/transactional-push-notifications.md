---
solution: Campaign Standard
product: campaign
title: Notifiche push transazionali
description: Scopri come inviare notifiche push transazionali con  Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '1336'
ht-degree: 4%

---


# Notifiche push transazionali{#transactional-push-notifications}

Potete utilizzare  Adobe Campaign per inviare notifiche push transazionali su dispositivi mobili iOS e Android. Questi messaggi vengono ricevuti sulle applicazioni mobili configurate in  Adobe Campaign sfruttando l&#39;SDK per dispositivi mobili  Experience Cloud.

>[!NOTE]
>
>Il canale push è opzionale. Controlla il contratto di licenza. Per ulteriori informazioni sulle notifiche push standard, consultate [Informazioni sulle notifiche push](../../channels/using/about-push-notifications.md).

Per poter inviare notifiche push transazionali, devi configurare  Adobe Campaign di conseguenza. Vedere [Configurazione di un&#39;applicazione mobile](../../administration/using/configuring-a-mobile-application.md).

Potete inviare due tipi di notifiche push transazionali:

* [Notifiche push transazionali indirizzate a un evento](#transactional-push-notifications-targeting-an-event)
* [Notifiche push transazionali per ](#transactional-push-notifications-targeting-a-profile) profili di targeting dal database Adobe Campaign

## Notifiche push transazionali per un evento {#transactional-push-notifications-targeting-an-event}

Potete utilizzare  Adobe Campaign per inviare **notifiche push transazionali anonime a tutti gli utenti** che hanno acconsentito alla ricezione di notifiche dall&#39;applicazione mobile.

In questo caso, solo **i dati contenuti nell&#39;evento stesso vengono utilizzati per definire la destinazione di consegna**. Nessun dato dal database del profilo integrato  Adobe Campaign viene utilizzato.

### Configurazione di una notifica push transazionale basata su eventi {#configuring-event-based-transactional-push-notification}

Per inviare una notifica push transazionale a tutti gli utenti che hanno acconsentito alla ricezione di notifiche dall&#39;applicazione mobile, è innanzitutto necessario creare e configurare un evento con targeting dei dati contenuti nell&#39;evento stesso.

>[!NOTE]
>
>Potete ancora personalizzare il contenuto di una notifica push transazionale basata su eventi utilizzando [attributi evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes) (dati dall&#39;evento) e [arricchimento dell&#39;evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) (dati dal database Campaign). Vedere [l&#39;esempio seguente](#sending-event-based-transactional-push-notification).

L&#39;evento deve contenere i tre elementi seguenti:

* Un **token di registrazione**, che è l&#39;ID utente per un&#39;applicazione mobile e un dispositivo. Potrebbe non corrispondere ad alcun profilo del database Adobe Campaign .
* Un **nome applicazione mobile** (uno per tutti i dispositivi - Android e iOS). Si tratta dell&#39;ID dell&#39;applicazione mobile configurata in  Adobe Campaign che verrà utilizzata per ricevere le notifiche push sui dispositivi degli utenti. Per ulteriori informazioni, vedere [Configurazione di un&#39;applicazione mobile](../../administration/using/configuring-a-mobile-application.md).
* Una **piattaforma push** (&quot;gcm&quot; per Android o &quot;apns&quot; per iOS).

Per configurare l’evento, effettuate le operazioni seguenti:

1. Quando create la configurazione dell&#39;evento, selezionate il canale **[!UICONTROL Push notification]** e la dimensione di targeting **[!UICONTROL Real-time event]** (vedete [Creazione di un evento](../../channels/using/configuring-transactional-event.md#creating-an-event)).
1. Aggiungete i campi all’evento. Questo vi consentirà di personalizzare il messaggio transazionale (vedete [Definizione degli attributi dell&#39;evento](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)). In questo esempio, definite i campi &quot;gateNumber&quot;, &quot;lastname&quot; e &quot;firstname&quot;.
1. Puoi anche arricchire il contenuto del messaggio. A tal fine, aggiungete i campi dalla tabella collegata alla configurazione dell&#39;evento (consultate [Arricchimento dell&#39;evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

   <!--Event-based transactional messaging is supposed to use only the data that are in the sent event to define the recipient and the message content personalization. However, you can enrich the content of your transactional message using information from the Adobe Campaign database.-->

1. [Visualizzate l’anteprima e pubblicate l’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Quando si visualizza l&#39;anteprima dell&#39;evento, l&#39;API REST contiene gli attributi &quot;registrationToken&quot;, &quot;application&quot; e &quot;pushPlatform&quot; che verranno utilizzati per eseguire il targeting della consegna.

   ![](assets/message-center_push_api.png)

   Una volta pubblicato l&#39;evento, viene automaticamente creata una notifica push transazionale collegata al nuovo evento. È ora possibile modificare e pubblicare il messaggio appena creato (vedere [questa sezione](#sending-event-based-transactional-push-notification)).

1. Integrare l&#39;evento nel sito Web (vedere [Integrare l&#39;attivazione dell&#39;evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Invio di una notifica push transazionale basata su eventi {#sending-event-based-transactional-push-notification}

Ad esempio, una compagnia aerea desidera invitare i propri utenti di applicazioni mobili a passare alla porta d&#39;imbarco pertinente.

L&#39;azienda invierà una notifica push transazionale per utente (identificata con un token di registrazione), utilizzando un&#39;applicazione mobile, tramite un singolo dispositivo.

1. Passa al messaggio transazionale creato per modificarlo. Vedere [Accesso ai messaggi transazionali](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

   ![](assets/message-center_push_message.png)

1. Fai clic sul blocco **[!UICONTROL Content]** per modificare il titolo e il corpo del messaggio.

1. Potete inserire campi di personalizzazione per aggiungere gli elementi definiti al momento della creazione dell&#39;evento (consultate [Defining the event attribute](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   ![](assets/message-center_push_content.png)

   Per trovare questi campi, fare clic sulla matita accanto a un elemento, fare clic su **[!UICONTROL Insert personalization field]** e selezionare **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_push_personalization.png)

   Per ulteriori informazioni sulla modifica di un contenuto di notifica push, consultate [Preparazione e invio di una notifica push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. È inoltre possibile arricchire il contenuto dei messaggi transazionali se si desidera utilizzare informazioni aggiuntive  database Adobe Campaign (vedere [Arricchimento dell&#39;evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)).

1. Salva le modifiche e pubblica il messaggio. Consulta [Pubblicazione di un messaggio transazionale](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).

1. Utilizzando l&#39;API REST di Adobe Campaign Standard , inviate un evento a un token di registrazione (ABCDEF123456789), utilizzando un&#39;applicazione mobile (WeFlight), su Android (gcm), contenente i dati di imbarco:

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

   Per ulteriori informazioni sull&#39;integrazione dell&#39;attivazione di un evento in un sistema esterno, vedere [Integrare l&#39;attivazione dell&#39;evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

Se il token di registrazione esiste, l&#39;utente corrispondente riceve una notifica push transazionale con il seguente contenuto:

*&quot;Ciao Jane Green, imbarco è appena iniziato! Procedere alla porta B18.&quot;*

## Notifiche push transazionali per un profilo {#transactional-push-notifications-targeting-a-profile}

Potete inviare una notifica push transazionale **ai profili Adobe Campaign  che hanno effettuato la sottoscrizione all&#39;applicazione mobile**. Questa consegna può contenere [campi di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field), ad esempio il nome del destinatario, recuperati direttamente dal database Adobe Campaign .

In questo caso, l&#39;evento deve contenere alcuni campi **che consentano la riconciliazione con un profilo del database Adobe Campaign**.

Quando si esegue il targeting dei profili, viene inviata una notifica push transazionale per applicazione mobile e per dispositivo. Ad esempio, se un utente Adobe Campaign  ha effettuato la sottoscrizione a due applicazioni, questo utente riceverà due notifiche. Se un utente si è iscritto alla stessa applicazione con due dispositivi diversi, riceverà una notifica su ciascun dispositivo.

Le applicazioni mobili a cui un profilo ha effettuato la sottoscrizione sono elencate nella scheda **[!UICONTROL Mobile App Subscriptions]** di questo profilo. Per accedere a questa scheda, seleziona un profilo e fai clic sul pulsante **[!UICONTROL Edit profile properties]** a destra.

![](assets/push_notif_subscriptions.png)

Per ulteriori informazioni sull&#39;accesso e la modifica dei profili, vedere [Informazioni sui profili](../../audiences/using/about-profiles.md).

### Configurazione di una notifica push transazionale basata su profilo {#configuring-profile-based-transactional-push-notification}

Per inviare una notifica push transazionale ai profili Adobe Campaign  che hanno effettuato l&#39;iscrizione all&#39;applicazione mobile, è innanzitutto necessario creare e configurare un evento per il targeting del database Adobe Campaign .

1. Quando create la configurazione dell&#39;evento, selezionate il canale **[!UICONTROL Push notification]** e la dimensione di targeting **[!UICONTROL Profile]** (vedete [Creazione di un evento](../../channels/using/configuring-transactional-event.md#creating-an-event)).

   Per impostazione predefinita, la notifica push transazionale viene inviata a tutte le applicazioni mobili alle quali i destinatari hanno effettuato la sottoscrizione. Per inviare la notifica push a una specifica applicazione mobile, selezionatela nell&#39;elenco. Le altre applicazioni mobili verranno indirizzate in base al messaggio, ma verranno escluse dall’invio.

   ![](assets/message-center_push_appfilter.png)

1. Aggiungete i campi all&#39;evento, se desiderate personalizzare il messaggio transazionale (consultate [Defining the event attribute](../../channels/using/configuring-transactional-event.md#defining-the-event-attributes)).

   >[!NOTE]
   >
   >Per creare un arricchimento è necessario aggiungere almeno un campo. Non è necessario creare altri campi quali **Nome** e **Cognome**, in quanto sarà possibile utilizzare i campi di personalizzazione del database Adobe Campaign .

1. Create un arricchimento per collegare l&#39;evento alla risorsa **[!UICONTROL Profile]** (vedete [Arricchimento dell&#39;evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)) e selezionate questo arricchimento come **[!UICONTROL Targeting enrichment]**.

   >[!IMPORTANT]
   >
   >Questo passaggio è obbligatorio per gli eventi basati sul profilo.

1. [Visualizzate l’anteprima e pubblicate l’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

   Quando si visualizza l&#39;anteprima dell&#39;evento, l&#39;API REST non contiene un attributo che specifica il token di registrazione, il nome dell&#39;applicazione e la piattaforma push così come verranno recuperati dalla risorsa **[!UICONTROL Profile]**.

   Una volta pubblicato l&#39;evento, viene automaticamente creata una notifica push transazionale collegata al nuovo evento. È ora possibile modificare e pubblicare il messaggio appena creato (vedere [questa sezione](#sending-profile-based-transactional-push-notification)).

1. Integrare l&#39;evento nel sito Web (vedere [Integrare l&#39;attivazione dell&#39;evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Invio di una notifica push transazionale basata su profilo {#sending-profile-based-transactional-push-notification}

Ad esempio, un&#39;azienda aerea desidera inviare un&#39;ultima chiamata per l&#39;imbarco a tutti  utenti Adobe Campaign che hanno effettuato l&#39;iscrizione alla propria applicazione mobile.

1. Passa al messaggio transazionale creato per modificarlo. Vedere [Accesso ai messaggi transazionali](../../channels/using/editing-transactional-message.md#accessing-transactional-messages).

1. Fai clic sul blocco **[!UICONTROL Content]** per modificare il titolo e il corpo del messaggio.

   A differenza delle configurazioni basate su eventi in tempo reale, puoi accedere direttamente a tutte le informazioni sul profilo per personalizzare il messaggio. Consulta [Inserimento di un campo di personalizzazione](../../designing/using/personalization.md#inserting-a-personalization-field).

   Per ulteriori informazioni sulla modifica di un contenuto di notifica push, consultate [Preparazione e invio di una notifica push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Salva le modifiche e pubblica il messaggio. Consulta [Pubblicazione di un messaggio transazionale](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message).
1. Utilizzando l&#39;API REST di Adobe Campaign Standard , inviate un evento a un profilo:

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

Per ulteriori informazioni sull&#39;integrazione dell&#39;attivazione di un evento in un sistema esterno, vedere [Integrare l&#39;attivazione dell&#39;evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

L&#39;utente corrispondente riceve una notifica push transazionale che include tutti gli elementi di personalizzazione recuperati dal database Adobe Campaign .

>[!NOTE]
>
>Nessun token di registrazione, campo applicazione e campi piattaforma push. In questo esempio, la riconciliazione viene eseguita con il campo e-mail.
