---
title: Definizione dei parametri durante la chiamata del flusso di lavoro
description: Questa sezione descrive come chiamare un flusso di lavoro con parametri esterni.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: f7de0186-4136-4603-8f80-9f58c641cd9d
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 13%

---

# Definizione dei parametri durante la chiamata del flusso di lavoro {#defining-the-parameters-when-calling-the-workflow}

Questa sezione descrive come definire i parametri durante la chiamata di un flusso di lavoro. Per ulteriori informazioni su come eseguire questa operazione da una chiamata API, consulta [Documentazione API REST](../../api/using/triggering-a-signal-activity.md).

Prima di definire i parametri, assicurati che:

* I parametri sono stati dichiarati nel **[!UICONTROL External Signal]** attività. Consulta [questa pagina](../../automating/using/declaring-parameters-external-signal.md).
* Il flusso di lavoro contenente l’attività del segnale è in esecuzione.

Per configurare le **[!UICONTROL End]** , segui i passaggi seguenti:

1. Apri **[!UICONTROL End]** , quindi seleziona la **[!UICONTROL External signal]** scheda .
1. Seleziona il flusso di lavoro e l’attività del segnale esterno che desideri chiamare.
1. Fai clic sul pulsante **[!UICONTROL Create element]** per aggiungere un parametro, compila il relativo nome e valore.

   * **[!UICONTROL Name]**: il nome dichiarato nel **[!UICONTROL External signal]** attività (vedi [questa pagina](../../automating/using/declaring-parameters-external-signal.md)).
   * **[!UICONTROL Value]**: il valore da assegnare al parametro. Il valore deve seguire la **Sintassi standard**, descritto in [questa sezione](../../automating/using/advanced-expression-editing.md#standard-syntax).

   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Assicurati che tutti i parametri siano stati dichiarati nel **[!UICONTROL External signal]** attività. In caso contrario, si verificherà un errore durante l’esecuzione dell’attività.

1. Una volta definiti i parametri, conferma l’attività, quindi salva il flusso di lavoro.
