---
title: Intersezione
description: L'attività Intersezione consente di mantenere solo gli elementi comuni alle diverse popolazioni in entrata nell'attività.
page-status-flag: never-activated
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 7a107d6b-edc3-44c3-bbb7-ba3dec8e43f9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# Intersezione{#intersection}

## Descrizione {#description}

![](assets/intersection.png)

L&#39; **[!UICONTROL Intersection]** attività consente di mantenere solo gli elementi comuni alle diverse popolazioni in entrata nell&#39;attività.

## Contesto di utilizzo {#context-of-use}

L&#39; **[!UICONTROL Intersection]** attività è generalmente utilizzata per effettuare ulteriori filtraggi sulle popolazioni provenienti da transizioni in entrata.

## Configurazione {#configuration}

1. Trascinate e rilasciate un&#39; **[!UICONTROL Intersection]** attività nel flusso di lavoro.
1. Connettetelo alle altre attività che vengono prima di esso, come le query.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Selezionate **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: Modalità predefinita. L&#39;attività mantiene un solo elemento quando gli elementi delle diverse transizioni in entrata hanno la stessa chiave.
   * **[!UICONTROL All shared columns]**: I dati vengono riconciliati in base alle colonne in comune con le transizioni in entrata. Pertanto, è necessario selezionare il set principale che fungerà da base per il confronto. Questa opzione può essere utilizzata se le dimensioni di targeting della popolazione in entrata sono diverse.
   * **[!UICONTROL A selection of columns]**: Selezionare questa opzione per definire l&#39;elenco di colonne su cui verrà applicata la riconciliazione dei dati. È innanzitutto necessario selezionare il set principale (quello contenente i dati di origine), quindi specificare i campi da utilizzare per il join.

1. Selezionare la **[!UICONTROL Use common additional data only]** casella se si desidera conservare solo i dati aggiuntivi presenti in tutte le transizioni in entrata.
1. Se necessario, gestite le [Transizioni](../../automating/using/activity-properties.md) dell&#39;attività per accedere alle opzioni avanzate per la popolazione in uscita.
1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.

## Esempio {#example}

L&#39;esempio seguente mostra l&#39;intersezione tra due attività di query. Viene utilizzato qui per esaminare il database di Adobe Campaign e recuperare i profili che hanno tra i 18 e i 27 anni e i profili il cui indirizzo e-mail è stato fornito rispettivamente.

![](assets/wkf_intersection_example.png)

