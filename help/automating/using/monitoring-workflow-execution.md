---
title: Esecuzione del flusso di lavoro di monitoraggio
description: Scopri come monitorare l’esecuzione di un flusso di lavoro.
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
source-git-commit: 3ed78fd610b0d134cd1e60f34c93161cb1e5c50f
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---


# Esecuzione del flusso di lavoro di monitoraggio {#monitoring}

## Flusso di lavoro e attività {#workflow-log-and-tasks}

L&#39; ![](assets/printpreview_darkgrey-24px.png) icona apre il registro del flusso di lavoro e il menu delle attività.

La cronologia del flusso di lavoro viene salvata per la durata specificata nelle opzioni di esecuzione del flusso di lavoro (vedere Proprietà [del](#workflow-properties)flusso di lavoro). Durante questa durata, tutti i messaggi vengono quindi salvati, anche dopo il riavvio. Se non si desidera salvare i messaggi da un&#39;esecuzione precedente, è necessario eliminare la cronologia facendo clic sul ![](assets/delete_darkgrey-24px.png) pulsante.

La **[!UICONTROL Log]** scheda contiene la cronologia di esecuzione di tutte le attività o di tutte le attività selezionate. Esso indicizza le operazioni eseguite e gli errori di esecuzione in ordine cronologico.

![](assets/wkf_execution_4.png)

La **[!UICONTROL Tasks]** scheda descrive la sequenza di esecuzione delle attività. Fate clic su un’attività per ottenere ulteriori informazioni.

![](assets/wkf_execution_5.png)

In questi due elenchi:

* Fare clic sul contatore per visualizzare il numero totale di attività in base al filtro applicato. Il contatore viene visualizzato per impostazione predefinita se il numero di elementi nell&#39;elenco è inferiore a 30.
* Il **[!UICONTROL Configure list]** pulsante consente di scegliere le informazioni visualizzate, definire l’ordine delle colonne e ordinare l’elenco.
* Potete utilizzare i filtri per trovare le informazioni necessarie in modo più rapido. Usate il campo di ricerca per cercare un testo specifico nei nomi delle attività del flusso di lavoro (ad esempio: &quot;query&quot;) e registri.

## Gestione errori {#error-management}

Quando si verifica un errore, il flusso di lavoro viene messo in pausa e l&#39;attività che veniva eseguita quando l&#39;errore veniva rilevato lampeggia in rosso.

Lo stato del flusso di lavoro diventa rosso e l’errore viene registrato nel registro.

È possibile configurare il flusso di lavoro in modo che non venga messo in pausa e che continui a essere eseguito senza errori. A questo scopo, passare alle proprietà del flusso di lavoro tramite il ![](assets/edit_darkgrey-24px.png) pulsante e, nella **[!UICONTROL Execution]** sezione, selezionare l&#39;opzione **Ignora** nel campo **In caso di errore** .

In questo caso, l&#39;attività errata viene interrotta. Questa modalità è particolarmente adatta ai flussi di lavoro progettati per ripetere l&#39;operazione in un secondo momento (azioni periodiche).

>[!NOTE]
>
>Potete applicare questa configurazione singolarmente per ogni attività. A questo scopo, selezionate un&#39;attività e apritela utilizzando l&#39;azione rapida ![](assets/edit_darkgrey-24px.png). Selezionate quindi la modalità di gestione degli errori nella scheda Opzioni **** esecuzione. Consultate Opzioni [di esecuzione](#activity-execution-options)dell&#39;attività.

Nelle proprietà [del](#workflow-properties)flusso di lavoro sono disponibili opzioni aggiuntive relative alla gestione degli errori.

![](assets/wkf_execution_error.png)

Le opzioni possibili sono:

* **[!UICONTROL Supervisors]**: consente di definire il gruppo di persone da notificare (e-mail e notifica in-app) in caso di errore nel flusso di lavoro. Se non viene definito alcun gruppo, non verrà inviata alcuna notifica. Per ulteriori informazioni sulle notifiche di Adobe Campaign, consulta le notifiche [di](../../administration/using/sending-internal-notifications.md)Adobe Campaign.

* **[!UICONTROL In case of error]**: consente di specificare l&#39;azione da eseguire in caso di errore dell&#39;attività. Sono disponibili due opzioni:

   * **Sospendere il processo**: il flusso di lavoro viene automaticamente sospeso. Lo stato del flusso di lavoro è quindi **Erroneo** e il colore associato diventa rosso. Una volta risolto il problema, riavviate il flusso di lavoro.
   * **Ignora**: l&#39;attività non viene eseguita, e di conseguenza nessuna delle attività che la seguono (nello stesso ramo). Ciò può risultare utile per le attività ricorrenti. Se il ramo dispone di un pianificatore posizionato a monte, questo deve essere attivato alla data di esecuzione successiva.

* **[!UICONTROL Consecutive errors]** : consente di definire un numero di errori consecutivi autorizzati prima che l&#39;esecuzione del flusso di lavoro venga automaticamente sospesa.

   * Se il numero specificato è **[!UICONTROL 0]** o finché il numero specificato non viene raggiunto, le attività che rilevano errori vengono ignorate. Gli altri rami del flusso di lavoro vengono eseguiti normalmente.

   * Se viene raggiunto il numero specificato, l&#39;intero flusso di lavoro viene sospeso e diventa **[!UICONTROL Erroneous]**. Se i supervisori sono stati definiti, vengono automaticamente informati tramite e-mail. Vedi Notifiche [di](../../administration/using/sending-internal-notifications.md)Adobe Campaign.
