---
title: Segmentazione in base ai gruppi di età
description: Questa pagina presenta una segmentazione dei profili del database in base al loro gruppo di età. Lo scopo del flusso di lavoro è quello di inviare un messaggio e-mail specifico per ogni gruppo di età.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: dab7ef86-4776-48f4-be9a-37de316e0dd9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 51%

---

# Segmentazione in base ai gruppi di età {#segmentation-age-groups}

L’esempio seguente mostra una segmentazione dei profili del database in base al loro gruppo di età.

Lo scopo del flusso di lavoro è quello di inviare un messaggio e-mail specifico per ogni gruppo di età. Dato che questo flusso di lavoro fa parte di una campagna di test, ogni segmento può contenere solo un massimo di 100 profili selezionati in modo casuale così da utilizzare tipi di pubblico allo stesso tempo limitati e rappresentativi.

![](assets/wkf_segment_example_4.png)

Il flusso di lavoro è costituito dai seguenti elementi:

* A [Attività Scheduler](../../automating/using/segmentation.md) per specificare la data di esecuzione del flusso di lavoro.
* A [Query](../../automating/using/query.md) attività per eseguire il targeting dei profili di persone che hanno inserito il compleanno e l’indirizzo e-mail.
* A [Segmentazione](../../automating/using/segmentation.md) attività per creare 3 segmenti divisi in diverse transizioni in uscita: 18-25 anni, 26-32 anni e profili che hanno più di 32 anni. I segmenti sono definiti in base ai seguenti parametri:

  ![](assets/wkf_segment_example_3.png)

   * Un filtro sulla pagina per definire il gruppo di età del segmento

     ![](assets/wkf_segment_new_segment.png)

   * Un limite **[!UICONTROL Random sampling]** del tipo collegato a un **[!UICONTROL Maximum size]** di 100

     ![](assets/wkf_segment_example_1.png)

* Un [Consegna e-mail](../../automating/using/email-delivery.md) attività per segmento.
