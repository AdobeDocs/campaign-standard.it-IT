---
title: Principi operativi del flusso di lavoro
description: Scopri i principali aspetti dei flussi di lavoro.
page-status-flag: mai attivato
uuid: 85755e85-617b-4a9b-bb30-96ba8333f4f0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: workflow e gestione dei dati
discoiquuid: 3a13785d-1ef7-4043-9927-2d495b83709f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Principi operativi del flusso di lavoro{#workflow-operating-principles}

Un flusso di lavoro è una **sequenza di attività** configurabili. Ogni attività ha un ruolo specifico nel processo. Il risultato di ogni attività viene inoltrato alla seguente attività da una **transizione**, rappresentata da una freccia.

Il tipo di dati scambiati tra un'attività e un'altra può influenzare la configurazione delle seguenti attività. Ad esempio, se una popolazione viene stabilita prima dell'attività di consegna delle e-mail, può fungere da destinazione per l'e-mail in questione.

Potete aprire le attività per controllare o modificare i parametri prima o dopo l'esecuzione del flusso di lavoro.

Potete aprire le transizioni per verificare che i dati inviati siano corretti durante o dopo l'esecuzione del flusso di lavoro. Per accedere alla visualizzazione dettagliata delle transizioni, è necessario selezionare l' **[!UICONTROL Keep interim results]** opzione nella **[!UICONTROL Execution]** sezione delle proprietà del flusso di lavoro.

![](assets/workflow_overview.png)

