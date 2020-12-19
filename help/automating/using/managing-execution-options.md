---
solution: Campaign Standard
product: campaign
title: Gestione delle opzioni di esecuzione
description: Scopri come gestire le opzioni di esecuzione dei flussi di lavoro.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Gestione delle opzioni di esecuzione {#managing-execution-options}

Per modificare le opzioni di esecuzione di un flusso di lavoro, utilizzare il pulsante ![](assets/edit_darkgrey-24px.png) per accedere alle proprietà del flusso di lavoro e selezionare la sezione **[!UICONTROL Execution]**.

![](assets/wkf_execution_6.png)

Le opzioni possibili sono:

* **[!UICONTROL Default affinity]**: questo campo consente di forzare l&#39;esecuzione di un flusso di lavoro o di un&#39;attività di workflow su un computer specifico.

* **[!UICONTROL History in days]**: specifica il numero di giorni dopo i quali la cronologia deve essere eliminata. La cronologia contiene elementi correlati al flusso di lavoro: registri, attività, eventi (oggetti tecnici collegati all&#39;operazione del flusso di lavoro), nonché file scaricati dall&#39;attività **[!UICONTROL Transfer file]**. Il valore predefinito è 30 giorni per i modelli di flusso di lavoro predefiniti.

   La rimozione della cronologia viene eseguita dal flusso di lavoro tecnico di pulizia del database, che viene eseguito quotidianamente per impostazione predefinita (vedere [Elenco di flussi di lavoro tecnici](../../administration/using/technical-workflows.md)).

   >[!IMPORTANT]
   >
   >Se il campo **[!UICONTROL History in days]** viene lasciato vuoto, il relativo valore verrà considerato come &quot;1&quot;, il che significa che la cronologia verrà eliminata dopo 1 giorno.

* **[!UICONTROL Save SQL queries in the log]**: consente di salvare le query SQL dal flusso di lavoro nei registri.

* **[!UICONTROL Keep interim results]**: selezionate questa opzione per visualizzare i dettagli delle transizioni.

   >[!CAUTION]
   >
   >Questa opzione consuma molto spazio su disco ed è progettata per consentire la creazione di un flusso di lavoro, garantendone la corretta configurazione e il giusto comportamento. Lascia deselezionata questa opzione nelle istanze di produzione.

* **[!UICONTROL Execute in the engine (do not use in production)]**: consente di eseguire il flusso di lavoro localmente, a scopo di verifica dell’ambiente di sviluppo.

* **[!UICONTROL Severity]**: consente di specificare un livello di priorità per l’esecuzione di flussi di lavoro nell’istanza di Adobe Campaign . Questo campo è utilizzato dai team  Adobe solo a scopo di monitoraggio.

La sezione **[!UICONTROL Error management]** offre opzioni aggiuntive che consentono di gestire il comportamento dei flussi di lavoro in caso di errori. Queste opzioni sono descritte dettagliatamente nella sezione [Gestione errori](../../automating/using/monitoring-workflow-execution.md#error-management).
