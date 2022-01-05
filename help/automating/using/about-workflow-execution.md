---
title: Informazioni sull’esecuzione di un flusso di lavoro
description: Ulteriori informazioni sull’esecuzione del flusso di lavoro.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3b95fc66-d6f4-44b2-be33-925c1109a57f
source-git-commit: 6ca3ffe3ba2cf7629e511e4ba035b170b25ad79e
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 8%

---

# Informazioni sull’esecuzione di un flusso di lavoro {#about-workflow-execution}

Un flusso di lavoro viene sempre avviato manualmente. Tuttavia, una volta avviato, può rimanere inattivo, a seconda delle informazioni specificate in un [Scheduler](../../automating/using/scheduler.md) attività.

>[!IMPORTANT]
>
> Adobe consiglia ai clienti di non eseguire più di 20 esecuzioni di flussi di lavoro attivi contemporaneamente e di assegnare priorità e distribuire l’esecuzione del flusso di lavoro nel tempo. Per ulteriori informazioni, consulta le best practice fornite in [questa pagina](../../automating/using/best-practices-workflows.md).

Azioni relative all’esecuzione (avvio, arresto, pausa, ecc.) sono **asincrono** processi: il comando viene salvato e diventerà effettivo una volta che il server sarà disponibile per applicarlo.

In un flusso di lavoro, il risultato di ogni attività viene generalmente inviato alla seguente attività tramite una transizione, rappresentata da una freccia.

Una transizione non viene terminata se non è collegata a un’attività di destinazione.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>È comunque possibile eseguire un flusso di lavoro contenente transizioni non terminate: viene generato un messaggio di avviso e il flusso di lavoro viene messo in pausa una volta raggiunta la transizione, ma questo non genera un errore. Puoi anche avviare un flusso di lavoro senza aver completato completamente la progettazione e completarlo man mano che prosegui.

Una volta eseguita un’attività, sopra di essa viene visualizzato il numero di record inviati nella transizione.

![](assets/wkf_transition_count.png)

Puoi aprire le transizioni per verificare che i dati inviati siano corretti durante o dopo l’esecuzione del flusso di lavoro. È possibile visualizzare i dati e la struttura dei dati.

Per impostazione predefinita, è possibile accedere solo ai dettagli dell’ultima transizione del flusso di lavoro. Per poter accedere ai risultati delle attività precedenti, devi controllare la **[!UICONTROL Keep interim results]** in **[!UICONTROL Execution]** prima di avviare il flusso di lavoro, sezione delle proprietà del flusso di lavoro.

>[!NOTE]
>
>Questa opzione consuma molta memoria ed è progettata per aiutare a costruire un flusso di lavoro e per assicurarti che sia configurato e si comporti correttamente. Lascia deselezionata questa opzione nelle istanze di produzione.

Quando una transizione è aperta, puoi modificarne la relativa **[!UICONTROL Label]** o collegare un **[!UICONTROL Segment code]** a esso. A questo scopo, modifica i campi corrispondenti e conferma le modifiche apportate.

Utilizzando le API REST di Campaign Standard, puoi **start**, **pause**, **riprendere** e **stop** un flusso di lavoro. Puoi trovare ulteriori dettagli ed esempi di chiamate REST nella sezione [Documentazione API.](../../api/using/controlling-a-workflow.md)
