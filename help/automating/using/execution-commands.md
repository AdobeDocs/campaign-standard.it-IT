---
title: Comandi di esecuzione
description: Scopri come utilizzare i comandi di esecuzione dei flussi di lavoro.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 2%

---


# Comandi di esecuzione {#execution-commands}

Le icone nella barra delle azioni consentono di avviare, tenere traccia e modificare l&#39;esecuzione di un flusso di lavoro. Vedere Barra [](../../automating/using/workflow-interface.md#action-bar)delle azioni.

![](assets/wkf_execution_2.png)

Le azioni disponibili sono le seguenti:

**Inizio**

Il ![](assets/play_darkgrey-24px.png) pulsante avvia l&#39;esecuzione di un flusso di lavoro, che assume quindi lo stato **In corso** (blu). Se il flusso di lavoro è stato messo in pausa, viene ripreso, in caso contrario viene avviato e le attività iniziali vengono quindi attivate.

>[!NOTE]
>
>Avvio è un processo asincrono: la richiesta viene salvata e verrà elaborata al più presto dal motore di esecuzione del flusso di lavoro.

**Pausa**

Il ![](assets/pause_darkgrey-24px.png) pulsante mette in pausa l&#39;esecuzione. Il flusso di lavoro assume lo stato **Avviso** (giallo). Nessuna nuova attività verrà attivata fino alla sua ripresa, ma le operazioni in corso non saranno sospese.

**Interruzione**

Il ![](assets/stop_darkgrey-24px.png) pulsante interrompe un flusso di lavoro in esecuzione, che assumerà quindi lo stato **Completato** (verde). Le operazioni in corso vengono interrotte, se possibile, e le importazioni o le query SQL in corso vengono immediatamente annullate. Non è possibile riprendere il flusso di lavoro dalla stessa posizione in cui è stato interrotto.

**Riavvio**

Il ![](assets/pauseplay_darkgrey-24px.png) pulsante comporta l&#39;arresto, quindi il riavvio di un flusso di lavoro. Nella maggior parte dei casi, questo consente di riavviare più rapidamente. Può essere utile anche automatizzare il riavvio una volta che l&#39;arresto richiede un certo tempo, perché il ![](assets/play_darkgrey-24px.png) pulsante è disponibile solo quando l&#39;arresto è effettivo.

Quando si selezionano una o più attività in un flusso di lavoro, è possibile eseguire altre azioni, ad esempio:

**Esecuzione immediata**

Il ![](assets/pending_darkgrey-24px.png) pulsante avvia tutte le attività in sospeso selezionate il prima possibile.

**Esecuzione normale**

Il ![](assets/check_darkgrey-24px.png) pulsante riattiva tutte le attività in pausa o disattivate.

**Esecuzione sospesa**

Il ![](assets/check_pause_darkgrey-24px.png) pulsante mette in pausa il flusso di lavoro nell&#39;attività selezionata: questa attività e tutte quelle che la seguono (nello stesso ramo) non vengono eseguite.

**Nessuna esecuzione**

Il ![](assets/checkdisable.png) pulsante disattiva tutte le attività selezionate.

>[!NOTE]
>
>Le azioni rapide consentono di accedere a diverse azioni relative a una particolare attività e vengono visualizzate quando un&#39;attività è selezionata.
