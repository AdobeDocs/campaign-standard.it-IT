---
title: Consegna compleanno
description: Questo esempio è un flusso di lavoro di compleanno. Ogni giorno un'email viene inviata a un profilo il cui compleanno è in quel giorno.
page-status-flag: never-activated
uuid: 7de53431-84ae-4d21-8361-2775ad314ed2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 5f288cf6-f8ff-4ac9-9c1a-8010260554bb
context-tags: delivery,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 0%

---


# Consegna compleanno {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Questo esempio è un flusso di lavoro di compleanno. Ogni giorno un&#39;email viene inviata a un profilo il cui compleanno è in quel giorno.

Per generare il flusso di lavoro, effettuate le seguenti operazioni:

* Il modulo [di pianificazione](../../automating/using/scheduler.md) consente di avviare il flusso di lavoro ogni giorno alle 8 del mattino.

   ![](assets/wkf_delivery_example_2.png)

* L&#39;attività [Query](../../automating/using/query.md) consente di calcolare i profili che hanno fornito un&#39;e-mail e il cui compleanno è il giorno corrente, ogni volta che viene eseguito il flusso di lavoro. Il calcolo del compleanno viene eseguito utilizzando un filtro predefinito disponibile nella palette nello strumento di modifica delle query.

   ![](assets/wkf_delivery_example_3.png)

* La consegna [](../../automating/using/email-delivery.md) e-mail è ricorrente. Le mandate sono aggregate per mese. Pertanto, tutte le e-mail inviate in un mese vengono aggregate in una singola vista. In un anno, vengono quindi eseguite 365 consegne, che vengono raggruppate in 12 viste (chiamate anche esecuzioni **** ricorrenti) nell&#39;interfaccia del Adobe Campaign . I dettagli della cronologia e del rapporto vengono visualizzati ogni mese e non per ogni invio.

   ![](assets/wkf_delivery_example_4.png)
