---
title: Informazioni sui tipi di pubblico
seo-title: Informazioni sui tipi di pubblico
description: Informazioni sui tipi di pubblico
seo-description: Scopri come creare tipi di pubblico da una query, un elenco o un file e come importarli da Adobe Experience Cloud.
page-status-flag: never-activated
uuid: b 3996642-96 ec -489 e-b 146-c 8 c 2 cb 52 aa 32
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: audience
content-type: riferimento
topic-tags: gestione dei tipi di pubblico
discoiquuid: 750 ecd 8 d -67 a 5-4180-bfec -2 a 8 e 3098 c 812
context-tags: pubblico, procedura guidata; audience, panoramica; distribuzione, pubblico,
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# About audiences{#about-audiences}

Un pubblico è un elenco di profili basati su regole e attributi.

Adobe Campaign consente di creare manualmente i tipi di pubblico utilizzando query o automaticamente utilizzando flussi di lavoro dedicati. Puoi anche utilizzare i tipi di pubblico condivisi da Adobe Experience Cloud. All of the audiences are regrouped into a list that can be accessed via the **[!UICONTROL Audiences]** card on the Adobe Campaign home page or from the **[!UICONTROL Audiences]** link.

![](assets/audience_1.png)

In Adobe Campaign puoi manipolare tipi di pubblico diversi. Il tipo di pubblico corrisponde al modo in cui è stato creato:

* **[!UICONTROL Query]**: indica che l'audience è stata creata da una [query](../../automating/using/editing-queries.md#about-query-editor) sui dati provenienti dal database Adobe Campaign dall'elenco di audience. Le audience definite da una query vengono ricalcolate a ogni altro utilizzo.
* **[!UICONTROL List]**: indica che l'audience è un elenco fisso di profili. These lists are created in a [workflow](../../automating/using/discovering-workflows.md), where the data dimension is known when saving the audience. For example, after targeting activities (especially **[!UICONTROL Query]** ) or after the reconciliation of data imported from a file.
* **[!UICONTROL File]**: indica che l'audience è stata creata direttamente da un [flusso di lavoro di importazione](../../automating/using/load-file.md) file e che la dimensione dati è sconosciuta al salvataggio del pubblico.
* **[!UICONTROL Experience Cloud]**: indica che l'audience è stata importata da Adobe Experience Cloud. Questa opzione è disponibile solo se la funzionalità di condivisione dell'audience è stata configurata. For more information, see [Importing an audience from the Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)

