---
solution: Campaign Standard
product: campaign
title: Passaggi principali per impostare un messaggio transazionale
description: Scopri i messaggi transazionali e scopri i passaggi principali per impostare un messaggio transazionale in  Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 00032b1a8bfef301d1a87750695ba1670b2eed6c
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 18%

---


# Guida introduttiva ai messaggi transazionali {#getting-started-with-transactional-messaging}

## Panoramica {#overview}

### Cos&#39;è un messaggio transazionale?

Si tratta di una comunicazione individuale e unica, inviata in tempo reale da un provider come un sito web. È particolarmente previsto, perché contiene informazioni importanti che il destinatario desidera controllare o confermare.

* **Quando è dovuto?** Poiché questo messaggio contiene informazioni importanti, l&#39;utente prevede che venga inviato in tempo reale. Di conseguenza, il ritardo tra l&#39;attivazione dell&#39;evento e l&#39;arrivo del messaggio deve essere molto breve.

* **Perché è importante?** Generalmente, un messaggio transazionale ha tassi di apertura elevati. Dovrebbe pertanto essere attentamente progettata, in quanto può avere un forte impatto sul comportamento dei clienti nel momento in cui definisce la relazione con il cliente.

* **Ad esempio?** Potrebbe trattarsi di un messaggio di benvenuto dopo la creazione di un account, la conferma che un ordine è stato spedito, una fattura, un messaggio di conferma di una modifica della password o una notifica dopo che un cliente ha visitato il sito Web...

### Invio di messaggi transazionali

 Adobe Campaign consente di integrare questa funzionalità con un sistema informativo che invia eventi da trasformare in messaggi transazionali personalizzati.

Puoi inviare i messaggi transazionali tramite e-mail, SMS o notifiche push, a seconda delle opzioni. Controlla il contratto di licenza.

>[!NOTE]
>
> Adobe Campaign assegna priorità all&#39;elaborazione dei messaggi transazionali rispetto a qualsiasi altra consegna.

I messaggi transazionali sono disponibili anche dall’API di Adobe Campaign Standard. Per ulteriori informazioni, consultare la [documentazione dedicata](../../api/using/managing-transactional-messages.md).

>[!NOTE]
>
>Tutti i messaggi transazionali ora vengono inviati con Adobe Campaign Enhanced MTA per migliorare il tasso di consegna, il throughput e la gestione dei messaggi non recapitati. Tutti gli effetti sono gli stessi dei messaggi di marketing standard. Per ulteriori informazioni, consulta [questa sezione](../../administration/using/configuring-email-channel.md).

### Tipi di messaggi transazionali {#transactional-message-types}

In Adobe Campaign sono disponibili due tipi di messaggi transazionali:

**I** messaggi transazionali degli eventi hanno come destinazione un evento:
* Non contengono informazioni sul profilo.
* Non sono compatibili con le regole di affaticamento (anche nel caso di un arricchimento con i profili).
* Il target di consegna è definito dai dati contenuti nell&#39;evento stesso.

**I** messaggi transazionali dei profili sono profili di targeting provenienti dal database di marketing di Campaign. Con questo tipo di messaggi, puoi:
* Applica le regole di [tipologia di marketing](../../sending/using/managing-typology-rules.md) o [regole di affaticamento](../../sending/using/fatigue-rules.md).
* Includere il collegamento di annullamento all’abbonamento nei messaggi;
* Aggiungere messaggi transazionali al reporting globale sulla distribuzione;
* Utilizzare messaggi transazionali nel customer journey.

Il tipo di messaggio viene definito durante la configurazione dell’evento che viene trasformato in un messaggio transazionale. Vedi [questa sezione](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations).

>[!IMPORTANT]
>
>Per accedere a tutti i messaggi transazionali, devi far parte del gruppo di sicurezza **[!UICONTROL Administrators (all units)]**.

## Principio operativo della messaggistica transazionale {#transactional-messaging-operating-principle}

Il processo globale di messaggistica transazionale può essere descritto come segue:

![](assets/message-center-process.png)

Ad esempio, supponiamo che tu sia un&#39;azienda con un sito Web in cui i clienti possono acquistare prodotti.

 Adobe Campaign consente di inviare un messaggio e-mail di notifica ai clienti che hanno aggiunto prodotti al carrello: quando uno di essi abbandona il sito Web senza procedere con i propri acquisti (evento esterno che attiva un evento Campaign), viene loro automaticamente inviato un messaggio e-mail di abbandono del carrello (consegna di messaggi transazionali).

<!--The steps for putting this into place are detailed below.-->

### Passaggi chiave {#key-steps}

I passaggi principali per la creazione e la gestione di messaggi transazionali personalizzati in  Adobe Campaign sono riepilogati nel grafico seguente.

![](assets/message-center-overview.png)

Ognuna di queste fasi è dettagliata qui di seguito.

### Passaggio 1 - Creare e pubblicare la configurazione dell&#39;evento {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| Utente | Azione | Risultato |
|--- |--- |--- |
| Questo passaggio deve essere eseguito da un utente con [diritti di amministrazione](../../administration/using/users-management.md#functional-administrators). | Configurate un evento che verrà denominato &quot;abbandono del carrello&quot; e pubblicate la configurazione dell&#39;evento. | L&#39;API che verrà utilizzata dallo sviluppatore del sito Web viene distribuita e viene automaticamente creato un messaggio transazionale. |

La creazione e la pubblicazione di un evento vengono presentate nelle sezioni [Configurazione di un evento transazionale](../../channels/using/configuring-transactional-event.md) e [Pubblicazione di un evento transazionale](../../channels/using/publishing-transactional-event.md).

### Passaggio 2 - Modifica e pubblica il messaggio di transazione {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| Utente | Azione | Risultato |
|--- |--- |--- |
| Questo passaggio può essere eseguito da qualsiasi utente di marketing con [diritti di accesso utente standard](../../administration/using/users-management.md#basic-users). | Modificate e personalizzate il messaggio transazionale, verificatelo e pubblicatelo. | Il messaggio transazionale sarà quindi pronto per essere inviato. |

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
