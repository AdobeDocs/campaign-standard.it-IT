---
solution: Campaign Standard
product: campaign
title: Intersection
description: L’attività Intersection ti consente di mantenere solo gli elementi comuni alle diverse popolazioni in entrata all’interno dell’attività.
audience: automating
content-type: reference
topic-tags: targeting-activities
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 98%

---


# Intersection{#intersection}

## Descrizione {#description}

![](assets/intersection.png)

L’attività **[!UICONTROL Intersection]** ti consente di mantenere solo gli elementi comuni alle diverse popolazioni in entrata all’interno dell’attività.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Intersection]** è generalmente utilizzata per effettuare ulteriori filtraggi sulle popolazioni provenienti da transizioni in entrata.

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Intersection]** nel flusso di lavoro.
1. Connettila alle altre attività che la precedono, come le query.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Seleziona **[!UICONTROL Reconciliation type]**:

   * **[!UICONTROL Keys only]**: modalità predefinita. L’attività mantiene un solo elemento quando gli elementi delle diverse transizioni in entrata hanno la stessa chiave.
   * **[!UICONTROL All shared columns]**: i dati vengono riconciliati in base alle colonne che hanno in comune con le transizioni in entrata. Pertanto, devi selezionare il set principale che fungerà da base per il confronto. È possibile utilizzare questa opzione se le dimensioni di targeting della popolazione in entrata sono diverse.
   * **[!UICONTROL A selection of columns]**: seleziona questa opzione per definire l’elenco di colonne alle quali viene applicata la riconciliazione dei dati. Devi innanzitutto selezionare il set principale, quello contenente i dati di origine, quindi specificare i campi da utilizzare per l’unione.

1. Seleziona la casella **[!UICONTROL Use common additional data only]** se desideri conservare solo i dati aggiuntivi presenti in tutte le transizioni in entrata.
1. Se necessario, gestisci le [Transizioni](../../automating/using/activity-properties.md) dell’attività per accedere alle opzioni avanzate per la popolazione in uscita.
1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

## Esempio {#example}

L’esempio seguente mostra l’intersezione tra due attività di query. In questo caso, viene utilizzato per esaminare il database di Adobe Campaign e recuperare, rispettivamente, i profili che hanno tra i 18 e i 27 anni di età e quelli che hanno indicato un indirizzo e-mail.

![](assets/wkf_intersection_example.png)

