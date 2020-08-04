---
title: Informazioni sulla messaggistica transazionale
description: Scopri i diversi tipi di messaggi transazionali che puoi inviare e come utilizzarli in Adobe Campaign.
page-status-flag: never-activated
uuid: 8470e9e2-ee17-456f-9e4c-460e69c78a2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 71a4d5d5-fe2a-4ce5-b22b-a4736f7add83
internal: n
snippet: y
translation-type: ht
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb
workflow-type: ht
source-wordcount: '1147'
ht-degree: 100%

---


# Informazioni sulla messaggistica transazionale{#about-transactional-messaging}

Puoi creare e gestire messaggi transazionali personalizzati in Adobe Campaign.

Un messaggio transazionale è una comunicazione singola e univoca inviata a un utente da un provider, ad esempio un sito web.

* Questo tipo di messaggio è particolarmente atteso, in quanto contiene informazioni che il destinatario desidera controllare o confermare. Potrebbe trattarsi di un messaggio di benvenuto dopo la creazione di un account, ad esempio, o di una conferma della spedizione di un ordine, di una fattura o di un messaggio di conferma della modifica della password.
* È un messaggio importante che definisce la relazione del cliente: l’utente si aspetta che gli venga inviato in tempo reale. Il ritardo tra l’attivazione dell’evento e l’arrivo del messaggio deve quindi essere molto breve.
* I messaggi transazionali hanno generalmente tassi di apertura elevati.

Adobe Campaign ti consente di integrare questa funzionalità con un sistema di informazioni che invia gli eventi da trasformare in messaggi transazionali personalizzati.

>[!NOTE]
>
>Puoi inviare i messaggi transazionali tramite e-mail, SMS o notifiche push, a seconda delle opzioni. Controlla il contratto di licenza.

In Adobe Campaign sono disponibili due tipi di messaggi transazionali:

* [Messaggi transazionali di evento](../../channels/using/event-transactional-messages.md) indirizzati a un evento. I dati contenuti nell’evento vengono utilizzati per definire il target della consegna.
* [Messaggi transazionali di profilo](../../channels/using/profile-transactional-messages.md) indirizzati ai profili dal database di marketing di Adobe Campaign. Puoi utilizzare le informazioni contenute nel database di Adobe Campaign per inviare un messaggio transazionale basato sui profili di marketing dei clienti.

