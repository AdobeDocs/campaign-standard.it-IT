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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Segmentazione in base ai gruppi di età {#segmentation-age-groups}

L&#39;esempio seguente mostra una segmentazione dei profili di database in base al gruppo di età.

Lo scopo del flusso di lavoro è quello di inviare un messaggio e-mail specifico per ogni gruppo di età. Dato che questo flusso di lavoro fa parte di una campagna di test, ogni segmento può contenere solo un massimo di 100 profili selezionati in modo casuale, al fine di utilizzare audience allo stesso tempo limitate e rappresentative.

![](assets/wkf_segment_example_4.png)

Il flusso di lavoro è costituito dai seguenti elementi:

* Un&#39;attività [](../../automating/using/segmentation.md) dell&#39;utilità di pianificazione per specificare la data di esecuzione del flusso di lavoro.
* Un&#39;attività [Query](../../automating/using/query.md) per eseguire il targeting dei profili di persone il cui compleanno e indirizzo e-mail sono stati immessi.
* Un&#39;attività di [segmentazione](../../automating/using/segmentation.md) per creare 3 segmenti divisi in diverse transizioni in uscita: 18-25 anni, 26-32 anni e profili che hanno più di 32 anni. I segmenti sono definiti in base ai seguenti parametri:

   ![](assets/wkf_segment_example_3.png)

   * Filtro sulla pagina per definire il gruppo di età del segmento

      ![](assets/wkf_segment_new_segment.png)

   * Limite **[!UICONTROL Random sampling]** del tipo collegato a un **[!UICONTROL Maximum size]** limite di 100

      ![](assets/wkf_segment_example_1.png)

* Un&#39;attività di consegna [tramite e-](../../automating/using/email-delivery.md) mail per segmento.
