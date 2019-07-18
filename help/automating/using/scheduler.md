---
title: Pianificatore
seo-title: Pianificatore
description: Pianificatore
seo-description: L'attività del pianificatore consente di pianificare quando un flusso di lavoro o un'attività viene avviata.
page-status-flag: never-activated
uuid: f 5 e 50 a 11-8 dc 9-4 d 98-9531-024 c 0 fb 3 f 7 da
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: esecuzione-attività
discoiquuid: 0 fb 16 cea -3941-404 f -899 c -33 f 81 ced 4 ed 5
context-tags: pianificazione, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Scheduler{#scheduler}

## Description {#description}

![](assets/scheduler.png)

The **[!UICONTROL Scheduler]** activity allows you to schedule when a workflow or an activity is started.

## Context of use {#context-of-use}

The **[!UICONTROL Scheduler]** activity should be considered as a scheduled start. The activity positioning rules within the chart are the same as for the **[!UICONTROL Start]** activity. Questa attività non deve avere una transizione in entrata.

When building your workflow, only use one **[!UICONTROL Scheduler]** activity per branch and remember to set a time zone. Altrimenti, verrà impostato sul fuso orario del server.

>[!CAUTION]
>
>The **[!UICONTROL Repetition frequency]** of the activity cannot be less than 10 minutes. Pertanto, non è possibile eseguire automaticamente un flusso di lavoro più di una volta ogni 10 minuti.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Scheduler]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: il flusso di lavoro viene eseguito una sola volta.
   * **[!UICONTROL Several times a day]**: il flusso di lavoro viene eseguito regolarmente più volte al giorno.
   * **[!UICONTROL Daily]**: il flusso di lavoro viene eseguito alla data e all'ora specificate una volta al giorno.
   * **[!UICONTROL Weekly]**: il flusso di lavoro viene eseguito a un momento specificato, una o più volte a settimana.
   * **[!UICONTROL Monthly]**: il flusso di lavoro viene eseguito a un momento specificato, una o più volte al mese.
   * **[!UICONTROL Yearly]**: il flusso di lavoro viene eseguito a un momento specificato, una o più volte all'anno.

1. Definite i dettagli di esecuzione in base alla frequenza selezionata. I campi di dettaglio possono variare a seconda della frequenza utilizzata (tempo, frequenza di ripetizione, giorni specificati, ecc.).

   >[!NOTE]
   >
   >**[!UICONTROL Repetition frequency]** Il campo consente di ridurre i tempi di attivazione del flusso di lavoro. For example, if you select a daily execution period and the repetition frequency is set at **2** (days), the workflow will be triggered every two days. Non può essere inferiore a 10 minuti. If the repetition frequency is set at **0** (also the default value), this option is not taken into account and the workflow will run according to the execution frequency specified.

1. Specifica quando scade l'esecuzione:

   * **[!UICONTROL Never]**: il flusso di lavoro verrà eseguito, in base alla frequenza specificata, senza alcun limite all'intervallo o al numero di iterazioni.
   * **[!UICONTROL After a certain number of iterations]**: il flusso di lavoro verrà eseguito in base alla frequenza specificata, fino al raggiungimento del limite **X** . The **[!UICONTROL Number of iterations]** will therefore need to be specified.
   * **[!UICONTROL On a specific date]**: il flusso di lavoro verrà eseguito in base alla frequenza specificata, fino a una data specifica. Sarà pertanto necessario specificare la scadenza di esecuzione.

1. In the **[!UICONTROL Execution options]** tab, set up the time zone for your scheduler in the **[!UICONTROL Time zone]** field. Questo consente di avviare il flusso di lavoro in un determinato fuso orario, in caso contrario il flusso di lavoro verrà eseguito nel fuso orario del server per impostazione predefinita.

   For more information on sending delivery depending on the recipient's time zone, refer to this [section](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) or this [example](../../automating/using/push-notification-delivery.md#sending-a-recurring-push-notification-with-a-workflow) of a recurring workflow.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example {#example}

Nell'esempio seguente, l'attività è configurata in modo da avviare il flusso di lavoro su base settimanale, ogni altro lunedì alle 7, per una durata non determinata.

![](assets/wkf_scheduler_example.png)

