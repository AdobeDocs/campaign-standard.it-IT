---
title: Best practice per i flussi di lavoro
description: Scopri come applicare le best practice ai flussi di lavoro.
page-status-flag: never-activated
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,overview;workflow,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1069'
ht-degree: 93%

---


# Best practice per i flussi di lavoro{#workflow-best-practices}

Con Adobe Campaign, puoi impostare tutti i tipi di flusso di lavoro per eseguire un’ampia gamma di attività. Tuttavia, durante la progettazione e l’esecuzione dei flussi di lavoro, devi prestare estrema attenzione, dato che una cattiva implementazione può portare a prestazioni sbagliate, errori e problemi di piattaforma. Di seguito è riportato un elenco delle best practice e dei suggerimenti per la risoluzione dei problemi.

>[!NOTE]
>
>La progettazione e l’esecuzione del flusso di lavoro devono essere effettuate da un utente avanzato di Adobe Campaign.

## Denominazione{#naming}

Per semplificare la risoluzione dei problemi del flusso di lavoro, Adobe consiglia di assegnare esplicitamente un nome ed un’etichetta ai flussi di lavoro. Compila il campo di descrizione del flusso di lavoro per riepilogare il processo da eseguire affinché l’operatore possa comprenderlo facilmente.
Se il flusso di lavoro fa parte di un processo che coinvolge più flussi di lavoro, quando inserisci un’etichetta puoi utilizzare i numeri, così da ordinarli chiaramente.

Ad esempio:

* 001 - Importazione - Destinatari importazione
* 002 - Importazione - Vendite all’importazione
* 003 - Importazione - Dettagli delle vendite all’importazione
* 010 - Esportazione - Registri di consegna delle esportazioni
* 011 - Esportazione - Registri di tracciamento delle esportazioni

## Duplicazione dei flussi di lavoro{#duplicating-workflows}

Puoi duplicare i flussi di lavoro. In **[!UICONTROL Marketing Activities]**, passa il mouse sul flusso di lavoro e fai clic su **[!UICONTROL Duplicate element]**. Una volta eseguita la duplicazione, le modifiche del flusso di lavoro non vengono riportate nella copia del flusso di lavoro. È possibile modificare la copia del flusso di lavoro.

![](assets/duplicating_workflow.png)

## Esecuzione{#execution}

### Numero di flussi di lavoro

Per impostazione predefinita, consigliamo di non avviare più di 20 esecuzioni di flussi di lavoro attivi in contemporanea. Una volta raggiunto tale limite, i flussi di lavoro verranno messi in coda per non influenzare le prestazioni. Allo stesso modo, Adobe consiglia di distribuire nel tempo l’esecuzione del flusso di lavoro.
In contesti specifici, potrebbe essere necessario eseguire più di 20 flussi di lavoro. Questa impostazione non si applica ai flussi di lavoro in attesa di un’esecuzione pianificata. In tal caso, devi consultare un esperto di Campaign e contattare anche l’Assistenza cliente Adobe per aumentare il limite.

### Frequenza

Un flusso di lavoro non può essere eseguito automaticamente con una frequenza maggiore a una volta ogni dieci minuti.
La frequenza di ripetizione dell’attività non può essere inferiore a 10 minuti. Se la frequenza di ripetizione è impostata su 0 (anche il valore predefinito), questa opzione non viene presa in considerazione e il flusso di lavoro viene eseguito in base alla frequenza di esecuzione.

### Flussi di lavoro in pausa

I flussi di lavoro che si trovano nello stato di pausa o di errore per più di 7 giorni vengono interrotti per ridurre lo spazio su disco. L’attività di pulizia viene visualizzata nei registri del flusso di lavoro.

### Transizioni

È comunque possibile eseguire un flusso di lavoro contenente transizioni non terminate: genererà un messaggio di avviso e il flusso di lavoro verrà messo in pausa una volta raggiunta la transizione, ma non causerà un errore. Puoi anche avviare un flusso di lavoro senza una progettazione completa, per poi ultimarlo e completarlo man mano che prosegui.

Per ulteriori informazioni, consulta [Esecuzione dei flussi di lavoro](../../automating/using/about-workflow-execution.md).

### Fuso orario

Le proprietà del flusso di lavoro ti consentono di definire un fuso orario specifico che verrà utilizzato per impostazione predefinita in tutte le relative attività. Per impostazione predefinita, il fuso orario del flusso di lavoro è quello definito per l’operatore corrente di Campaign.

## Attività{#activity}

### Numero di attività per flusso di lavoro {#number-activities}

È consigliabile utilizzare fino a 100 attività in un unico flusso di lavoro. Più di 100 attività possono verificarsi problemi di prestazioni durante la progettazione e la configurazione del flusso di lavoro.

### Progettazione flussi di lavoro

Per garantire il corretto completamento del flusso di lavoro, evitare di lasciare l’ultima transizione di un flusso di lavoro da sola utilizzando un **[!UICONTROL End activity]**.

Per accedere alla visualizzazione dettagliata delle transizioni, seleziona l’opzione **[!UICONTROL Keep interim results]** nella sezione Execution delle proprietà del flusso di lavoro.

>[!CAUTION]
>
>Questa opzione consuma molto spazio su disco ed è progettata per consentire la creazione di un flusso di lavoro, garantendone la corretta configurazione e il giusto comportamento. Lascia deselezionata questa opzione nelle istanze di produzione.

![](assets/keep_interim_best_practices.png)


