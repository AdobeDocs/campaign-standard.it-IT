---
title: Read audience
description: L’attività Read audience ti consente di recuperare un pubblico esistente e di perfezionarlo applicando condizioni di filtro aggiuntive.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 92%

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

   L’opzione **[!UICONTROL Use a dynamic audience]** ti consente di definire il nome del pubblico di cui eseguire il targeting in base alle variabili degli eventi del flusso di lavoro. Per ulteriori informazioni, consulta la sezione [Personalizzazione di attività con variabili di eventi](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables).

   ![](assets/readaudience_activity1.png)

1. Se desideri applicare un filtro aggiuntivo al pubblico selezionato, aggiungi condizioni tramite la scheda **[!UICONTROL Source filtering]** dell’attività.

   Per ulteriori informazioni sulla creazione di condizioni di filtro, consulta la documentazione [Creazione di query](../../automating/using/editing-queries.md#creating-queries).

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.
