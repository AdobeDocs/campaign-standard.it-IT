---
title: Intersezione
description: L'attività Intersezione consente di mantenere solo gli elementi comuni alle diverse popolazioni in entrata nell'attività.
page-status-flag: mai attivato
uuid: a60f9811-0158-44b3-952b-392685c006cc
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di targeting
discoiquuid: 7a107d6b-edc3-44c3-bbb7-ba3dec8e43f9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Intersezione{#intersection}

## Descrizione {#description}

![](assets/intersection.png)

L' **[!UICONTROL Intersection]** attività consente di mantenere solo gli elementi comuni alle diverse popolazioni in entrata nell'attività.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL Intersection]** attività è generalmente utilizzata per effettuare ulteriori filtraggi sulle popolazioni provenienti da transizioni in entrata.

## Configurazione {#configuration}

1. Trascinate e rilasciate un' **[!UICONTROL Intersection]** attività nel flusso di lavoro.
1. Connettetelo alle altre attività che vengono prima di esso, come le query.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Selezionate **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: Modalità predefinita. L'attività mantiene un solo elemento quando gli elementi delle diverse transizioni in entrata hanno la stessa chiave.
   * **[!UICONTROL All shared columns]**: I dati vengono riconciliati in base alle colonne in comune con le transizioni in entrata. Pertanto, è necessario selezionare il set principale che fungerà da base per il confronto. Questa opzione può essere utilizzata se le dimensioni di targeting della popolazione in entrata sono diverse.
   * **[!UICONTROL A selection of columns]**: Selezionare questa opzione per definire l'elenco di colonne su cui verrà applicata la riconciliazione dei dati. È innanzitutto necessario selezionare il set principale (quello contenente i dati di origine), quindi specificare i campi da utilizzare per il join.

1. Selezionare la **[!UICONTROL Use common additional data only]** casella se si desidera conservare solo i dati aggiuntivi presenti in tutte le transizioni in entrata.
1. Se necessario, gestite le [Transizioni](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) dell'attività per accedere alle opzioni avanzate per la popolazione in uscita.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Esempio {#example}

L'esempio seguente mostra l'intersezione tra due attività di query. Viene utilizzato qui per esaminare il database di Adobe Campaign e recuperare i profili che hanno tra i 18 e i 27 anni e i profili il cui indirizzo e-mail è stato fornito rispettivamente.

![](assets/wkf_intersection_example.png)

