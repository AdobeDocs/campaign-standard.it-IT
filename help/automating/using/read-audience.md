---
solution: Campaign Standard
product: campaign
title: Read audience
description: L’attività Read audience ti consente di recuperare un pubblico esistente e di perfezionarlo applicando condizioni di filtro aggiuntive.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 87%

---


# Read audience{#read-audience}

## Descrizione {#description}

![](assets/prefill.png)

L’attività **[!UICONTROL Read audience]** ti consente di recuperare un pubblico esistente e di perfezionarlo applicando condizioni di filtro aggiuntive.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Read audience]** è una versione più semplice di quella **[!UICONTROL Query]**, progettata per i casi in cui devi selezionare solo un pubblico esistente.

**Argomenti correlati**

* [Caso di utilizzo: Unione su due tipi di pubblico raffinati](../../automating/using/union-on-two-refined-audiences.md)
* [Caso di utilizzo: Riconciliare un pubblico di file con il database](../../automating/using/reconcile-file-audience-with-database.md)

## Configurazione {#configuration}

1. Rilascia un’attività **[!UICONTROL Read audience]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Seleziona il pubblico da recuperare dalla scheda **[!UICONTROL Properties]**.

   Puoi recuperare i seguenti tipi di pubblico: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** e **[!UICONTROL Experience Cloud]**. Per ulteriori informazioni sui tipi di pubblico, consulta la documentazione [Audiences](../../audiences/using/about-audiences.md).

   L’opzione **[!UICONTROL Use a dynamic audience]** ti consente di definire il nome del pubblico di cui eseguire il targeting in base alle variabili degli eventi del flusso di lavoro. For more on this, refer to [this page](../../automating/using/customizing-workflow-external-parameters.md) section.

   ![](assets/readaudience_activity1.png)

1. Se desideri applicare un filtro aggiuntivo al pubblico selezionato, aggiungi condizioni tramite la scheda **[!UICONTROL Source filtering]** dell’attività.

   Per ulteriori informazioni sulla creazione di condizioni di filtro, consulta la documentazione [Creazione di query](../../automating/using/editing-queries.md#creating-queries).

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.
