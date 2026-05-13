---
title: Guida introduttiva ai messaggi transazionali
description: Scopri cos’è la messaggistica transazionale e i passaggi principali per impostare un messaggio transazionale in Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Beginner
exl-id: 49fba1af-3c99-45b7-bcbb-b9b9678eedcd
TQID: https://experienceleague.adobe.com/vveKWyxi6u44BmNqzEVeMwPvtvP8uWhAI-4UMD2CnVU
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2:
  - id: b5852c32-876b-41ae-92a7-9f588865ae52
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
  - id: d3b34fea-a110-482f-adb2-aae8d686bac8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 996
ht-degree: 8%

---

# Guida introduttiva ai messaggi transazionali {#getting-started-with-transactional-messaging}

Un messaggio transazionale è una comunicazione singola e univoca, inviata in tempo reale da un provider, ad esempio un sito web. È particolarmente atteso, perché contiene informazioni importanti che il destinatario desidera controllare o confermare.

* **Quando scade?** Poiché questo messaggio contiene informazioni importanti, l’utente si aspetta che vengano inviate in tempo reale. Di conseguenza, il ritardo tra l’attivazione dell’evento e l’arrivo del messaggio deve essere molto breve.

* **Perché è importante?** In genere, un messaggio sulle transazioni ha tassi di apertura elevati. Dovrebbe quindi essere concepita con attenzione, in quanto può avere un forte impatto sul comportamento dei clienti in quanto definisce la relazione con essi.

* **Ad esempio?** Potrebbe trattarsi di un messaggio di benvenuto dopo la creazione di un account, di una conferma della spedizione di un ordine, di una fattura, di un messaggio di conferma di una modifica della password o di una notifica dopo che un cliente ha visitato il tuo sito web, ecc.

Adobe Campaign consente di integrare questa funzionalità con un sistema di informazioni che invia eventi da trasformare in messaggi transazionali personalizzati.

I messaggi transazionali possono essere inviati tramite e-mail, SMS o [notifica push](../../channels/using/transactional-push-notifications.md), a seconda delle opzioni. Controlla il contratto di licenza.

>[!NOTE]
>
>Adobe Campaign dà priorità all’elaborazione dei messaggi transazionali rispetto a qualsiasi altra consegna.

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

Prima di iniziare a utilizzare i messaggi transazionali, assicurati di aver letto le [best practice e limitazioni](../../channels/using/transactional-messaging-limitations.md) corrispondenti.

## Principio operativo della messaggistica transazionale {#transactional-messaging-operating-principle}

Il processo generale di messaggistica transazionale può essere descritto come segue:

![](assets/message-center-process.png)

Ad esempio, immagina di essere un’azienda con un sito web in cui i clienti possono acquistare prodotti.

Adobe Campaign consente di inviare un’e-mail di notifica ai clienti che hanno aggiunto prodotti al carrello. Quando uno di loro lascia il sito web senza procedere con gli acquisti (evento esterno che attiva un evento Campaign), riceve automaticamente un’e-mail di abbandono del carrello (consegna di messaggi transazionali).

I passaggi principali per l&#39;implementazione sono descritti di seguito in [questa sezione](#key-steps).

## Tipi di messaggi transazionali {#transactional-message-types}

In Adobe Campaign sono disponibili due tipi di messaggi transazionali.

**Messaggi transazionali di evento** dati di destinazione contenuti nell&#39;evento stesso. Questi messaggi:
* Non contenere informazioni di profilo e pertanto non può includere collegamenti di annullamento dell’abbonamento.
* Non sono compatibili con le regole di affaticamento (anche nel caso di un arricchimento con profili).
* Il target di consegna deve essere definito dai dati contenuti nell’evento stesso.

Ad esempio, potrebbe essere utile inviare un messaggio transazionale di evento a un cliente che deve recuperare una password dimenticata o confermare un ordine. In effetti, non desideri che il destinatario annulli l’abbonamento a questo tipo di comunicazioni e che questa notifica non venga aggiunta al contatore dei messaggi di marketing come parte di una regola di affaticamento.

**Messaggi transazionali di profilo** indirizzati ai profili dal database di marketing di Campaign. Con questo tipo di messaggi puoi:
* Sfruttare i dati contenuti nel database di Adobe Campaign.
* Personalizza il messaggio con le informazioni del profilo aggiungendo un [arricchimento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) alla configurazione dell&#39;evento.
* Applicare [regole di tipologia di marketing](../../sending/using/managing-typology-rules.md) o [regole di affaticamento](../../sending/using/fatigue-rules.md).
* Includere il collegamento di annullamento all’abbonamento nei messaggi;
* Aggiungere messaggi transazionali al reporting globale sulla distribuzione;
* Utilizzare messaggi transazionali nel customer journey.

