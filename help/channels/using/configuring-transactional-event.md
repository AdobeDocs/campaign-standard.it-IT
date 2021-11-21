---
title: Configurazione di un evento transazionale
description: Scopri come configurare eventi transazionali in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 1b91fb97-fe97-4564-936c-438be7ea7bc0
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '1672'
ht-degree: 6%

---

# Configurazione di un evento transazionale {#configuring-transactional-event}

Per inviare un messaggio transazionale con Adobe Campaign, devi innanzitutto descrivere la struttura dei dati dell’evento creando e configurando un evento.

>[!IMPORTANT]
>
>Solo [Amministratori funzionali](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->dispongono dei diritti appropriati per creare e modificare le configurazioni dell’evento.

La configurazione varia a seconda del [tipo di messaggio sulle transazioni](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types) vuoi inviare e sul canale che verrà utilizzato. Per ulteriori informazioni, consulta [Configurazioni specifiche](#transactional-event-specific-configurations).

Al termine della configurazione, l’evento deve essere pubblicato. Vedi [Pubblicazione di un evento sulle transazioni](../../channels/using/publishing-transactional-event.md).

## Creazione di un evento {#creating-an-event}

Per iniziare, crea l’evento corrispondente alle tue esigenze.

1. Fai clic sul pulsante **Adobe** , nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Fai clic sul pulsante **[!UICONTROL Create]**.
1. Inserisci un **[!UICONTROL Label]** e **[!UICONTROL ID]** per l&#39;evento. La **[!UICONTROL ID]** Il campo è obbligatorio e deve iniziare con il prefisso &quot;EVT&quot;. Se non utilizzi questo prefisso, viene aggiunto automaticamente una volta fatto clic su **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >L&#39;ID non deve superare i 64 caratteri, incluso il prefisso EVT.

1. Seleziona il canale che verrà utilizzato per inviare i messaggi transazionali **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** o **[!UICONTROL Push notification]**. Per ogni evento può essere utilizzato un solo canale e non può essere successivamente modificato.

1. Seleziona la dimensione di targeting corrispondente alla configurazione dell’evento desiderata e fai clic su **[!UICONTROL Create]**.

   I messaggi transazionali basati su eventi sono destinati ai dati contenuti nell’evento stesso, mentre i messaggi transazionali basati su profili sono destinati ai dati contenuti nel database Adobe Campaign. Per ulteriori informazioni, consulta [Configurazioni specifiche](#transactional-event-specific-configurations).

>[!NOTE]
>
>Il numero di eventi transazionali può avere un impatto sulla piattaforma. Per garantire prestazioni ottimali, assicurati di eliminare gli eventi inutilizzati. Vedi [Eliminazione di un evento](../../channels/using/publishing-transactional-event.md#deleting-an-event).

## Definizione degli attributi dell’evento {#defining-the-event-attributes}

In **[!UICONTROL Fields]** definisci gli attributi che saranno integrati nel contenuto dell’evento e saranno quindi in grado di utilizzare per personalizzare il messaggio transazionale.

I passaggi per aggiungere e modificare i campi sono gli stessi che per [risorse personalizzate](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>Se desideri creare un messaggio transazionale multilingue, definisci un attributo di evento aggiuntivo con il **[!UICONTROL AC_language]** ID. Questo vale solo per i messaggi transazionali di evento. Dopo la pubblicazione dell’evento, i passaggi per modificare il contenuto di un messaggio transazionale multilingue sono gli stessi che per un messaggio e-mail standard multilingue. Vedi [Creazione di un messaggio e-mail multilingue](../../channels/using/creating-a-multilingual-email.md).

## Definizione delle raccolte di dati {#defining-data-collections}

Puoi aggiungere al contenuto dell’evento una raccolta di elementi, ciascuno stesso elemento con diversi attributi.

Questa raccolta può essere utilizzata in un’e-mail sulle transazioni per aggiungere [inserzioni di prodotti](../../designing/using/using-product-listings.md) al contenuto del messaggio, ad esempio un elenco di prodotti, con il prezzo, il numero di riferimento, la quantità, ecc. per ogni prodotto dell&#39;elenco.

1. In **[!UICONTROL Collections]** fai clic sulla sezione **[!UICONTROL Create element]** pulsante .

   ![](assets/message-center_collection_create.png)

1. Aggiungi un’etichetta e un ID per la raccolta.
1. Aggiungi tutti i campi da visualizzare nel messaggio sulle transazioni per ciascun prodotto dell’elenco.

   In questo esempio sono stati aggiunti i campi seguenti:

   ![](assets/message-center_collection_fields.png)

1. La **[!UICONTROL Enrichment]** consente di arricchire ogni elemento della raccolta. In questo modo puoi personalizzare gli elementi dell’elenco di prodotti corrispondente con le informazioni provenienti dal database di Adobe Campaign o da altre risorse create.

>[!NOTE]
>
>Le fasi di arricchimento degli elementi di una raccolta sono le stesse descritte nella sezione [Arricchimento dell’evento](#enriching-the-transactional-message-content) sezione . Tieni presente che l’arricchimento dell’evento non ti consentirà di arricchire una raccolta: è necessario aggiungere un arricchimento alla raccolta stessa nel **[!UICONTROL Collections]** sezione .

Una volta pubblicati l’evento e il messaggio, potrai utilizzare questa raccolta nel messaggio transazionale.

Ecco l’anteprima API per questo esempio:

![](assets/message-center_collection_api-preview.png)

**Argomenti correlati:**

* [Anteprima e pubblicazione dell’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [Utilizzo degli elenchi di prodotti in un messaggio sulle transazioni](../../designing/using/using-product-listings.md)
* [Pubblicazione di un messaggio sulle transazioni](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## Arricchimento dell’evento {#enriching-the-transactional-message-content}

Per personalizzare i messaggi, puoi arricchire il contenuto dei messaggi transazionali con le informazioni contenute nel database di Adobe Campaign. Dal cognome o dall’ID CRM di ciascuno dei destinatari, ad esempio, puoi recuperare dati quali il loro indirizzo o la data di nascita o qualsiasi altro campo personalizzato aggiunto nella tabella Profilo, al fine di personalizzare le informazioni inviate.

È possibile arricchire il contenuto dei messaggi transazionali con le informazioni provenienti da **[!UICONTROL Profile and services Ext API]**. Per ulteriori informazioni, consulta [Estensione dell’API: Pubblicazione dell&#39;estensione](../../developing/using/step-2--publish-the-extension.md)

Queste informazioni possono essere memorizzate anche in nuove risorse. In tal caso, la risorsa deve essere collegata al **[!UICONTROL Profile]** o **[!UICONTROL Service]** risorse direttamente o tramite un’altra tabella. Ad esempio, nella configurazione seguente, è possibile arricchire il contenuto dei messaggi transazionali con le informazioni contenute nel **[!UICONTROL Product]** come la categoria o l&#39;ID del prodotto, se **[!UICONTROL Product]** la risorsa è collegata al **[!UICONTROL Profile]** risorsa.

![](assets/message-center_usecaseschema.png)

Per ulteriori informazioni sulla creazione e la pubblicazione delle risorse, consulta [questa sezione](../../developing/using/key-steps-to-add-a-resource.md).

1. In **[!UICONTROL Enrichment]** fai clic sulla sezione **[!UICONTROL Create element]** pulsante .

   ![](assets/message-center_addenrichment.png)

1. Seleziona la risorsa con cui desideri collegare il messaggio. In questo caso, scegli la **[!UICONTROL Profile]** risorsa.

   ![](assets/message-center_new-enrichment.png)

1. Utilizza la **[!UICONTROL Create element]** per collegare un campo dalla risorsa selezionata a uno dei campi precedentemente aggiunti all’evento (vedi [Definizione degli attributi dell’evento](#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. In questo esempio, riconciliiamo il **[!UICONTROL Last name]** e **[!UICONTROL First name]** i campi con i campi corrispondenti nel campo **[!UICONTROL Profile]** risorsa.

   ![](assets/message-center_enrichment-join-fields.png)

   Puoi anche arricchire il contenuto dei messaggi transazionali utilizzando **[!UICONTROL Service]** risorsa. Per ulteriori informazioni sui servizi, consulta [questa sezione](../../audiences/using/creating-a-service.md).

1. Se crei o modifichi un [evento basato su profilo](#profile-based-transactional-messages), nella **[!UICONTROL Targeting enrichment]** seleziona l’arricchimento che verrà utilizzato come destinazione del messaggio durante l’esecuzione della consegna.

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >Creazione di un arricchimento e selezione di un arricchimento di targeting basato su **[!UICONTROL Profile]** le risorse sono obbligatorie per gli eventi basati su profilo.

Dopo la pubblicazione dell’evento e del messaggio, questo collegamento ti consente di arricchire il contenuto del messaggio sulle transazioni.

**Argomenti correlati:**

* [Anteprima e pubblicazione dell’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)
* [Personalizzazione di un messaggio sulle transazioni](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message)
* [Pubblicazione di un messaggio sulle transazioni](../../channels/using/publishing-transactional-message.md#publishing-a-transactional-message)

## Ricerca di eventi transazionali {#searching-transactional-events}

Per accedere e cercare gli eventi transazionali già creati, segui i passaggi seguenti.

1. Fai clic sul pulsante **Adobe** , nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Fai clic sul pulsante **[!UICONTROL Show search]**.

   ![](assets/message-center_search-events.png)

1. Puoi filtrare il **[!UICONTROL Publication status]**. Questo consente ad esempio di visualizzare solo gli eventi pubblicati.
1. Puoi anche filtrare gli eventi utilizzando la **[!UICONTROL Last event received]**. Ad esempio, se immetti 10, verranno visualizzate solo le configurazioni dell’evento con l’ultimo evento ricevuto 10 giorni fa o più. Questo consente di visualizzare gli eventi inattivi per un determinato periodo di tempo.

   ![](assets/message-center_last-event-received.png)

   >[!NOTE]
   >
   >Il valore predefinito è 0. Vengono quindi visualizzati tutti gli eventi.

## Configurazioni specifiche {#transactional-event-specific-configurations}

La configurazione dell’evento transazionale può variare a seconda del [tipo di messaggio sulle transazioni](../../channels/using/getting-started-with-transactional-msg.md#transactional-message-types) desideri inviare (evento o profilo) e sul canale che verrà utilizzato.

Nelle sezioni seguenti viene descritto in dettaglio quale configurazione specifica deve essere impostata in base al messaggio transazionale desiderato. Per ulteriori informazioni sui passaggi generali per configurare un evento, consulta [Creazione di un evento](#creating-an-event).

### Messaggi transazionali basati su eventi {#event-based-transactional-messages}

Puoi inviare messaggi sulle transazioni destinati a un evento. Questo tipo di messaggi sulle transazioni non contiene informazioni del profilo: il target di consegna è definito dai dati contenuti nell’evento stesso.

Per inviare un messaggio transazionale basato su eventi, devi innanzitutto creare e configurare un evento che esegua il targeting di **dati contenuti nell&#39;evento stesso**.

1. Quando crei la configurazione dell’evento, seleziona la **[!UICONTROL Real-time event]** dimensione di targeting (vedi [Creazione di un evento](#creating-an-event)).
1. Aggiungi dei campi all’evento per poter personalizzare il messaggio sulle transazioni (consulta [Definizione degli attributi dell’evento](#defining-the-event-attributes)).
1. La messaggistica transazionale basata su eventi dovrebbe utilizzare solo i dati presenti nell’evento inviato per definire il destinatario e la personalizzazione del contenuto del messaggio.

   Tuttavia, se desideri utilizzare informazioni aggiuntive dal database di Adobe Campaign, puoi arricchire il contenuto dei messaggi transazionali (vedi [Arricchimento del contenuto dei messaggi transazionali](#enriching-the-transactional-message-content)).

1. Anteprima e pubblicazione dell’evento (consulta [Anteprima e pubblicazione dell’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)).

   Quando visualizzi l’anteprima dell’evento, l’API REST contiene un attributo che specifica l’indirizzo e-mail, il telefono cellulare o gli attributi specifici della notifica push, in base al canale selezionato.

   Una volta pubblicato l’evento, viene automaticamente creato un messaggio transazionale collegato al nuovo evento. Affinché l’evento attivi l’invio di un messaggio sulle transazioni, devi [modificare](../../channels/using/editing-transactional-message.md) e [pubblicare](../../channels/using/publishing-transactional-message.md) il messaggio appena creato.

1. Integra l’evento nel tuo sito web (vedi [Integrare l’attivazione dell’evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

### Messaggi transazionali basati su profili {#profile-based-transactional-messages}

Puoi inviare messaggi transazionali basati sui profili dei clienti, che ti consentono di applicare regole di tipologia di marketing, includere il collegamento per l’annullamento dell’abbonamento, aggiungere il messaggio al reporting globale sulla consegna e sfruttarlo nel percorso di clienti.

Per inviare un messaggio transazionale basato su profilo, devi innanzitutto creare e configurare un targeting di evento **dati del database Adobe Campaign**.

1. Quando crei la configurazione dell’evento, seleziona la **[!UICONTROL Profile event]** dimensione di targeting (vedi [Creazione di un evento](#creating-an-event)).
1. Aggiungi dei campi all’evento per poter personalizzare il messaggio sulle transazioni (consulta [Definizione degli attributi dell’evento](#defining-the-event-attributes)). Per creare un arricchimento è necessario aggiungere almeno un campo. Non è necessario creare altri campi, ad esempio **Nome** e **Cognome** Potrai utilizzare i campi di personalizzazione del database Adobe Campaign.
1. Creare un arricchimento per collegare l’evento al **[!UICONTROL Profile]** risorsa (vedi [Arricchimento dell’evento](#enriching-the-transactional-message-content)) e seleziona questo arricchimento come **[!UICONTROL Targeting enrichment]**.

   >[!IMPORTANT]
   >
   >Questo passaggio è obbligatorio per gli eventi basati su profilo.

1. Anteprima e pubblicazione dell’evento (consulta [Anteprima e pubblicazione dell’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)).

   Quando visualizzi l’anteprima dell’evento, l’API REST non contiene un attributo che specifica gli attributi specifici dell’indirizzo e-mail, del telefono cellulare o della notifica push, in quanto verrà recuperato dal **[!UICONTROL Profile]** risorsa.

   Una volta pubblicato l’evento, viene automaticamente creato un messaggio transazionale collegato al nuovo evento. Affinché l’evento attivi l’invio di un messaggio sulle transazioni, devi [modificare](../../channels/using/editing-transactional-message.md) e [pubblicare](../../channels/using/publishing-transactional-message.md) il messaggio appena creato.

1. Integra l’evento nel tuo sito web (vedi [Integrare l’attivazione dell’evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger)).

<!--### Transactional SMS messages {#transactional-sms}

The steps to configure an  event to send an SMS transactional message are the same as for the email channel. The only differences are as follows:

* When creating the corresponding event, you need to select the **[!UICONTROL Mobile (SMS)]** channel.

* When previewing the event corresponding to an event-based transactional SMS, the REST API contains an attribute specifying the mobile phone instead of the email address.

* The specificities to edit the content of an SMS transactional message are the same as for a [standard SMS](../../channels/using/about-sms-and-push-content-design.md).-->

### Notifiche push transazionali {#transactional-push-notifications}

Puoi inviare due tipi di notifiche push transazionali:
* Una notifica push transazionale anonima a tutti gli utenti che hanno acconsentito alla ricezione di notifiche dalla tua app mobile. Vedi [Configurazione delle notifiche push transazionali basate su eventi](../../channels/using/transactional-push-notifications.md#event-based-transactional-push-notifications).
* Una notifica push transazionale ai profili Adobe Campaign abbonati alla tua app mobile. Vedi [Configurazione delle notifiche push transazionali basate su profili](../../channels/using/transactional-push-notifications.md#profile-based-transactional-push-notifications).

>[!IMPORTANT]
>
>Per poter inviare notifiche push transazionali, devi configurare Adobe Campaign di conseguenza. Vedi [Configurazione di un’app mobile](../../administration/using/configuring-a-mobile-application.md).

### Messaggi di follow-up {#follow-up-messages}

Puoi inviare un messaggio di follow-up ai clienti che hanno ricevuto un messaggio transazionale specifico.

I passaggi per configurare un evento che consente di inviare un messaggio di follow-up sono descritti in [questa sezione](../../channels/using/follow-up-messages.md#configuring-an-event-to-send-a-follow-up-message).
