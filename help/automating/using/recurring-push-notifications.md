---
solution: Campaign Standard
product: campaign
title: Invio di una notifica push ricorrente con un flusso di lavoro
description: In questo esempio, una notifica push personalizzata viene inviata ogni primo giorno del mese alle 20:00 agli abbonati dell'applicazione mobile a seconda dei fusi orari.
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Invio di una notifica push ricorrente con un flusso di lavoro {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

In questo esempio, una notifica push personalizzata viene inviata ogni primo giorno del mese alle 20:00 agli abbonati dell&#39;applicazione mobile a seconda dei fusi orari.

Per generare il flusso di lavoro, effettuate le seguenti operazioni:

1. L&#39;attività [Scheduler](../../automating/using/scheduler.md) consente di avviare i giorni del flusso di lavoro prima dell&#39;inizio della consegna per poter inviare la notifica a ogni utente iscritto alle 20:00 in un dato fuso orario:

   * Nel campo **[!UICONTROL Execution frequency]**, selezionare Mensile.
   * Selezionare 8 pm nel campo **[!UICONTROL Time]**.
   * Scegliere il giorno in cui verrà inviata la consegna ogni mese.
   * Selezionate una data di inizio per il flusso di lavoro, almeno un giorno prima dell’inizio della consegna. In caso contrario, alcuni destinatari potrebbero ricevere il messaggio un giorno dopo se l’ora selezionata è già passata nei loro fusi orari.
   * Nella scheda **[!UICONTROL Execution options]**, selezionare il fuso orario in cui il flusso di lavoro verrà avviato nel campo **[!UICONTROL Time zone]**. Qui, ad esempio, il flusso di lavoro inizia alle 20:00 ora del Pacifico, una settimana prima del primo giorno del mese, per consentire la creazione di un certo numero di consegne per tutti i fusi orari applicabili.

   >[!NOTE]
   >
   >Per impostazione predefinita, il fuso orario selezionato è quello definito nelle proprietà del flusso di lavoro (vedi [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. L&#39;attività [Query](../../automating/using/query.md) consente di eseguire il targeting dei clienti VIP di età compresa tra i 20 e i 30 anni, che si sono abbonati all&#39;applicazione mobile e che non hanno aperto l&#39;e-mail inviata:

   * Selezionate un&#39;audience (i clienti VIP) e filtratene l&#39;età.
   * Trascinate l&#39;elemento **Iscrizioni su un elemento applicazione** nell&#39;area di lavoro. Selezionare **Exists** e selezionare l&#39;applicazione mobile che si desidera utilizzare.
   * Selezionate l’e-mail inviata ai clienti.
   * Trascinare l&#39;elemento **Registri di consegna (registri)** nell&#39;area di lavoro e selezionare **Esiste** per eseguire il targeting di tutti i clienti che hanno ricevuto l&#39;e-mail.
   * Trascinare l&#39;elemento **Registri di tracciamento (tracciamento)** nell&#39;area di lavoro e selezionare **Non esiste** per indirizzare tutti i clienti che non hanno aperto l&#39;e-mail.

      ![](assets/wkf_push_example_2.png)

1. L&#39;attività [Distribuzione delle notifiche push](../../automating/using/push-notification-delivery.md) consente di inserire il contenuto del messaggio e di selezionare i campi di personalizzazione che si desidera utilizzare:

   * Selezionare l&#39;opzione **[!UICONTROL Recurring notification]**.
   * Definite il contenuto della notifica push. Per ulteriori informazioni sul contenuto delle notifiche push, consultate questa [sezione](../../channels/using/preparing-and-sending-a-push-notification.md).
   * Nel blocco **[!UICONTROL Schedule]**, selezionare **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Qui abbiamo scelto il **[!UICONTROL Time zone of the contact date]** Pacifico come nel flusso di lavoro **[!UICONTROL Scheduler]**.
   * Nel campo **[!UICONTROL Optimize the sending time per recipient]** seleziona **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Fare clic sul pulsante **[!UICONTROL Start]** per avviare il flusso di lavoro periodico.

   ![](assets/wkf_push_example_3.png)

Il flusso di lavoro è ora in esecuzione. Inizierà dalla data di inizio scelta del **[!UICONTROL Scheduler]** alle 20.00 ora del Pacifico, il push periodico verrà inviato ogni primo giorno del mese alle 20.00 a seconda del fuso orario dei clienti.
