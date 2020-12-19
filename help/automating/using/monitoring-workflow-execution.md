---
solution: Campaign Standard
product: campaign
title: Monitoraggio dell’esecuzione dei flussi di lavoro
description: Scopri come monitorare l’esecuzione di un flusso di lavoro.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 3%

---


# Monitoraggio dell’esecuzione dei flussi di lavoro {#monitoring}

## Registro dei flussi di lavoro e attività {#workflow-log-and-tasks}

L&#39;icona ![](assets/printpreview_darkgrey-24px.png) apre il registro del flusso di lavoro e il menu delle attività.

La cronologia del flusso di lavoro viene salvata per la durata specificata nelle opzioni di esecuzione del flusso di lavoro (fare riferimento a [Proprietà del flusso di lavoro](../../automating/using/managing-execution-options.md)). Durante questa durata, tutti i messaggi vengono quindi salvati, anche dopo il riavvio. Se non si desidera salvare i messaggi da un&#39;esecuzione precedente, è necessario eliminare la cronologia facendo clic sul pulsante ![](assets/delete_darkgrey-24px.png).

La scheda **[!UICONTROL Log]** contiene la cronologia di esecuzione di tutte le attività o di tutte le attività selezionate. Questi registri indicizzano in ordine cronologico le operazioni effettuate e gli errori di esecuzione.

![](assets/wkf_execution_4.png)

La scheda **[!UICONTROL Tasks]** indica la sequenza di esecuzione delle attività. Fate clic su un’attività per ottenere ulteriori informazioni.

![](assets/wkf_execution_5.png)

In questi due elenchi:

* Fare clic sul contatore per visualizzare il numero totale di attività in base al filtro applicato. Il contatore viene visualizzato per impostazione predefinita se il numero di elementi nell&#39;elenco è inferiore a 30.
* Il pulsante **[!UICONTROL Configure list]** consente di scegliere le informazioni visualizzate, definire l&#39;ordine delle colonne e ordinare l&#39;elenco.
* Potete utilizzare i filtri per trovare le informazioni necessarie in modo più rapido. Usate il campo di ricerca per cercare un testo specifico nei nomi delle attività del flusso di lavoro (ad esempio: &quot;query&quot;) e registri.

## Gestione errori {#error-management}

Quando si verifica un errore, il flusso di lavoro viene messo in pausa e l&#39;attività che veniva eseguita quando l&#39;errore veniva rilevato lampeggia in rosso.

Lo stato del flusso di lavoro diventa rosso e l’errore viene registrato nel registro.

È possibile configurare il flusso di lavoro in modo che non venga messo in pausa e che continui a essere eseguito senza errori. A tal fine, passare alle proprietà del flusso di lavoro tramite il pulsante ![](assets/edit_darkgrey-24px.png) e, nella sezione **[!UICONTROL Execution]**, selezionare l&#39;opzione **Ignore** nel campo **In caso di errore**.

In questo caso, l&#39;attività errata viene interrotta. Questa modalità è particolarmente adatta ai flussi di lavoro progettati per ripetere l&#39;operazione in un secondo momento (azioni periodiche).

>[!NOTE]
>
>Potete applicare questa configurazione singolarmente per ogni attività. A questo scopo, selezionate un&#39;attività e apritela utilizzando l&#39;azione rapida ![](assets/edit_darkgrey-24px.png). Quindi selezionare la modalità di gestione degli errori nella scheda **Opzioni di esecuzione**. Vedere [Opzioni di esecuzione dell&#39;attività](../../automating/using/activity-properties.md).

Nelle proprietà del [flusso di lavoro](../../automating/using/managing-execution-options.md) sono disponibili opzioni aggiuntive relative alla gestione degli errori.

![](assets/wkf_execution_error.png)

Le opzioni possibili sono:

* **[!UICONTROL Supervisors]**: consente di definire il gruppo di persone a cui inviare una notifica (e-mail e notifica in-app) in caso di errore nel flusso di lavoro. Se non viene definito alcun gruppo, non verrà inviata alcuna notifica. Per ulteriori informazioni  notifiche Adobe Campaign, fare riferimento a [ notifiche Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **[!UICONTROL In case of error]**: consente di specificare l&#39;azione da eseguire in caso di errore dell&#39;attività. Sono disponibili due opzioni:

   * **Sospendere il processo**: il flusso di lavoro viene automaticamente sospeso. Lo stato del flusso di lavoro è quindi **Erroneo** e il colore associato diventa rosso. Una volta risolto il problema, riavviate il flusso di lavoro.
   * **Ignora**: l&#39;attività non viene eseguita, e di conseguenza nessuna delle attività che la seguono (nello stesso ramo). Ciò può risultare utile per le attività ricorrenti. Se il ramo dispone di un pianificatore posizionato a monte, questo deve essere attivato alla data di esecuzione successiva.

* **[!UICONTROL Consecutive errors]** : consente di definire un numero di errori consecutivi autorizzati prima che l&#39;esecuzione del flusso di lavoro venga automaticamente sospesa.

   * Se il numero specificato è **[!UICONTROL 0]**, o finché il numero specificato non viene raggiunto, le attività che rilevano errori vengono ignorate. Gli altri rami del flusso di lavoro vengono eseguiti normalmente.

   * Se viene raggiunto il numero specificato, l&#39;intero flusso di lavoro viene sospeso e diventa **[!UICONTROL Erroneous]**. Se i supervisori sono stati definiti, vengono automaticamente informati tramite e-mail. Consulta [Notifiche di Adobe Campaign](../../administration/using/sending-internal-notifications.md).
