---
solution: Campaign Standard
product: campaign
title: Invio di una notifica push ricorrente con un flusso di lavoro
description: In questo esempio, una notifica push personalizzata viene inviata ogni primo giorno del mese alle 20:00 agli abbonati della tua app mobile a seconda del loro fuso orario.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 4%

---


# Invio di una notifica push ricorrente con un flusso di lavoro {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

In questo esempio, una notifica push personalizzata viene inviata ogni primo giorno del mese alle 20:00 agli abbonati della tua app mobile a seconda del loro fuso orario.

Per creare il flusso di lavoro, segui questi passaggi:

1. L’attività [Scheduler](../../automating/using/scheduler.md) ti consente di avviare il flusso di lavoro giorni prima dell’inizio della consegna per poter inviare la notifica a ogni abbonato alle 20 in un dato fuso orario:

   * Nel campo **[!UICONTROL Execution frequency]**, selezionare Mensile.
   * Selezionare le 20 nel campo **[!UICONTROL Time]**.
   * Scegli il giorno in cui la consegna verrà inviata ogni mese.
   * Seleziona una data di inizio per il flusso di lavoro, almeno un giorno prima dell’inizio della consegna. In caso contrario, alcuni destinatari potrebbero ricevere il messaggio un giorno dopo se l’ora selezionata è già passata nei rispettivi fusi orari.
   * Nella scheda **[!UICONTROL Execution options]** , seleziona il fuso orario in cui verrà avviato il flusso di lavoro nel campo **[!UICONTROL Time zone]** . In questo caso, ad esempio, il flusso di lavoro inizia alle 20.00 ora del Pacifico, una settimana prima del primo giorno del mese, per consentire la creazione di consegne per tutti i fusi orari applicabili.

   >[!NOTE]
   >
   >Per impostazione predefinita, il fuso orario selezionato è quello definito nelle proprietà del flusso di lavoro (vedi [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. L’attività [Query](../../automating/using/query.md) ti consente di eseguire il targeting dei clienti VIP di età compresa tra i 20 e i 30 anni che si sono abbonati alla tua app mobile e che non hanno aperto l’e-mail inviata:

   * Seleziona un pubblico (i tuoi clienti VIP) e applica un filtro in base alla loro età.
   * Trascina nell’area di lavoro l’elemento **Sottoscrizioni a un’applicazione** . Seleziona **Esiste** e seleziona l’app mobile da utilizzare.
   * Seleziona l’e-mail inviata ai clienti.
   * Trascina e rilascia l’elemento **Log di consegna (log)** nell’area di lavoro e seleziona **Esiste** per eseguire il targeting per tutti i clienti che hanno ricevuto l’e-mail.
   * Trascina e rilascia l’elemento **Registri di tracciamento (tracciamento)** nell’area di lavoro e seleziona **Non esiste** per eseguire il targeting di tutti i clienti che non hanno aperto l’e-mail.

      ![](assets/wkf_push_example_2.png)

1. L’attività [Invio di notifiche push](../../automating/using/push-notification-delivery.md) ti consente di inserire il contenuto del messaggio e di selezionare i campi di personalizzazione che desideri utilizzare:

   * Selezionare l&#39;opzione **[!UICONTROL Recurring notification]**.
   * Definisci il contenuto della notifica push. Per ulteriori informazioni sul contenuto delle notifiche push, consulta questa [sezione](../../channels/using/preparing-and-sending-a-push-notification.md).
   * Nel blocco **[!UICONTROL Schedule]**, seleziona **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. In questo caso, abbiamo scelto il **[!UICONTROL Time zone of the contact date]** Pacifico come nel flusso di lavoro **[!UICONTROL Scheduler]**.
   * Nel campo **[!UICONTROL Optimize the sending time per recipient]** seleziona **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Fai clic sul pulsante **[!UICONTROL Start]** per avviare il flusso di lavoro ricorrente.

   ![](assets/wkf_push_example_3.png)

Il flusso di lavoro è ora in esecuzione. Il push ricorrente verrà quindi inviato ogni primo giorno del mese alle 20:00 a seconda del fuso orario del cliente.**[!UICONTROL Scheduler]**
