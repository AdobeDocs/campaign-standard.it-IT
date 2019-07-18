---
title: Segnale esterno
seo-title: Segnale esterno
description: Segnale esterno
seo-description: L'attività Segnale esterno attiva un flusso di lavoro quando alcune condizioni vengono soddisfatte correttamente in un altro flusso di lavoro.
page-status-flag: never-activated
uuid: 884 b 6 daf-bfd 9-440 b -8336-004 b 80 c 76 def
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: esecuzione-attività
discoiquuid: 911 c 71 b 5-da 8 b -4916-b 645-13 bba 6 d 21715
context-tags: segnale, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# External signal{#external-signal}

## Description {#description}

![](assets/signal.png)

The **[!UICONTROL External signal]** activity triggers a workflow when some conditions are successfully met in another workflow or from a REST API call.

## Context of use {#context-of-use}

The **[!UICONTROL External signal]** activity is used to organize and orchestrate different processes that are part of the same customer journey into different workflows. Consente di avviare un flusso di lavoro da un altro, consentendo di supportare percorsi più complessi dei clienti, e di monitorare e rispondere meglio in caso di problemi.

The **[!UICONTROL External signal]** activity is designed to be placed as the first activity of a workflow. It can be triggered from the **[!UICONTROL End]** activity of another workflow or from a REST API call (for more on this, refer to the [API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity) ).

Quando attivati, è possibile definire parametri esterni e essere disponibili nelle variabili degli eventi del flusso di lavoro. The process to call a workflow with external parameters is detailed in [this section](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>L'attività non può essere attivata più spesso di ogni 10 minuti.

Note that an **[!UICONTROL External signal]** activity can be triggered from several different events. In that case, the **[!UICONTROL External signal]** is triggered as soon as one of the source workflows or API call is executed. Non è necessario che tutti i flussi di lavoro sorgente siano completati.

## Configuration {#configuration}

When configuring an external signal, it is important to first configure the **[!UICONTROL External signal]** activity in the destination workflow. Once this configuration is done, the **[!UICONTROL External signal]** activity of this workflow becomes available to configure the **[!UICONTROL End]** activity of the source workflow.

1. Drag and drop an **[!UICONTROL External signal]** activity into your destination workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Modificate l'etichetta dell'attività. This label is needed when configuring the source workflow that triggers the **[!UICONTROL External signal]**.

   If you want to call the workflow with parameters, use the **[!UICONTROL Parameters]** area to declare them. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).

   ![](assets/external_signal_configuration.png)

1. Confermate la configurazione dell'attività, aggiungete qualsiasi altra attività necessaria e salvate il flusso di lavoro.

   >[!NOTE]
   >
   >Se desiderate attivare il flusso di lavoro di destinazione da un altro flusso di lavoro, procedete con i seguenti passaggi. If you want to trigger the destination workflow from a REST API call, consult the [API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity) to get more details.

1. Open the source workflow and select an **[!UICONTROL End]** activity. If there is no **[!UICONTROL End]** activity available, add one after the last activity of a branch of the workflow.

   Per impostazione predefinita alcune attività non dispongono di transizioni in uscita. From the **[!UICONTROL Properties]** tab of these activities, you can add an outbound transition.

   For example, in an **[!UICONTROL Update data]** activity, go to the **[!UICONTROL Transitions]** tab and check the **[!UICONTROL Add an outbound transition without the population]** option. Questa opzione consente di aggiungere una transizione che non contiene dati e non consuma spazio inutile nel sistema. It is just used to connect the extra **[!UICONTROL End]** activity that triggers the destination workflow.

   ![](assets/external_signal_empty_transition.png)

1. In the **[!UICONTROL External signal]** tab of the **[!UICONTROL End]** activity, select the destination workflow as well as the **[!UICONTROL External signal]** activity to trigger within that workflow.

   When you set an **[!UICONTROL End]** activity to trigger another workflow, its icon is updated with an additional signal symbol.

   If you want to call the workflow with parameters, use the **[!UICONTROL Parameters and values]** area. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow).

   ![](assets/external_signal_end.png)

1. Salvate il flusso di lavoro sorgente.

Once the **[!UICONTROL End]** activity of the source workflow or the REST API call is executed, the destination workflow is automatically triggered from the **[!UICONTROL External signal]** activity.

>[!NOTE]
>
>Il flusso di lavoro di destinazione deve essere avviato manualmente prima che sia possibile attivarlo. When started, the **[!UICONTROL External activity]** is activated and waits for the signal from the source workflow.

## Example {#example}

The following example illustrates the **[!UICONTROL External signal]** activity in a typical use case. Un'importazione di dati viene eseguita in un flusso di lavoro sorgente. Una volta completata l'importazione e il database aggiornato, viene attivato un secondo flusso di lavoro. Questo secondo flusso di lavoro viene utilizzato per aggiornare un aggregato sui dati importati.

Il flusso di lavoro di origine viene presentato come segue:

* A [Load file](../../automating/using/load-file.md) activity uploads a file containing new purchase data. Note that the [database has been extended](../../developing/using/data-model-concepts.md) accordingly as purchase data are not present by default in the datamart.

   Ad esempio:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* A [Reconciliation](../../automating/using/reconciliation.md) activity creates the links between the imported data and the database so that the transactions data are properly connected to profiles and products.
* An [Update data](../../automating/using/update-data.md) activity inserts and updates the Transactions resource of the database with the incoming data.
* An **[!UICONTROL End]** activity triggers the destination workflow, which is used to update aggregates.

![](assets/signal_example_source1.png)

Il flusso di lavoro di destinazione viene presentato come segue:

* An **[!UICONTROL External signal]** activity waits for the source workflow to be successfully finished.
* A [Query](../../automating/using/query.md#enriching-data) activity targets profiles and enrich them with a collection set to retrieve the last purchase date.
* An [Update data](../../automating/using/update-data.md) activity stores the additional data in a dedicated custom field. Note that the profile resource has been extended to add the **Last purchase date** field.

![](assets/signal_example_source2.png)

