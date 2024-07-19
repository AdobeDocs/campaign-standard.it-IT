---
title: Definizione dei parametri durante la chiamata del flusso di lavoro
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 13%

---

# Definizione dei parametri durante la chiamata del flusso di lavoro {#defining-the-parameters-when-calling-the-workflow}

Questa sezione descrive come definire i parametri quando si chiama un flusso di lavoro. Per ulteriori informazioni su come eseguire questa operazione da una chiamata API, consulta la [documentazione API REST](../../api/using/triggering-a-signal-activity.md).

Prima di definire i parametri, assicurati che:

* Parametri dichiarati nell&#39;attività **[!UICONTROL External Signal]**. Consulta [questa pagina](../../automating/using/declaring-parameters-external-signal.md).
* Il flusso di lavoro contenente l’attività del segnale è in esecuzione.

Per configurare l&#39;attività **[!UICONTROL End]**, eseguire la procedura seguente:

1. Apri l&#39;attività **[!UICONTROL End]**, quindi seleziona la scheda **[!UICONTROL External signal]**.
1. Seleziona il flusso di lavoro e l’attività del segnale esterno che desideri chiamare.
1. Fare clic sul pulsante **[!UICONTROL Create element]** per aggiungere un parametro, quindi inserirne il nome e il valore.

   * **[!UICONTROL Name]**: nome dichiarato nell&#39;attività **[!UICONTROL External signal]** (vedere [questa pagina](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: il valore che si desidera assegnare al parametro. Il valore deve seguire la **sintassi standard**, descritta in [questa sezione](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Verificare che tutti i parametri siano stati dichiarati nell&#39;attività **[!UICONTROL External signal]**. In caso contrario, si verificherà un errore durante l’esecuzione dell’attività.

1. Una volta definiti i parametri, conferma l’attività, quindi salva il flusso di lavoro.
