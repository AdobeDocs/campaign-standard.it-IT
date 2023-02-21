---
title: Monitoraggio dell’esecuzione dei flussi di lavoro
description: Scopri come monitorare l’esecuzione di un flusso di lavoro.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d2ce702b-92d1-4b94-bd47-34ef46a8bd9f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 6%

---

# Monitoraggio dell’esecuzione dei flussi di lavoro {#monitoring}

## Registro di lavoro e attività {#workflow-log-and-tasks}

La ![](assets/printpreview_darkgrey-24px.png) apre il registro del flusso di lavoro e il menu attività.

La cronologia del flusso di lavoro viene salvata per la durata specificata nelle opzioni di esecuzione del flusso di lavoro (consulta [Proprietà del flusso di lavoro](../../automating/using/managing-execution-options.md)). Durante questa durata, tutti i messaggi vengono quindi salvati, anche dopo un riavvio. Se non desideri salvare i messaggi da un’esecuzione precedente, devi eliminare la cronologia facendo clic sul pulsante ![](assets/delete_darkgrey-24px.png) pulsante .

La **[!UICONTROL Log]** contiene la cronologia di esecuzione di tutte le attività o di tutte le attività selezionate. Questi registri indicizzano in ordine cronologico le operazioni effettuate e gli errori di esecuzione.

![](assets/wkf_execution_4.png)

La **[!UICONTROL Tasks]** la scheda descrive la sequenza di esecuzione delle attività. Fai clic su un’attività per ottenere ulteriori informazioni.

![](assets/wkf_execution_5.png)

In questi due elenchi:

* Fai clic sul contatore per visualizzare il numero totale di attività in base al filtro applicato. Il contatore viene visualizzato per impostazione predefinita se il numero di elementi nell’elenco è inferiore a 30.
* La **[!UICONTROL Configure list]** consente di scegliere le informazioni visualizzate, definire l’ordine delle colonne e ordinare l’elenco.
* Puoi utilizzare i filtri per trovare le informazioni necessarie in modo più rapido. Utilizza il campo di ricerca per cercare un testo specifico nei nomi delle attività del flusso di lavoro (ad esempio: &quot;query&quot;) e registri.

## Gestione degli errori {#error-management}

Quando si verifica un errore, il flusso di lavoro viene messo in pausa e l&#39;attività in esecuzione quando si è verificato l&#39;errore lampeggia in rosso.

Lo stato del flusso di lavoro diventa rosso e l’errore viene registrato nel registro.

Puoi configurare il flusso di lavoro in modo che non venga messo in pausa e continui l’esecuzione senza errori. A questo scopo, vai alle proprietà del flusso di lavoro tramite il ![](assets/edit_darkgrey-24px.png) e **[!UICONTROL Execution]** seleziona la sezione **Ignora** in **In caso di errore** campo .

In questo caso, l&#39;attività errata viene interrotta. Questa modalità è particolarmente adatta ai flussi di lavoro progettati per riprovare più tardi (azioni periodiche).

>[!NOTE]
>
>Puoi applicare questa configurazione singolarmente per ogni attività. A questo scopo, seleziona un’attività e aprila utilizzando l’azione rapida . ![](assets/edit_darkgrey-24px.png). Quindi seleziona la modalità di gestione degli errori nel **Opzioni di esecuzione** scheda . Vedi [Opzioni di esecuzione delle attività](../../automating/using/activity-properties.md).

In [proprietà del flusso di lavoro](../../automating/using/managing-execution-options.md), sono disponibili opzioni aggiuntive relative alla gestione degli errori.

![](assets/wkf_execution_error.png)

Le opzioni possibili sono:

* **[!UICONTROL Supervisors]**: consente di definire il gruppo di persone a cui inviare una notifica (e-mail e notifica in-app) se il flusso di lavoro incontra un errore. Se non viene definito alcun gruppo, non verrà inviata alcuna notifica. Per ulteriori informazioni sulle notifiche di Adobe Campaign, consulta [Notifiche di Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **[!UICONTROL In case of error]**: consente di specificare l’azione da eseguire in caso di errore nell’attività. Sono disponibili due opzioni:

   * **Sospendi il processo**: il flusso di lavoro viene sospeso automaticamente. Lo stato del flusso di lavoro viene quindi **Erroneo** e il colore associato diventa rosso. Una volta risolto il problema, riavvia il flusso di lavoro.
   * **Ignora**: l’attività non viene eseguita e, di conseguenza, nessuna delle attività che la seguono (nello stesso ramo). Questo può rivelarsi utile per le attività ricorrenti. Se il ramo dispone di una pianificazione posizionata a monte, questa deve essere attivata alla data di esecuzione successiva.

* **[!UICONTROL Consecutive errors]** : consente di definire un numero di errori consecutivi autorizzati prima che l’esecuzione del flusso di lavoro venga sospesa automaticamente.

   * Se il numero specificato è **[!UICONTROL 0]**, oppure finché il numero specificato non viene raggiunto, le attività che riscontrano errori vengono ignorate. Gli altri rami del flusso di lavoro vengono eseguiti normalmente.

   * Se viene raggiunto il numero specificato, l&#39;intero flusso di lavoro viene sospeso e diventa **[!UICONTROL Erroneous]**. Se i supervisori sono stati definiti, vengono automaticamente informati tramite e-mail. Consulta [Notifiche di Adobe Campaign](../../administration/using/sending-internal-notifications.md).
