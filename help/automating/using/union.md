---
title: Unione
seo-title: Unione
description: Unione
seo-description: L'attività Unione consente di riportare il risultato di più attività in una singola destinazione.
page-status-flag: never-activated
uuid: fafc 3 ce 9-2212-4403-8754-cfbb 28 ba 6 e 26
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: targeting-activity
discoiquuid: 99 a 8 c 3 a 5-7 d 90-4 dbb-aa 37-1 d 0 a 84719 cf 6
context-tags: union, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Union{#union}

## Description {#description}

![](assets/union.png)

The **[!UICONTROL Union]** activity allows you to regroup the result of multiple activities into a single target.

>[!NOTE]
>
>I set non devono necessariamente essere coerenti.

## Context of use {#context-of-use}

The **[!UICONTROL Union]** activity is used to combine the populations from inbound transitions when performing a segmentation, defining an audience, or when preparing the message target for example.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Union]** activity into your workflow.
1. Connettetevi alle altre attività che vengono prima di essa, come query.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Reconciliation type]** to define how duplicates are from the confrontation between inbound populations are handled:

   * **[!UICONTROL Keys only]**: questa è la modalità predefinita. L'attività mantiene un solo elemento quando gli elementi delle diverse transizioni in entrata hanno la stessa chiave. Questa opzione può essere utilizzata solo se le popolazioni in entrata sono omogenee.
   * **[!UICONTROL All shared columns]**: I dati vengono riconciliati in base a tutte le colonne in comune con le transizioni in entrata. Occorre quindi selezionare il set principale che verrà mantenuto nel caso di duplicati. Questa opzione può essere utilizzata se le dimensioni di targeting della popolazione in entrata sono diverse.
   * **[!UICONTROL A selection of columns]**: selezionare questa opzione per definire l'elenco delle colonne in cui sarà applicata la riconciliazione dei dati. Occorre anzitutto selezionare il set principale (che contiene i dati sorgente), quindi le colonne da utilizzare per l'unione.

1. Check the **[!UICONTROL Use common additional data only]** box if you would like to keep only the additional data that is in all inbound transitions.
1. If you would like to limit the size of the final population, check the **[!UICONTROL Limit size of generated population]** box. The size can be specified in the **[!UICONTROL Maximum number of records]** field.
1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the calculated population.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example {#example}

L'esempio seguente mostra il risultato di due attività di query che mirano a ristabilire i profili dal database Adobe Campaign che hanno tra 18 e 27 anni e quelli che hanno una durata compresa tra 34 e 40 anni. Il risultato contiene tutti i profili delle due query o il numero massimo di record, se applicabile, nel corso della configurazione.

![](assets/wkf_union_example.png)