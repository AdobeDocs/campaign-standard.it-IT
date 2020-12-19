---
solution: Campaign Standard
product: campaign
title: Informazioni sull’esecuzione di un flusso di lavoro
description: Ulteriori informazioni sull'esecuzione del flusso di lavoro.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 8%

---


# Informazioni sull’esecuzione di un flusso di lavoro {#about-workflow-execution}

Un flusso di lavoro viene sempre avviato manualmente. Tuttavia, una volta avviato, può rimanere inattivo, a seconda delle informazioni specificate in un&#39;attività [Scheduler](../../automating/using/scheduler.md).

>[!CAUTION]
>
>  Adobe consiglia ai clienti di assegnare priorità alle esecuzioni dei flussi di lavoro e di eseguire fino a venti esecuzioni simultanee per ottenere in modo coerente il massimo delle prestazioni nell’istanza. Per impostazione predefinita, è possibile pianificare più di venti esecuzioni simultanee del flusso di lavoro e l&#39;esecuzione sequenziale sarà eseguita per impostazione predefinita. Puoi regolare le impostazioni predefinite per il numero massimo di esecuzioni simultanee del flusso di lavoro inviando un ticket all&#39;Assistenza clienti.

Azioni relative all’esecuzione (avvio, arresto, pausa, ecc.) sono processi **asincroni**: il comando viene salvato e diventerà effettivo una volta che il server sarà disponibile ad applicarlo.

In un flusso di lavoro, il risultato di ogni attività viene in genere inviato alla seguente attività tramite una transizione, rappresentata da una freccia.

Una transizione non viene terminata se non è collegata a un&#39;attività di destinazione.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>È comunque possibile eseguire un flusso di lavoro contenente transizioni non interrotte: viene generato un messaggio di avviso e il flusso di lavoro viene messo in pausa una volta raggiunta la transizione, ma questo non genera un errore. Potete anche avviare un flusso di lavoro senza aver completato completamente la progettazione e completarlo man mano che procedete.

Una volta eseguita un&#39;attività, il numero di record inviati nella transizione viene visualizzato sopra di essa.

![](assets/wkf_transition_count.png)

Puoi aprire le transizioni per verificare che i dati inviati siano corretti durante o dopo l’esecuzione del flusso di lavoro. È possibile visualizzare i dati e la struttura dei dati.

Per impostazione predefinita, è possibile accedere solo ai dettagli dell&#39;ultima transizione del flusso di lavoro. Per poter accedere ai risultati delle attività precedenti, è necessario selezionare l&#39;opzione **[!UICONTROL Keep interim results]** nella sezione **[!UICONTROL Execution]** delle proprietà del flusso di lavoro prima di avviare il flusso di lavoro.

>[!NOTE]
>
>Questa opzione consuma molta memoria ed è stata progettata per aiutare a creare un flusso di lavoro e garantire che sia configurato e si comporti correttamente. Lascia deselezionata questa opzione nelle istanze di produzione.

Quando una transizione è aperta, potete modificarne **[!UICONTROL Label]** o collegare un **[!UICONTROL Segment code]**. A questo scopo, modificate i campi corrispondenti e confermate le modifiche.

Utilizzando le API REST Campaign Standard, è possibile **avviare**, **sospendere**, **riprendere** e **arrestare** un flusso di lavoro. Per ulteriori dettagli ed esempi di chiamate REST, consultare la documentazione [API.](../../api/using/controlling-a-workflow.md)
