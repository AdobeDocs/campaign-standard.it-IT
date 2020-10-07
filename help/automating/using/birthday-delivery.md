---
title: Consegna compleanno
description: Questo esempio è un flusso di lavoro di compleanno. Ogni giorno un’e-mail viene inviata ai profili che compiono gli anni in quel giorno.
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 69%

---


# Consegna compleanno {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Questo esempio è un flusso di lavoro di compleanno. Ogni giorno un’e-mail viene inviata ai profili che compiono gli anni in quel giorno.

Per generare il flusso di lavoro, effettuate le seguenti operazioni:

* The [Scheduler](../../automating/using/scheduler.md) allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* The [Query](../../automating/using/query.md) activity allows you to calculate the profiles who have provided an email and whose birthday it is on the current day, every time the workflow is executed. Il calcolo del compleanno viene eseguito utilizzando un filtro predefinito disponibile nella palette nello strumento di modifica delle query.

   ![](assets/wkf_delivery_example_3.png)

* La consegna [](../../automating/using/email-delivery.md) e-mail è ricorrente. Gli invii sono aggregati per mese. In questo modo, tutte le e-mail inviate in un mese vengono aggregate in un’unica vista. In un anno vengono quindi eseguite 365 consegne, che vengono raggruppate in 12 viste (dette anche **esecuzioni ricorrenti**) nell’interfaccia di Adobe Campaign. La cronologia e i dettagli sui report vengono visualizzati ogni mese e non per ogni invio.

   ![](assets/wkf_delivery_example_4.png)
