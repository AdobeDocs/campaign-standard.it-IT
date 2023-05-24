---
title: Ciclo di vita di un flusso di lavoro
description: Ulteriori informazioni sul ciclo di vita del flusso di lavoro
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---

# Ciclo di vita di un flusso di lavoro {#life-cycle}

Il ciclo di vita di un flusso di lavoro include tre passaggi principali e ogni passaggio è collegato a uno stato e a un colore:

* **Modifica** (grigio)

   Questa è la fase di progettazione iniziale di un flusso di lavoro (fare riferimento a [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md#creating-a-workflow)). Il flusso di lavoro non è ancora gestito dal server e può essere modificato senza alcun rischio.

* **In corso** (blu)

   Una volta completata la fase di progettazione iniziale, il flusso di lavoro può essere avviato e gestito dal server.

* **Completato** (verde)

   Un flusso di lavoro viene completato una volta che non sono più presenti attività in corso o quando un operatore ha esplicitamente arrestato l’istanza.

Una volta avviato, un flusso di lavoro può avere anche altri due stati:

* **Avvertenza** (giallo)

   Il flusso di lavoro non è stato completato o è stato messo in pausa utilizzando ![](assets/pause_darkgrey-24px.png) o ![](assets/check_pause_darkgrey-24px.png) pulsanti.

* **Errato** (rosso)

   Si è verificato un errore durante l’esecuzione di un flusso di lavoro. Il flusso di lavoro è stato interrotto e l’utente deve eseguire un’azione. Per ulteriori informazioni su questo errore, utilizzare ![](assets/printpreview_darkgrey-24px.png) per accedere al registro del flusso di lavoro (consultare [Monitorare](../../automating/using/monitoring-workflow-execution.md)).

L’elenco delle attività di marketing ti consente di visualizzare tutti i flussi di lavoro e i relativi stati. Per ulteriori informazioni, consulta [Gestione delle attività di marketing](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