Il tipo di messaggio viene definito durante la configurazione dell’evento che viene trasformato in un messaggio transazionale. Vedi [Configurazione dei messaggi transazionali](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign dà priorità all’elaborazione dei messaggi transazionali rispetto a qualsiasi altra consegna.

I messaggi transazionali sono disponibili anche dall’API di Adobe Campaign Standard. Per ulteriori informazioni, consulta la [documentazione dedicata](../../api/using/managing-transactional-messages.md).

>[!NOTE]
>
>Tutti i messaggi transazionali ora vengono inviati con Adobe Campaign Enhanced MTA per migliorare il tasso di consegna, il throughput e la gestione dei messaggi non recapitati. Tutti gli effetti sono gli stessi dei messaggi di marketing standard. Per ulteriori informazioni, consulta questa [sezione](../../administration/using/configuring-email-channel.md).

## Principio operativo della messaggistica transazionale {#transactional-messaging-operating-principle}

Prendi l’esempio di un’azienda che ha un sito web dove gli utenti possono acquistare prodotti.

Adobe Campaign ti consente di inviare un messaggio e-mail di notifica agli utenti del sito che hanno aggiunto prodotti al carrello: quando uno di loro abbandona il sito senza procedere con gli acquisti, riceve automaticamente un’e-mail di carrello abbandonato.

I passaggi per implementare ciò sono i seguenti:

1. Configura un evento denominato &quot;Abbandono del carrello&quot; e pubblica la configurazione dell’evento, che crea automaticamente un messaggio transazionale. La creazione e la pubblicazione di un evento sono presentate nella sezione [Configurazione di un evento per l’invio di un messaggio transazionale di evento](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).
1. Devi personalizzare, verificare e infine pubblicare il messaggio transazionale. Vedi [Messaggi transazionali di evento](../../channels/using/event-transactional-messages.md).
1. Inoltre, per poter attivare l’evento quando un cliente abbandona il carrello, è necessario che venga inviato dal sito web dell’azienda tramite l’API REST di Adobe Campaign Standard. Vedi [Integrazione del sito](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Dopo l’esecuzione di tutti questi passaggi, non appena un utente abbandona il sito senza ordinare i prodotti aggiunti nel carrello, riceve automaticamente un’e-mail di notifica.

## Processo di pubblicazione della messaggistica transazionale {#transactional-messaging-pub-process}

Il grafico seguente illustra il processo di pubblicazione della messaggistica transazionale.

![](assets/message-center_pub-process.png)

Per ulteriori informazioni sui passaggi di configurazione dell’evento, consulta [Configurazione della messaggistica transazionale](../../administration/using/configuring-transactional-messaging.md).

## Limitazioni della messaggistica transazionale {#transactional-messaging-limitations}

>[!NOTE]
>
>Per accedere ai messaggi transazionali, devi disporre di diritti di amministrazione.

### Progettazione e pubblicazione {#design-and-publication}

Durante la progettazione e la pubblicazione dei messaggi transazionali, non è possibile ripristinare alcuni dei passaggi da eseguire. Devi conoscere i seguenti limiti:

* Puoi utilizzare un solo canale per ogni configurazione dell’evento. Vedi [Creazione di un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Dopo la creazione dell’evento, non puoi più cambiare il canale. Pertanto, se un messaggio non viene inviato correttamente, devi progettare il meccanismo che consenta di inviarlo da un altro canale utilizzando un flusso di lavoro. Vedi [Dati e processi del flusso di lavoro](../../automating/using/get-started-workflows.md).
* Non puoi modificare la dimensione di targeting (**[!UICONTROL Real-time event]** o **[!UICONTROL Profile]**) dopo la creazione dell’evento. Vedi [Creazione di un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Non puoi ripristinare una pubblicazione, ma puoi annullare la pubblicazione di un evento: questa operazione rende inaccessibili l’evento e il messaggio transazionale associato. Vedi [Annullamento della pubblicazione di un evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* L’unico messaggio transazionale associabile a un evento è il messaggio creato automaticamente durante la pubblicazione dell’evento. Vedi [Anteprima e pubblicazione dell’evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalizzazione {#personalization}

La modalità di personalizzazione del contenuto di un messaggio dipende dal tipo di messaggio transazionale. Le specifiche sono elencate di seguito:

**Messaggi transazionali basati su eventi**:

* Le informazioni sulla personalizzazione provengono dai dati contenuti nell’evento. Vedi [Messaggi transazionali di evento](../../channels/using/event-transactional-messages.md).
* Non puoi utilizzare blocchi di contenuto di **collegamento di annullamento dell’abbonamento** in un messaggio transazionale di evento.
* La messaggistica transazionale basata su eventi dovrebbe utilizzare solo i dati presenti nell’evento inviato per definire il destinatario e la personalizzazione del contenuto del messaggio. Tuttavia, puoi arricchire il contenuto del messaggio transazionale utilizzando le informazioni contenute nel database di Adobe Campaign. Consulta [Arricchimento del contenuto dei messaggi transazionali](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Poiché i messaggi transazionali di evento non contengono informazioni sul profilo, non sono compatibili con le regole di affaticamento, nemmeno nel caso di un arricchimento tramite profili. Consulta [Regole di affaticamento](../../sending/using/fatigue-rules.md).

**Messaggi transazionali basati su profili**:

* Le informazioni sulla personalizzazione possono provenire dai dati contenuti nell’evento o dal record del profilo riconciliato. Vedi [Messaggi transazionali di profilo](../../channels/using/profile-transactional-messages.md).
* Puoi utilizzare i blocchi di contenuto di **collegamento dell’annullamento all’abbonamento** in un messaggio transazionale di profilo. Consulta [Aggiunta di un blocco di contenuto](../../designing/using/personalization.md#adding-a-content-block).
* Le regole di affaticamento sono compatibili con i messaggi transazionali di profilo. Consulta [Regole di affaticamento](../../sending/using/fatigue-rules.md).

Gli elenchi di prodotti sono disponibili solo nei messaggi e-mail transazionali. Vedi [Utilizzo degli elenchi dei prodotti in un messaggio transazionale](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Autorizzazioni e branding {#permissions-and-branding}

Per quanto riguarda la gestione del [branding](../../administration/using/branding.md), la messaggistica transazionale offre una flessibilità inferiore rispetto a quella standard. Adobe consiglia di collegare tutti i brand utilizzati nei messaggi transazionali all’[unità organizzativa](../../administration/using/organizational-units.md) **[!UICONTROL All]**. Per ulteriori informazioni, consulta la spiegazione dettagliata qui di seguito.

Quando modifichi un messaggio transazionale, puoi collegarlo a un brand per applicare automaticamente alcuni parametri, ad esempio il nome o il logo del brand. L’opzione **[!UICONTROL Default brand]** è selezionata per impostazione predefinita nelle proprietà dei messaggi transazionali.

![](assets/message-center_branding.png)

Tutti gli oggetti (compreso il branding) utilizzati in un messaggio transazionale devono essere visibili dall’unità organizzativa **[!UICONTROL Message Center]**, il che significa che questi oggetti devono trovarsi nelle unità organizzative **[!UICONTROL Message Center]** o **[!UICONTROL All]**.

Tuttavia, se il brand selezionato nelle proprietà del messaggio è collegato a un’unità organizzativa diversa da **[!UICONTROL Message Center]** o **[!UICONTROL All]**, si verifica un errore ed è impossibile inviare il messaggio transazionale.

Pertanto, se desideri utilizzare il multi-branding nel contesto dei messaggi transazionali, dovresti collegare tutti i brand all’unità organizzativa **[!UICONTROL Message Center]** o all’unità organizzativa **[!UICONTROL All]**.

### Esportazione e importazione dei messaggi transazionali {#exporting-and-importing-transactional-messages}

* Per esportare un messaggio transazionale, devi includere la configurazione dell’evento corrispondente durante la [creazione dell’esportazione del pacchetto](../../automating/using/managing-packages.md#creating-a-package).
* Dopo che il messaggio transazionale viene [importato tramite un pacchetto](../../automating/using/managing-packages.md#importing-a-package), non viene visualizzato nel relativo elenco. Devi [pubblicare](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) la configurazione dell’evento per rendere disponibile il messaggio transazionale associato.

