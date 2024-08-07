---
title: Limitazioni della messaggistica transazionale
description: Scopri i consigli e le limitazioni principali relativi ai messaggi transazionali in Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: d6aaec6e-c718-46a2-88e8-7402970def1a
source-git-commit: 2d3ef53d5ea5603d90da169366be6ea516d96823
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 61%

---

# Best practice e limitazioni dei messaggi transazionali {#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

In questa sezione sono elencate le best practice e le limitazioni di cui dovresti essere a conoscenza prima di iniziare a creare messaggi transazionali.

<!--For more on transactional messages, including on how to configure and create them, see [Getting started with transactional messaging](../../channels/using/getting-started-with-transactional-msg.md).-->

## Autorizzazioni {#permissions}

Solo gli utenti con il ruolo [Amministrazione](../../administration/using/users-management.md#functional-administrators) possono configurare eventi transazionali e accedere ai messaggi transazionali.

## Configurazione e pubblicazione degli eventi {#design-and-publication}

Durante la configurazione e la pubblicazione degli eventi transazionali, non è possibile ripristinare alcuni dei passaggi da eseguire. Devi conoscere i seguenti limiti:

* I canali disponibili per i messaggi transazionali sono: **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** e **[!UICONTROL Push notification]**.
* Puoi utilizzare un solo canale per ogni configurazione dell’evento. Vedi [Creazione di un evento](../../channels/using/configuring-transactional-event.md#creating-an-event).
* Dopo la creazione dell’evento, non puoi più cambiare il canale. Pertanto, se un messaggio non viene inviato correttamente, devi progettare il meccanismo che consenta di inviarlo da un altro canale utilizzando un flusso di lavoro. Vedi [Dati e processi del flusso di lavoro](../../automating/using/get-started-workflows.md).
* Non puoi modificare la dimensione di targeting (**[!UICONTROL Real-time event]** o **[!UICONTROL Profile]**) dopo la creazione dell’evento. Vedi [Creazione di un evento](../../channels/using/configuring-transactional-event.md#creating-an-event).
* Non puoi ripristinare una pubblicazione, ma puoi annullare la pubblicazione di un evento: questa operazione rende inaccessibili l’evento e il messaggio transazionale associato. Vedi [Annullamento della pubblicazione di un evento](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
* L’unico messaggio transazionale associabile a un evento è il messaggio creato automaticamente durante la pubblicazione dell’evento. Vedi [Anteprima e pubblicazione dell’evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Numero di messaggi transazionali {#transactional-message-number}

Il numero di messaggi transazionali pubblicati può avere un impatto significativo sulla piattaforma. Per prestazioni ottimali, il numero di messaggi transazionali pubblicati deve rimanere inferiore a 100, altrimenti si può verificare un deterioramento delle prestazioni. Per questo motivo, annulla la pubblicazione o elimina eventuali messaggi transazionali non utilizzati per rispettare il guardrail di cui sopra. Consulta [Annullamento della pubblicazione di un messaggio sulle transazioni](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message) e [Eliminazione di un messaggio sulle transazioni](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message).

Per ottenere prestazioni ottimali, puoi anche annullare o eliminare la pubblicazione degli eventi non utilizzati. In effetti, l’annullamento della pubblicazione o l’eliminazione di un evento annullerà o eliminerà anche i messaggi transazionali corrispondenti e i relativi registri di invio e di tracciamento, se presenti. Vedere [Annullamento della pubblicazione di un evento](../../channels/using/publishing-transactional-event.md#unpublishing-an-event) e [Eliminazione di un evento](../../channels/using/publishing-transactional-event.md#deleting-an-event).

## Personalizzazione {#personalization}

La modalità di personalizzazione del contenuto di un messaggio dipende dal tipo di messaggio transazionale. Le specifiche sono elencate di seguito.

### Messaggi transazionali basati su eventi

* Le informazioni sulla personalizzazione provengono dai dati contenuti nell’evento. Vedi [Configurazione dei messaggi transazionali basati su eventi](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).
* **impossibile** utilizzare **[!UICONTROL Unsubscription link]** blocchi di contenuto in un messaggio transazionale di evento.
* La messaggistica transazionale basata su eventi dovrebbe utilizzare solo i dati presenti nell’evento inviato per definire il destinatario e la personalizzazione del contenuto del messaggio. Tuttavia, puoi arricchire il contenuto del messaggio transazionale utilizzando le informazioni contenute nel database di Adobe Campaign. Vedi [Arricchimento di un evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) e [Personalizzazione di un messaggio transazionale](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).
* Poiché i messaggi transazionali di evento non contengono informazioni sul profilo, non sono compatibili con le regole di affaticamento, anche nel caso di un arricchimento con profili.

### Messaggi transazionali basati su profili

* Le informazioni sulla personalizzazione possono provenire dai dati contenuti nell’evento o dal record del profilo riconciliato. Consulta [Configurazione dei messaggi transazionali basati su profili](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) e [Specificità dei messaggi transazionali basati su profili](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
* **puoi** utilizzare **[!UICONTROL Unsubscription link]** blocchi di contenuto in un messaggio transazionale di profilo. Consulta [Aggiunta di un blocco di contenuto](../../designing/using/personalization.md#adding-a-content-block).
* Le regole di affaticamento sono compatibili con i messaggi transazionali di profilo. Consulta [Regole di affaticamento](../../sending/using/fatigue-rules.md).

### Elenco prodotti

Gli elenchi di prodotti sono disponibili solo nei **messaggi e-mail** transazionali. Vedi [Utilizzo degli elenchi dei prodotti in un messaggio transazionale](../../designing/using/using-product-listings.md).

## Branding {#permissions-and-branding}

Per quanto riguarda la gestione del [branding](../../administration/using/branding.md), la messaggistica transazionale offre una flessibilità inferiore rispetto a quella standard. Adobe consiglia di collegare tutti i brand utilizzati nei messaggi transazionali all’[unità organizzativa](../../administration/using/organizational-units.md) **[!UICONTROL All]**. Per ulteriori informazioni, consulta la spiegazione dettagliata qui di seguito.

Quando modifichi un messaggio transazionale, puoi collegarlo a un brand per applicare automaticamente alcuni parametri, ad esempio il nome o il logo del brand. L’opzione **[!UICONTROL Default brand]** è selezionata per impostazione predefinita nelle proprietà dei messaggi transazionali.

![](assets/message-center_branding.png)

Tutti gli oggetti (compreso il branding) utilizzati in un messaggio transazionale devono essere visibili dall’unità organizzativa **[!UICONTROL Message Center]**, il che significa che questi oggetti devono trovarsi nelle unità organizzative **[!UICONTROL Message Center]** o **[!UICONTROL All]**.

Tuttavia, se il brand selezionato nelle proprietà del messaggio è collegato a un’unità organizzativa diversa da **[!UICONTROL Message Center]** o **[!UICONTROL All]**, si verifica un errore ed è impossibile inviare il messaggio transazionale.

Pertanto, se desideri utilizzare il multi-branding nel contesto dei messaggi transazionali, dovresti collegare tutti i brand all’unità organizzativa **[!UICONTROL Message Center]** o all’unità organizzativa **[!UICONTROL All]**.

## Esportazione e importazione di messaggi transazionali {#exporting-and-importing-transactional-messages}

* Per esportare un messaggio transazionale, devi includere la configurazione dell’evento corrispondente durante la [creazione dell’esportazione del pacchetto](../../automating/using/managing-packages.md#creating-a-package).
* Dopo che il messaggio transazionale viene [importato tramite un pacchetto](../../automating/using/managing-packages.md#importing-a-package), non viene visualizzato nel relativo elenco. Devi [pubblicare](../../channels/using/publishing-transactional-event.md) la configurazione dell’evento per rendere disponibile il messaggio transazionale associato.
