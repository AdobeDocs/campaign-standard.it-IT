---
solution: Campaign Standard
product: campaign
title: Segmentazione in base ai gruppi di età
description: Questa pagina presenta una segmentazione dei profili del database in base al gruppo di età. Lo scopo del flusso di lavoro è quello di inviare un messaggio e-mail specifico per ogni gruppo di età.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Flussi di lavoro
role: Architetto dati
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 65%

---


# Segmentazione in base ai gruppi di età {#segmentation-age-groups}

L’esempio seguente mostra una segmentazione dei profili del database in base al gruppo di età.

Lo scopo del flusso di lavoro è quello di inviare un messaggio e-mail specifico per ogni gruppo di età. Dato che questo flusso di lavoro fa parte di una campagna di test, ogni segmento può contenere solo un massimo di 100 profili selezionati in modo casuale così da utilizzare tipi di pubblico allo stesso tempo limitati e rappresentativi.

![](assets/wkf_segment_example_4.png)

Il flusso di lavoro è costituito dai seguenti elementi:

* Un [Attività di pianificazione](../../automating/using/segmentation.md) per specificare la data di esecuzione del flusso di lavoro.
* Un&#39;attività [Query](../../automating/using/query.md) per eseguire il targeting dei profili di persone che hanno inserito il compleanno e l&#39;indirizzo e-mail.
* Un&#39;attività [Segmentation](../../automating/using/segmentation.md) per creare 3 segmenti suddivisi in diverse transizioni in uscita: 18-25 anni, 26-32 anni e profili che hanno più di 32 anni. I segmenti sono definiti in base ai seguenti parametri:

   ![](assets/wkf_segment_example_3.png)

   * Un filtro sulla pagina per definire il gruppo di età del segmento

      ![](assets/wkf_segment_new_segment.png)

   * Un limite **[!UICONTROL Random sampling]** del tipo collegato a un **[!UICONTROL Maximum size]** di 100

      ![](assets/wkf_segment_example_1.png)

* Un’attività [Email delivery](../../automating/using/email-delivery.md) per segmento.
