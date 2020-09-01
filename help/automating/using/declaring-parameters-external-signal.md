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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51e98bb6212ad96d9c11b848df9dcad25b3f1b61
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 5%

---


# Dichiarazione dei parametri nell&#39;attività del segnale esterno {#declaring-the-parameters-in-the-external-signal-activity}

Il primo passo per chiamare un flusso di lavoro con parametri consiste nel dichiararlo in un&#39; **[!UICONTROL External signal]** attività.

1. Open the **[!UICONTROL External signal]** activity, then select the **[!UICONTROL Parameters]** tab.
1. Fate clic sul **[!UICONTROL Create element]** pulsante, quindi specificate il nome e il tipo di ogni parametro.

   >[!CAUTION]
   >
   >Accertatevi che il nome e il numero di parametri siano identici a quelli definiti per la chiamata al flusso di lavoro (vedete [](../../automating/using/defining-parameters-calling-workflow.md)). Inoltre, i tipi di parametri devono essere coerenti con i valori previsti.

   ![](assets/extsignal_declaringparameters_1.png)

1. Una volta dichiarati i parametri, completate la configurazione del flusso di lavoro, quindi eseguitela.
