---
title: Leggi pubblico
description: L’attività Read audience ti consente di recuperare un pubblico esistente e di perfezionarlo applicando condizioni di filtro aggiuntive.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 9a77a2c7-cc1c-416f-8103-bb7d5c84a373
TQID: https://experienceleague.adobe.com/mPVqmIC2ovLQdipvGbwI7GCZXejCTyCgwBYWFbCeTRg
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 206
ht-degree: 86%

---

# Leggere tipi di pubblico{#read-audience}

## Descrizione {#description}

![](assets/prefill.png)

L’attività **[!UICONTROL Read audience]** ti consente di recuperare un pubblico esistente e di perfezionarlo applicando condizioni di filtro aggiuntive.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Read audience]** è una versione più semplice di quella **[!UICONTROL Query]**, progettata per i casi in cui devi selezionare solo un pubblico esistente.

**Argomenti correlati**

* [Caso d’uso: unione di due tipi di pubblico perfezionati](../../automating/using/union-on-two-refined-audiences.md)
* [Caso d’uso: riconciliare un pubblico di tipo File con il database](../../automating/using/reconcile-file-audience-with-database.md)

## Configurazione {#configuration}

1. Rilascia un’attività **[!UICONTROL Read audience]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Seleziona il pubblico da recuperare dalla scheda **[!UICONTROL Properties]**.

   Puoi recuperare i seguenti tipi di pubblico: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** e **[!UICONTROL Experience Cloud]**. Per ulteriori informazioni sui tipi di pubblico, consulta la documentazione [Audiences](../../audiences/using/about-audiences.md).

   L’opzione **[!UICONTROL Use a dynamic audience]** ti consente di definire il nome del pubblico di cui eseguire il targeting in base alle variabili degli eventi del flusso di lavoro. Per ulteriori informazioni, consulta la sezione [questa pagina](../../automating/using/customizing-workflow-external-parameters.md).

   ![](assets/readaudience_activity1.png)

1. Se desideri applicare un filtro aggiuntivo al pubblico selezionato, aggiungi condizioni tramite la scheda **[!UICONTROL Source filtering]** dell’attività.

   Per ulteriori informazioni sulla creazione di condizioni di filtro, consulta la documentazione [Creazione di query](../../automating/using/editing-queries.md#creating-queries).

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.
