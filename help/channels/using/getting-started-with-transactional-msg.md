---
title: Passaggi principali per impostare un messaggio transazionale
description: Scopri i messaggi transazionali e scopri i passaggi principali per impostare un messaggio transazionale in  Adobe Campaign Standard.
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07adae5bac947df794520e48361fd3c20eba5ff8
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 30%

---


# Guida introduttiva ai messaggi transazionali {#getting-started-with-transactional-messaging}

## Panoramica


<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

<table>
<tr>
<td ><br><p>I messaggi transazionali consentono di <b>inviare messaggi</b> singoli e univoci ai clienti in tempo reale.</p></td>
<td>Può essere messaggi di benvenuto, conferme di spedizione ordine, modifica della password, ecc.</td>
</tr>
</table>

 Adobe Campaign consente di integrare questa funzionalità con un sistema informativo che invia eventi da trasformare in messaggi transazionali personalizzati.

>[!NOTE]
>
>Puoi inviare i messaggi transazionali tramite e-mail, SMS o notifiche push, a seconda delle opzioni. Controlla il contratto di licenza.

 Adobe Campaign assegna priorità all&#39;elaborazione dei messaggi transazionali rispetto a qualsiasi altra consegna.

I messaggi transazionali sono disponibili anche dall’API di Adobe Campaign Standard. Per ulteriori informazioni, consulta la [documentazione dedicata](../../api/using/managing-transactional-messages.md).

>[!NOTE]
>
>Tutti i messaggi transazionali ora vengono inviati con Adobe Campaign Enhanced MTA per migliorare il tasso di consegna, il throughput e la gestione dei messaggi non recapitati. Tutti gli effetti sono gli stessi dei messaggi di marketing standard. Per ulteriori informazioni, consulta questa [sezione](../../administration/using/configuring-email-channel.md).

## Definizione di messaggi transazionali {#transactional-messaging-definition}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_concepts.svg" width="60px"><br><p><b>Cos'è un messaggio transazionale?</b></p></td>
<td><p>Si tratta di una comunicazione individuale e unica, inviata da un provider come un sito web.</p></td>
<td><p>È particolarmente previsto, perché contiene informazioni importanti che il destinatario desidera controllare o confermare.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_channels.svg" width="60px"><br><p><b>Quando è dovuto?</b></p></td>
<td><p> Poiché questo messaggio contiene informazioni importanti, l'utente prevede che venga inviato in tempo reale.</p></td>
<td><p>Di conseguenza, il ritardo tra l'attivazione dell'evento e l'arrivo del messaggio deve essere molto breve.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_important.svg" width="60px"><br><p><b>Perché è importante?</b></p></td>
<td><p>Generalmente, un messaggio transazionale ha tassi di apertura elevati. Dovrebbe pertanto essere attentamente progettata.</p></td>
<td><p>In effetti, può avere un forte impatto sul comportamento dei clienti mentre definisce la relazione con il cliente.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_example.svg" width="60px"><br><p><b>Ad esempio?</b></p></td>
<td><p>Potrebbe essere un messaggio di benvenuto dopo la creazione di un account, la conferma che un ordine è stato spedito, una fattura...</p></td>
<td><p>Può trattarsi anche di un messaggio di conferma della modifica della password o di una notifica dopo che un cliente ha visitato il sito Web...</p></td>
</tr>
</table>

## Tipi di messaggi transazionali

In Adobe Campaign sono disponibili due tipi di messaggi transazionali:

<!--[Event transactional messages](../../channels/using/event-transactional-messages.md) targeting an **event**. The data contained in the event itself is used to define the delivery target.-->

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_event.svg" width="60px"><br><p><a href="../../channels/using/event-transactional-messages.md">Messaggi transazionali di evento</a><br><b> indirizzati a un evento</b></p></td>
<td><p><ul><li>Non contengono informazioni sul profilo.</li><li>Non sono compatibili con le regole <a href="../../sending/using/fatigue-rules.md">di</a> affaticamento (anche nel caso di un arricchimento con profili).</li><li>Il target di consegna è definito dai dati contenuti nell'evento stesso.</li></ul></p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_profile.svg" width="60px"><br><p><a href="../../channels/using/profile-transactional-messages.md">Messaggi transazionali di profilo</a><br><b> indirizzati ai profili dal database di marketing di Adobe Campaign</b></p></td>
<td><p>I messaggi transazionali del profilo consentono di:<ul><li>Applica le regole di tipologia di marketing, ad esempio <b>Indirizzo su  elenco Bloccati</b> o <a href="../../sending/using/fatigue-rules.md">regole</a>di affaticamento.</li><li>Includere il collegamento di annullamento all’abbonamento nei messaggi;</li><li>Aggiungere messaggi transazionali al reporting globale sulla distribuzione;</li><li>Utilizzare messaggi transazionali nel customer journey.</li></ul></p></td>
</tr>
</table>

