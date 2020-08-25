---
title: Limitazioni della messaggistica transazionale
description: Scopri le principali limitazioni e raccomandazioni relative ai messaggi transazionali in  Adobe Campaign Standard.
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
source-git-commit: 6c768132a297d324f6aec87c215222b3587091c6
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 89%

---


# Limitazioni della messaggistica transazionale {#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

La sezione seguente elenca i limiti di cui dovreste essere consapevoli prima di iniziare a creare messaggi transazionali.

Per ulteriori informazioni sui messaggi transazionali, ad esempio su come configurarli e crearli, consulta [Guida introduttiva ai messaggi](../../channels/using/getting-started-with-transactional-msg.md)transazionali.

>[!IMPORTANT]
>
>Per accedere ai messaggi transazionali, devi disporre di diritti di amministrazione.

## Progettazione e pubblicazione {#design-and-publication}

Durante la progettazione e la pubblicazione dei messaggi transazionali, non è possibile ripristinare alcuni dei passaggi da eseguire. Devi conoscere i seguenti limiti:

* Puoi utilizzare un solo canale per ogni configurazione dell’evento. Vedi [Creazione di un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Dopo la creazione dell’evento, non puoi più cambiare il canale. Pertanto, se un messaggio non viene inviato correttamente, devi progettare il meccanismo che consenta di inviarlo da un altro canale utilizzando un flusso di lavoro. Vedi [Dati e processi del flusso di lavoro](../../automating/using/get-started-workflows.md).
* Non puoi modificare la dimensione di targeting (**[!UICONTROL Real-time event]** o **[!UICONTROL Profile]**) dopo la creazione dell’evento. Vedi [Creazione di un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Non puoi ripristinare una pubblicazione, ma puoi annullare la pubblicazione di un evento: questa operazione rende inaccessibili l’evento e il messaggio transazionale associato. Vedi [Annullamento della pubblicazione di un evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* L’unico messaggio transazionale associabile a un evento è il messaggio creato automaticamente durante la pubblicazione dell’evento. Vedi [Anteprima e pubblicazione dell’evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

## Personalizzazione {#personalization}

La modalità di personalizzazione del contenuto di un messaggio dipende dal tipo di messaggio transazionale. Le specifiche sono elencate di seguito.

### Messaggi transazionali basati su eventi

* Le informazioni sulla personalizzazione provengono dai dati contenuti nell’evento. Vedi [Messaggi transazionali di evento](../../channels/using/event-transactional-messages.md).
* You **cannot** use **[!UICONTROL Unsubscription link]** content blocks in an event transactional message.
* La messaggistica transazionale basata su eventi dovrebbe utilizzare solo i dati presenti nell’evento inviato per definire il destinatario e la personalizzazione del contenuto del messaggio. Tuttavia, puoi arricchire il contenuto del messaggio transazionale utilizzando le informazioni contenute nel database di Adobe Campaign. Consulta [Arricchimento del contenuto dei messaggi transazionali](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Poiché i messaggi transazionali di evento non contengono informazioni sul profilo, non sono compatibili con le regole di affaticamento, nemmeno nel caso di un arricchimento tramite profili. Consulta [Regole di affaticamento](../../sending/using/fatigue-rules.md).

### Messaggi transazionali basati su profili

* Le informazioni sulla personalizzazione possono provenire dai dati contenuti nell’evento o dal record del profilo riconciliato. Vedi [Messaggi transazionali di profilo](../../channels/using/profile-transactional-messages.md).
* You **can** use **[!UICONTROL Unsubscription link]** content blocks in a profile transactional message. Consulta [Aggiunta di un blocco di contenuto](../../designing/using/personalization.md#adding-a-content-block).
* Le regole di affaticamento sono compatibili con i messaggi transazionali di profilo. Consulta [Regole di affaticamento](../../sending/using/fatigue-rules.md).

Gli elenchi di prodotti sono disponibili solo nei messaggi e-mail transazionali. Vedi [Utilizzo degli elenchi dei prodotti in un messaggio transazionale](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

## Autorizzazioni e branding {#permissions-and-branding}

Per quanto riguarda la gestione del [branding](../../administration/using/branding.md), la messaggistica transazionale offre una flessibilità inferiore rispetto a quella standard. Adobe consiglia di collegare tutti i brand utilizzati nei messaggi transazionali all’[unità organizzativa](../../administration/using/organizational-units.md) **[!UICONTROL All]**. Per ulteriori informazioni, consulta la spiegazione dettagliata qui di seguito.

Quando modifichi un messaggio transazionale, puoi collegarlo a un brand per applicare automaticamente alcuni parametri, ad esempio il nome o il logo del brand. L’opzione **[!UICONTROL Default brand]** è selezionata per impostazione predefinita nelle proprietà dei messaggi transazionali.

![](assets/message-center_branding.png)

Tutti gli oggetti (compreso il branding) utilizzati in un messaggio transazionale devono essere visibili dall’unità organizzativa **[!UICONTROL Message Center]**, il che significa che questi oggetti devono trovarsi nelle unità organizzative **[!UICONTROL Message Center]** o **[!UICONTROL All]**.

Tuttavia, se il brand selezionato nelle proprietà del messaggio è collegato a un’unità organizzativa diversa da **[!UICONTROL Message Center]** o **[!UICONTROL All]**, si verifica un errore ed è impossibile inviare il messaggio transazionale.

Pertanto, se desideri utilizzare il multi-branding nel contesto dei messaggi transazionali, dovresti collegare tutti i brand all’unità organizzativa **[!UICONTROL Message Center]** o all’unità organizzativa **[!UICONTROL All]**.

## Esportazione e importazione dei messaggi transazionali {#exporting-and-importing-transactional-messages}

* Per esportare un messaggio transazionale, devi includere la configurazione dell’evento corrispondente durante la [creazione dell’esportazione del pacchetto](../../automating/using/managing-packages.md#creating-a-package).
* Dopo che il messaggio transazionale viene [importato tramite un pacchetto](../../automating/using/managing-packages.md#importing-a-package), non viene visualizzato nel relativo elenco. Devi [pubblicare](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) la configurazione dell’evento per rendere disponibile il messaggio transazionale associato.
