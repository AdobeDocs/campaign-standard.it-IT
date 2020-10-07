---
title: Segmentazione in base ai gruppi di età
description: Questa pagina presenta una segmentazione dei profili di database in base al gruppo di età. Lo scopo del flusso di lavoro è quello di inviare un messaggio e-mail specifico per ogni gruppo di età.
page-status-flag: never-activated
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentation,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 66%

---


# Segmentazione in base ai gruppi di età {#segmentation-age-groups}

L’esempio seguente mostra una segmentazione dei profili del database in base al gruppo di età.

Lo scopo del flusso di lavoro è quello di inviare un messaggio e-mail specifico per ogni gruppo di età. Dato che questo flusso di lavoro fa parte di una campagna di test, ogni segmento può contenere solo un massimo di 100 profili selezionati in modo casuale così da utilizzare tipi di pubblico allo stesso tempo limitati e rappresentativi.

![](assets/wkf_segment_example_4.png)

Il flusso di lavoro è costituito dai seguenti elementi:

* A [Scheduler activity](../../automating/using/segmentation.md) to specify the workflow&#39;s execution date.
* A [Query](../../automating/using/query.md) activity to target profiles of people whose birthday and email address have been entered.
* A [Segmentation](../../automating/using/segmentation.md) activity to create 3 segments divided into different outbound transitions: 18-25-year old, 26-32-year old and profiles that are over 32 years old. I segmenti sono definiti in base ai seguenti parametri:

   ![](assets/wkf_segment_example_3.png)

   * Un filtro sulla pagina per definire il gruppo di età del segmento

      ![](assets/wkf_segment_new_segment.png)

   * Un limite **[!UICONTROL Random sampling]** del tipo collegato a un **[!UICONTROL Maximum size]** di 100

      ![](assets/wkf_segment_example_1.png)

* Un&#39;attività di consegna [tramite e-](../../automating/using/email-delivery.md) mail per segmento.
