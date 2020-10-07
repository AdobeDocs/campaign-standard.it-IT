---
title: Invio di una notifica push ricorrente con un flusso di lavoro
description: In questo esempio, una notifica push personalizzata viene inviata ogni primo giorno del mese alle 20:00 agli abbonati dell'applicazione mobile a seconda dei fusi orari.
page-status-flag: never-activated
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---


# Invio di una notifica push ricorrente con un flusso di lavoro {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

In questo esempio, una notifica push personalizzata viene inviata ogni primo giorno del mese alle 20:00 agli abbonati dell&#39;applicazione mobile a seconda dei fusi orari.

Per generare il flusso di lavoro, effettuate le seguenti operazioni:

1. L&#39;attività [Pianificatore](../../automating/using/scheduler.md) consente di avviare i giorni del flusso di lavoro prima dell&#39;inizio della consegna per poter inviare la notifica a ogni abbonato alle 20 in un dato fuso orario:

   * In the **[!UICONTROL Execution frequency]** field, select Monthly.
   * Selezionare le 20:00 nel **[!UICONTROL Time]** campo.
   * Scegliere il giorno in cui verrà inviata la consegna ogni mese.
   * Selezionate una data di inizio per il flusso di lavoro, almeno un giorno prima dell’inizio della consegna. In caso contrario, alcuni destinatari potrebbero ricevere il messaggio un giorno dopo se l’ora selezionata è già passata nei loro fusi orari.
   * Nella **[!UICONTROL Execution options]** scheda, selezionare il fuso orario in cui il flusso di lavoro verrà avviato nel **[!UICONTROL Time zone]** campo. Qui, ad esempio, il flusso di lavoro inizia alle 20:00 ora del Pacifico, una settimana prima del primo giorno del mese, per consentire la creazione di un certo numero di consegne per tutti i fusi orari applicabili.

   >[!NOTE]
   >
   >Per impostazione predefinita, il fuso orario selezionato è quello definito nelle proprietà del flusso di lavoro (vedi [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. L&#39;attività [Query](../../automating/using/query.md) consente di eseguire il targeting dei clienti VIP di età compresa tra i 20 e i 30 anni che hanno effettuato l&#39;iscrizione all&#39;applicazione mobile e che non hanno aperto l&#39;e-mail inviata:

   * Selezionate un&#39;audience (i clienti VIP) e filtratene l&#39;età.
   * Trascinate le **iscrizioni a un elemento dell&#39;applicazione** nell&#39;area di lavoro. Selezionate **Esiste** e selezionate l’applicazione mobile da usare.
   * Selezionate l’e-mail inviata ai clienti.
   * Trascinate e rilasciate l’elemento dei registri di **consegna (file di registro)** nell’area di lavoro e selezionate **Esiste** per indirizzare tutti i clienti che hanno ricevuto l’e-mail.
   * Trascinate l’elemento dei registri di **tracciamento (tracciamento)** nell’area di lavoro e selezionate **Non esiste** per indirizzare tutti i clienti che non hanno aperto l’e-mail.

      ![](assets/wkf_push_example_2.png)

1. L&#39;attività di consegna [delle notifiche](../../automating/using/push-notification-delivery.md) push consente di immettere il contenuto del messaggio e selezionare i campi di personalizzazione che si desidera utilizzare:

   * Selezionate l’ **[!UICONTROL Recurring notification]** opzione.
   * Definite il contenuto della notifica push. For more information on push notification content, refer to this [section](../../channels/using/preparing-and-sending-a-push-notification.md).
   * In the **[!UICONTROL Schedule]** block, select **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Qui abbiamo scelto il **[!UICONTROL Time zone of the contact date]** Pacifico come nel flusso di lavoro **[!UICONTROL Scheduler]**.
   * Nel campo **[!UICONTROL Optimize the sending time per recipient]** seleziona **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Fate clic sul **[!UICONTROL Start]** pulsante per avviare il flusso di lavoro periodico.

   ![](assets/wkf_push_example_3.png)

Il flusso di lavoro è ora in esecuzione. Comincerà dalla data di inizio scelta delle **[!UICONTROL Scheduler]** 20:00 ora del Pacifico, il push periodico verrà inviato ogni primo giorno del mese alle 20:00 a seconda del fuso orario dei clienti.