<!--[Profile transactional messages](../../channels/using/profile-transactional-messages.md) targeting **profiles from the Adobe Campaign marketing database**. You can use information from the Adobe Campaign database to send a transactional message based on customer marketing profiles.-->

Il tipo di messaggio viene definito durante la configurazione dell’evento che viene trasformato in un messaggio transazionale. Vedi [Configurazione dei messaggi transazionali](../../administration/using/configuring-transactional-messaging.md).

>[!IMPORTANT]
>
>To access all transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.

<!--Event transactional messages do not contain profile information, therefore they are not compatible with fatigue rules (even in the case of an enrichment with profiles). However, profile transactional messages are compatible. For more on fatigue rules, see [this section](../../sending/using/fatigue-rules.md#choosing-the-channel).-->

## Principio operativo della messaggistica transazionale {#transactional-messaging-operating-principle}

Prendiamo l&#39;esempio di un&#39;azienda che ha un sito web e su questo sito i suoi clienti possono acquistare prodotti.

Adobe Campaign ti consente di inviare un messaggio e-mail di notifica agli utenti del sito che hanno aggiunto prodotti al carrello: quando uno di loro abbandona il sito senza procedere con gli acquisti, riceve automaticamente un’e-mail di carrello abbandonato.

I passi per la realizzazione di questo progetto sono i seguenti.

### Passaggio 1 - Creazione e pubblicazione della configurazione dell&#39;evento {#create-event-configuration}

<!--<img src="assets/do-not-localize/icon_config.svg" width="60px">

Configure an event that will be named "Cart abandonment" and publish this event configuration.

The API that will be used by your website developer is deployed and a transactional message is automatically created.-->

<img src="assets/do-not-localize/icon_config.svg" width="60px">

<table>
<tr>
<td><br><p>Configurate un evento che verrà denominato "abbandono del carrello" e pubblicate la configurazione dell'evento.</p></td>
<td>L'API che verrà utilizzata dallo sviluppatore del sito Web viene distribuita e viene automaticamente creato un messaggio transazionale.</td>
</tr>
</table>

La creazione e la pubblicazione di un evento sono presentate nella sezione [Configurazione di un evento per l’invio di un messaggio transazionale di evento](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

### Passaggio 2 - Modifica e pubblicazione del messaggio di transazione {#create-transactional-message}

<!--<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Edit and personalize the transactional message, test it, and then publish it.-->

<img src="assets/do-not-localize/icon_notification.svg" width="45px">

<table>
<tr>
<td><br><p>Modificate e personalizzate il messaggio transazionale, verificatelo e pubblicatelo.</p></td>
<td>Il messaggio transazionale sarà quindi pronto per essere inviato.</td>
</tr>
</table>

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### Passaggio 3 - Integrare l&#39;attivazione dell&#39;evento {#integrate-event-trigger}

<!--<img src="assets/do-not-localize/icon_api.svg" width="60px">

Use the REST Transactional Messages API to integrate the event into your website.

The event will be triggered when a client abandons their cart.-->

<img src="assets/do-not-localize/icon_api.svg" width="60px">

<table>
<tr>
<td><br><p>Utilizzate REST Transactional Messages API per integrare l'evento nel sito Web.</p></td>
<td>L'evento viene attivato quando un cliente abbandona il carrello.</td>
</tr>
</table>

Per ulteriori informazioni sull&#39;integrazione dell&#39;evento nel sito Web, consultate Integrazione [del](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)sito.

### Passaggio 4 - Invio di messaggi {#message-delivery}

<!--Once all of these steps have been carried out, the message can be delivered:

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

As soon as a user leaves the site without ordering the products in their cart, they automatically receive a notification email.-->

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

<table>
<tr>
<td><br><p>Una volta che tutti questi passaggi sono stati eseguiti, il messaggio può essere recapitato.</p></td>
<td>Non appena un utente lascia il sito senza ordinare i prodotti nel suo carrello, riceve automaticamente un messaggio e-mail di notifica.</td>
</tr>
</table>

## Passaggi chiave {#key-steps}

I passaggi principali per la creazione e la gestione di messaggi transazionali personalizzati in  Adobe Campaign sono riepilogati nel grafico seguente.

![](assets/message-center-overview.png)

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the whole transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on the event configuration steps, see [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

Read more:

* [About transactional messaging](../../channels/using/about-transactional-messaging.md)
* [Event transactional messages](../../channels/using/event-transactional-messages.md)
* [Profile transactional messages](../../channels/using/profile-transactional-messages.md)
* [Transactional push notifications](../../channels/using/transactional-push-notifications.md)
* [Follow-up messages](../../channels/using/follow-up-messages.md)-->

**Argomenti correlati:**

* [Passaggi fondamentali per l’invio di un messaggio](../../channels/using/key-steps-to-send-a-message.md)
* [Guida introduttiva ai canali di comunicazione](../../channels/using/get-started-communication-channels.md)