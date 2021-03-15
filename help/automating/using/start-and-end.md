---
solution: Campaign Standard
product: campaign
title: Start ed End
description: Le attività Start ed End ti consentono di contrassegnare chiaramente dove inizia e termina il flusso di lavoro.
audience: automating
content-type: reference
topic-tags: execution-activities
feature: Flussi di lavoro
role: Architetto dati
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 98%

---


# Start ed End{#start-and-end}

## Descrizione {#description}

![](assets/start.png)

![](assets/end.png)

Le attività **[!UICONTROL Start]** ed **[!UICONTROL End]** ti consentono di contrassegnare chiaramente dove inizia e termina il flusso di lavoro.

## Contesto di utilizzo {#context-of-use}

L’esecuzione di un flusso di lavoro inizia con le attività senza una transizione in entrata e si interrompe quando non sono più presenti attività in corso. Tuttavia, puoi aggiungere attività **[!UICONTROL Start]** ed **[!UICONTROL End]** per contrassegnare chiaramente i punti iniziali e finali di un flusso di lavoro. Questo è particolarmente utile per flussi di lavoro relativamente complessi.

È consigliabile utilizzare un’attività **[!UICONTROL End]** invece di uscire dall’ultima transizione di un flusso di lavoro per assicurarsi che termini correttamente.

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Start]** o **[!UICONTROL End]** nel flusso di lavoro.
1. Posiziona l’attività **[!UICONTROL Start]** davanti ad altre attività, come le query, e l’attività **[!UICONTROL End]** dopo una serie di attività.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Puoi configurare l’oggetto **End** in modo che interrompa tutte le attività in corso del flusso di lavoro, incluse quelle che non sono state completate. A questo scopo, seleziona l’opzione corrispondente.
1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

## Attivazione di un altro flusso di lavoro {#triggering-another-workflow}

Puoi attivare un altro flusso di lavoro utilizzando la scheda **[!UICONTROL External signal]** di un’attività **[!UICONTROL End]**. Consulta la sezione [External signal](../../automating/using/external-signal.md).

## Esempio {#example}

L’esempio seguente mostra come viene eseguito un flusso di lavoro complesso con un’attività **[!UICONTROL Start]** e diverse attività **[!UICONTROL End]**. La casella **[!UICONTROL Stop all tasks in progress]** è stata selezionata per la prima attività **[!UICONTROL End]**. Al termine dell’attività corrispondente viene interrotto l’intero flusso di lavoro: ha lo stesso effetto di quando il pulsante ![](assets/stop_darkgrey-24px.png) è stato selezionato (consulta la sezione della [barra delle azioni](../../automating/using/workflow-interface.md#action-bar)).

![](assets/wkf_start_end_example.png)

