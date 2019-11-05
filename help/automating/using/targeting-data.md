---
title: Dati di targeting
description: Scopri i diversi modi per eseguire il targeting e selezionare i dati necessari.
page-status-flag: mai attivato
uuid: 0645d6e5-6a7e-4917-874a-7e7725f06abd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: workflow generale
discoiquuid: 382ea74e-1662-4c64-96d7-676040586913
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Dati di targeting{#targeting-data}

## Selezione dei dati {#selecting-data}

È possibile selezionare i dati utilizzando le attività seguenti:

* L' **[!UICONTROL Query]** attività consente di filtrare ed estrarre una serie di elementi dal database di Adobe Campaign. Vedere la sezione [Query](../../automating/using/query.md) .
* L' **[!UICONTROL Incremental query]** attività consente di filtrare ed estrarre una serie di elementi dal database di Adobe Campaign. Ogni volta che questa attività viene eseguita, i risultati delle esecuzioni precedenti sono esclusi. Questo consente di eseguire il targeting solo dei nuovi elementi Vedere il pannello. [Sezione query](../../automating/using/incremental-query.md) incrementale.
* L' **[!UICONTROL Read audience]** attività consente di recuperare un'audience esistente e di perfezionarla applicando condizioni di filtraggio aggiuntive.Vedere la sezione [Leggi pubblico](../../automating/using/read-audience.md) .

## Segmentazione dei dati {#segmenting-data}

Adobe Campaign consente di elaborare i set di dati in entrata. È quindi possibile combinare più popolazioni, escluderne una parte o mantenere solo dati comuni a più target.

* L' **[!UICONTROL Union]** attività consente di raggruppare il risultato di più attività in un unico target. Vedere la sezione [Unione](../../automating/using/union.md) .
* L' **[!UICONTROL Intersection]** attività consente di mantenere solo gli elementi comuni alle diverse popolazioni in entrata nell'attività. Vedere la sezione [Intersezione](../../automating/using/intersection.md) .
* L' **[!UICONTROL Exclusion]** attività consente di escludere elementi da una popolazione in base a determinati criteri. Vedere la sezione [Esclusione](../../automating/using/exclusion.md) .
* L' **[!UICONTROL Segmentation]** attività consente di creare uno o più segmenti da una popolazione calcolata dalle attività inserite in precedenza nel flusso di lavoro. Al termine dell'attività, possono essere elaborati in un'unica transizione o in diverse transizioni. Vedere la sezione [Segmentazione](../../automating/using/segmentation.md) .

## Arricchimento dei dati {#enriching-data}

I dati identificati e raccolti possono essere arricchiti, aggregati e manipolati per ottimizzare la costruzione del target. È possibile semplificare e ottimizzare i processi di targeting, includendo i dati non modellati nel data mart.

La **[!UICONTROL Additional data]** scheda delle attività **[!UICONTROL Query]** e **[!UICONTROL Incremental query]** consente di arricchire i dati di destinazione della query e di trasferire tali dati alle seguenti attività del flusso di lavoro, dove è possibile utilizzarli. In particolare, potete aggiungere:

* Dati semplici
* Aggregati
* Raccolte

**Argomenti correlati**

* [Caso di utilizzo: Creare una consegna di e-mail una volta alla settimana](../../automating/using/workflow-weekly-offer.md)
* [Caso di utilizzo: Creazione di una consegna segmentata sulla posizione](../../automating/using/workflow-segmentation-location.md)
* [Caso di utilizzo: Creazione di consegne con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso di utilizzo: Flusso di lavoro di retargeting che invia una nuova consegna a non-openers](../../automating/using/workflow-cross-channel-retargeting.md)
