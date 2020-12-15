---
solution: Campaign Standard
product: campaign
title: Guida introduttiva ai messaggi transazionali
description: Scopri i messaggi transazionali e scopri i passaggi principali per impostare un messaggio transazionale in  Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 9%

---


# Guida introduttiva ai messaggi transazionali {#getting-started-with-transactional-messaging}

## Panoramica {#overview}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Un messaggio transazionale è una comunicazione individuale e univoca, inviata in tempo reale da un fornitore come un sito Web. È particolarmente previsto, perché contiene informazioni importanti che il destinatario desidera controllare o confermare.

* **Quando è dovuto?** Poiché questo messaggio contiene informazioni importanti, l&#39;utente prevede che venga inviato in tempo reale. Di conseguenza, il ritardo tra l&#39;attivazione dell&#39;evento e l&#39;arrivo del messaggio deve essere molto breve.

* **Perché è importante?** Generalmente, un messaggio transazionale ha tassi di apertura elevati. Dovrebbe pertanto essere attentamente progettata, in quanto può avere un forte impatto sul comportamento dei clienti nel momento in cui definisce la relazione con il cliente.

* **Ad esempio?** Potrebbe essere un messaggio di benvenuto dopo la creazione di un account, la conferma che un ordine è stato spedito, una fattura, un messaggio di conferma di una modifica della password, o una notifica dopo che un cliente ha visitato il sito Web, ecc.

 Adobe Campaign consente di integrare questa funzionalità con un sistema informativo che invia eventi da trasformare in messaggi transazionali personalizzati.

I messaggi transazionali possono essere inviati via e-mail, SMS o [notifica push](../../channels/using/transactional-push-notifications.md), a seconda delle opzioni. Controlla il contratto di licenza.

>[!NOTE]
>
> Adobe Campaign assegna priorità all&#39;elaborazione dei messaggi transazionali rispetto a qualsiasi altra consegna.

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

<!--All transactional messages are now sent with the Adobe Campaign Enhanced MTA for improved deliverability, throughput, and bounce handling. All impacts are the same as for standard marketing messages. For more on this, see [this section](../../administration/using/configuring-email-channel.md).-->

Prima di iniziare con i messaggi transazionali, assicurati di leggere le [best practice e limitazioni ](../../channels/using/transactional-messaging-limitations.md) corrispondenti.

## Principio operativo della messaggistica transazionale {#transactional-messaging-operating-principle}

Il processo globale di messaggistica transazionale può essere descritto come segue:

![](assets/message-center-process.png)

Ad esempio, immaginate di essere un&#39;azienda con un sito Web in cui i clienti possono acquistare prodotti.

 Adobe Campaign consente di inviare un messaggio e-mail di notifica ai clienti che hanno aggiunto prodotti al carrello. Quando uno di essi lascia il sito Web senza procedere con gli acquisti (evento esterno che attiva un evento Campaign), viene loro automaticamente inviato un messaggio e-mail di abbandono del carrello (consegna di messaggi transazionali).

