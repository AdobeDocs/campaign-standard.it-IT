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
ht-degree: 17%

---

# Comandi di esecuzione {#execution-commands}

Le icone nella barra delle azioni ti consentono di avviare, tracciare e modificare l’esecuzione di un flusso di lavoro. Consulta [Barra delle azioni](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Le azioni disponibili sono le seguenti:

**Inizio**

Il ![](assets/play_darkgrey-24px.png) inizia l’esecuzione di un flusso di lavoro, che quindi assume il **In corso** (blu). Se il flusso di lavoro è stato messo in pausa, viene ripristinato, altrimenti viene avviato e le attività iniziali vengono quindi attivate.

>[!NOTE]
>
>L’avvio è un processo asincrono: la richiesta viene salvata e verrà elaborata il prima possibile dal motore di esecuzione del flusso di lavoro.

**Pausa**

Il ![](assets/pause_darkgrey-24px.png) sospende l’esecuzione. Il flusso di lavoro assume **Avvertenza** (giallo). Non verranno attivate nuove attività finché non viene ripresa, ma le operazioni in corso non vengono sospese.

**Interrompi**

Il ![](assets/stop_darkgrey-24px.png) arresta un flusso di lavoro in esecuzione, che assume il **Completato** (verde). Le operazioni in corso vengono interrotte, se possibile, e le importazioni o le query SQL in corso vengono immediatamente annullate. Non è possibile riprendere dal flusso di lavoro dalla stessa posizione in cui è stato interrotto.

**Riavvia**

Il ![](assets/pauseplay_darkgrey-24px.png) comporta l’arresto e il riavvio di un flusso di lavoro. Nella maggior parte dei casi, questo consente di riavviare il sistema più rapidamente. Può inoltre essere utile automatizzare il riavvio quando l&#39;arresto richiede un certo periodo di tempo, perché ![](assets/play_darkgrey-24px.png) è disponibile solo quando l&#39;interruzione è effettiva.

Quando selezioni una o più attività in un flusso di lavoro, puoi eseguire altre azioni, ad esempio:

**Esecuzione immediata**

Il ![](assets/pending_darkgrey-24px.png) Il pulsante avvia tutte le attività in sospeso selezionate il prima possibile.

**Esecuzione normale**

Il ![](assets/check_darkgrey-24px.png) riattiva tutte le attività in pausa o disattivate.

**Esecuzione sospesa**

Il ![](assets/check_pause_darkgrey-24px.png) pulsante mette in pausa il flusso di lavoro nell’attività selezionata: questa attività e tutte quelle che la seguono (nello stesso ramo) non vengono eseguite.

**Nessuna esecuzione**

Il ![](assets/checkdisable.png) disattiva tutte le attività selezionate.

>[!NOTE]
>
>Le azioni rapide consentono di accedere a diverse azioni relative a una particolare attività e vengono visualizzate quando si seleziona un’attività.
