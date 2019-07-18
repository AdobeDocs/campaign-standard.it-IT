---
title: Targeting dei dati
seo-title: Targeting dei dati
description: Targeting dei dati
seo-description: Scopri i diversi modi per eseguire il targeting e selezionare i dati necessari.
page-status-flag: never-activated
uuid: 0645 d 6 e 5-6 a 7 e -4917-874 a -7 e 7725 f 06 abd
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: workflow-general-operation
discoiquuid: 382 ea 74 e -1662-4 c 64-96 d 7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Targeting data{#targeting-data}

## Selecting data {#selecting-data}

Potete selezionare i dati utilizzando le attività seguenti:

* The **[!UICONTROL Query]** activity allows you to filter and extract a population of elements from the Adobe Campaign database. See the [Query](../../automating/using/query.md) section.
* The **[!UICONTROL Incremental query]** activity allows you to filter and extract a population of elements from the Adobe Campaign database. Ogni volta che questa attività viene eseguita, i risultati delle esecuzioni precedenti sono esclusi. Questo consente di eseguire il targeting solo di elementi nuovi Vedere la sezione. [Sezione query incrementale](../../automating/using/incremental-query.md) .
* The **[!UICONTROL Read audience]** activity allows you to retrieve an existing audience and to refine it by applying additional filtering conditions.See the [Read audience](../../automating/using/read-audience.md) section.

## Segmenting data {#segmenting-data}

Adobe Campaign consente di elaborare i set sui dati in entrata. Potete quindi combinare diverse popolazioni, escluderne parte o mantenere solo i dati comuni a più destinazioni.

* The **[!UICONTROL Union]** activity allows you to regroup the result of multiple activities into a single target. See the [Union](../../automating/using/union.md) section.
* The **[!UICONTROL Intersection]** activity allows you to keep only the elements common to the different inbound populations in the activity. See the [Intersection](../../automating/using/intersection.md) section.
* The **[!UICONTROL Exclusion]** activity allows you to exclude elements from one population according to certain criteria. See the [Exclusion](../../automating/using/exclusion.md) section.
* The **[!UICONTROL Segmentation]** activity lets you create one or several segments from a population calculated by activities placed earlier in the workflow. Alla fine dell'attività, possono essere elaborate con una singola transizione o con transizioni diverse. See the [Segmentation](../../automating/using/segmentation.md) section.

## Enriching data {#enriching-data}

I dati identificati e raccolti possono essere arricchiti, aggregati e manipolati per ottimizzare la costruzione di target. Potete semplificare e ottimizzare i processi di targeting includendo dati non modellati nel mart dati.

The **[!UICONTROL Additional data]** tab of the **[!UICONTROL Query]** and **[!UICONTROL Incremental query]** activities allows you to enrich the data targeted by the query and transfer this data to the following workflow activities, where it can be utilized. In particolare, potete aggiungere:

* Dati semplici
* Aggregati
* Raccolte

