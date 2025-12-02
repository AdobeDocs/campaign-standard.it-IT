---
title: Comandi di esecuzione
description: Scopri come utilizzare i comandi di esecuzione dei flussi di lavoro.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: fddd88b1-603a-465b-b5e7-624632c0d5cd
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 17%

---

# Comandi di esecuzione {#execution-commands}

Le icone nella barra delle azioni ti consentono di avviare, tracciare e modificare l’esecuzione di un flusso di lavoro. Vedi [Barra delle azioni](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Le azioni disponibili sono le seguenti:

**Inizio**

Il pulsante ![](assets/play_darkgrey-24px.png) avvia l&#39;esecuzione di un flusso di lavoro che assume lo stato **In corso** (blu). Se il flusso di lavoro è stato messo in pausa, viene ripristinato, altrimenti viene avviato e le attività iniziali vengono quindi attivate.

>[!NOTE]
>
>L’avvio è un processo asincrono: la richiesta viene salvata e verrà elaborata il prima possibile dal motore di esecuzione del flusso di lavoro.

**Pausa**

Il pulsante ![](assets/pause_darkgrey-24px.png) sospende l&#39;esecuzione. Il flusso di lavoro assume lo stato **Avviso** (giallo). Non verranno attivate nuove attività finché non viene ripresa, ma le operazioni in corso non vengono sospese.

**Interrompi**

Il pulsante ![](assets/stop_darkgrey-24px.png) interrompe un flusso di lavoro in esecuzione che assume lo stato **Completato** (verde). Le operazioni in corso vengono interrotte, se possibile, e le importazioni o le query SQL in corso vengono immediatamente annullate. Non è possibile riprendere dal flusso di lavoro dalla stessa posizione in cui è stato interrotto.

**Riavvia**

Il pulsante ![](assets/pauseplay_darkgrey-24px.png) prevede l&#39;arresto e il riavvio di un flusso di lavoro. Nella maggior parte dei casi, questo consente di riavviare il sistema più rapidamente. Può inoltre essere utile automatizzare il riavvio quando l&#39;arresto richiede un certo periodo di tempo, perché il pulsante ![](assets/play_darkgrey-24px.png) è disponibile solo quando l&#39;arresto è effettivo.

Quando selezioni una o più attività in un flusso di lavoro, puoi eseguire altre azioni, ad esempio:

**Esecuzione immediata**

Il pulsante ![](assets/pending_darkgrey-24px.png) avvia tutte le attività in sospeso selezionate il prima possibile.

**Esecuzione normale**

Il pulsante ![](assets/check_darkgrey-24px.png) riattiva tutte le attività in pausa o disattivate.

**Esecuzione sospesa**

Il pulsante ![](assets/check_pause_darkgrey-24px.png) mette in pausa il flusso di lavoro nell&#39;attività selezionata: questa attività e tutte quelle che la seguono (nello stesso ramo) non vengono eseguite.

**Nessuna esecuzione**

Il pulsante ![](assets/checkdisable.png) disattiva tutte le attività selezionate.

>[!NOTE]
>
>Le azioni rapide consentono di accedere a diverse azioni relative a una particolare attività e vengono visualizzate quando si seleziona un’attività.