### Attività di etichettatura{#activity-labeling}

Durante lo sviluppo del flusso di lavoro, viene generato un nome per ogni attività, come per tutti gli oggetti di Adobe Campaign. Anche se il nome di un’attività viene generato dallo strumento e non può essere modificato, al momento della configurazione è consigliabile assegnargli un nome esplicito.

### Duplicazione delle attività{#activity-duplicating}

Per duplicare le attività esistenti, puoi utilizzare la funzione di copia e incolla. In questo modo, puoi mantenere le impostazioni definite in origine. Per ulteriori informazioni, consulta [Duplicazione delle attività del flusso di lavoro](../../automating/using/workflow-interface.md).

### Attività Scheduler{#acheduler-activity}

Durante la creazione del flusso di lavoro, usa solo un’**[!UICONTROL Scheduler activity]** per ramo. Se lo stesso ramo di un flusso di lavoro include più pianificatori (collegati tra loro), il numero di attività da eseguire verrà moltiplicato in modo esponenziale, il che sovraccaricherebbe notevolmente il database.

Puoi visualizzare in anteprima le prossime dieci esecuzioni dei flussi di lavoro facendo clic su **[!UICONTROL Preview next executions]**.

![](assets/preview_scheduler.png)

Per ulteriori informazioni, consulta [Attività di pianificazione](../../automating/using/scheduler.md).

## Chiamata del flusso di lavoro con parametri{#workflow-with-parameters}

Accertatevi che il nome e il numero di parametri siano identici a quelli definiti per la chiamata al flusso di lavoro (vedete [](../../automating/using/defining-parameters-calling-workflow.md). Anche i tipi di parametri devono essere coerenti con i valori previsti.

Verifica che tutti i parametri siano stati dichiarati nell’**[!UICONTROL External signal activity]**. In caso contrario, si verificherà un errore durante l’esecuzione dell’attività.

Per ulteriori informazioni, consulta [Chiamata di un flusso di lavoro con parametri esterni](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Esportazione di pacchetti{#exporting-packages}

Per esportare i pacchetti, le risorse esportate non devono contenere ID predefiniti. Pertanto, gli ID delle risorse esportabili devono essere modificati utilizzando un nome diverso dai modelli forniti come standard da Adobe Campaign Standard.
Per ulteriori informazioni, consulta [Gestione dei pacchetti](../../automating/using/managing-packages.md).

## Esportazione di elenchi{#exporting-lists}

L’opzione esportazione di elenchi ti consente di esportare un massimo di 100.000 righe per impostazione predefinita ed è definita dall’opzione **** Nms_ExportListLimit. Questa opzione può essere gestita dall’amministratore funzionale in **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.
Per ulteriori informazioni, consulta [Esportazione di elenchi](../../automating/using/exporting-lists.md).

## Risoluzione dei problemi{#workflow-troubleshooting}

Adobe Campaign offre diversi registri per comprendere meglio i tuoi problemi dei flussi di lavoro.

### Utilizzo dei registri del flusso di lavoro{#using-workflow-logs}

Puoi accedere ai registri del flusso di lavoro per monitorare l’esecuzione delle tue attività. Questi registri indicizzano in ordine cronologico le operazioni effettuate e gli errori di esecuzione. La scheda Registri è costituita dalla cronologia dell’esecuzione di tutte o di alcune attività selezionate.
Nella scheda Attività viene illustrata la sequenza di esecuzione delle attività. Per ottenere ulteriori informazioni su un’attività, fai clic su di essa.
Per ulteriori informazioni, consulta [Monitoraggio dell’esecuzione del flusso di lavoro](../../automating/using/monitoring-workflow-execution.md).

#### Risoluzione dei problemi delle attività di gestione dei dati{#troubleshooting-data-management-activities}

Puoi analizzare le query SQL nella scheda Registro.

1. Nell’area di lavoro del flusso di lavoro, fai clic su **[!UICONTROL Edit properties]**.
1. In **[!UICONTROL General]** > **[!UICONTROL Execution]**, seleziona le opzioni **[!UICONTROL Save SQL queries in the log]** e **[!UICONTROL Execute in the engine]** fai clic su **[!UICONTROL Confirm]**.

**Per visualizzare le query SQL nel registro:**
1. Fai clic su **[!UICONTROL Log and Tasks]**.
1. Nella scheda **[!UICONTROL Logs]**, apri il pannello **[!UICONTROL Search]**.
1. Controlla **[!UICONTROL Display SQL logs only]**.

La query viene visualizzata nella colonna **[!UICONTROL Message]** dei registri.

### Utilizzo dei registri di consegna{#using-delivery-logs}

I registri di consegna ti consentono di monitorare il successo delle consegne. I registri di esclusione restituiscono i messaggi esclusi durante la preparazione dell’invio. I registri di invio ti forniscono lo stato della consegna per ciascun profilo.
Per ulteriori informazioni, consulta [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md).

### Utilizzo degli avvisi sulla consegna{#delivery-alerting}

La funzione di avviso sulla consegna è un sistema di gestione degli avvisi che consente a un gruppo di utenti di ricevere automaticamente le notifiche contenenti informazioni sull’esecuzione delle consegne.
Per ulteriori informazioni, consulta [Avvisi sulla consegna](../../sending/using/receiving-alerts-when-failures-happen.md).

**Argomenti correlati:**

* [Gestione degli errori](../../automating/using/monitoring-workflow-execution.md)
