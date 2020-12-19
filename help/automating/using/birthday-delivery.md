---
solution: Campaign Standard
product: campaign
title: Consegna compleanno
description: Questo esempio è un flusso di lavoro di compleanno. Ogni giorno un’e-mail viene inviata ai profili che compiono gli anni in quel giorno.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '172'
ht-degree: 69%

---


# Consegna compleanno {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Questo esempio è un flusso di lavoro di compleanno. Ogni giorno un’e-mail viene inviata ai profili che compiono gli anni in quel giorno.

Per generare il flusso di lavoro, effettuate le seguenti operazioni:

* Il modulo [Scheduler](../../automating/using/scheduler.md) consente di avviare il flusso di lavoro ogni giorno alle 8 di mattina.

   ![](assets/wkf_delivery_example_2.png)

* L&#39;attività [Query](../../automating/using/query.md) consente di calcolare i profili che hanno fornito un&#39;e-mail e il cui compleanno è il giorno corrente, ogni volta che il flusso di lavoro viene eseguito. Il calcolo del compleanno viene eseguito utilizzando un filtro predefinito disponibile nella palette nello strumento di modifica delle query.

   ![](assets/wkf_delivery_example_3.png)

* La [distribuzione e-mail](../../automating/using/email-delivery.md) è ricorrente. Gli invii sono aggregati per mese. In questo modo, tutte le e-mail inviate in un mese vengono aggregate in un’unica vista. In un anno vengono quindi eseguite 365 consegne, che vengono raggruppate in 12 viste (dette anche **esecuzioni ricorrenti**) nell’interfaccia di Adobe Campaign. La cronologia e i dettagli sui report vengono visualizzati ogni mese e non per ogni invio.

   ![](assets/wkf_delivery_example_4.png)
