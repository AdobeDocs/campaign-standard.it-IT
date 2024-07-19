---
title: Dichiarazione dei parametri nell’attività External signal
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: e6148b40-f608-4aab-81f6-756608c6828e
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 0%

---

# Dichiarazione dei parametri nell’attività External signal {#declaring-the-parameters-in-the-external-signal-activity}

Il primo passaggio per richiamare un flusso di lavoro con parametri consiste nel dichiararli in un&#39;attività **[!UICONTROL External signal]**.

1. Apri l&#39;attività **[!UICONTROL External signal]**, quindi seleziona la scheda **[!UICONTROL Parameters]**.
1. Fare clic sul pulsante **[!UICONTROL Create element]**, quindi specificare il nome e il tipo di ciascun parametro.

   >[!CAUTION]
   >
   >Verificare che il nome e il numero di parametri siano identici a quelli definiti durante la chiamata al flusso di lavoro (vedere [questa pagina](../../automating/using/defining-parameters-calling-workflow.md)). Inoltre, i tipi di parametri devono essere coerenti con i valori previsti.

   ![](assets/extsignal_declaringparameters_1.png)

1. Una volta dichiarati i parametri, completa la configurazione del flusso di lavoro, quindi eseguila.
