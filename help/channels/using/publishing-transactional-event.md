---
solution: Campaign Standard
product: campaign
title: Configurazione della messaggistica transazionale
description: Scopri come configurare i messaggi transazionali.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: 9ad23468d3d1cf386d9558e6cd2344ea2316fc82
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 7%

---


# Pubblicazione di un evento transazionale {#publishing-transactional-event}

Al termine della [configurazione](../../channels/using/configuring-transactional-event.md), l&#39;evento è pronto per essere pubblicato. Di seguito sono descritti i passaggi per visualizzare in anteprima, pubblicare, annullare la pubblicazione ed eliminare un evento.

>[!IMPORTANT]
>
>La configurazione e la pubblicazione dell&#39;evento devono essere eseguite da un [amministratore](../../administration/using/users-management.md#functional-administrators).

In [questa sezione](../../channels/using/publishing-transactional-message.md) è disponibile un grafico che illustra l&#39;intero processo di pubblicazione dei messaggi transazionali, comprese le configurazioni dell&#39;evento per la pubblicazione e l&#39;annullamento della pubblicazione.

Al termine della pubblicazione:
* Il messaggio transazionale corrispondente viene creato automaticamente. Vedere [Modifica di messaggi transazionali](../../channels/using/editing-transactional-message.md).
* L&#39;API che verrà utilizzata dallo sviluppatore del sito Web viene distribuita e gli eventi transazionali possono ora essere inviati. Consultate Attivazione degli eventi integrata (../../channels/using/getting-started-with-transactional-msg.md#integration-event-trigger).

## Visualizzazione in anteprima e pubblicazione dell&#39;evento {#previewing-and-publishing-the-event}

Prima di poter utilizzare l’evento, dovete visualizzarlo in anteprima e pubblicarlo.

1. Fate clic sul pulsante **[!UICONTROL API preview]** per visualizzare una simulazione dell&#39;API REST che verrà utilizzata dallo sviluppatore del sito Web prima della pubblicazione.

   Una volta pubblicato l&#39;evento, questo pulsante consente anche di visualizzare un&#39;anteprima dell&#39;API in produzione. Consultate Attivazione degli eventi integrata (../../channels/using/getting-started-with-transactional-msg.md#integration-event-trigger).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >L&#39;API REST varia in base al canale selezionato e alla dimensione di targeting selezionata. Per ulteriori dettagli sulle diverse configurazioni, fare riferimento a [Configurazioni specifiche per gli eventi transazionali](../../channels/using/configuring-transactional-event.md#transactional-event-specific-configurations).

1. Fare clic su **[!UICONTROL Publish]** per avviare la pubblicazione.

   ![](assets/message-center_pub.png)

   L&#39;API che verrà utilizzata dallo sviluppatore del sito Web viene distribuita e gli eventi transazionali possono ora essere inviati.

1. Potete visualizzare i registri di pubblicazione nella scheda corrispondente.

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >Ogni volta che modificate l’evento, dovete fare di nuovo clic su **[!UICONTROL Publish]** per generare l’API REST aggiornata che verrà utilizzata dallo sviluppatore del sito Web.

   Una volta pubblicato l&#39;evento, viene automaticamente creato un [messaggio di transazione](../../channels/using/editing-transactional-message.md) collegato al nuovo evento.

1. Puoi accedere direttamente a questo messaggio transazionale tramite il collegamento situato nell’area a sinistra.

   ![](assets/message-center_messagegeneration.png)

   >[!NOTE]
   >
   >* Affinché l’evento possa attivare l’invio di un messaggio transazionale, è necessario modificare e pubblicare il messaggio appena creato. Vedere le sezioni [Modifica](../../channels/using/editing-transactional-message.md) e [Pubblicazione di un messaggio transazionale](../../channels/using/publishing-transactional-message.md).
      >
      >
   * È inoltre necessario [integrare questo evento di attivazione](../../channels/using/getting-started-with-transactional-msg.md#integrate-event-trigger) nel sito Web.


1. Una volta che  Adobe Campaign inizia a ricevere eventi relativi a questa configurazione di evento, potete fare clic sul collegamento **[!UICONTROL Latest transactional events]** nella sezione **[!UICONTROL History]** per accedere agli eventi più recenti inviati dal servizio di terze parti ed elaborati da  Adobe Campaign.

![](assets/message-center_latest-events.png)

Gli eventi (in formato JSON) sono elencati tra quelli più recenti e quelli meno recenti. Questo elenco consente di controllare dati quali il contenuto o lo stato di un evento, a scopo di controllo e debug.

## Annullamento della pubblicazione di un evento {#unpublishing-an-event}

Il pulsante **[!UICONTROL Unpublish]** consente di annullare la pubblicazione dell&#39;evento, che elimina dall&#39;API REST la risorsa corrispondente all&#39;evento creato in precedenza.

Adesso, anche se l’evento viene attivato nel sito web, i messaggi corrispondenti non saranno più inviati e pertanto non verranno memorizzati nel database.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Se hai già pubblicato il messaggio transazionale corrispondente, anche la pubblicazione dei messaggi transazionali viene annullata. Vedere [Annullamento della pubblicazione di un messaggio transazionale](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message).

Fate clic sul pulsante **[!UICONTROL Publish]** per generare una nuova API REST.

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on publishing, pausing and unpublishing a transactional message, see [this section](../../channels/using/publishing-transactional-message.md).-->

## Eliminazione di un evento {#deleting-an-event}

Dopo aver annullato la pubblicazione di un evento o se l’evento non è ancora stato pubblicato, potete eliminarlo dall’elenco di configurazione dell’evento. Per eseguire questa operazione:

1. Fai clic sul logo **[!UICONTROL Adobe Campaign]** nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Passate il mouse sulla configurazione dell&#39;evento desiderata e fate clic sul pulsante **[!UICONTROL Delete element]**.

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >Verificate che la configurazione dell&#39;evento disponga dello stato **[!UICONTROL Draft]**, altrimenti non potrete eliminarla. Lo stato **[!UICONTROL Draft]** si applica a un evento che non è ancora stato pubblicato o che è stato [non pubblicato](#unpublishing-an-event).

1. Fai clic sul pulsante **[!UICONTROL Confirm]**.

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>Eliminando una configurazione di evento che è stata pubblicata e già utilizzata, verranno eliminati anche i messaggi transazionali corrispondenti e i relativi registri di invio e tracciamento.
