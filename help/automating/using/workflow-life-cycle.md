---
solution: Campaign Standard
product: campaign
title: Ciclo di vita di un flusso di lavoro
description: Ulteriori informazioni sul ciclo di vita del flusso di lavoro
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---


# Ciclo di vita di un flusso di lavoro {#life-cycle}

Il ciclo di vita di un flusso di lavoro comprende tre passaggi principali, ciascuno dei quali è collegato a uno stato e a un colore:

* **Modifica**  (grigia)

   Si tratta della fase iniziale di progettazione di un flusso di lavoro (vedere [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md#creating-a-workflow)). Il flusso di lavoro non è ancora gestito dal server e può essere modificato senza rischi.

* **In corso**  (blu)

   Una volta completata la fase di progettazione iniziale, il flusso di lavoro può essere avviato e gestito dal server.

* **Finito**  (verde)

   Un flusso di lavoro viene completato una volta che non sono più presenti attività in corso o quando un operatore ha interrotto in modo esplicito l&#39;istanza.

Una volta avviato, un flusso di lavoro potrebbe presentare anche altri due stati:

* **Avviso**  (giallo)

   Impossibile completare il flusso di lavoro o è stato messo in pausa utilizzando i pulsanti ![](assets/pause_darkgrey-24px.png) o ![](assets/check_pause_darkgrey-24px.png).

* **Erroneo**  (rosso)

   Errore durante l&#39;esecuzione di un flusso di lavoro. Il flusso di lavoro è stato arrestato e l&#39;utente deve eseguire un&#39;azione. Per ulteriori informazioni su questo errore, utilizzare il pulsante ![](assets/printpreview_darkgrey-24px.png) per accedere al registro del flusso di lavoro (fare riferimento a [Monitoring](../../automating/using/monitoring-workflow-execution.md)).

L&#39;elenco delle attività di marketing consente di visualizzare tutti i flussi di lavoro e i relativi stati. Per ulteriori informazioni, vedere [Gestione delle attività di marketing](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
