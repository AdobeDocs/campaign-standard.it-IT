---
title: Invio di una notifica push ricorrente con un flusso di lavoro
description: In questo esempio, una notifica push personalizzata viene inviata ogni primo giorno del mese alle 20:00 agli abbonati della tua app mobile a seconda del loro fuso orario.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 4%

---

# Invio di una notifica push ricorrente con un flusso di lavoro {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

In questo esempio, una notifica push personalizzata viene inviata ogni primo giorno del mese alle 20:00 agli abbonati della tua app mobile a seconda del loro fuso orario.

Per creare il flusso di lavoro, segui questi passaggi:

1. La [Scheduler](../../automating/using/scheduler.md) l’attività ti consente di avviare i giorni del flusso di lavoro prima dell’inizio della consegna per poter inviare la notifica a ogni abbonato alle 20 in un dato fuso orario:

   * In **[!UICONTROL Execution frequency]** selezionare Mensile.
   * Seleziona le 20 in **[!UICONTROL Time]** campo .
   * Scegli il giorno in cui la consegna verrà inviata ogni mese.
   * Seleziona una data di inizio per il flusso di lavoro, almeno un giorno prima dell’inizio della consegna. In caso contrario, alcuni destinatari potrebbero ricevere il messaggio un giorno dopo se l’ora selezionata è già passata nei rispettivi fusi orari.
   * In **[!UICONTROL Execution options]** , seleziona il fuso orario in cui verrà avviato il flusso di lavoro nella **[!UICONTROL Time zone]** campo . In questo caso, ad esempio, il flusso di lavoro inizia alle 20.00 ora del Pacifico, una settimana prima del primo giorno del mese, per consentire la creazione di consegne per tutti i fusi orari applicabili.

   >[!NOTE]
   >
   >Per impostazione predefinita, il fuso orario selezionato è quello definito nelle proprietà del flusso di lavoro (vedi [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. La [Query](../../automating/using/query.md) l’attività ti consente di rivolgerti ai clienti VIP di età compresa tra i 20 e i 30 anni che si sono abbonati alla tua app mobile e che non hanno aperto l’e-mail inviata:

   * Seleziona un pubblico (i tuoi clienti VIP) e applica un filtro in base alla loro età.
   * Trascina e rilascia la **Abbonamenti a un’applicazione** nell&#39;area di lavoro. Seleziona **Esiste** e seleziona l’app mobile da utilizzare.
   * Seleziona l’e-mail inviata ai clienti.
   * Trascina e rilascia la **Log di consegna (registri)** nell’area di lavoro e seleziona **Esiste** per eseguire il targeting di tutti i clienti che hanno ricevuto l’e-mail.
   * Trascina e rilascia la **Registri di tracciamento (tracciamento)** nell’area di lavoro e seleziona **Non esiste** per eseguire il targeting di tutti i clienti che non hanno aperto l’e-mail.

      ![](assets/wkf_push_example_2.png)

1. La [Consegna notifiche push](../../automating/using/push-notification-delivery.md) activity ti consente di inserire il contenuto del messaggio e selezionare i campi di personalizzazione che desideri utilizzare:

   * Seleziona la **[!UICONTROL Recurring notification]** opzione .
   * Definisci il contenuto della notifica push. Per ulteriori informazioni sul contenuto delle notifiche push, consulta questo [sezione](../../channels/using/preparing-and-sending-a-push-notification.md).
   * In **[!UICONTROL Schedule]** blocco, seleziona **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Qui abbiamo scelto il **[!UICONTROL Time zone of the contact date]** Pacifico come nel flusso di lavoro **[!UICONTROL Scheduler]**.
   * Nel campo **[!UICONTROL Optimize the sending time per recipient]** seleziona **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Fai clic sul pulsante **[!UICONTROL Start]** per avviare il flusso di lavoro ricorrente.

   ![](assets/wkf_push_example_3.png)

Il flusso di lavoro è ora in esecuzione. Inizierà alla data di inizio scelta del **[!UICONTROL Scheduler]** alle 20 ora del Pacifico, il push ricorrente verrà quindi inviato ogni primo giorno del mese alle 20 (ora del Pacifico), a seconda del fuso orario dei clienti.
