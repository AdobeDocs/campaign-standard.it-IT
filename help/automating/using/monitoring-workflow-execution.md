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
source-wordcount: '578'
ht-degree: 6%

---

# Monitoraggio dell’esecuzione dei flussi di lavoro {#monitoring}

## Registro del flusso di lavoro e attività {#workflow-log-and-tasks}

Il ![](assets/printpreview_darkgrey-24px.png) apre il menu log e task del flusso di lavoro.

La cronologia del flusso di lavoro viene salvata per la durata specificata nelle opzioni di esecuzione del flusso di lavoro (consultare [Proprietà del flusso di lavoro](../../automating/using/managing-execution-options.md)). Durante questo periodo, tutti i messaggi vengono quindi salvati, anche dopo un riavvio. Se non desideri salvare i messaggi di un’esecuzione precedente, devi eliminare la cronologia facendo clic sul pulsante ![](assets/delete_darkgrey-24px.png) pulsante.

Il **[!UICONTROL Log]** contiene la cronologia di esecuzione di tutte le attività o di qualsiasi attività selezionata. Questi registri indicizzano in ordine cronologico le operazioni effettuate e gli errori di esecuzione.

![](assets/wkf_execution_4.png)

Il **[!UICONTROL Tasks]** La scheda descrive la sequenza di esecuzione delle attività. Fare clic su un&#39;attività per ottenere ulteriori informazioni.

![](assets/wkf_execution_5.png)

In questi due elenchi:

* Fai clic sul contatore per visualizzare il numero totale di attività in base al filtro applicato. Il contatore viene visualizzato per impostazione predefinita se il numero di elementi nell&#39;elenco è inferiore a 30.
* Il **[!UICONTROL Configure list]** consente di scegliere le informazioni visualizzate, definire l’ordine delle colonne e ordinare l’elenco.
* I filtri consentono di trovare più rapidamente le informazioni necessarie. Utilizza il campo di ricerca per cercare un testo specifico nei nomi delle attività del flusso di lavoro (ad esempio: &quot;query&quot;) e nei registri.

## Gestione degli errori {#error-management}

Quando si verifica un errore, il flusso di lavoro viene sospeso e l’attività in esecuzione al momento dell’errore lampeggia in rosso.

Lo stato del flusso di lavoro diventa rosso e l’errore viene registrato nel registro.

Puoi configurare il flusso di lavoro in modo che non venga messo in pausa e continui a essere eseguito senza errori. A questo scopo, vai alle proprietà del flusso di lavoro tramite ![](assets/edit_darkgrey-24px.png) e, nella **[!UICONTROL Execution]** , seleziona la sezione **Ignora** opzione in **In caso di errore** campo.

In questo caso, l&#39;attività errata viene interrotta. Questa modalità è particolarmente adatta per i flussi di lavoro progettati per ritentare l’operazione in un secondo momento (azioni periodiche).

>[!NOTE]
>
>Puoi applicare questa configurazione singolarmente per ogni attività. A questo scopo, seleziona un’attività e aprila utilizzando l’azione rapida ![](assets/edit_darkgrey-24px.png). Quindi seleziona la modalità di gestione degli errori in **Opzioni di esecuzione** scheda. Consulta [Opzioni di esecuzione attività](../../automating/using/activity-properties.md).

In [proprietà del flusso di lavoro](../../automating/using/managing-execution-options.md), sono disponibili opzioni aggiuntive relative alla gestione degli errori.

![](assets/wkf_execution_error.png)

Le opzioni possibili sono:

* **[!UICONTROL Supervisors]**: consente di definire il gruppo di persone a cui inviare la notifica (e-mail e notifica in-app) in caso di errore del flusso di lavoro. Se non è definito alcun gruppo, non verrà inviata alcuna notifica. Per ulteriori informazioni sulle notifiche di Adobe Campaign, consulta [Notifiche di Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **[!UICONTROL In case of error]**: ti consente di specificare l’azione da eseguire in caso di errore dell’attività. Sono disponibili due opzioni:

   * **Sospendi il processo**: il flusso di lavoro viene sospeso automaticamente. Lo stato del flusso di lavoro è quindi **Errato** e il colore associato diventa rosso. Una volta risolto il problema, riavvia il flusso di lavoro.
   * **Ignora**: l’attività non viene eseguita e, di conseguenza, non esiste alcuna delle attività che la seguono (nello stesso ramo). Ciò può rivelarsi utile per attività ricorrenti. Se il ramo dispone di un modulo di pianificazione posizionato a monte, questo dovrebbe attivarsi alla data di esecuzione successiva.

* **[!UICONTROL Consecutive errors]** : consente di definire una serie di errori consecutivi autorizzati prima della sospensione automatica dell’esecuzione del flusso di lavoro.

   * Se il numero specificato è **[!UICONTROL 0]** oppure finché non viene raggiunto il numero specificato, le attività che presentano errori vengono ignorate. Gli altri rami del flusso di lavoro vengono eseguiti normalmente.

   * Se viene raggiunto il numero specificato, l’intero flusso di lavoro viene sospeso e diventa **[!UICONTROL Erroneous]**. Se sono stati definiti dei supervisori, questi vengono automaticamente informati tramite e-mail. Consulta [Notifiche di Adobe Campaign](../../administration/using/sending-internal-notifications.md).
