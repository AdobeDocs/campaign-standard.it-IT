---
title: Esecuzione di un flusso di lavoro
seo-title: Esecuzione di un flusso di lavoro
description: Esecuzione di un flusso di lavoro
seo-description: Scopri come eseguire e monitorare un flusso di lavoro.
page-status-flag: never-activated
uuid: ff 02 b 74 e -53 e 8-49 c 6-bf 8 e -0 c 729 eaa 7 d 25
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: workflow-general-operation
discoiquuid: 906 c 85 ea -83 b 7-4268-86 da-cd 353 f 1 dc 591
context-tags: flusso di lavoro, panoramica; flusso di lavoro, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e33cbfbf6376dabfe81b9bd6f7cce817f35d1b75

---


# Executing a workflow{#executing-a-workflow}

## About workflow execution {#about-workflow-execution}

Un flusso di lavoro viene sempre avviato manualmente. However, once started, it can remain inactive, depending on the information specified in a [Scheduler](../../automating/using/scheduler.md) activity.

>[!CAUTION]
>
> Adobe consiglia ai clienti di dare priorità alle esecuzioni del flusso di lavoro ed eseguire fino a venti esecuzioni simultanee di flussi di lavoro per ottenere in modo coerente le prestazioni massime nell'istanza. Possono essere pianificate più di venti esecuzioni di flussi di lavoro simultanee e vengono eseguite in sequenza per impostazione predefinita. Puoi regolare le impostazioni predefinite per il numero massimo di esecuzioni simultanee del flusso di lavoro inviando un ticket all'Assistenza clienti.

Azioni relative all'esecuzione (avvio, interruzione, pausa, ecc.) are **asynchronous** processes: the command is saved and will become effective once the server is available to apply it.

In un flusso di lavoro, il risultato di ogni attività viene generalmente inviato all'attività seguente tramite una transizione, rappresentata da una freccia.

Una transizione non viene terminata se non è collegata a un'attività di destinazione.

![](assets/wkf_execution_1.png)

>[!NOTE]
>
>È possibile eseguire un flusso di lavoro contenente transizioni non ancora chiamate: viene generato un messaggio di avviso e il flusso di lavoro si interrompe una volta raggiunta la transizione, ma questo non genererà un errore. Potete anche avviare un flusso di lavoro senza aver completato completamente la progettazione e completarlo man mano che passate.

Una volta eseguita un'attività, il numero di record inviati nella transizione viene visualizzato al di sopra di esso.

![](assets/wkf_transition_count.png)

È possibile aprire le transizioni per verificare che i dati inviati siano corretti durante o dopo l'esecuzione del flusso di lavoro. È possibile visualizzare i dati e la struttura dati.

Per impostazione predefinita, sono accessibili solo i dettagli dell'ultima transizione del flusso di lavoro. To be able to access the results of the preceding activities, you need to check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties, before starting the workflow.

>[!NOTE]
>
>Questa opzione consuma molta memoria ed è concepita per aiutare a costruire un flusso di lavoro e a garantire che sia configurata e eseguita correttamente. Lasciatela non selezionata per le istanze di produzione.

When a transition is open, you can edit its **[!UICONTROL Label]** or link a **[!UICONTROL Segment code]** to it. A tal fine, modificate i campi corrispondenti e confermate le modifiche.

## Controlling a workflow from the REST API {#controlling-a-workflow-from-the-rest-api}

Using the REST API, you can **start**, **pause**, **resume** and **stop** a workflow.

