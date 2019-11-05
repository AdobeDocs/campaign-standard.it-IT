---
title: Unione
description: L'attività dell'Unione consente di raggruppare il risultato di più attività in un unico obiettivo.
page-status-flag: mai attivato
uuid: fafc3ce9-2212-4403-8754-cfbb28ba6e26
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di targeting
discoiquuid: 99a8c3a5-7d90-4dbb-aa37-1d0a84719cf6
context-tags: unione,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Unione{#union}

## Descrizione {#description}

![](assets/union.png)

L' **[!UICONTROL Union]** attività consente di raggruppare il risultato di più attività in un unico target.

>[!NOTE]
>
>I set non devono necessariamente essere omogenei.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL Union]** attività viene utilizzata per combinare le popolazioni provenienti da transizioni in entrata quando si esegue una segmentazione, si definisce un'audience o, ad esempio, quando si prepara la destinazione del messaggio.

## Configurazione {#configuration}

1. Trascinate e rilasciate un' **[!UICONTROL Union]** attività nel flusso di lavoro.
1. Connettetelo alle altre attività che vengono prima di esso, come le query.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Selezionare l'opzione **[!UICONTROL Reconciliation type]** per definire il modo in cui i duplicati vengono gestiti dal confronto tra le popolazioni in ingresso:

   * **[!UICONTROL Keys only]**: questa è la modalità predefinita. L'attività mantiene un solo elemento quando gli elementi delle diverse transizioni in entrata hanno la stessa chiave. Questa opzione può essere utilizzata solo se le popolazioni in entrata sono omogenee.
   * **[!UICONTROL All shared columns]**: I dati vengono riconciliati in base a tutte le colonne in comune con le transizioni in entrata. Pertanto, è necessario selezionare il set principale che verrà mantenuto in caso di un duplicato. Questa opzione può essere utilizzata se le dimensioni di targeting della popolazione in entrata sono diverse.
   * **[!UICONTROL A selection of columns]**: selezionare questa opzione per definire l'elenco di colonne alle quali verrà applicata la riconciliazione dei dati. È innanzitutto necessario selezionare il set principale (quello contenente i dati di origine), quindi le colonne da utilizzare per il join.

1. Selezionare la **[!UICONTROL Use common additional data only]** casella se si desidera conservare solo i dati aggiuntivi presenti in tutte le transizioni in entrata.
1. Per limitare la dimensione della popolazione finale, selezionate la **[!UICONTROL Limit size of generated population]** casella. È possibile specificare la dimensione nel **[!UICONTROL Maximum number of records]** campo.
1. Se necessario, gestite le [Transizioni](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) dell'attività per accedere alle opzioni avanzate per la popolazione calcolata.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Esempio {#example}

L'esempio seguente mostra il risultato di due attività di query volte a raggruppare i profili dal database Adobe Campaign che hanno tra i 18 e i 27 anni e che hanno tra i 34 e i 40 anni. Il risultato contiene tutti i profili delle due query o il numero massimo di record, se applicabile, come specificato durante la configurazione.

![](assets/wkf_union_example.png)