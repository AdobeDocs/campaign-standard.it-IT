---
title: Consegna compleanno
description: Questo esempio è un flusso di lavoro di compleanno. Ogni giorno un’e-mail viene inviata ai profili che compiono gli anni in quel giorno.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 535ddbce-d8ba-4578-9e37-10604291c95d
TQID: 'https://experienceleague.adobe.com/LXiYfz5VXaY7j0pOHWUCGJzp5F4bCsSCmFzEqsQG18E'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 52%
---
# Consegna compleanno {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Questo esempio è un flusso di lavoro di compleanno. Ogni giorno un’e-mail viene inviata ai profili che compiono gli anni in quel giorno.

Per creare il flusso di lavoro, effettua le seguenti operazioni:

* L&#39;[Utilità di pianificazione](../../automating/using/scheduler.md) ti consente di avviare il flusso di lavoro ogni giorno alle 8.

  ![](assets/wkf_delivery_example_2.png)

* L&#39;attività [Query](../../automating/using/query.md) ti consente di calcolare i profili che hanno fornito un&#39;e-mail e il cui compleanno cade nel giorno corrente ogni volta che il flusso di lavoro viene eseguito. Il calcolo del compleanno viene eseguito utilizzando un filtro predefinito disponibile nella palette nello strumento di modifica delle query.

  ![](assets/wkf_delivery_example_3.png)

* La [consegna e-mail](../../automating/using/email-delivery.md) è ricorrente. Gli invii sono aggregati per mese. In questo modo, tutte le e-mail inviate in un mese vengono aggregate in un’unica vista. In un anno vengono quindi eseguite 365 consegne, che vengono raggruppate in 12 viste (dette anche **esecuzioni ricorrenti**) nell’interfaccia di Adobe Campaign. La cronologia e i dettagli sui report vengono visualizzati ogni mese e non per ogni invio.

  ![](assets/wkf_delivery_example_4.png)