You can find more details and examples of REST calls in the [API documentation.](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#controlling-a-workflow)

## Life cycle {#life-cycle}

Il ciclo di vita di un flusso di lavoro comprende tre passaggi principali e ciascun passaggio è collegato a uno stato e a un colore:

* **Modifica** (grigio)

   This is the initial design phase of a workflow (refer to [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow)). Il flusso di lavoro non è ancora gestito dal server e può essere modificato senza rischi.

* **In corso** (blu)

   Una volta completata la fase iniziale della progettazione, il flusso di lavoro può essere avviato e gestito dal server.

* **Completato** (verde)

   Un flusso di lavoro è terminato una volta che non sono più presenti attività in corso o se un operatore ha interrotto esplicitamente l'istanza.

Una volta avviata, un flusso di lavoro può avere anche due stati:

* **Avviso** (giallo)

   The workflow could not finish or was paused using the ![](assets/pause_darkgrey-24px.png) or ![](assets/check_pause_darkgrey-24px.png) buttons.

* **Sbagliato** (rosso)

   Si è verificato un errore durante l'esecuzione di un flusso di lavoro. Il flusso di lavoro è stato interrotto e l'utente deve eseguire un'azione. To find out more about this error, use the ![](assets/printpreview_darkgrey-24px.png) button to access the workflow log (refer to [Monitoring](../../automating/using/executing-a-workflow.md#monitoring)).

L'elenco delle attività di marketing consente di visualizzare tutti i flussi di lavoro e i relativi stati. For more on this, see [Managing marketing activities](../../start/using/marketing-activities.md#about-marketing-activities).

![](assets/wkf_execution_3.png)

## Execution commands {#execution-commands}

Le icone nella barra delle azioni consentono di avviare, tracciare e modificare l'esecuzione di un flusso di lavoro. See [Action bar](../../automating/using/workflow-interface.md#action-bar).

![](assets/wkf_execution_2.png)

Le azioni disponibili sono le seguenti:

**Start**

![](assets/play_darkgrey-24px.png) Il pulsante avvia l'esecuzione di un flusso di lavoro, che quindi assume lo **stato in corso** (blu). Se il flusso di lavoro è stato messo in pausa, viene ripreso, altrimenti viene avviato e le attività iniziali vengono attivate.

>[!NOTE]
>
>L'avvio è un processo asincrono: la richiesta viene salvata e sarà elaborata il prima possibile dal motore di esecuzione del flusso di lavoro.

**Pausa**

![](assets/pause_darkgrey-24px.png) Il pulsante mette in pausa l'esecuzione. The workflow takes on the **Warning** (yellow) status. Nessuna nuova attività verrà attivata finché non viene ripresa, ma le operazioni in corso non vengono sospese.

**Interrompi**

![](assets/stop_darkgrey-24px.png) Il pulsante interrompe un flusso di lavoro che viene eseguito, che quindi assumerà lo **stato Completato** (verde). Le operazioni in corso vengono interrotte, se possibile, e le importazioni o le query SQL in corso vengono immediatamente annullate. Non è possibile riprendere dal flusso di lavoro nello stesso punto in cui è stato interrotto.

**Riavvia**

The ![](assets/pauseplay_darkgrey-24px.png) button involves stopping, then restarting a workflow. Nella maggior parte dei casi, questo consente di riavviare più rapidamente. It can also be useful to automate restarting once stopping takes a certain amount of time, because the ![](assets/play_darkgrey-24px.png) button is only available when the stop is effective.

Quando sono selezionate una o più attività in un flusso di lavoro, sono disponibili altre azioni, ad esempio:

**Esecuzione immediata**

![](assets/pending_darkgrey-24px.png) Il pulsante avvia tutte le attività in sospeso selezionate il prima possibile.

**Esecuzione normale**

![](assets/check_darkgrey-24px.png) Il pulsante riattiva tutte le attività in pausa o disattivate.

**Esecuzione sospesa**

![](assets/check_pause_darkgrey-24px.png) Il pulsante mette in pausa il flusso di lavoro nell'attività selezionata: tale attività e tutti quelli che lo seguono (nello stesso ramo) non vengono eseguiti.

**Nessuna esecuzione**

![](assets/checkdisable.png) Il pulsante disattiva tutte le attività selezionate.

>[!NOTE]
>
>Le azioni rapide consentono di accedere a diverse azioni relative a una particolare attività e di visualizzare quando un'attività è selezionata.

## Monitoring {#monitoring}

The ![](assets/printpreview_darkgrey-24px.png) icon opens the workflow log and task menu.

The workflow history is saved for the duration specified in the workflow execution options (refer to [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties)). Durante questa durata, tutti i messaggi vengono salvati, anche dopo un riavvio. If you do not want to save the messages from a previous execution, you have to purge the history by clicking the ![](assets/delete_darkgrey-24px.png) button.

The **[!UICONTROL Log]** tab contains the execution history of all the activities or any selected activities. Indicizza le operazioni eseguite e gli errori di esecuzione in base all'ordine cronologico.

![](assets/wkf_execution_4.png)

The **[!UICONTROL Tasks]** tab details the execution sequencing of the activities. Fate clic su un'attività per ottenere ulteriori informazioni.

![](assets/wkf_execution_5.png)

In questi due elenchi:

* Fate clic sul contatore per visualizzare il numero totale di attività in base al filtro applicato. Il contatore viene visualizzato per impostazione predefinita se il numero di elementi nell'elenco è inferiore a 30.
* **[!UICONTROL Configure list]** Il pulsante consente di scegliere le informazioni visualizzate, definire l'ordine delle colonne e ordinare l'elenco.
* Potete usare i filtri per trovare le informazioni necessarie. Utilizzate il campo di ricerca per cercare un testo specifico nei nomi delle attività del flusso di lavoro (ad esempio: " query ") e i registri.

## Error management {#error-management}

Quando si verifica un errore, il flusso di lavoro viene messo in pausa e l'attività che era in esecuzione quando si verifica l'errore lampeggia in rosso.

Lo stato del flusso di lavoro diventa rosso e l'errore viene registrato nel registro.

Potete configurare il flusso di lavoro in modo che non si interrompa e continui a essere eseguito senza errori. To do this, go to the workflow properties via the ![](assets/edit_darkgrey-24px.png) button and, in the **[!UICONTROL Execution]** section, select the **Ignore** option in the **In case of error** field.

In questo caso, l'attività errata viene interrotta. Questa modalità è particolarmente adatta ai flussi di lavoro progettati per riprovare a eseguire nuovamente l'operazione (azioni periodiche).

>[!NOTE]
>
>Potete applicare questa configurazione singolarmente per ogni attività. To do this, select an activity and open it using the quick action ![](assets/edit_darkgrey-24px.png). Then select the error management mode in the **Execution options** tab. See [Activity execution options](../../automating/using/executing-a-workflow.md#activity-execution-options).

The **[!UICONTROL Execution]** section of the workflow properties also allows you to define a number of **[!UICONTROL Consecutive errors]** that are authorized before the workflow execution is automatically suspended. Fintanto che questo numero non viene raggiunto, gli elementi errati vengono ignorati e gli altri rami del flusso di lavoro vengono eseguiti normalmente. Se questo numero viene raggiunto, il flusso di lavoro viene sospeso e i supervisori del flusso di lavoro ricevono una notifica automatica (e-mail e notifica in-app). See [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties) and [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

I supervisori possono anche essere definiti nelle proprietà di esecuzione del flusso di lavoro.

## Workflow properties {#workflow-properties}

To modify a workflow's execution options, use the ![](assets/edit_darkgrey-24px.png) button to access the workflow properties and select the **[!UICONTROL Execution]** section.

**[!UICONTROL Default affinity]** Il campo consente di forzare l'esecuzione di un flusso di lavoro o di un'attività di flusso di lavoro su un particolare computer.

In the **[!UICONTROL History in days]** field, specify the duration after which the history must be purged.

You can choose to check the **[!UICONTROL Save SQL queries in the log]** and **[!UICONTROL Execute in the engine (do not use in production)]** options if necessary.

Check the **[!UICONTROL Keep interim results]** option if you would like to be able to view the detail of transitions. Avviso: il controllo di questa opzione può rallentare notevolmente l'esecuzione del flusso di lavoro.

The **[!UICONTROL Severity]** field allows you to specify a level of priority for executing workflows in your Adobe Campaign instance. Verranno eseguiti prima i flussi di lavoro critici.

The **[!UICONTROL Supervisors]** field is where you can define the group of people to notify (email and in-app notification) if the workflow encounters an error. Se non viene definito alcun gruppo, non verrà notificato alcun gruppo. For more on Adobe Campaign notifications, refer to [Adobe Campaign notifications](../../administration/using/sending-internal-notifications.md).

**[!UICONTROL In case of error]** Il campo consente di specificare l'azione da eseguire qualora l'attività dovesse rilevare un errore. Sono disponibili due opzioni:

* **Sospendi il processo**: il flusso di lavoro viene sospeso automaticamente. The workflow status is then **Erroneous** and the color associated turns red. Una volta risolto il problema, riavviate il flusso di lavoro.
* **Ignora**: l'attività non viene eseguita e, come risultato, nessuna delle attività che lo segue (nello stesso ramo). Ciò potrebbe risultare utile per attività ricorrenti. Se il ramo ha un pianificatore collocato a monte, questo dovrebbe attivarsi alla data di esecuzione successiva.

   By selecting this option, you can also define a number of **[!UICONTROL Consecutive errors]** that are authorized:

   * If the number specified is **[!UICONTROL 0]**, or as long as the number specified is not reached, activities that encounter errors are ignored. Gli altri rami del flusso di lavoro vengono eseguiti normalmente.
   * If the number specified is reached, the whole of the workflow is suspended and becomes **[!UICONTROL Erroneous]**. Se sono stati definiti dei supervisori, vengono notificati automaticamente da un messaggio e-mail.

![](assets/wkf_execution_6.png)

## Activity properties {#activity-properties}

### General properties of an activity {#general-properties-of-an-activity}

Each activity has a **[!UICONTROL Properties]** tab. Questa scheda consente di modificare i parametri generali dell'attività, in particolare l'etichetta e l'ID. La configurazione di questa scheda è facoltativa.

### Managing an activity's outbound transitions {#managing-an-activity-s-outbound-transitions}

Per impostazione predefinita, alcune attività non dispongono di una transizione in uscita. You can add one from the **[!UICONTROL Transitions]** tab or from the activity's **[!UICONTROL Properties]** tab to apply other processes to your population in the same workflow.

A seconda delle attività, potete aggiungere diversi tipi di transizioni in uscita:

* Transizione standard: popolazione calcolata dall'attività
* Transizione senza popolazione: questo tipo di transizione in uscita può essere aggiunto per continuare il flusso di lavoro e non contiene popolazioni per evitare inutili spazi nel sistema.
* Rifiuta: popolazione rifiutata. Ad esempio, se i dati in entrata dell'attività non sono stati elaborati perché era errato o incompleto.
* Complemento: popolazione rimanente dopo l'esecuzione dell'attività. Ad esempio, se un'attività di segmentazione è configurata per salvare solo una percentuale della popolazione in entrata.

If applicable, specify a **[!UICONTROL Segment code]** for the activity's outbound transition. Questo codice del segmento consente di identificare la provenienza dei sottoinsiemi dalla popolazione di destinazione e, successivamente, di servire a scopo di personalizzazione dei messaggi.

### Activity execution options {#activity-execution-options}

In the activity's properties screen, there is an **[!UICONTROL Advanced options]** tab that lets you define the activity's execution mode and behavior in case of errors.

To access these options, select an activity in a workflow, then open it using the ![](assets/edit_darkgrey-24px.png) button from the action bar.

![](assets/wkf_advanced_parameters.png)

**[!UICONTROL Execution]** Il campo consente di definire l'azione da eseguire quando l'attività viene avviata. Sono disponibili tre opzioni:

* **Normale**: l'attività viene eseguita normalmente.
* **Abilita ma non viene eseguito**: L'attività viene messa in pausa e, di conseguenza, tutti i processi futuri successivi. Questo può diventare utile se desiderate essere presente quando l'attività viene avviata.
* **Non abilitare**: l'attività non viene eseguita e di conseguenza non tutte le attività successive (nello stesso ramo).

**[!UICONTROL In case of error]** Il campo consente di specificare l'azione da eseguire qualora l'attività dovesse rilevare un errore. Sono disponibili due opzioni:

* **Sospendi il processo**: il flusso di lavoro viene sospeso automaticamente. The workflow status is then **Erroneous** and the color associated turns red. Una volta risolto il problema, riavviate il flusso di lavoro.
* **Ignora**: l'attività non viene eseguita e, come risultato, nessuna delle attività che lo segue (nello stesso ramo). Ciò potrebbe risultare utile per attività ricorrenti. Se il ramo ha un pianificatore collocato a monte, questo dovrebbe attivarsi alla data di esecuzione successiva.

**[!UICONTROL Behavior]** Il campo consente di definire la procedura da seguire se vengono utilizzate attività asincrone. Sono disponibili due opzioni:

* **Più attività autorizzate**: più attività possono essere eseguite contemporaneamente anche se la prima non è terminata.
* **L'attività corrente ha priorità**: Una volta in corso un'attività, questa ha priorità. Fintanto che un'attività è ancora in corso, non viene eseguita nessun'altra attività.

**[!UICONTROL Max. execution duration]** Il campo consente di specificare una durata come "30 s" o "1 h". Se l'attività non viene completata dopo la durata della durata specificata, viene attivato un avviso. Questo non ha alcun impatto sulla modalità di funzionamento delle funzioni del flusso di lavoro.

**[!UICONTROL Affinity]** Il campo consente di forzare l'esecuzione di un flusso di lavoro o di un'attività di flusso di lavoro su un particolare computer. A tal fine, dovete specificare una o più affinità per il flusso di lavoro o l'attività in questione.

The **[!UICONTROL Time zone]** field allows you to select the time zone of the activity. Adobe Campaign consente di gestire le differenze temporali tra più paesi nella stessa istanza. L'impostazione applicata è configurata quando l'istanza viene creata.

The **Comment** field is a free field that allows you to add a note.
