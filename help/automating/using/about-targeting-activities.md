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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 6%

---


# Informazioni sulle attività di targeting{#about-targeting-activities}

Dalla palette, sul lato sinistro dello schermo, aprire la **[!UICONTROL Targeting]** sezione.

Tali attività sono specifiche per il targeting, la manipolazione dei dati sulla popolazione e le attività di filtraggio. Consentono di creare uno o più target definendo set e dividendo o combinando questi set mediante operazioni di intersezione, unione o esclusione.

![](assets/wkf_targeting_activities.png)

La **[!UICONTROL Targeting]** sezione include le seguenti attività:

* [Query](../../automating/using/query.md)
* [Query incrementale](../../automating/using/incremental-query.md)
* [Unione](../../automating/using/union.md)
* [Intersezione](../../automating/using/intersection.md)
* [Esclusione](../../automating/using/exclusion.md)
* [Segmentazione](../../automating/using/segmentation.md)
* [Leggi pubblico](../../automating/using/read-audience.md)
* [Salva pubblico](../../automating/using/save-audience.md)
* [Deduplicazione](../../automating/using/deduplication.md)
* [Arricchimento](../../automating/using/enrichment.md)

**[!UICONTROL Targeting]** attività consente di definire i codici **dei** segmenti per le transizioni in uscita. Potete quindi creare rapporti basati su questi codici di segmento per misurare l&#39;efficienza delle campagne di marketing. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../reporting/using/creating-a-report-workflow-segment.md).

## Selezione dei dati {#selecting-data}

È possibile selezionare i dati utilizzando le attività seguenti:

* L&#39; **[!UICONTROL Query]** attività consente di filtrare ed estrarre una serie di elementi dal database del Adobe Campaign . Vedere la sezione [Query](../../automating/using/query.md) .
* L&#39; **[!UICONTROL Incremental query]** attività consente di filtrare ed estrarre una serie di elementi dal database del Adobe Campaign . Ogni volta che questa attività viene eseguita, i risultati delle esecuzioni precedenti sono esclusi. Questo consente di eseguire il targeting solo dei nuovi elementi Vedere il pannello. [Sezione query](../../automating/using/incremental-query.md) incrementale.
* L&#39; **[!UICONTROL Read audience]** attività consente di recuperare un&#39;audience esistente e di perfezionarla applicando condizioni di filtraggio aggiuntive.Vedere la sezione [Leggi pubblico](../../automating/using/read-audience.md) .

## Segmentazione dei dati {#segmenting-data}

 Adobe Campaign consente di elaborare i set su dati in entrata. È quindi possibile combinare più popolazioni, escluderne una parte o mantenere solo dati comuni a più target.

* L&#39; **[!UICONTROL Union]** attività consente di raggruppare il risultato di più attività in un unico target. Vedere la sezione [Unione](../../automating/using/union.md) .
* L&#39; **[!UICONTROL Intersection]** attività consente di mantenere solo gli elementi comuni alle diverse popolazioni in entrata nell&#39;attività. Vedere la sezione [Intersezione](../../automating/using/intersection.md) .
* L&#39; **[!UICONTROL Exclusion]** attività consente di escludere elementi da una popolazione in base a determinati criteri. Consultate la sezione [Esclusione](../../automating/using/exclusion.md) .
* L&#39; **[!UICONTROL Segmentation]** attività consente di creare uno o più segmenti da una popolazione calcolata dalle attività inserite in precedenza nel flusso di lavoro. Al termine dell&#39;attività, possono essere elaborati in un&#39;unica transizione o in diverse transizioni. Vedere la sezione [Segmentazione](../../automating/using/segmentation.md) .

## Arricchimento dei dati {#enriching-data}

I dati identificati e raccolti possono essere arricchiti, aggregati e manipolati per ottimizzare la costruzione del target. È possibile semplificare e ottimizzare i processi di targeting, includendo i dati non modellati nel data mart.

La **[!UICONTROL Additional data]** scheda delle attività **[!UICONTROL Query]** e **[!UICONTROL Incremental query]** consente di arricchire i dati di destinazione della query e di trasferire tali dati alle seguenti attività del flusso di lavoro, dove è possibile utilizzarli. In particolare, potete aggiungere:

* Dati semplici
* Aggregati
* Raccolte

**Argomenti correlati:**

* [Caso di utilizzo: Personalizzazione di un’e-mail con dati aggiuntivi](../../automating/using/personalizing-email-with-additional-data.md)