Ad esempio, puoi utilizzare questo tipo di messaggi quando contatti i clienti dopo che hanno abbandonato il carrello sul tuo sito web, per incoraggiarli a procedere con il loro acquisto. In questo modo, puoi personalizzare più facilmente il messaggio con l’accesso diretto a tutte le informazioni dal database dei profili, applicare le regole di marketing e includere il messaggio nel percorso globale dei clienti, oltre a generare rapporti per una migliore visualizzazione del comportamento dei clienti.

Il tipo di messaggio viene definito durante la configurazione dell’evento che viene trasformato in un messaggio transazionale. Consulta le sezioni di configurazione [Messaggi transazionali basati su eventi](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages) e [Messaggi transazionali basati su profili](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

## Passaggi chiave {#key-steps}

I passaggi principali durante la creazione e la gestione di messaggi transazionali personalizzati in Adobe Campaign sono riepilogati nello schema seguente.

![](assets/message-center-overview.png)

Ciascuna di queste fasi è descritta più dettagliatamente di seguito.

>[!IMPORTANT]
>
>Solo gli utenti con il ruolo [Amministrazione](../../administration/using/users-management.md#functional-administrators) possono configurare eventi transazionali e accedere ai messaggi transazionali.

### Passaggio 1: creare e pubblicare la configurazione dell’evento {#create-event-configuration}

<!--<img src="assets/do-not-localize/icon_config.svg" width="60px">-->

| Creare un evento | Utente | Azione | Risultato |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_config.svg" width="60px"> | Questo passaggio deve essere eseguito da un amministratore con [diritti di amministrazione](../../administration/using/users-management.md#functional-administrators). | Configura un evento denominato &quot;Abbandono del carrello&quot; e pubblica la configurazione dell’evento. | L’API che verrà utilizzata dallo sviluppatore del sito web viene distribuita e viene creato automaticamente un messaggio transazionale. |

La creazione e la pubblicazione di un evento sono presentate nelle sezioni [Configurazione di un evento transazionale](../../channels/using/configuring-transactional-event.md) e [Pubblicazione di un evento transazionale](../../channels/using/publishing-transactional-event.md).

### Passaggio 2: modificare e pubblicare il messaggio sulle transazioni {#create-transactional-message}

<!--<img src="assets/do-not-localize/icon_notification.svg" width="40px">-->

| Modifica il messaggio | Utente | Azione | Risultato |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_notification.svg" width="40px"> | Questo passaggio può essere eseguito da un utente marketing con [diritti di amministrazione](../../administration/using/users-management.md#functional-administrators). | Modifica e personalizza il messaggio transazionale, testalo e infine pubblicalo. | Il messaggio sulle transazioni è quindi pronto per essere inviato. |

Per ulteriori informazioni sulla modifica e la pubblicazione di un messaggio sulle transazioni, consulta [Modifica dei messaggi sulle transazioni](../../channels/using/editing-transactional-message.md) e [Ciclo di vita dei messaggi sulle transazioni](../../channels/using/publishing-transactional-message.md).

### Passaggio 3: integrare l’attivazione dell’evento {#integrate-event-trigger}

<!--<img src="assets/do-not-localize/icon_api.svg" width="55px">-->

Dopo aver creato un evento, è necessario integrare l&#39;attivazione di questo evento nel sito Web.<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> A tale scopo, lo sviluppatore Web del sito Web deve utilizzare l&#39;**API REST di Adobe Campaign Standard**.

| Implementare il trigger | Utente | Azione | Risultato |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_api.svg" width="55px"> | Questo passaggio viene eseguito dallo sviluppatore del sito web. | Utilizza l’API per messaggi transazionali REST per integrare l’evento nel sito web. | L’evento viene attivato quando un client abbandona il carrello. |

Per ulteriori informazioni sull&#39;utilizzo dell&#39;API REST di Campaign per gestire i messaggi transazionali, consulta la [documentazione REST API](../../api/using/managing-transactional-messages.md).

### Passaggio 4: consegna dei messaggi {#message-delivery}

<!--<img src="assets/do-not-localize/icon_channels.svg" width="60px">-->

Una volta eseguiti tutti i passaggi di cui sopra, il messaggio può essere consegnato.

| Consegna il messaggio | Utente | Azione | Risultato |
| --- |--- |--- |--- |
| <img src="assets/do-not-localize/icon_channels.svg" width="60px"> | Questo passaggio viene eseguito dai clienti che visitano il tuo sito web. | Non appena un utente abbandona il sito senza ordinare i prodotti nel carrello, si attiva l’evento Campaign corrispondente. | L’utente riceve automaticamente un’e-mail di notifica. |

## Argomenti correlati

* [Passaggi fondamentali per l’invio di un messaggio](../../channels/using/key-steps-to-send-a-message.md)
* [Introduzione ai canali di comunicazione](../../channels/using/get-started-communication-channels.md)
* [Notifiche push transazionali](../../channels/using/transactional-push-notifications.md)
* [Messaggi di follow-up](../../channels/using/follow-up-messages.md)
