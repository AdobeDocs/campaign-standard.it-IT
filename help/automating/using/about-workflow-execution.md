---
solution: Campaign Standard
product: campaign
title: Informazioni sull’esecuzione di un flusso di lavoro
description: Ulteriori informazioni sull’esecuzione del flusso di lavoro.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 8%

---


# Informazioni sull’esecuzione di un flusso di lavoro {#about-workflow-execution}

Un flusso di lavoro viene sempre avviato manualmente. Tuttavia, una volta avviato, può rimanere inattivo, a seconda delle informazioni specificate in un&#39;attività [Scheduler](../../automating/using/scheduler.md).

>[!CAUTION]
>
> Adobe consiglia ai clienti di assegnare priorità alle esecuzioni dei flussi di lavoro ed eseguire fino a venti esecuzioni simultanee dei flussi di lavoro per ottenere in modo coerente le prestazioni massime in tutta l’istanza. Puoi pianificare più di venti esecuzioni simultanee di flussi di lavoro ed eseguirle in sequenza per impostazione predefinita. È possibile modificare le impostazioni predefinite per il numero massimo di esecuzioni simultanee di flussi di lavoro inviando un ticket all’Assistenza clienti.

Azioni relative all’esecuzione (avvio, arresto, pausa, ecc.) sono processi **asincroni**: il comando viene salvato e diventerà effettivo una volta che il server sarà disponibile per applicarlo.

In un flusso di lavoro, il risultato di ogni attività viene generalmente inviato alla seguente attività tramite una transizione, rappresentata da una freccia.

Una transizione non viene terminata se non è collegata a un’attività di destinazione.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>È comunque possibile eseguire un flusso di lavoro contenente transizioni non terminate: viene generato un messaggio di avviso e il flusso di lavoro viene messo in pausa una volta raggiunta la transizione, ma questo non genera un errore. Puoi anche avviare un flusso di lavoro senza aver completato completamente la progettazione e completarlo man mano che prosegui.

Una volta eseguita un’attività, sopra di essa viene visualizzato il numero di record inviati nella transizione.

![](assets/wkf_transition_count.png)

Puoi aprire le transizioni per verificare che i dati inviati siano corretti durante o dopo l’esecuzione del flusso di lavoro. È possibile visualizzare i dati e la struttura dei dati.

Per impostazione predefinita, è possibile accedere solo ai dettagli dell’ultima transizione del flusso di lavoro. Per poter accedere ai risultati delle attività precedenti, è necessario selezionare l’opzione **[!UICONTROL Keep interim results]** nella sezione **[!UICONTROL Execution]** delle proprietà del flusso di lavoro prima di avviare il flusso di lavoro.

>[!NOTE]
>
>Questa opzione consuma molta memoria ed è progettata per aiutare a costruire un flusso di lavoro e per assicurarti che sia configurato e si comporti correttamente. Lascia deselezionata questa opzione nelle istanze di produzione.

Quando una transizione è aperta, puoi modificarne la sezione **[!UICONTROL Label]** o collegarvi una sezione **[!UICONTROL Segment code]**. A questo scopo, modifica i campi corrispondenti e conferma le modifiche apportate.

Utilizzando le API REST di Campaign Standard, puoi **avviare**, **sospendere**, **riprendere** e **arrestare** un flusso di lavoro. Per ulteriori dettagli ed esempi di chiamate REST, consulta la documentazione [API .](../../api/using/controlling-a-workflow.md)
