---
title: Leggi pubblico
description: L'attività Leggi audience consente di recuperare un'audience esistente e di perfezionarla applicando ulteriori condizioni di filtro.
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
ht-degree: 3%

---


# Leggi pubblico{#read-audience}

## Descrizione {#description}

![](assets/prefill.png)

L&#39; **[!UICONTROL Read audience]** attività consente di recuperare un&#39;audience esistente e di perfezionarla applicando ulteriori condizioni di filtro.

## Contesto di utilizzo {#context-of-use}

L&#39; **[!UICONTROL Read audience]** attività è una versione più semplice dell&#39; **[!UICONTROL Query]** attività progettata per i casi in cui è solo necessario selezionare un&#39;audience esistente.

**Argomenti correlati**

* [Caso di utilizzo: Unione su due tipi di pubblico raffinati](../../automating/using/union-on-two-refined-audiences.md)
* [Caso di utilizzo: Riconciliare un pubblico di file con il database](../../automating/using/reconcile-file-audience-with-database.md)

## Configurazione {#configuration}

1. Rilasciate un&#39; **[!UICONTROL Read audience]** attività nel flusso di lavoro.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Selezionate l&#39;audience da recuperare dalla **[!UICONTROL Properties]** scheda.

   Puoi recuperare tipi di pubblico dei seguenti tipi: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** e **[!UICONTROL Experience Cloud]**. Per ulteriori informazioni sui tipi di pubblico, consulta la documentazione [Audiences](../../audiences/using/about-audiences.md) .

   L&#39; **[!UICONTROL Use a dynamic audience]** opzione consente di definire il nome dell&#39;audience di cui eseguire il targeting in base alle variabili degli eventi del flusso di lavoro. Per ulteriori informazioni, vedere la sezione [Personalizzazione delle attività con variabili](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) di eventi.

   ![](assets/readaudience_activity1.png)

1. Se desiderate applicare un filtro aggiuntivo all&#39;audience selezionata, aggiungete condizioni tramite la **[!UICONTROL Source filtering]** scheda dell&#39;attività.

   Per ulteriori informazioni sulla creazione di condizioni di filtraggio, consultare la documentazione [Creazione di query](../../automating/using/editing-queries.md#creating-queries) .

1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.
