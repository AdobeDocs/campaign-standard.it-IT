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
TQID: 'https://experienceleague.adobe.com/jDS-3Rz--h6N17JfbijrtOaj8jVDPDW9HiOoiLwPHSY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
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
