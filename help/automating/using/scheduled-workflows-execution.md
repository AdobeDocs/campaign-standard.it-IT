---
solution: Campaign Standard
product: campaign
title: Esecuzione sovrapposta dei flussi di lavoro programmati
description: Scoprite come impedire la sovrapposizione di flussi di lavoro pianificati.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 4a61c988f95dd84797e6e33707651304223045fb
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 0%

---


# Esecuzione sovrapposta dei flussi di lavoro programmati{#preventing-overlapping-execution-of-scheduled-workflows}

## Informazioni sull&#39;esecuzione dei flussi di lavoro pianificati

In Campaign Standard, il motore del flusso di lavoro garantisce che un&#39;istanza del flusso di lavoro venga eseguita da un solo processo. Il blocco di attività come importazioni, query in esecuzione prolungate o operazioni di scrittura nel database impedisce l&#39;esecuzione di qualsiasi altra attività durante l&#39;esecuzione.

D&#39;altro canto, le attività di non blocco non bloccano l&#39;esecuzione di altre attività (solitamente le attività in attesa di un evento come l&#39;attività **[!UICONTROL Scheduler]**).

Ciò potrebbe causare l’avvio di un flusso di lavoro basato sulla pianificazione anche quando l’esecuzione precedente dello stesso flusso di lavoro non è ancora terminata, con possibili problemi di dati imprevisti.

Pertanto, durante la progettazione di un flusso di lavoro pianificato che include più attività, è necessario assicurarsi che il flusso di lavoro non venga ripianificato fino al termine. A tal fine, è necessario configurare il flusso di lavoro in modo da impedirne l&#39;esecuzione se una o più attività di un&#39;esecuzione precedente sono ancora in sospeso.

## Configurazione del flusso di lavoro

Per verificare se una o più attività di una precedente esecuzione del flusso di lavoro sono ancora in sospeso, è necessario utilizzare un&#39;attività **[!UICONTROL Query]** e **[!UICONTROL Test]**.

1. Aggiungete un&#39;attività **[!UICONTROL Query]** dopo l&#39;attività **[!UICONTROL Scheduler]**, quindi configuratela come segue.

1. Modificate la risorsa dell&#39;attività in **[!UICONTROL WorkflowTaskDetail]**, il che significa che verrà indirizzata alle attività correnti del flusso di lavoro.

   ![](assets/scheduled-wkf-resource.png)

1. Configura la query con le regole riportate di seguito:

   ![](assets/scheduled-wkf-query.png)

   * La prima regola esclude l&#39;attività corrente (query2) e l&#39;attività di pianificazione successiva (pianificazione2) appartenente al flusso di lavoro corrente.

      >[!NOTE]
      >
      >Quando inizia un&#39;attività **[!UICONTROL Scheduler]**, aggiunge immediatamente un&#39;altra attività di pianificazione da eseguire all&#39;ora pianificata successiva e avvia il flusso di lavoro. Pertanto, è importante filtrare sia la query che le attività di pianificazione quando si cercano le attività in sospeso da un&#39;esecuzione precedente.

   * La seconda regola determina se le attività di una precedente esecuzione del flusso di lavoro sono ancora attive (in attesa), che corrisponde allo stato di esecuzione 0.

1. Aggiungete un&#39;attività **[!UICONTROL Test]** per verificare il numero di attività in sospeso restituite dall&#39;attività **[!UICONTROL Query]**. A questo scopo, configurate due transizioni in uscita.

   ![](assets/scheduled-wkf-test.png)

   * La prima transizione prosegue l&#39;esecuzione del flusso di lavoro in assenza di attività in sospeso,
   * La seconda transizione annulla l&#39;esecuzione del flusso di lavoro in presenza di attività in sospeso.

   ![](assets/scheduled-wkf-workflow.png)

Ora puoi configurare il resto del flusso di lavoro in base alle esigenze. Se l&#39;esecuzione del flusso di lavoro viene annullata a causa di attività in sospeso, quando il flusso di lavoro viene eseguito nuovamente secondo la pianificazione, è possibile eseguire questi passaggi. In questo modo l&#39;esecuzione del flusso di lavoro procederà solo se non sono presenti attività attive (in sospeso) da un&#39;esecuzione precedente.
