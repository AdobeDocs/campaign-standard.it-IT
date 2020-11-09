---
title: Chiamata di un flusso di lavoro con parametri esterni
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
translation-type: tm+mt
source-git-commit: 121b36056317cc89909607220f988c02ae470f08
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 13%

---


# Definizione dei parametri durante la chiamata del flusso di lavoro {#defining-the-parameters-when-calling-the-workflow}

In questa sezione viene illustrato come definire i parametri durante la chiamata di un flusso di lavoro. Per ulteriori informazioni su come eseguire questa operazione da una chiamata API, consulta la documentazione [](../../api/using/triggering-a-signal-activity.md)REST APIs.

Prima di definire i parametri, accertatevi che:

* I parametri sono stati dichiarati nell&#39; **[!UICONTROL External Signal]** attività. Consulta [questa pagina](../../automating/using/declaring-parameters-external-signal.md).
* Il flusso di lavoro contenente l&#39;attività del segnale è in esecuzione.

Per configurare l&#39; **[!UICONTROL End]** attività, attenetevi alla procedura seguente:

1. Open the **[!UICONTROL End]** activity, then select the **[!UICONTROL External signal]** tab.
1. Seleziona il flusso di lavoro e l’attività del segnale esterno da chiamare.
1. Fate clic sul **[!UICONTROL Create element]** pulsante per aggiungere un parametro, quindi compilate il relativo nome e valore.

   * **[!UICONTROL Name]**: il nome dichiarato nell&#39; **[!UICONTROL External signal]** attività (consultate [questa pagina](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: il valore che si desidera assegnare al parametro. Il valore deve seguire la sintassi **** Standard, descritta in [questa sezione](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Make sure that all the parameters have been declared in the **[!UICONTROL External signal]** activity. In caso contrario, si verificherà un errore durante l’esecuzione dell’attività.

1. Una volta definiti i parametri, confermate l&#39;attività, quindi salvate il flusso di lavoro.
