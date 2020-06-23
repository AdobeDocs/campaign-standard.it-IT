---
title: Gestione delle opzioni di esecuzione
description: Scopri come gestire le opzioni di esecuzione dei flussi di lavoro.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d4ac80810a77c0a6b512b3ed4c925fa0fb8a219c
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 0%

---


# Gestione delle opzioni di esecuzione {#managing-execution-options}

Per modificare le opzioni di esecuzione di un flusso di lavoro, utilizzate il ![](assets/edit_darkgrey-24px.png) pulsante per accedere alle proprietà del flusso di lavoro e selezionate la **[!UICONTROL Execution]** sezione.

![](assets/wkf_execution_6.png)

Le opzioni possibili sono:

* **[!UICONTROL Default affinity]**: questo campo consente di forzare l&#39;esecuzione di un flusso di lavoro o di un&#39;attività di workflow su un computer specifico.

* **[!UICONTROL History in days]**: specifica il numero di giorni dopo i quali la cronologia deve essere eliminata. La cronologia contiene elementi correlati al flusso di lavoro: registri, attività, eventi (oggetti tecnici collegati all&#39;operazione del flusso di lavoro), nonché file scaricati dall&#39; **[!UICONTROL Transfer file]** attività. Il valore predefinito è 30 giorni per i modelli di flusso di lavoro predefiniti.

   La rimozione della cronologia viene eseguita dal flusso di lavoro tecnico di pulizia del database, che viene eseguito quotidianamente per impostazione predefinita (vedere [Elenco di flussi di lavoro](../../administration/using/technical-workflows.md)tecnici).

   >[!IMPORTANT]
   >
   >Se il **[!UICONTROL History in days]** campo viene lasciato vuoto, il relativo valore verrà considerato come &quot;1&quot;, il che significa che la cronologia verrà eliminata dopo 1 giorno.

* **[!UICONTROL Save SQL queries in the log]**: consente di salvare le query SQL dal flusso di lavoro nei registri.

* **[!UICONTROL Keep interim results]**: selezionate questa opzione per visualizzare i dettagli delle transizioni. Avviso: se si seleziona questa opzione, l&#39;esecuzione del flusso di lavoro potrebbe risultare notevolmente rallentata.

* **[!UICONTROL Execute in the engine (do not use in production)]**: consente di eseguire il flusso di lavoro localmente, a scopo di verifica dell’ambiente di sviluppo.

* **[!UICONTROL Severity]**: consente di specificare un livello di priorità per l’esecuzione di flussi di lavoro nell’istanza del Adobe Campaign . I flussi di lavoro critici verranno prima eseguiti.

La **[!UICONTROL Error management]** sezione fornisce opzioni aggiuntive che consentono di gestire il funzionamento dei flussi di lavoro in caso di errori. Queste opzioni sono descritte dettagliatamente nella sezione Gestione [](../../automating/using/monitoring-workflow-execution.md#error-management) errori.
