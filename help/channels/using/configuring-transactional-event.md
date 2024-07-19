---
title: Configurazione di un evento transazionale
description: Scopri come configurare gli eventi transazionali in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 1b91fb97-fe97-4564-936c-438be7ea7bc0
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '1709'
ht-degree: 3%

---

# Configurazione di un evento transazionale {#configuring-transactional-event}

Per inviare un messaggio transazionale con Adobe Campaign, devi innanzitutto descrivere la struttura dei dati dell’evento creando e configurando un evento.

>[!IMPORTANT]
>
>Solo gli [amministratori funzionali](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->dispongono dei diritti appropriati per creare e modificare le configurazioni degli eventi.

La configurazione varia a seconda del [tipo di messaggio transazionale](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types) che desideri inviare e del canale che verrà utilizzato. Per ulteriori informazioni, consulta [Configurazioni specifiche](#transactional-event-specific-configurations).

Al termine della configurazione, l’evento deve essere pubblicato. Vedi [Pubblicazione di un evento transazionale](../../channels/using/publishing-transactional-event.md).

## Creazione di un evento {#creating-an-event}

Per iniziare, crea l’evento corrispondente alle tue esigenze.

1. Fai clic sul logo **Adobe** nell&#39;angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Fai clic sul pulsante **[!UICONTROL Create]**.
1. Immettere **[!UICONTROL Label]** e **[!UICONTROL ID]** per l&#39;evento. Il campo **[!UICONTROL ID]** è obbligatorio e deve iniziare con il prefisso &quot;EVT&quot;. Se non si utilizza questo prefisso, verrà aggiunto automaticamente dopo aver fatto clic su **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >L’ID non può superare i 64 caratteri, incluso il prefisso EVT.

1. Seleziona il canale che verrà utilizzato per inviare i messaggi transazionali **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** o **[!UICONTROL Push notification]**. È possibile utilizzare un solo canale per ogni evento e non è possibile modificarlo in seguito.

1. Selezionare la dimensione di targeting corrispondente alla configurazione dell&#39;evento desiderata e fare clic su **[!UICONTROL Create]**.

   I messaggi transazionali basati su eventi hanno come target i dati contenuti nell’evento stesso, mentre i messaggi transazionali basati su profili hanno come target i dati contenuti nel database di Adobe Campaign. Per ulteriori informazioni, consulta [Configurazioni specifiche](#transactional-event-specific-configurations).

>[!NOTE]
>
>Il numero di eventi transazionali può avere un impatto sulla piattaforma. Per prestazioni ottimali, assicurati di eliminare gli eventi non utilizzati. Vedere [Eliminazione di un evento](../../channels/using/publishing-transactional-event.md#deleting-an-event).

## Definizione degli attributi dell’evento {#defining-the-event-attributes}

Nella sezione **[!UICONTROL Fields]**, definisci gli attributi che verranno integrati nel contenuto dell&#39;evento e che potranno quindi essere utilizzati per personalizzare il messaggio transazionale.

I passaggi per aggiungere e modificare i campi sono gli stessi delle [risorse personalizzate](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>Per creare un messaggio transazionale multilingue, definire un attributo evento aggiuntivo con l&#39;ID **[!UICONTROL AC_language]**. Questo si applica solo ai messaggi transazionali di evento. Dopo la pubblicazione dell’evento, i passaggi per modificare il contenuto di un messaggio transazionale multilingue sono gli stessi di un’e-mail standard multilingue. Vedi [Creazione di un&#39;e-mail multilingue](../../channels/using/creating-a-multilingual-email.md).

## Definizione delle raccolte di dati {#defining-data-collections}

Puoi aggiungere al contenuto dell’evento una raccolta di elementi, ciascuno dei quali include diversi attributi.

Questa raccolta può essere utilizzata in un&#39;e-mail transazionale per aggiungere [elenchi di prodotti](../../designing/using/using-product-listings.md) al contenuto del messaggio, ad esempio un elenco di prodotti, con il prezzo, il numero di riferimento, la quantità e così via. per ciascun prodotto dell’elenco.

1. Nella sezione **[!UICONTROL Collections]** fare clic sul pulsante **[!UICONTROL Create element]**.

   ![](assets/message-center_collection_create.png)

1. Aggiungi un’etichetta e un ID per la raccolta.
1. Aggiungi tutti i campi che desideri visualizzare nel messaggio transazionale per ciascun prodotto dell’elenco.

   In questo esempio sono stati aggiunti i seguenti campi:

   ![](assets/message-center_collection_fields.png)

1. La scheda **[!UICONTROL Enrichment]** ti consente di arricchire ogni elemento della raccolta. In questo modo potrai personalizzare gli elementi dell’elenco di prodotti corrispondente con le informazioni provenienti dal database di Adobe Campaign o da altre risorse create.

>[!NOTE]
>
>I passaggi per arricchire gli elementi di una raccolta sono gli stessi descritti nella sezione [Arricchimento dell&#39;evento](#enriching-the-transactional-message-content). L&#39;arricchimento dell&#39;evento non consente di arricchire una raccolta: è necessario aggiungere un arricchimento alla raccolta stessa nella sezione **[!UICONTROL Collections]**.

Dopo la pubblicazione dell’evento e del messaggio, potrai utilizzare questa raccolta nel messaggio sulle transazioni.

Ecco l’anteprima API per questo esempio:

![](assets/message-center_collection_api-preview.png)

**Argomenti correlati:**

* [Anteprima e pubblicazione dell’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [Utilizzo degli elenchi di prodotti in un messaggio sulle transazioni](../../designing/using/using-product-listings.md)
* [Pubblicazione di un messaggio sulle transazioni](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## Arricchimento dell’evento {#enriching-the-transactional-message-content}

Puoi arricchire il contenuto dei messaggi transazionali con le informazioni provenienti dal database di Adobe Campaign per personalizzare i messaggi. Dal cognome o dall’ID del sistema di gestione delle relazioni con i clienti di ciascuno dei destinatari, ad esempio, puoi recuperare dati quali l’indirizzo o la data di nascita o qualsiasi altro campo personalizzato aggiunto nella tabella Profilo, al fine di personalizzare le informazioni inviate.

È possibile arricchire il contenuto del messaggio sulle transazioni con informazioni provenienti da **[!UICONTROL Profile and services Ext API]** esteso. Per ulteriori informazioni, vedere [Estensione dell&#39;API: pubblicazione dell&#39;estensione](../../developing/using/step-2-publish-the-extension.md)

Queste informazioni possono anche essere memorizzate in nuove risorse. In tal caso, la risorsa deve essere collegata alle risorse **[!UICONTROL Profile]** o **[!UICONTROL Service]** direttamente o tramite un&#39;altra tabella. Ad esempio, nella configurazione seguente, è possibile arricchire il contenuto del messaggio transazionale con le informazioni della risorsa **[!UICONTROL Product]** come la categoria di prodotto o l&#39;ID, se la risorsa **[!UICONTROL Product]** è collegata alla risorsa **[!UICONTROL Profile]**.

![](assets/message-center_usecaseschema.png)

Per ulteriori informazioni sulla creazione e la pubblicazione di risorse, vedere [questa sezione](../../developing/using/key-steps-to-add-a-resource.md).

1. Nella sezione **[!UICONTROL Enrichment]** fare clic sul pulsante **[!UICONTROL Create element]**.

   ![](assets/message-center_addenrichment.png)

1. Seleziona la risorsa con cui desideri collegare il messaggio. In questo caso, scegliere la risorsa **[!UICONTROL Profile]**.

   ![](assets/message-center_new-enrichment.png)

1. Utilizza il pulsante **[!UICONTROL Create element]** per collegare un campo della risorsa selezionata a uno dei campi precedentemente aggiunti all&#39;evento (consulta [Definizione degli attributi dell&#39;evento](#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

   >[!NOTE]
   >
   >Se definisci una condizione che potrebbe consentire di selezionare più destinatari (ad esempio un campo che può avere lo stesso valore per più profili), non verrà eseguito il targeting di più profili.

1. In questo esempio, i campi **[!UICONTROL Last name]** e **[!UICONTROL First name]** vengono riconciliati con i campi corrispondenti nella risorsa **[!UICONTROL Profile]**.

   ![](assets/message-center_enrichment-join-fields.png)

   È inoltre possibile arricchire il contenuto dei messaggi transazionali utilizzando la risorsa **[!UICONTROL Service]**. Per ulteriori informazioni sui servizi, vedere [questa sezione](../../audiences/using/creating-a-service.md).

1. Se stai creando o modificando un [evento basato su profilo](#profile-based-transactional-messages), nella sezione **[!UICONTROL Targeting enrichment]** seleziona l&#39;arricchimento che verrà utilizzato come destinazione del messaggio durante l&#39;esecuzione della consegna.

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >La creazione di un arricchimento e la selezione di un arricchimento di targeting in base alla risorsa **[!UICONTROL Profile]** sono obbligatorie per gli eventi basati su profili.

Dopo la pubblicazione dell’evento e del messaggio, questo collegamento ti consentirà di arricchire il contenuto del messaggio transazionale.

**Argomenti correlati:**

* [Anteprima e pubblicazione dell’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [Personalizzazione di un messaggio sulle transazioni](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)
* [Pubblicazione di un messaggio sulle transazioni](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## Ricerca di eventi transazionali {#searching-transactional-events}

Per accedere ed eseguire ricerche negli eventi transazionali già creati, segui i passaggi indicati di seguito.

1. Fai clic sul logo **Adobe** nell&#39;angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Fai clic sul pulsante **[!UICONTROL Show search]**.

   ![](assets/message-center_search-events.png)

1. È possibile filtrare in base a **[!UICONTROL Publication status]**. Questo consente di visualizzare solo gli eventi pubblicati, ad esempio.
1. È inoltre possibile filtrare gli eventi utilizzando **[!UICONTROL Last event received]**. Ad esempio, se immetti 10, verranno visualizzate solo le configurazioni dell’evento con l’ultimo evento ricevuto 10 giorni fa o più. Questo consente di visualizzare quali eventi sono stati inattivi per un determinato periodo.

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >Il valore predefinito è 0. Vengono quindi visualizzati tutti gli eventi.

## Configurazioni specifiche {#transactional-event-specific-configurations}

La configurazione degli eventi transazionali può variare a seconda del [tipo di messaggio transazionale](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types) che desideri inviare (evento o profilo) e del canale che verrà utilizzato.

Le sezioni seguenti descrivono in dettaglio quale configurazione specifica deve essere impostata in base al messaggio transazionale desiderato. Per ulteriori informazioni sui passaggi generali per configurare un evento, vedere [Creazione di un evento](#creating-an-event).

### Messaggi transazionali basati su eventi {#event-based-transactional-messages}

Puoi inviare messaggi sulle transazioni destinati a un evento. Questo tipo di messaggi sulle transazioni non contiene informazioni del profilo: il target di consegna è definito dai dati contenuti nell’evento stesso.

Per inviare un messaggio transazionale basato su eventi, devi innanzitutto creare e configurare un evento che esegua il targeting dei **dati contenuti nell&#39;evento stesso**.

1. Durante la creazione della configurazione dell&#39;evento, selezionare la dimensione di targeting **[!UICONTROL Real-time event]** (vedere [Creazione di un evento](#creating-an-event)).
1. Aggiungere campi all&#39;evento per personalizzare il messaggio sulle transazioni (vedere [Definizione degli attributi dell&#39;evento](#defining-the-event-attributes)).
1. La messaggistica transazionale basata su eventi dovrebbe utilizzare solo i dati presenti nell’evento inviato per definire il destinatario e la personalizzazione del contenuto del messaggio.

   Tuttavia, se desideri utilizzare informazioni aggiuntive dal database di Adobe Campaign, puoi arricchire il contenuto dei messaggi transazionali (vedi [Arricchimento del contenuto dei messaggi transazionali](#enriching-the-transactional-message-content)).

1. Anteprima e pubblicazione dell&#39;evento (vedere [Anteprima e pubblicazione dell&#39;evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)).

   Quando si visualizza l’anteprima dell’evento, l’API REST contiene un attributo che specifica l’indirizzo e-mail, il telefono cellulare o gli attributi specifici della notifica push, in base al canale selezionato.

   Dopo la pubblicazione dell’evento, viene creato automaticamente un messaggio transazionale collegato al nuovo evento. Affinché l&#39;evento attivi l&#39;invio di un messaggio sulle transazioni, è necessario [modificare](../../channels/using/editing-transactional-message.md) e [pubblicare](../../channels/using/publishing-transactional-message.md) il messaggio appena creato.

1. Integrare l&#39;evento nel sito Web (vedere [Integrare l&#39;attivazione dell&#39;evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Messaggi transazionali basati su profili {#profile-based-transactional-messages}

Puoi inviare messaggi transazionali basati sui profili dei clienti, che ti consentono di applicare le regole di tipologia di marketing, includere il collegamento per annullare l’abbonamento, aggiungere il messaggio ai rapporti globali sulla consegna e sfruttarli nel percorso di clienti.

Per inviare un messaggio transazionale basato su profilo, devi innanzitutto creare e configurare un evento che esegue il targeting di **dati dal database di Adobe Campaign**.

1. Durante la creazione della configurazione dell&#39;evento, selezionare la dimensione di targeting **[!UICONTROL Profile event]** (vedere [Creazione di un evento](#creating-an-event)).
1. Aggiungere campi all&#39;evento per personalizzare il messaggio sulle transazioni (vedere [Definizione degli attributi dell&#39;evento](#defining-the-event-attributes)). Devi aggiungere almeno un campo per creare un arricchimento. Non è necessario creare altri campi, ad esempio **Nome** e **Cognome**, poiché sarà possibile utilizzare i campi di personalizzazione del database di Adobe Campaign.
1. Creare un arricchimento per collegare l&#39;evento alla risorsa **[!UICONTROL Profile]** (vedere [Arricchimento dell&#39;evento](#enriching-the-transactional-message-content)) e selezionare l&#39;arricchimento come **[!UICONTROL Targeting enrichment]**.

   >[!IMPORTANT]
   >
   >Questo passaggio è obbligatorio per gli eventi basati su profilo.

1. Anteprima e pubblicazione dell&#39;evento (vedere [Anteprima e pubblicazione dell&#39;evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)).

   Durante l&#39;anteprima dell&#39;evento, l&#39;API REST non contiene un attributo che specifica l&#39;indirizzo e-mail, il telefono cellulare o gli attributi specifici della notifica push, poiché verrà recuperato dalla risorsa **[!UICONTROL Profile]**.

   Dopo la pubblicazione dell’evento, viene creato automaticamente un messaggio transazionale collegato al nuovo evento. Affinché l&#39;evento attivi l&#39;invio di un messaggio sulle transazioni, è necessario [modificare](../../channels/using/editing-transactional-message.md) e [pubblicare](../../channels/using/publishing-transactional-message.md) il messaggio appena creato.

1. Integrare l&#39;evento nel sito Web (vedere [Integrare l&#39;attivazione dell&#39;evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

<!--### Transactional SMS messages {#transactional-sms}

The steps to configure an  event to send an SMS transactional message are the same as for the email channel. The only differences are as follows:

* When creating the corresponding event, you need to select the **[!UICONTROL Mobile (SMS)]** channel.

* When previewing the event corresponding to an event-based transactional SMS, the REST API contains an attribute specifying the mobile phone instead of the email address.

* The specificities to edit the content of an SMS transactional message are the same as for a [standard SMS](../../channels/using/about-sms-and-push-content-design.md).-->

### Notifiche push transazionali {#transactional-push-notifications}

Puoi inviare due tipi di notifiche push transazionali:
* Una notifica push transazionale anonima a tutti gli utenti che hanno acconsentito alla ricezione di notifiche dalla tua app mobile. Consulta [Configurazione delle notifiche push transazionali basate su eventi](../../channels/using/transactional-push-notifications.md#event-based-transactional-push-notifications).
* Una notifica push transazionale ai profili Adobe Campaign che si sono abbonati alla tua app mobile. Consulta [Configurazione delle notifiche push transazionali basate su profili](../../channels/using/transactional-push-notifications.md#profile-based-transactional-push-notifications).

>[!IMPORTANT]
>
>Per poter inviare notifiche push transazionali, devi configurare Adobe Campaign di conseguenza. Vedi [Configurazione di un&#39;app mobile](../../administration/using/configuring-a-mobile-application.md).

### Messaggi di follow-up {#follow-up-messages}

Puoi inviare un messaggio di follow-up ai clienti che hanno ricevuto un messaggio transazionale specifico.

I passaggi per configurare un evento che consenta di inviare un messaggio di follow-up sono descritti in [questa sezione](../../channels/using/follow-up-messages.md#configuring-an-event-to-send-a-follow-up-message).
