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
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# Targeting dei dati{#targeting-data}

## Selezione dei dati {#selecting-data}

Potete selezionare i dati utilizzando le attività seguenti:

* L' **[!UICONTROL Query]** attività consente di filtrare ed estrarre una popolazione di elementi dal database Adobe Campaign. Consultate la sezione [Query](../../automating/using/query.md) .
* L' **[!UICONTROL Incremental query]** attività consente di filtrare ed estrarre una popolazione di elementi dal database Adobe Campaign. Ogni volta che questa attività viene eseguita, i risultati delle esecuzioni precedenti sono esclusi. Questo consente di eseguire il targeting solo di elementi nuovi Vedere la sezione. [Sezione query incrementale](../../automating/using/incremental-query.md) .
* L' **[!UICONTROL Read audience]** attività consente di recuperare un'audience esistente e di perfezionarla applicando condizioni [di filtro aggiuntive. Consultate la](../../automating/using/read-audience.md) sezione Leggi audience.

## Segmentazione dei dati {#segmenting-data}

Adobe Campaign consente di elaborare i set sui dati in entrata. Potete quindi combinare diverse popolazioni, escluderne parte o mantenere solo i dati comuni a più destinazioni.

* L' **[!UICONTROL Union]** attività consente di riportare il risultato di più attività in una singola destinazione. Consultate la sezione [Unione](../../automating/using/union.md) .
* L' **[!UICONTROL Intersection]** attività consente di mantenere solo gli elementi comuni alle diverse popolazioni in entrata dell'attività. Consultate Sezione [Intersezione](../../automating/using/intersection.md) .
* L' **[!UICONTROL Exclusion]** attività consente di escludere gli elementi di una popolazione in base a determinati criteri. Vedere la sezione [Esclusione](../../automating/using/exclusion.md) .
* L' **[!UICONTROL Segmentation]** attività consente di creare uno o più segmenti da una popolazione calcolata in base alle attività inserite in precedenza nel flusso di lavoro. Alla fine dell'attività, possono essere elaborate con una singola transizione o con transizioni diverse. Consulta la sezione [Segmentazione](../../automating/using/segmentation.md) .

## Arricchimento dei dati {#enriching-data}

I dati identificati e raccolti possono essere arricchiti, aggregati e manipolati per ottimizzare la costruzione di target. Potete semplificare e ottimizzare i processi di targeting includendo dati non modellati nel mart dati.

La **[!UICONTROL Additional data]** scheda delle **[!UICONTROL Query]** attività e **[!UICONTROL Incremental query]** consente di arricchire i dati mirati dalla query e di trasferire questi dati alle seguenti attività del flusso di lavoro, dove può essere utilizzato. In particolare, potete aggiungere:

* Dati semplici
* Aggregati
* Raccolte

**Argomenti correlati**

* [Caso d'uso: Creazione di una consegna e-mail una tantum](../../automating/using/workflow-weekly-offer.md)
* [Caso d'uso: Creazione di una distribuzione segmentata sulla posizione](../../automating/using/workflow-segmentation-location.md)
* [Caso d'uso: Creazione di consegne con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso d'uso: Flusso di lavoro di retargeting che invia una nuova consegna a non-openers](../../automating/using/workflow-cross-channel-retargeting.md)
