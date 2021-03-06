---
title: Pubblicazione di un evento transazionale
description: Scopri come visualizzare in anteprima, pubblicare, annullare la pubblicazione ed eliminare una configurazione di un evento transazionale.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 6bcd8dcd-d710-4ca3-937d-bf4339f36069
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 6%

---

# Pubblicazione di un evento transazionale {#publishing-transactional-event}

Una volta [configurazione](../../channels/using/configuring-transactional-event.md) l’evento è pronto per essere pubblicato. Di seguito sono descritti i passaggi per visualizzare in anteprima, pubblicare, annullare la pubblicazione ed eliminare un evento.

>[!IMPORTANT]
>
>Solo [Amministratori funzionali](../../administration/using/users-management.md#functional-administrators) <!--being part of the **[!UICONTROL All]** [organizational unit](../../administration/using/organizational-units.md) -->dispone dei diritti appropriati per pubblicare le configurazioni dell’evento.

È disponibile un grafico che illustra l’intero processo di pubblicazione dei messaggi transazionali, incluse le configurazioni di pubblicazione e annullamento della pubblicazione degli eventi, in [questa sezione](../../channels/using/publishing-transactional-message.md).

Al termine della pubblicazione:
* Il messaggio transazionale corrispondente viene creato automaticamente. Vedi [Modifica dei messaggi transazionali](../../channels/using/editing-transactional-message.md).
* L’API che verrà utilizzata dallo sviluppatore del sito web viene distribuita e gli eventi transazionali possono ora essere inviati. Vedi [Integrare l’attivazione dell’evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

## Anteprima e pubblicazione di un evento {#previewing-and-publishing-the-event}

Prima di poter utilizzare l’evento, devi visualizzarlo in anteprima e pubblicarlo.

1. Fai clic sul pulsante **[!UICONTROL API preview]** per visualizzare una simulazione dell’API REST che verrà utilizzata dallo sviluppatore del sito web prima della sua pubblicazione.

   Una volta pubblicato l’evento, questo pulsante ti consente anche di visualizzare un’anteprima dell’API in produzione. Vedi [Integrare l’attivazione dell’evento](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >L’API REST varia a seconda del canale selezionato e della dimensione di targeting selezionata. Per ulteriori dettagli sulle varie configurazioni, consulta [questa sezione](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations).

1. Fai clic su **[!UICONTROL Publish]** per avviare la pubblicazione.

   ![](assets/message-center_pub.png)

   L’API che verrà utilizzata dallo sviluppatore del sito web viene distribuita e gli eventi transazionali possono ora essere inviati.

1. Puoi visualizzare i registri di pubblicazione nella scheda corrispondente.

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >Ogni volta che modifichi l’evento, devi fare clic su **[!UICONTROL Publish]** per generare nuovamente l’API REST aggiornata che verrà utilizzata dallo sviluppatore del sito web.

   Una volta pubblicato l’evento, un [messaggio sulle transazioni](../../channels/using/editing-transactional-message.md) collegato al nuovo evento viene creato automaticamente.

1. Puoi accedere direttamente a questo messaggio sulle transazioni tramite il collegamento situato nell’area a sinistra.

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >Affinché l’evento attivi l’invio di un messaggio sulle transazioni, devi modificare e pubblicare il messaggio appena creato. Vedi [Modifica](../../channels/using/editing-transactional-message.md) e [Pubblicazione di un messaggio sulle transazioni](../../channels/using/publishing-transactional-message.md) sezioni. Dovete anche [integrare questo evento trigger](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) nel sito web.

1. Una volta che Adobe Campaign inizia a ricevere gli eventi relativi a questa configurazione di evento, puoi fare clic sul pulsante **[!UICONTROL Latest transactional events]** link sotto **[!UICONTROL History]** per accedere agli eventi più recenti inviati dal servizio di terze parti ed elaborati da Adobe Campaign.

![](assets/message-center_latest-events.png)

Gli eventi (in formato JSON) sono elencati dal più recente al meno recente. Questo elenco consente di controllare i dati, ad esempio il contenuto o lo stato di un evento, a scopo di controllo e debug.

## Annullamento della pubblicazione di un evento {#unpublishing-an-event}

La **[!UICONTROL Unpublish]** consente di annullare la pubblicazione dell’evento, che elimina dall’API REST la risorsa corrispondente all’evento creato in precedenza.

Adesso, anche se l’evento viene attivato nel sito web, i messaggi corrispondenti non saranno più inviati e pertanto non verranno memorizzati nel database.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Se hai già pubblicato il messaggio transazionale corrispondente, anche la pubblicazione del messaggio transazionale viene annullata. Vedi [Annullamento della pubblicazione di un messaggio sulle transazioni](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message).

Fai clic sul pulsante **[!UICONTROL Publish]** per generare una nuova API REST.

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## Eliminazione di un evento {#deleting-an-event}

Una volta che un evento è stato annullato o se non è ancora stato pubblicato, puoi eliminarlo dall’elenco di configurazione dell’evento. Per eseguire questa operazione:

1. Fai clic sul pulsante **Adobe** , nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Passa il puntatore del mouse sulla configurazione dell’evento desiderata e seleziona la **[!UICONTROL Delete element]** pulsante .

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >Assicurati che la configurazione dell’evento abbia **[!UICONTROL Draft]** altrimenti non potrai eliminarlo. La **[!UICONTROL Draft]** lo stato si applica a un evento non ancora pubblicato o che è stato [non pubblicato](#unpublishing-an-event).

1. Fai clic sul pulsante **[!UICONTROL Confirm]**.

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>L’eliminazione di una configurazione di evento pubblicata e già utilizzata comporta anche l’eliminazione dei messaggi transazionali corrispondenti e dei relativi registri di invio e tracciamento.
