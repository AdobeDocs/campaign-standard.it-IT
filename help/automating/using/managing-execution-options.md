---
title: Gestione delle opzioni di esecuzione
description: Scopri come gestire le opzioni di esecuzione dei flussi di lavoro.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: b0cc38fe-cf71-4350-8b4e-7daf0bf94066
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 8%

---

# Gestione delle opzioni di esecuzione {#managing-execution-options}

Per modificare le opzioni di esecuzione di un workflow, utilizzare il pulsante ![](assets/edit_darkgrey-24px.png) per accedere alle proprietà del workflow e selezionare la sezione **[!UICONTROL Execution]**.

![](assets/wkf_execution_6.png)

Le opzioni possibili sono:

* **[!UICONTROL Default affinity]**: questo campo consente di forzare l&#39;esecuzione di un flusso di lavoro o di un&#39;attività del flusso di lavoro su un computer specifico.

* **[!UICONTROL History in days]**: specifica il numero di giorni dopo i quali la cronologia deve essere eliminata. La cronologia contiene elementi correlati al flusso di lavoro: registri, attività, eventi (oggetti tecnici collegati all&#39;operazione del flusso di lavoro), nonché file scaricati dall&#39;attività **[!UICONTROL Transfer file]**. Per i modelli di flusso di lavoro preconfigurati, il valore predefinito è 30 giorni.

  La rimozione della cronologia viene eseguita dal flusso di lavoro tecnico per la pulizia del database, eseguito per impostazione predefinita ogni giorno (vedere [Elenco dei flussi di lavoro tecnici](../../administration/using/technical-workflows.md)).

  >[!IMPORTANT]
  >
  >Se il campo **[!UICONTROL History in days]** viene lasciato vuoto, il relativo valore verrà considerato come &quot;1&quot;, il che significa che la cronologia verrà eliminata dopo 1 giorno.

* **[!UICONTROL Save SQL queries in the log]**: consente di salvare le query SQL dal flusso di lavoro nei registri.

* **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]**: selezionare questa opzione se si desidera registrare l&#39;intero piano di esecuzione. Per impostazione predefinita, è disabilitata.

  Per ulteriori informazioni su questa opzione, consulta questa [sezione](#diagnostic-mode).

* **[!UICONTROL Keep interim results]**: selezionare questa opzione se si desidera visualizzare i dettagli delle transizioni.

  >[!CAUTION]
  >
  >Questa opzione consuma molto spazio su disco ed è progettata per consentire la creazione di un flusso di lavoro, garantendone la corretta configurazione e il giusto comportamento. Lascia deselezionata questa opzione nelle istanze di produzione.

* **[!UICONTROL Execute in the engine (do not use in production)]**: consente di eseguire il flusso di lavoro localmente, a scopo di test dell&#39;ambiente di sviluppo.

* **[!UICONTROL Severity]**: consente di specificare un livello di priorità per l&#39;esecuzione dei flussi di lavoro nell&#39;istanza Adobe Campaign. Questo campo viene utilizzato dai team di Adobe solo a scopo di monitoraggio.

La sezione **[!UICONTROL Error management]** fornisce opzioni aggiuntive che consentono di gestire il comportamento dei flussi di lavoro in caso di errori. Queste opzioni sono descritte in dettaglio nella sezione [Gestione degli errori](../../automating/using/monitoring-workflow-execution.md#error-management).

## Modalità diagnostica {#diagnostic-mode}

>[!CAUTION]
>
>Questa opzione può avere un impatto significativo sulle prestazioni del flusso di lavoro e deve essere utilizzata con moderazione.

Se abilitata, l&#39;opzione **[!UICONTROL Diagnostic mode (Log execution plan of long running queries and give recommendations)]** nella sezione **[!UICONTROL Execution]** delle proprietà del flusso di lavoro registra l&#39;intero piano di esecuzione se una query richiede più di un minuto.

![](assets/wkf_diagnostic.png)

Dopo aver abilitato questa opzione e aver avviato il flusso di lavoro, se la query richiede più di un minuto, il piano di esecuzione verrà registrato. È quindi possibile recuperare il piano di esecuzione utilizzando EXPLAIN ANALYZE.

Per ulteriori informazioni, consulta la [documentazione PostgreSQL](https://www.postgresql.org/docs/9.4/using-explain.html).

Se si dispone di un&#39;analisi sequenza in questa query, **[!UICONTROL Diagnostic mode]** fornirà anche suggerimenti per la creazione di un indice con l&#39;aiuto di un&#39;espressione di filtro.

>[!NOTE]
>
> Queste raccomandazioni sono destinate esclusivamente a scopi di riferimento e devono essere utilizzate con attenzione a seconda del caso d’uso.

![](assets/wkf_diagnostic_4.png)

Per attivare i consigli, è necessario soddisfare le due condizioni seguenti durante l’esecuzione del flusso di lavoro:

* La scansione della sequenza richiede più del 40% del tempo della query.

* Le righe risultanti dopo la scansione della sequenza sono meno dell’1 % delle righe totali presenti nella tabella.

È possibile gestire l&#39;opzione dal menu avanzato selezionando **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**:

* **[!UICONTROL Time of query execution (in milliseconds)(DiagnosticModeQueryTime)]**: dal campo **[!UICONTROL Value]**, è possibile impostare una nuova ora per l&#39;esecuzione della query. Se l’esecuzione della query supera questo valore, il piano di esecuzione verrà registrato.

  ![](assets/wkf_diagnostic_2.png)

* **[!UICONTROL Percentage of seq scan time (DiagnosticModeSeqScanPercentage)]**: dal campo **[!UICONTROL Value]**, è possibile modificare la percentuale di tempo di query che l&#39;analisi della sequenza deve richiedere per generare il consiglio.

  ![](assets/wkf_diagnostic_3.png)
