---
title: Ciclo di vita del flusso di lavoro
description: Ulteriori informazioni sul ciclo di vita del flusso di lavoro
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 906c85ea-83b7-4268-86da-cd353f1dc591
context-tags: workflow,overview;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4d0aa1a9f116f022890d5eccd87730a7a513103
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 0%

---


# Ciclo di vita del flusso di lavoro {#life-cycle}

Il ciclo di vita di un flusso di lavoro comprende tre passaggi principali, ciascuno dei quali è collegato a uno stato e a un colore:

* **Modifica** (grigio)

   Si tratta della fase iniziale di progettazione di un flusso di lavoro (vedere [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md#creating-a-workflow)). Il flusso di lavoro non è ancora gestito dal server e può essere modificato senza rischi.

* **In corso** (blu)

   Una volta completata la fase di progettazione iniziale, il flusso di lavoro può essere avviato e gestito dal server.

* **Finito** (verde)

   Un flusso di lavoro viene completato una volta che non sono più presenti attività in corso o quando un operatore ha interrotto in modo esplicito l&#39;istanza.

Una volta avviato, un flusso di lavoro potrebbe presentare anche altri due stati:

* **Avviso** (giallo)

   Impossibile completare il flusso di lavoro o è stato messo in pausa utilizzando i ![](assets/pause_darkgrey-24px.png) pulsanti o ![](assets/check_pause_darkgrey-24px.png) .

* **Erroneo** (rosso)

   Errore durante l&#39;esecuzione di un flusso di lavoro. Il flusso di lavoro è stato arrestato e l&#39;utente deve eseguire un&#39;azione. Per ulteriori informazioni su questo errore, utilizzare il ![](assets/printpreview_darkgrey-24px.png) pulsante per accedere al registro del flusso di lavoro (fare riferimento a [Monitoraggio](../../automating/using/monitoring-workflow-execution.md)).

L&#39;elenco delle attività di marketing consente di visualizzare tutti i flussi di lavoro e i relativi stati. Per ulteriori informazioni, consulta [Gestione delle attività](../../start/using/marketing-activities.md#about-marketing-activities)di marketing.

![](assets/wkf_execution_3.png)
