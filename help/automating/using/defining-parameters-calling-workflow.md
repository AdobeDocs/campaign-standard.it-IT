---
solution: Campaign Standard
product: campaign
title: Chiamata di un flusso di lavoro con parametri esterni
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 13%

---


# Definizione dei parametri durante la chiamata del flusso di lavoro {#defining-the-parameters-when-calling-the-workflow}

In questa sezione viene illustrato come definire i parametri durante la chiamata di un flusso di lavoro. Per ulteriori informazioni su come eseguire questa operazione da una chiamata API, fare riferimento alla documentazione [REST APIs](../../api/using/triggering-a-signal-activity.md).

Prima di definire i parametri, accertatevi che:

* I parametri sono stati dichiarati nell&#39;attività **[!UICONTROL External Signal]**. Consulta [questa pagina](../../automating/using/declaring-parameters-external-signal.md).
* Il flusso di lavoro contenente l&#39;attività del segnale è in esecuzione.

Per configurare l&#39;attività **[!UICONTROL End]**, attenetevi alla procedura seguente:

1. Aprite l&#39;attività **[!UICONTROL End]**, quindi selezionate la scheda **[!UICONTROL External signal]**.
1. Seleziona il flusso di lavoro e l’attività del segnale esterno da chiamare.
1. Fate clic sul pulsante **[!UICONTROL Create element]** per aggiungere un parametro, quindi compilatene il nome e il valore.

   * **[!UICONTROL Name]**: il nome dichiarato nell&#39; **[!UICONTROL External signal]** attività (consultate  [questa pagina](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: il valore che si desidera assegnare al parametro. Il valore deve seguire la **sintassi standard**, descritta in [questa sezione](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Accertatevi che tutti i parametri siano stati dichiarati nell&#39;attività **[!UICONTROL External signal]**. In caso contrario, si verificherà un errore durante l’esecuzione dell’attività.

1. Una volta definiti i parametri, confermate l&#39;attività, quindi salvate il flusso di lavoro.
