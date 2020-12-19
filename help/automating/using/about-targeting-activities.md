---
solution: Campaign Standard
product: campaign
title: Informazioni sulle attività di targeting
description: È possibile accedere alle attività di targeting dal lato sinistro dello schermo.
audience: automating
content-type: reference
topic-tags: targeting-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
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

**[!UICONTROL Targeting]** le attività consentono di definire  **i** codici dei segmenti per le loro transizioni in uscita. Puoi quindi creare report basati su questi codici di segmento per misurare l’efficienza delle campagne di marketing. Per ulteriori informazioni, consulta [questa sezione](../../reporting/using/creating-a-report-workflow-segment.md).

## Selezione dei dati {#selecting-data}

È possibile selezionare i dati utilizzando le attività seguenti:

* L’attività **[!UICONTROL Query]** ti consente di filtrare ed estrarre una popolazione di elementi dal database di Adobe Campaign. Vedere la sezione [Query](../../automating/using/query.md).
* L’attività **[!UICONTROL Incremental query]** ti consente di filtrare ed estrarre una popolazione di elementi dal database di Adobe Campaign. Ogni volta che questa attività viene eseguita, i risultati delle esecuzioni precedenti sono esclusi. Questo consente di eseguire il targeting solo dei nuovi elementi Vedere il pannello. [Sezione ](../../automating/using/incremental-query.md) query incrementale.
* L&#39;attività **[!UICONTROL Read audience]** consente di recuperare un&#39;audience esistente e di perfezionarla applicando condizioni di filtraggio aggiuntive.Vedere la sezione [Leggi audience](../../automating/using/read-audience.md).

## Segmentazione dei dati {#segmenting-data}

 Adobe Campaign consente di elaborare i set su dati in entrata. È quindi possibile combinare più popolazioni, escluderne una parte o mantenere solo dati comuni a più target.

* L’attività **[!UICONTROL Union]** ti consente di raggruppare il risultato di più attività in un unico target. Vedere la sezione [Union](../../automating/using/union.md).
* L’attività **[!UICONTROL Intersection]** ti consente di mantenere solo gli elementi comuni alle diverse popolazioni in entrata all’interno dell’attività. Vedere la sezione [Intersezione](../../automating/using/intersection.md).
* L’attività **[!UICONTROL Exclusion]** consente di escludere elementi da una popolazione in base a determinati criteri. Vedere la sezione [Esclusione](../../automating/using/exclusion.md).
* L’attività **[!UICONTROL Segmentation]** ti consente di creare uno o più segmenti da un gruppo calcolato dalle attività inserite in precedenza nel flusso di lavoro. Al termine dell’attività, puoi elaborarli in un’unica transizione o in diverse transizioni. Vedere la sezione [Segmentazione](../../automating/using/segmentation.md).

## Arricchimento dei dati {#enriching-data}

I dati identificati e raccolti possono essere arricchiti, aggregati e manipolati per ottimizzare la costruzione del target. È possibile semplificare e ottimizzare i processi di targeting, includendo i dati non modellati nel data mart.

La scheda **[!UICONTROL Additional data]** delle attività **[!UICONTROL Query]** e **[!UICONTROL Incremental query]** consente di arricchire i dati di destinazione della query e di trasferire tali dati alle seguenti attività del flusso di lavoro, dove è possibile utilizzarli. In particolare, puoi aggiungere:

* Dati semplici
* Aggregati
* Raccolte

**Argomenti correlati:**

* [Caso di utilizzo: Personalizzazione di un’e-mail con dati aggiuntivi](../../automating/using/personalizing-email-with-additional-data.md)
