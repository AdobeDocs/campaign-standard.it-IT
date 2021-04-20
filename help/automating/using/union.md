---
solution: Campaign Standard
product: campaign
title: Union
description: L’attività Union ti consente di raggruppare il risultato di più attività in un unico target.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: union,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 97%

---


# Union{#union}

## Descrizione {#description}

![](assets/union.png)

L’attività **[!UICONTROL Union]** ti consente di raggruppare il risultato di più attività in un unico target.

>[!NOTE]
>
>I set non devono necessariamente essere omogenei.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Union]** viene utilizzata per combinare le popolazioni delle transizioni in entrata, ad esempio, durante l’esecuzione di una segmentazione, la definizione di un pubblico o la preparazione del target del messaggio.

**Argomenti correlati:**

* [Caso di utilizzo: Unione di due tipi di pubblico perfezionati](../../automating/using/union-on-two-refined-audiences.md)

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Union]** nel flusso di lavoro.
1. Connettila alle altre attività che la precedono, come le query.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Seleziona l’opzione **[!UICONTROL Reconciliation type]** per definire la modalità di gestione dei duplicati dal confronto tra le popolazioni in ingresso:

   * **[!UICONTROL Keys only]**: è la modalità predefinita. L’attività mantiene un solo elemento quando gli elementi delle diverse transizioni in entrata hanno la stessa chiave. È possibile utilizzare questa opzione solo se le popolazioni in entrata sono omogenee.
   * **[!UICONTROL All shared columns]**: i dati vengono riconciliati in base a tutte le colonne in comune con le transizioni in entrata. Pertanto, devi selezionare il set principale da mantenere in caso di un duplicato. È possibile utilizzare questa opzione se le dimensioni di targeting della popolazione in entrata sono diverse.
   * **[!UICONTROL A selection of columns]**: seleziona questa opzione per definire l’elenco di colonne alle quali viene applicata la riconciliazione dei dati. Devi innanzitutto selezionare il set principale (quello contenente i dati di origine), quindi le colonne da utilizzare per il join.

1. Seleziona la casella **[!UICONTROL Use common additional data only]** se desideri conservare solo i dati aggiuntivi presenti in tutte le transizioni in entrata.
1. Se desideri limitare la dimensione della popolazione finale, seleziona la casella **[!UICONTROL Limit size of generated population]**. È possibile specificare la dimensione nel campo **[!UICONTROL Maximum number of records]**.
1. Se necessario, gestisci l’attività [Transitions](../../automating/using/activity-properties.md) per accedere alle opzioni avanzate per la popolazione calcolata.
1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

## Esempio {#example}

L’esempio seguente mostra il risultato di due attività Query volte a raggruppare i profili del database di Adobe Campaign che hanno tra i 18 e i 27 anni e quelli che hanno tra i 34 e i 40 anni. Il risultato contiene tutti i profili delle due query o il numero massimo di record, se applicabile, come specificato durante la configurazione.

![](assets/wkf_union_example.png)