---
title: Definizione dei parametri durante la chiamata del flusso di lavoro
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
TQID: https://experienceleague.adobe.com/-YjlK1Op8P08sxb--BOHl8AWyciX4BqPnCPQ3lpD3Co
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2: id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 189
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
