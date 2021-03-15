---
solution: Campaign Standard
product: campaign
title: Comandi di esecuzione
description: Scopri come utilizzare i comandi di esecuzione dei flussi di lavoro.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Flussi di lavoro
role: Architetto dati
level: Principiante
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 2%

---


# Comandi di esecuzione {#execution-commands}

Le icone nella barra delle azioni ti consentono di avviare, tracciare e modificare l’esecuzione di un flusso di lavoro. Vedere [Barra delle azioni](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Le azioni disponibili sono le seguenti:

**Inizio**

Il pulsante ![](assets/play_darkgrey-24px.png) inizia l&#39;esecuzione di un flusso di lavoro, che assume lo stato **In corso** (blu). Se il flusso di lavoro è stato messo in pausa, viene ripreso, altrimenti viene avviato e le attività iniziali vengono quindi attivate.

>[!NOTE]
>
>L&#39;avvio è un processo asincrono: la richiesta viene salvata e verrà elaborata il prima possibile dal motore di esecuzione del flusso di lavoro.

**Pausa**

Il pulsante ![](assets/pause_darkgrey-24px.png) mette in pausa l’esecuzione. Il flusso di lavoro assume lo stato **Avviso** (giallo). Nessuna nuova attività verrà attivata finché non sarà ripresa, ma le operazioni in corso non saranno sospese.

**Interruzione**

Il pulsante ![](assets/stop_darkgrey-24px.png) arresta un flusso di lavoro in esecuzione, che assume lo stato **Finished** (verde). Le operazioni in corso vengono interrotte, se possibile, e le importazioni o le query SQL in corso vengono immediatamente annullate. Non è possibile riprendere dal flusso di lavoro dalla stessa posizione in cui è stato interrotto.

**Riavvio**

Il pulsante ![](assets/pauseplay_darkgrey-24px.png) comporta l’arresto e il riavvio di un flusso di lavoro. Nella maggior parte dei casi, questo consente di riavviare più rapidamente. Può essere utile anche automatizzare il riavvio una volta che l&#39;arresto richiede un certo tempo, perché il pulsante ![](assets/play_darkgrey-24px.png) è disponibile solo quando l&#39;arresto è effettivo.

Quando selezioni una o più attività in un flusso di lavoro, puoi eseguire altre azioni, ad esempio:

**Esecuzione immediata**

Il pulsante ![](assets/pending_darkgrey-24px.png) avvia tutte le attività in sospeso selezionate il prima possibile.

**Esecuzione normale**

Il pulsante ![](assets/check_darkgrey-24px.png) riattiva tutte le attività in pausa o disattivate.

**Esecuzione sospesa**

Il pulsante ![](assets/check_pause_darkgrey-24px.png) mette in pausa il flusso di lavoro nell’attività selezionata: questa attività e tutte quelle che la seguono (nello stesso ramo) non vengono eseguite.

**Nessuna esecuzione**

Il pulsante ![](assets/checkdisable.png) disattiva tutte le attività selezionate.

>[!NOTE]
>
>Le azioni rapide ti consentono di accedere a diverse azioni relative a una particolare attività e vengono visualizzate quando selezioni un’attività.
