---
title: Intersezione
seo-title: Intersezione
description: Intersezione
seo-description: L'attività Intersezione consente di mantenere solo gli elementi comuni alle diverse popolazioni in entrata dell'attività.
page-status-flag: never-activated
uuid: a 60 f 9811-0158-44 b 3-952 b -392685 c 006 cc
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: targeting-activity
discoiquuid: 7 a 107 d 6 b-edc 3-44 c 3-bbb 7-ba 3 dec 8 e 43 f 9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Intersection{#intersection}

## Description {#description}

![](assets/intersection.png)

The **[!UICONTROL Intersection]** activity allows you to keep only the elements common to the different inbound populations in the activity.

## Context of use {#context-of-use}

The **[!UICONTROL Intersection]** activity is generally used to carry out additional filtering on populations from inbound transitions.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Intersection]** activity into your workflow.
1. Connettetevi alle altre attività che vengono prima di essa, come query.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: Modalità predefinita. L'attività mantiene un solo elemento quando gli elementi delle diverse transizioni in entrata hanno la stessa chiave.
   * **[!UICONTROL All shared columns]**: I dati vengono riconciliati in base alle colonne in comune con le transizioni in entrata. Pertanto, è necessario selezionare il set principale da utilizzare come base per il confronto. Questa opzione può essere utilizzata se le dimensioni di targeting della popolazione in entrata sono diverse.
   * **[!UICONTROL A selection of columns]**: Selezionare questa opzione per definire l'elenco delle colonne in cui sarà applicata la riconciliazione dei dati. Occorre anzitutto selezionare il set principale (quello che contiene i dati sorgente), quindi specificare i campi da utilizzare per l'unione.

1. Check the **[!UICONTROL Use common additional data only]** box if you would like to keep only the additional data that is in all inbound transitions.
1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example {#example}

L'esempio seguente mostra l'intersezione tra due attività di query. Viene utilizzato qui per esaminare il database di Adobe Campaign e recuperare i profili che sono compresi tra 18 e 27 anni e i cui indirizzo e-mail sono stati forniti rispettivamente.

![](assets/wkf_intersection_example.png)

