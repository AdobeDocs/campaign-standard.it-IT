---
title: Informazioni sulle attività di targeting
description: È possibile accedere alle attività di targeting dal lato sinistro dello schermo.
page-status-flag: never-activated
uuid: a6cbc431-1ae3-428e-b2c9-893454b32ae2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 5f7607a1-5f71-4d66-9688-3e5a1774f1b4
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 48%

---


# Informazioni sulle attività di targeting{#about-targeting-activities}

Dalla palette, sul lato sinistro dello schermo, apri la sezione **[!UICONTROL Targeting]**.

Tali attività sono specifiche per il targeting, la manipolazione dei dati sulla popolazione e le attività di filtraggio. Consentono di creare uno o più target definendo set e dividendo o combinando questi set mediante operazioni di intersezione, unione o esclusione.

![](assets/wkf_targeting_activities.png)

La sezione **[!UICONTROL Targeting]** include le seguenti attività:

* [Query](../../automating/using/query.md)
* [Incremental query](../../automating/using/incremental-query.md)
* [Union](../../automating/using/union.md)
* [Intersection](../../automating/using/intersection.md)
* [Exclusion](../../automating/using/exclusion.md)
* [Segmentation](../../automating/using/segmentation.md)
* [Read audience](../../automating/using/read-audience.md)
* [Save audience](../../automating/using/save-audience.md)
* [Deduplication](../../automating/using/deduplication.md)
* [Enrichment](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** attività consente di definire i codici **dei** segmenti per le transizioni in uscita. Puoi quindi creare report basati su questi codici di segmento per misurare l’efficienza delle campagne di marketing. Per ulteriori informazioni, consulta [questa sezione](../../reporting/using/creating-a-report-workflow-segment.md).

## Selezione dei dati {#selecting-data}

È possibile selezionare i dati utilizzando le attività seguenti:

* L’attività **[!UICONTROL Query]** ti consente di filtrare ed estrarre una popolazione di elementi dal database di Adobe Campaign. Vedere la sezione [Query](../../automating/using/query.md) .
* L’attività **[!UICONTROL Incremental query]** ti consente di filtrare ed estrarre una popolazione di elementi dal database di Adobe Campaign. Ogni volta che questa attività viene eseguita, i risultati delle esecuzioni precedenti sono esclusi. Questo consente di eseguire il targeting solo dei nuovi elementi Vedere il pannello. [Sezione query](../../automating/using/incremental-query.md) incrementale.
* The **[!UICONTROL Read audience]** activity allows you to retrieve an existing audience and to refine it by applying additional filtering conditions.See the [Read audience](../../automating/using/read-audience.md) section.

## Segmentazione dei dati {#segmenting-data}

 Adobe Campaign consente di elaborare i set su dati in entrata. È quindi possibile combinare più popolazioni, escluderne una parte o mantenere solo dati comuni a più target.

* L’attività **[!UICONTROL Union]** ti consente di raggruppare il risultato di più attività in un unico target. Vedere la sezione [Unione](../../automating/using/union.md) .
* L’attività **[!UICONTROL Intersection]** ti consente di mantenere solo gli elementi comuni alle diverse popolazioni in entrata all’interno dell’attività. Vedere la sezione [Intersezione](../../automating/using/intersection.md) .
* L’attività **[!UICONTROL Exclusion]** consente di escludere elementi da una popolazione in base a determinati criteri. Consultate la sezione [Esclusione](../../automating/using/exclusion.md) .
* L’attività **[!UICONTROL Segmentation]** ti consente di creare uno o più segmenti da un gruppo calcolato dalle attività inserite in precedenza nel flusso di lavoro. Al termine dell’attività, puoi elaborarli in un’unica transizione o in diverse transizioni. Vedere la sezione [Segmentazione](../../automating/using/segmentation.md) .

## Arricchimento dei dati {#enriching-data}

I dati identificati e raccolti possono essere arricchiti, aggregati e manipolati per ottimizzare la costruzione del target. È possibile semplificare e ottimizzare i processi di targeting, includendo i dati non modellati nel data mart.

The **[!UICONTROL Additional data]** tab of the **[!UICONTROL Query]** and **[!UICONTROL Incremental query]** activities allows you to enrich the data targeted by the query and transfer this data to the following workflow activities, where it can be utilized. In particolare, puoi aggiungere:

* Dati semplici
* Aggregati
* Raccolte

**Argomenti correlati:**

* [Caso di utilizzo: Personalizzazione di un’e-mail con dati aggiuntivi](../../automating/using/personalizing-email-with-additional-data.md)
