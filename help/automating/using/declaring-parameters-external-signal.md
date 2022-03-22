---
title: Dichiarazione dei parametri nell’attività del segnale esterno
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

# Dichiarazione dei parametri nell’attività del segnale esterno {#declaring-the-parameters-in-the-external-signal-activity}

Il primo passaggio per chiamare un flusso di lavoro con parametri consiste nel dichiararlo in un **[!UICONTROL External signal]** attività.

1. Apri **[!UICONTROL External signal]** , quindi seleziona la **[!UICONTROL Parameters]** scheda .
1. Fai clic sul pulsante **[!UICONTROL Create element]** quindi specifica il nome e il tipo di ciascun parametro.

   >[!CAUTION]
   >
   >Assicurati che il nome e il numero di parametri siano identici a quelli definiti durante la chiamata al flusso di lavoro (vedi [questa pagina](../../automating/using/defining-parameters-calling-workflow.md)). Inoltre, i tipi di parametri devono essere coerenti con i valori previsti.

   ![](assets/extsignal_declaringparameters_1.png)

1. Una volta dichiarati i parametri, completa la configurazione del flusso di lavoro, quindi eseguiscila.
