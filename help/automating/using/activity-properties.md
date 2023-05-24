---
title: Gestione delle proprietà delle attività
description: Scopri come gestire le proprietà delle attività del flusso di lavoro.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 9c47ef72-59af-4b55-8e65-d8f687fb5fbe
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---

# Gestione delle proprietà delle attività {#activity-properties}

## Proprietà globali di un’attività {#global-properties-of-an-activity}

Ogni attività ha un **[!UICONTROL General]** , che ti consente di modificare i parametri generali specifici dell’attività.

![](assets/activity-properties.png)

Il **[!UICONTROL Properties]** Questa scheda ti consente di modificare i parametri globali dell’attività, in particolare l’etichetta e l’ID. La configurazione di questa scheda è facoltativa.

![](assets/activity-properties2.png)

## Gestione delle transizioni in uscita di un’attività {#managing-an-activity-s-outbound-transitions}

Per impostazione predefinita, alcune attività non hanno una transizione in uscita. Puoi aggiungerne uno dalla sezione **[!UICONTROL Transitions]** o dalla scheda dell’attività **[!UICONTROL Properties]** per applicare altri processi alla popolazione nello stesso flusso di lavoro.

A seconda delle attività, puoi aggiungere diversi tipi di transizioni in uscita:

* **Transizione standard**: popolazione calcolata dall’attività
* **Transizione senza popolazione**: è possibile aggiungere questo tipo di transizione in uscita per continuare il flusso di lavoro e non contiene alcuna popolazione per non consumare spazio inutile sul sistema.
* **Rifiuti**: popolazione rifiutata. Ad esempio, se i dati in entrata dell’attività non possono essere elaborati perché errati o incompleti.
* **Complemento**: popolazione rimanente dopo l’esecuzione dell’attività. Ad esempio, se un’attività di segmentazione è configurata per salvare solo una percentuale del gruppo in entrata.

Se del caso, specificare: **[!UICONTROL Segment code]** per la transizione in uscita dell’attività. Questo codice di segmento ti consente di identificare da dove provengono i sottoinsiemi della popolazione target e può, in seguito, servire a scopo di personalizzazione dei messaggi.

## Opzioni di esecuzione attività {#activity-execution-options}

Nella schermata delle proprietà dell’attività è **[!UICONTROL Advanced options]** che consente di definire la modalità di esecuzione dell’attività e il comportamento in caso di errori.

Per accedere a queste opzioni, seleziona un’attività in un flusso di lavoro, quindi aprila utilizzando ![](assets/edit_darkgrey-24px.png) dalla barra delle azioni.

![](assets/wkf_advanced_parameters.png)

Il **[!UICONTROL Execution]** consente di definire l&#39;azione da eseguire all&#39;avvio dell&#39;attività. Sono disponibili tre opzioni:

* **Normale**: l’attività viene eseguita normalmente.
* **Attiva ma non esegui**: l’attività viene sospesa e, di conseguenza, anche i processi futuri successivi. Questa funzione può rivelarsi utile se si desidera essere presenti all&#39;avvio dell&#39;attività.
* **Non abilitare**: l’attività non viene eseguita e, di conseguenza, non tutte le attività che seguono (nello stesso ramo).

Il **[!UICONTROL In case of error]** consente di specificare l’azione da eseguire in caso di errore dell’attività. Sono disponibili due opzioni:

* **Sospendi il processo**: il flusso di lavoro viene sospeso automaticamente. Lo stato del flusso di lavoro è quindi **Errato** e il colore associato diventa rosso. Una volta risolto il problema, riavvia il flusso di lavoro.
* **Ignora**: l’attività non viene eseguita e, di conseguenza, non esiste alcuna delle attività che la seguono (nello stesso ramo). Ciò può rivelarsi utile per attività ricorrenti. Se il ramo dispone di un modulo di pianificazione posizionato a monte, questo dovrebbe attivarsi alla data di esecuzione successiva.

Il **[!UICONTROL Behavior]** consente di definire la procedura da seguire se vengono utilizzate attività asincrone. Sono disponibili due opzioni:

* **Più attività autorizzate**: è possibile eseguire più attività contemporaneamente anche se la prima non è stata completata.
* **L&#39;attività corrente ha la priorità**: quando un’attività è in corso, ha la priorità. Se un&#39;attività è ancora in corso, non verrà eseguita alcuna altra attività.

Il **[!UICONTROL Max. execution duration]** consente di specificare una durata, ad esempio &quot;30s&quot; o &quot;1h&quot;. Se l’attività non viene completata dopo la scadenza della durata specificata, viene attivato un avviso. Questo non ha alcun impatto sul funzionamento del flusso di lavoro.

Il **[!UICONTROL Affinity]** consente di forzare l’esecuzione di un flusso di lavoro o di un’attività del flusso di lavoro su un determinato computer. A questo scopo, devi specificare una o più affinità per il flusso di lavoro o l’attività in questione.

Il **[!UICONTROL Time zone]** consente di selezionare il fuso orario dell’attività. Adobe Campaign consente di gestire le differenze di tempo tra più paesi nella stessa istanza. L’impostazione applicata viene configurata al momento della creazione dell’istanza.

>[!NOTE]
>
>Per impostazione predefinita, se non è selezionato alcun fuso orario, l’attività utilizzerà il fuso orario definito nelle proprietà del flusso di lavoro.

Il **Commento** campo libero che consente di aggiungere una nota.
