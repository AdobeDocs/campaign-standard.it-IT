---
title: Invio di una notifica push ricorrente con un flusso di lavoro
description: In questo esempio, viene inviata una notifica push personalizzata ogni primo giorno del mese alle 20 agli abbonati della tua app mobile in base al loro fuso orario
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5e6034c-3673-4069-ac0b-49c7ad07259d
source-git-commit: 0ab950d4124bf459ba889e2f1c2954210dd350e0
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 4%

---

# Invio di una notifica push ricorrente con un flusso di lavoro {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

In questo esempio, viene inviata una notifica push personalizzata ogni primo giorno del mese alle 20 agli abbonati della tua app mobile in base al loro fuso orario.

Per creare il flusso di lavoro, effettua le seguenti operazioni:

1. Il [Scheduler](../../automating/using/scheduler.md) attività ti consente di avviare il flusso di lavoro giorni prima dell’inizio della consegna per poter inviare la notifica a ogni abbonato alle 20 in qualsiasi fuso orario:

   * In **[!UICONTROL Execution frequency]** , selezionare Mensile.
   * Selezionare le 20.00 in **[!UICONTROL Time]** campo.
   * Scegli il giorno in cui la consegna verrà inviata ogni mese.
   * Seleziona una data di inizio per il flusso di lavoro, almeno un giorno prima dell’inizio della consegna. In caso contrario, alcuni destinatari potrebbero ricevere il messaggio un giorno dopo se l’ora selezionata è già trascorsa nei rispettivi fusi orari.
   * In **[!UICONTROL Execution options]** , seleziona il fuso orario in cui inizierà il flusso di lavoro nel **[!UICONTROL Time zone]** campo. In questo caso, ad esempio, il flusso di lavoro inizierà alle 20 (ora del Pacifico), una settimana prima del primo giorno del mese, in modo da consentire la creazione delle consegne per tutti i fusi orari applicabili.

   >[!NOTE]
   >
   >Per impostazione predefinita, il fuso orario selezionato è quello definito nelle proprietà del flusso di lavoro (vedi [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. Il [Query](../../automating/using/query.md) L’attività ti consente di eseguire il targeting dei clienti VIP di età compresa tra i 20 e i 30 anni che si sono abbonati alla tua app mobile e che non hanno aperto l’e-mail inviata:

   * Seleziona un pubblico (i clienti VIP) e applica un filtro in base alla loro età.
   * Trascina la **Abbonamenti a un’applicazione** nel workspace. Seleziona **Esiste** e seleziona l’app mobile che desideri utilizzare.
   * Seleziona l’e-mail inviata ai clienti.
   * Trascina la **Registri di consegna (registri)** nell&#39;area di lavoro e selezionare **Esiste** per eseguire il targeting per tutti i clienti che hanno ricevuto l’e-mail.
   * Trascina la **Registri di tracciamento (tracciamento)** nell&#39;area di lavoro e selezionare **Non esiste** per eseguire il targeting per tutti i clienti che non hanno aperto l’e-mail.

     ![](assets/wkf_push_example_2.png)

1. Il [Consegna notifiche push](../../automating/using/push-notification-delivery.md) attività ti consente di inserire il contenuto del messaggio e di selezionare i campi di personalizzazione che desideri utilizzare:

   * Seleziona la **[!UICONTROL Recurring notification]** opzione.
   * Definisci il contenuto della notifica push. Per ulteriori informazioni sul contenuto delle notifiche push, consulta questa [sezione](../../channels/using/preparing-and-sending-a-push-notification.md).
   * In **[!UICONTROL Schedule]** blocco, seleziona **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. In questo caso, abbiamo scelto **[!UICONTROL Time zone of the contact date]** Pacifico come nel flusso di lavoro **[!UICONTROL Scheduler]**.
   * Nel campo **[!UICONTROL Optimize the sending time per recipient]** seleziona **[!UICONTROL Send at the recipient's time zone]**.

     ![](assets/wkf_push_example_4.png)

1. Fai clic su **[!UICONTROL Start]** per avviare il flusso di lavoro ricorrente.

   ![](assets/wkf_push_example_3.png)

Il flusso di lavoro è in esecuzione. Inizierà alla data di inizio scelta del **[!UICONTROL Scheduler]** alle 20:00 (ora del Pacifico), il messaggio push ricorrente verrà inviato ogni primo giorno del mese alle 20:00, in base al fuso orario del cliente.
