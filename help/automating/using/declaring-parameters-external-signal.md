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
source-wordcount: '108'
ht-degree: 5%

---


# Declaring the parameters in the External signal activity {#declaring-the-parameters-in-the-external-signal-activity}

Il primo passo per chiamare un flusso di lavoro con parametri consiste nel dichiararlo in un&#39; **[!UICONTROL External signal]** attività.

1. Open the **[!UICONTROL External signal]** activity, then select the **[!UICONTROL Parameters]** tab.
1. Fate clic sul **[!UICONTROL Create element]** pulsante, quindi specificate il nome e il tipo di ogni parametro.

   >[!CAUTION]
   >
   >Accertatevi che il nome e il numero di parametri siano identici a quelli definiti per la chiamata al flusso di lavoro (consultate [questa pagina](../../automating/using/defining-parameters-calling-workflow.md)). Inoltre, i tipi di parametri devono essere coerenti con i valori previsti.

   ![](assets/extsignal_declaringparameters_1.png)

1. Una volta dichiarati i parametri, completate la configurazione del flusso di lavoro, quindi eseguitela.
