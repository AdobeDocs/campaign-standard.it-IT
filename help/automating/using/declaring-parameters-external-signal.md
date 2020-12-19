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


# Dichiarazione dei parametri nell&#39;attività del segnale esterno {#declaring-the-parameters-in-the-external-signal-activity}

Il primo passo per chiamare un flusso di lavoro con i parametri è dichiararlo in un&#39;attività **[!UICONTROL External signal]**.

1. Aprite l&#39;attività **[!UICONTROL External signal]**, quindi selezionate la scheda **[!UICONTROL Parameters]**.
1. Fate clic sul pulsante **[!UICONTROL Create element]**, quindi specificate il nome e il tipo di ciascun parametro.

   >[!CAUTION]
   >
   >Accertatevi che il nome e il numero di parametri siano identici a quelli definiti per la chiamata al flusso di lavoro (consultate [this page](../../automating/using/defining-parameters-calling-workflow.md)). Inoltre, i tipi di parametri devono essere coerenti con i valori previsti.

   ![](assets/extsignal_declaringparameters_1.png)

1. Una volta dichiarati i parametri, completate la configurazione del flusso di lavoro, quindi eseguitela.
