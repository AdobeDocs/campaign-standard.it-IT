---
title: Ciclo di vita di un flusso di lavoro
description: Ulteriori informazioni sul ciclo di vita del flusso di lavoro
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: ba968add-25a3-4962-9e90-f0a06d9b74a8
TQID: 'https://experienceleague.adobe.com/nWv8hOZa2JQgiO2CEnffriIqb6czIA7Gh0AwWCTwRAA'
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
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
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

* **Avviso** (giallo)

  Impossibile completare o sospendere il flusso di lavoro utilizzando i pulsanti ![](assets/pause_darkgrey-24px.png) o ![](assets/check_pause_darkgrey-24px.png).

* **Errato** (rosso)

  Si è verificato un errore durante l’esecuzione di un flusso di lavoro. Il flusso di lavoro è stato interrotto e l’utente deve eseguire un’azione. Per ulteriori informazioni sull&#39;errore, utilizzare il pulsante ![](assets/printpreview_darkgrey-24px.png) per accedere al registro del flusso di lavoro (consultare [Monitoraggio](../../automating/using/monitoring-workflow-execution.md)).

L’elenco delle attività di marketing ti consente di visualizzare tutti i flussi di lavoro e i relativi stati. Per ulteriori informazioni, consulta [Gestione delle attività di marketing](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)
