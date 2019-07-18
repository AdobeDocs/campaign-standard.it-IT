---
title: Principi operativi del flusso di lavoro
seo-title: Principi operativi del flusso di lavoro
description: Principi operativi del flusso di lavoro
seo-description: Scopri gli aspetti principali dei flussi di lavoro.
page-status-flag: never-activated
uuid: 85755 e 85-617 b -4 a 9 b-bb 30-96 ba 8333 f 4 f 0
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: about-workflows-and-data-management
discoiquuid: 3 a 13785 d -1 ef 7-4043-9927-2 d 495 b 83709 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Workflow operating principles{#workflow-operating-principles}

A workflow is a **sequence of configurable activities**. Ogni attività ha un ruolo specifico nel processo. The result of each activity is forwarded to the following activity by a **transition**, represented by an arrow.

Il tipo di dati scambiati tra un'attività e un'altra può influenzare il modo in cui sono configurate le attività seguenti. Ad esempio, se una popolazione è stabilita prima dell'attività di consegna dell'e-mail, può fungere da destinazione per l'e-mail in questione.

Potete aprire le attività per controllare o modificare i parametri prima o dopo l'esecuzione del flusso di lavoro.

È possibile aprire le transizioni per verificare che i dati inviati siano corretti durante o dopo l'esecuzione del flusso di lavoro. To access the detail view of the transitions, you have to check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties.

![](assets/workflow_overview.png)

