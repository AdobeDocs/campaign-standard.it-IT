---
title: Inizio e fine
description: Le attività Inizio e Fine consentono di contrassegnare chiaramente dove inizia e termina il flusso di lavoro.
page-status-flag: mai attivato
uuid: 146b6337-122c-453d-8ffd-5c157db29217
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di esecuzione
discoiquuid: a0a8a725-8ede-4626-9798-b86924b58beb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Inizio e fine{#start-and-end}

## Descrizione {#description}

![](assets/start.png)

![](assets/end.png)

Le attività **[!UICONTROL Start]** e **[!UICONTROL End]** consentono di contrassegnare chiaramente dove inizia e termina il flusso di lavoro.

## Contesto di utilizzo {#context-of-use}

L'esecuzione di un flusso di lavoro inizia con le attività senza una transizione in entrata e si arresta quando non sono più presenti attività in corso. Tuttavia, potete aggiungere **[!UICONTROL Start]** e **[!UICONTROL End]** attività per contrassegnare chiaramente i punti iniziale e finale di un flusso di lavoro. Questo è particolarmente utile per flussi di lavoro relativamente complessi.

È consigliabile utilizzare un' **[!UICONTROL End]** attività invece di uscire dall'ultima transizione di un flusso di lavoro per assicurarsi che il flusso di lavoro termini correttamente.

## Configurazione {#configuration}

1. Trascinate un’ **[!UICONTROL Start]** **[!UICONTROL End]** attività o un’attività nel flusso di lavoro.
1. Posizionare l' **[!UICONTROL Start]** attività davanti ad altre attività, come le query, e dopo una serie di **[!UICONTROL End]** attività.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. È possibile configurare l'oggetto **End** in modo che interrompa tutte le attività in corso del flusso di lavoro, incluse quelle che non sono state completate. A questo scopo, selezionare l'opzione corrispondente.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Attivazione di un altro flusso di lavoro {#triggering-another-workflow}

Utilizzando la **[!UICONTROL External signal]** scheda di un' **[!UICONTROL End]** attività, potete attivare un altro flusso di lavoro. Fare riferimento alla sezione [Segnale](../../automating/using/external-signal.md) esterno.

## Esempio {#example}

L'esempio seguente mostra come viene eseguito un flusso di lavoro complesso con un' **[!UICONTROL Start]** attività e diverse **[!UICONTROL End]** attività. La **[!UICONTROL Stop all tasks in progress]** casella è stata selezionata per la prima **[!UICONTROL End]** attività. Al termine dell’attività corrispondente, verrà interrotto l’intero flusso di lavoro: avrà lo stesso effetto di quando il ![](assets/stop_darkgrey-24px.png) pulsante è stato selezionato (fare riferimento alla sezione della barra [delle](../../automating/using/workflow-interface.md#action-bar) azioni).

![](assets/wkf_start_end_example.png)

