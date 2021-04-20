---
solution: Campaign Standard
product: campaign
title: Gestione delle opzioni di esecuzione
description: Scopri come gestire le opzioni di esecuzione dei flussi di lavoro.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 13%

---


# Gestione delle opzioni di esecuzione {#managing-execution-options}

Per modificare le opzioni di esecuzione di un flusso di lavoro, utilizza il pulsante ![](assets/edit_darkgrey-24px.png) per accedere alle proprietà del flusso di lavoro e seleziona la sezione **[!UICONTROL Execution]** .

![](assets/wkf_execution_6.png)

Le opzioni possibili sono:

* **[!UICONTROL Default affinity]**: questo campo ti consente di forzare l’esecuzione di un flusso di lavoro o di un’attività del flusso di lavoro su un determinato computer.

* **[!UICONTROL History in days]**: specifica il numero di giorni dopo i quali la cronologia deve essere eliminata. La cronologia contiene gli elementi relativi al flusso di lavoro : registri, attività, eventi (oggetti tecnici collegati all’operazione del flusso di lavoro), nonché file scaricati dall’attività **[!UICONTROL Transfer file]**. Il valore predefinito è 30 giorni per i modelli di flusso di lavoro predefiniti.

   L&#39;eliminazione della cronologia viene eseguita dal flusso di lavoro tecnico Database cleanup , che viene eseguito quotidianamente per impostazione predefinita (vedere [Elenco dei flussi di lavoro tecnici](../../administration/using/technical-workflows.md)).

   >[!IMPORTANT]
   >
   >Se il campo **[!UICONTROL History in days]** viene lasciato vuoto, il relativo valore verrà considerato come &quot;1&quot;, il che significa che la cronologia verrà eliminata dopo 1 giorno.

* **[!UICONTROL Save SQL queries in the log]**: consente di salvare le query SQL dal flusso di lavoro nei registri.

* **[!UICONTROL Keep interim results]**: seleziona questa opzione se desideri visualizzare i dettagli delle transizioni.

   >[!CAUTION]
   >
   >Questa opzione consuma molto spazio su disco ed è progettata per consentire la creazione di un flusso di lavoro, garantendone la corretta configurazione e il giusto comportamento. Lascia deselezionata questa opzione nelle istanze di produzione.

* **[!UICONTROL Execute in the engine (do not use in production)]**: consente di eseguire il flusso di lavoro localmente, a scopo di test dell’ambiente di sviluppo.

* **[!UICONTROL Severity]**: consente di specificare un livello di priorità per l’esecuzione dei flussi di lavoro nell’istanza Adobe Campaign. Questo campo viene utilizzato dai team di Adobe solo a scopo di monitoraggio.

La sezione **[!UICONTROL Error management]** fornisce opzioni aggiuntive che ti consentono di gestire il comportamento dei flussi di lavoro in caso di errori. Queste opzioni sono descritte in dettaglio nella sezione [Gestione errori](../../automating/using/monitoring-workflow-execution.md#error-management) .
