---
title: Informazioni sull’esecuzione di un flusso di lavoro
description: Ulteriori informazioni sull’esecuzione dei flussi di lavoro.
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
source-wordcount: '354'
ht-degree: 8%

---

# Informazioni sull’esecuzione di un flusso di lavoro {#about-workflow-execution}

Un workflow viene sempre avviato manualmente. Tuttavia, una volta avviato, può rimanere inattivo, a seconda delle informazioni specificate in un&#39;attività [Scheduler](../../automating/using/scheduler.md).

>[!IMPORTANT]
>
> L’Adobe consiglia ai clienti di non eseguire più di 20 esecuzioni di flussi di lavoro attivi contemporaneamente e di assegnare le priorità e distribuire l’esecuzione del flusso di lavoro nel tempo. Per ulteriori informazioni, consulta le best practice fornite in [questa pagina](../../automating/using/best-practices-workflows.md).

Azioni correlate all’esecuzione (avvio, arresto, pausa, ecc.) sono **processi asincroni**: il comando viene salvato e diventerà effettivo quando il server sarà disponibile per applicarlo.

In un flusso di lavoro, il risultato di ogni attività viene generalmente inviato all’attività seguente tramite una transizione, rappresentata da una freccia.

Una transizione non termina se non è collegata a un’attività di destinazione.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>È comunque possibile eseguire un flusso di lavoro contenente transizioni non terminate: verrà generato un messaggio di avviso e il flusso di lavoro verrà messo in pausa una volta raggiunta la transizione, ma non verrà generato un errore. Puoi anche avviare un flusso di lavoro senza aver completato completamente la progettazione e completarla man mano che prosegui.

Una volta eseguita un’attività, il numero di record inviati nella transizione viene visualizzato sopra di essa.

![](assets/wkf_transition_count.png)

Puoi aprire le transizioni per verificare che i dati inviati siano corretti durante o dopo l’esecuzione del flusso di lavoro. Puoi visualizzare i dati e la struttura dei dati.

Per impostazione predefinita, è possibile accedere solo ai dettagli dell’ultima transizione del flusso di lavoro. Per poter accedere ai risultati delle attività precedenti, è necessario selezionare l&#39;opzione **[!UICONTROL Keep interim results]** nella sezione **[!UICONTROL Execution]** delle proprietà del flusso di lavoro prima di avviare il flusso di lavoro.

>[!NOTE]
>
>Questa opzione consuma molta memoria ed è progettata per facilitare la costruzione di un flusso di lavoro e garantirne la corretta configurazione e il corretto funzionamento. Lascia deselezionata questa opzione nelle istanze di produzione.

Quando una transizione è aperta, è possibile modificarne **[!UICONTROL Label]** o collegarvi **[!UICONTROL Segment code]**. A questo scopo, modifica i campi corrispondenti e conferma le modifiche.

Utilizzando le API REST di Campaign Standard, puoi **avviare**, **sospendere**, **riprendere** e **interrompere** un flusso di lavoro. Ulteriori dettagli ed esempi di chiamate REST sono disponibili nella [documentazione API.](../../api/using/controlling-a-workflow.md)
