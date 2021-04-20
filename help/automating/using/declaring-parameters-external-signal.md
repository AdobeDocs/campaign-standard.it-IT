---
solution: Campaign Standard
product: campaign
title: Chiamata di un flusso di lavoro con parametri esterni
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 6%

---


# Dichiarazione dei parametri nell&#39;attività del segnale esterno {#declaring-the-parameters-in-the-external-signal-activity}

Il primo passaggio per chiamare un flusso di lavoro con parametri consiste nel dichiararli in un’attività **[!UICONTROL External signal]** .

1. Apri l’attività **[!UICONTROL External signal]**, quindi seleziona la scheda **[!UICONTROL Parameters]** .
1. Fai clic sul pulsante **[!UICONTROL Create element]** , quindi specifica il nome e il tipo di ciascun parametro.

   >[!CAUTION]
   >
   >Assicurati che il nome e il numero di parametri siano identici a quelli definiti durante la chiamata al flusso di lavoro (consulta [questa pagina](../../automating/using/defining-parameters-calling-workflow.md)). Inoltre, i tipi di parametri devono essere coerenti con i valori previsti.

   ![](assets/extsignal_declaringparameters_1.png)

1. Una volta dichiarati i parametri, completa la configurazione del flusso di lavoro, quindi eseguiscila.
