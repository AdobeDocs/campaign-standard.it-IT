---
title: Chiamata di un flusso di lavoro con parametri esterni
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 13%

---

# Definizione dei parametri durante la chiamata del flusso di lavoro {#defining-the-parameters-when-calling-the-workflow}

Questa sezione descrive come definire i parametri durante la chiamata di un flusso di lavoro. Per ulteriori informazioni su come eseguire questa operazione da una chiamata API, consulta la documentazione [REST APIs](../../api/using/triggering-a-signal-activity.md).

Prima di definire i parametri, assicurati che:

* I parametri sono stati dichiarati nell’attività **[!UICONTROL External Signal]** . Consulta [questa pagina](../../automating/using/declaring-parameters-external-signal.md).
* Il flusso di lavoro contenente l’attività del segnale è in esecuzione.

Per configurare l&#39;attività **[!UICONTROL End]**, segui i passaggi seguenti:

1. Apri l’attività **[!UICONTROL End]**, quindi seleziona la scheda **[!UICONTROL External signal]** .
1. Seleziona il flusso di lavoro e l’attività del segnale esterno che desideri chiamare.
1. Fai clic sul pulsante **[!UICONTROL Create element]** per aggiungere un parametro, quindi compila il relativo nome e valore.

   * **[!UICONTROL Name]**: il nome dichiarato nell’ **[!UICONTROL External signal]** attività (consulta  [questa pagina](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: il valore da assegnare al parametro. Il valore deve seguire la **Sintassi standard**, descritta in [questa sezione](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Assicurati che tutti i parametri siano stati dichiarati nell&#39;attività **[!UICONTROL External signal]**. In caso contrario, si verificherà un errore durante l’esecuzione dell’attività.

1. Una volta definiti i parametri, conferma l’attività, quindi salva il flusso di lavoro.
