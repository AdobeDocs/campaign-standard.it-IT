---
title: Comandi di esecuzione
description: Scopri come utilizzare i comandi di esecuzione dei flussi di lavoro.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 3%

---

# Comandi di esecuzione {#execution-commands}

Le icone nella barra delle azioni ti consentono di avviare, tracciare e modificare l’esecuzione di un flusso di lavoro. Vedi [Barra delle azioni](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Le azioni disponibili sono le seguenti:

**Inizio**

La ![](assets/play_darkgrey-24px.png) inizia l’esecuzione di un flusso di lavoro, che assume quindi **In corso** (blu). Se il flusso di lavoro è stato messo in pausa, viene ripreso, altrimenti viene avviato e le attività iniziali vengono quindi attivate.

>[!NOTE]
>
>L&#39;avvio è un processo asincrono: la richiesta viene salvata e verrà elaborata il prima possibile dal motore di esecuzione del flusso di lavoro.

**Pausa**

La ![](assets/pause_darkgrey-24px.png) mette in pausa l’esecuzione del pulsante. Il flusso di lavoro assume le **Avviso** (giallo). Nessuna nuova attività verrà attivata finché non sarà ripresa, ma le operazioni in corso non saranno sospese.

**Interruzione**

La ![](assets/stop_darkgrey-24px.png) il pulsante interrompe un flusso di lavoro in esecuzione, che assume quindi **Completato** (verde). Le operazioni in corso vengono interrotte, se possibile, e le importazioni o le query SQL in corso vengono immediatamente annullate. Non è possibile riprendere dal flusso di lavoro dalla stessa posizione in cui è stato interrotto.

**Riavvio**

La ![](assets/pauseplay_darkgrey-24px.png) Il pulsante comporta l’arresto, quindi il riavvio di un flusso di lavoro. Nella maggior parte dei casi, questo consente di riavviare più rapidamente. Può anche essere utile automatizzare il riavvio una volta che l&#39;arresto richiede un certo tempo, perché il ![](assets/play_darkgrey-24px.png) è disponibile solo quando l&#39;arresto è efficace.

Quando selezioni una o più attività in un flusso di lavoro, puoi eseguire altre azioni, ad esempio:

**Esecuzione immediata**

La ![](assets/pending_darkgrey-24px.png) avvia tutte le attività in sospeso selezionate il prima possibile.

**Esecuzione normale**

La ![](assets/check_darkgrey-24px.png) il pulsante riattiva tutte le attività in pausa o disattivate.

**Esecuzione sospesa**

La ![](assets/check_pause_darkgrey-24px.png) mette in pausa il flusso di lavoro nell’attività selezionata: questa attività e tutte quelle che la seguono (nello stesso ramo) non vengono eseguite.

**Nessuna esecuzione**

La ![](assets/checkdisable.png) consente di disattivare tutte le attività selezionate.

>[!NOTE]
>
>Le azioni rapide ti consentono di accedere a diverse azioni relative a una particolare attività e vengono visualizzate quando selezioni un’attività.
