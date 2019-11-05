---
title: Informazioni sui tipi di audience
description: Scopri come creare audience da una query, un elenco o un file e come importarli da Adobe Experience Cloud.
page-status-flag: mai attivato
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: management-audience
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: pubblico,procedura guidata;pubblico,panoramica;consegna,pubblico,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Informazioni sui tipi di audience{#about-audiences}

Un'audience è un elenco di profili basati su regole e attributi.

Adobe Campaign consente di creare il pubblico manualmente utilizzando le query o automaticamente utilizzando flussi di lavoro dedicati. Puoi anche utilizzare i tipi di pubblico condivisi da Adobe Experience Cloud. Tutte le audience vengono raggruppate in un elenco a cui è possibile accedere tramite la **[!UICONTROL Audiences]** scheda nella home page di Adobe Campaign o dal **[!UICONTROL Audiences]** collegamento.

![](assets/audience_1.png)

In Adobe Campaign puoi manipolare diversi tipi di pubblico. Il tipo di pubblico corrisponde al modo in cui è stato creato:

* **[!UICONTROL Query]**: indica che l'audience è stata creata da una [query](../../automating/using/editing-queries.md#about-query-editor) sui dati del database di Adobe Campaign dall'elenco delle audience. Le audience definite da una query vengono ricalcolate a ogni ulteriore utilizzo.
* **[!UICONTROL List]**: indica che l'audience è un elenco fisso di profili. Questi elenchi vengono creati in un [flusso di lavoro](../../automating/using/discovering-workflows.md), in cui la dimensione dati è nota al momento del salvataggio dell'audience. Ad esempio, dopo le attività di targeting (in particolare **[!UICONTROL Query]** ) o dopo la riconciliazione dei dati importati da un file.
* **[!UICONTROL File]**: indica che l'audience è stata creata direttamente da un flusso di lavoro di importazione [di](../../automating/using/load-file.md) file e che la dimensione dati era sconosciuta durante il salvataggio dell'audience.
* **[!UICONTROL Experience Cloud]**: indica che il pubblico è stato importato da Adobe Experience Cloud. Questa opzione è disponibile solo se è stata configurata la funzionalità di condivisione dell'audience. Per ulteriori informazioni, consulta [Importazione di un pubblico da Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)