Le fasi principali per la realizzazione di questo progetto sono descritte in [questa sezione](#key-steps).

## Tipi di messaggi transazionali {#transactional-message-types}

In Adobe Campaign sono disponibili due tipi di messaggi transazionali.

**I dati** del messaggio di transazione evento contenuti nell&#39;evento stesso. Questi messaggi:
* Non contengono informazioni sul profilo e pertanto non possono includere collegamenti di annullamento della sottoscrizione.
* Non sono compatibili con le regole di affaticamento (anche nel caso di un arricchimento con i profili).
* Definite il target di consegna in base ai dati contenuti nell&#39;evento stesso.

Potrebbe essere utile inviare un messaggio di transazione evento a un cliente che deve recuperare una password dimenticata, ad esempio, o per confermare un ordine. In effetti, non si desidera che il destinatario annulli l&#39;iscrizione a questo tipo di comunicazioni e questa notifica non deve essere aggiunta al contatore dei messaggi di marketing come parte di una regola di affaticamento.

**Profili** del messaggio di marketing transazionali del profilo dal database di marketing di Campaign. Con questo tipo di messaggi, puoi:
* Utilizzo dei dati contenuti nel database Adobe Campaign .
* Personalizzate il messaggio con le informazioni sul profilo aggiungendo un [arricchimento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) alla configurazione dell&#39;evento.
* Applica le regole di [tipologia di marketing](../../sending/using/managing-typology-rules.md) o [regole di affaticamento](../../sending/using/fatigue-rules.md).
* Includere il collegamento di annullamento all’abbonamento nei messaggi;
* Aggiungere messaggi transazionali al reporting globale sulla distribuzione;
* Utilizzare messaggi transazionali nel customer journey.

Ad esempio, puoi utilizzare questo tipo di messaggi quando contatta i clienti dopo che hanno abbandonato il carrello sul tuo sito Web, per incoraggiarli a procedere con il loro acquisto. In questo modo, puoi personalizzare più facilmente il messaggio con accesso diretto a tutte le informazioni presenti nel tuo database dei profili, applicare le regole di marketing e includere questo messaggio nel percorso globale del cliente e nei rapporti per una migliore visualizzazione del comportamento del cliente.

Il tipo di messaggio viene definito durante la configurazione dell’evento che viene trasformato in un messaggio transazionale. Vedere le sezioni di configurazione dei messaggi transazionali basati su eventi [ e ](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages)messaggi transazionali basati su profilo[.](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages)

## Passaggi chiave {#key-steps}

I passaggi principali per la creazione e la gestione di messaggi transazionali personalizzati in  Adobe Campaign sono riepilogati nello schema seguente.

![](assets/message-center-overview.png)

Ognuna di queste fasi è dettagliata qui di seguito.

>[!IMPORTANT]
>
>Solo gli utenti con il ruolo [Amministrazione](../../administration/using/users-management.md#functional-administrators) possono configurare eventi transazionali e accedere ai messaggi transazionali.

### Passaggio 1 - Creare e pubblicare la configurazione dell&#39;evento {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| Utente | Azione | Risultato |
|--- |--- |--- |
| Questo passaggio deve essere eseguito da un amministratore che detiene [diritti di amministrazione](../../administration/using/users-management.md#functional-administrators). | Configurate un evento che verrà denominato &quot;abbandono del carrello&quot; e pubblicate la configurazione dell&#39;evento. | L&#39;API che verrà utilizzata dallo sviluppatore del sito Web viene distribuita e viene automaticamente creato un messaggio transazionale. |

La creazione e la pubblicazione di un evento vengono presentate nelle sezioni [Configurazione di un evento transazionale](../../channels/using/configuring-transactional-event.md) e [Pubblicazione di un evento transazionale](../../channels/using/publishing-transactional-event.md).

### Passaggio 2 - Modifica e pubblica il messaggio di transazione {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| Utente | Azione | Risultato |
|--- |--- |--- |
| Questo passaggio può essere eseguito da un utente marketing che detiene [diritti di amministrazione](../../administration/using/users-management.md#functional-administrators). | Modificate e personalizzate il messaggio transazionale, verificatelo e pubblicatelo. | Il messaggio transazionale sarà quindi pronto per essere inviato. |

Per ulteriori informazioni sulla modifica e la pubblicazione di un messaggio transazionale, vedere [Modifica di messaggi transazionali](../../channels/using/editing-transactional-message.md) e [ciclo di vita dei messaggi transazionali](../../channels/using/publishing-transactional-message.md).

### Passaggio 3 - Integrare l&#39;attivazione dell&#39;evento {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| Utente | Azione | Risultato |
|--- |--- |--- |
| Questo passaggio viene eseguito dallo sviluppatore del sito Web. | Utilizzate REST Transactional Messages API per integrare l&#39;evento nel sito Web. | L&#39;evento viene attivato quando un cliente abbandona il carrello. |

Dopo aver creato un evento, è necessario integrare l’attivazione di questo evento nel sito Web.<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> A tal fine, lo sviluppatore Web del sito Web deve utilizzare l&#39;API **REST** Adobe Campaign Standard.

Per ulteriori informazioni sull&#39;utilizzo di Campaign REST API per gestire i messaggi transazionali, consulta la [Documentazione REST API](../../api/using/managing-transactional-messages.md).

### Passaggio 4 - Invio di messaggi {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Una volta che tutti questi passaggi sono stati eseguiti, il messaggio può essere recapitato.

Non appena un utente lascia il sito senza ordinare i prodotti nel carrello, viene attivato l&#39;evento Campaign corrispondente. L’utente riceve automaticamente un messaggio e-mail di notifica.

## Argomenti correlati

* [Passaggi fondamentali per l’invio di un messaggio](../../channels/using/key-steps-to-send-a-message.md)
* [Guida introduttiva ai canali di comunicazione](../../channels/using/get-started-communication-channels.md)
* [Notifiche push transazionali](../../channels/using/transactional-push-notifications.md)
* [Messaggi di follow-up](../../channels/using/follow-up-messages.md)
