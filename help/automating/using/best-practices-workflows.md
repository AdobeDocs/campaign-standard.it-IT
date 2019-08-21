---
title: Best practice per flussi di lavoro
seo-title: Best practice per flussi di lavoro
description: Best practice per flussi di lavoro
seo-description: Scopri come best practice per i tuoi flussi di lavoro.
page-status-flag: never-activated
uuid: ff 02 b 74 e -53 e 8-49 c 6-bf 8 e -0 c 729 eaa 7 d 25
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: workflow-general-operation
context-tags: flusso di lavoro, panoramica; flusso di lavoro, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3ed76cc48c94510b40e7a946031ec4331c6e0905

---


# Best practice per il flusso di lavoro{#workflow-best-practices}

Con Adobe Campaign, puoi configurare tutti i tipi di flusso di lavoro per eseguire un'ampia gamma di attività. Tuttavia, durante la progettazione e l'esecuzione dei flussi di lavoro, è necessario essere molto prudenti in quanto un'implementazione insoddisfacente può causare prestazioni, errori e problemi di piattaforma errati. Sotto un elenco di best practice e suggerimenti per la risoluzione di problemi.

>[!NOTE]
>
>La progettazione e l'esecuzione del flusso di lavoro devono essere eseguite da un utente avanzato Adobe Campaign.

## Denominazione{#naming}

Per semplificare la risoluzione dei problemi del flusso di lavoro, Adobe consiglia di assegnare un nome e etichettare esplicitamente i flussi di lavoro. Compilare il campo di descrizione del flusso di lavoro per riepilogare il processo da eseguire in modo che l'operatore possa facilmente comprenderlo.
Se il flusso di lavoro fa parte di un processo che prevede più flussi di lavoro, puoi utilizzare i numeri per immetterli chiaramente.

Ad esempio:

* 001 - Importazione - Importazione di destinatari
* 002 - Importazione - Importazione di vendite
* 003 - Importazione - Importazione di dettagli di vendita
* 010 - Esportazione - Registri di consegna esportazione
* 011 - Esportazione - Registri di tracciamento esportazione

## Duplicazione dei flussi di lavoro{#duplicating-workflows}

Potete duplicare i flussi di lavoro. In **[!UICONTROL Marketing Activities]**, passate il mouse sul flusso di lavoro e fate clic **[!UICONTROL Duplicate element]**. Una volta duplicate, le modifiche del flusso di lavoro non vengono portate alla copia del flusso di lavoro. La copia del flusso di lavoro può essere modificata.

![](assets/duplicating_workflow.png)

## Esecuzione{#execution}

### Numero di flussi di lavoro

Per impostazione predefinita, si consiglia di non eseguire più di 20 flussi di lavoro attivi contemporaneamente. Dopo aver raggiunto tale limite, i flussi di lavoro verranno messi in coda per non influire sulle prestazioni. Analogamente, Adobe consiglia di distribuire il flusso di lavoro nel tempo.
In contesti specifici, potrebbe essere necessario eseguire più di 20 flussi di lavoro. Non si applica ai flussi di lavoro in attesa di un'esecuzione pianificata. In tal caso, devi controllare i casi d'uso con un esperto di Campaign e contattare l'Assistenza clienti Adobe per aumentare il limite.

### Frequenza

Un flusso di lavoro non può essere eseguito automaticamente più volte di una volta ogni dieci minuti.
La frequenza Ripetuta dell'attività non può essere inferiore a 10 minuti. Se la frequenza di ripetizione è impostata su 0 (anche il valore predefinito), questa opzione non viene considerata e il flusso di lavoro viene eseguito in base alla frequenza di esecuzione.

### Flussi di lavoro in pausa

I flussi di lavoro che sono stati in pausa o in stato non riuscito per più di 7 giorni vengono interrotti per poter utilizzare meno spazio su disco. L'attività di pulizia viene visualizzata nei registri di workflow.

### Transizioni

È possibile eseguire un flusso di lavoro contenente transizioni non ancora chiamate: viene generato un messaggio di avviso e il flusso di lavoro si interrompe una volta raggiunta la transizione ma non genera un errore. Potete anche avviare un flusso di lavoro senza una progettazione completata e completarlo man mano che passate.

Per ulteriori informazioni, consulta [Esecuzione dei flussi di lavoro](../../automating/using//executing-a-workflow.md).

## Attività{#activity}

### Progettazione del flusso di lavoro

Per assicurare che il flusso di lavoro termini correttamente, utilizza un **[!UICONTROL End activity]**. Evitate di uscire dall'ultima transizione di un flusso di lavoro.

Per accedere alla visualizzazione dettagli delle transizioni, controllate l' **[!UICONTROL Keep interim results]** opzione nella sezione Esecuzione delle proprietà del flusso di lavoro.

>[!CAUTION]
>
>Questa opzione consuma molto spazio su disco ed è progettata per facilitare la creazione di un flusso di lavoro e per garantire la corretta configurazione e il comportamento. Lasciatela non selezionata per le istanze di produzione.

![](assets/keep_interim_best_practices.png)


### Attività di etichettatura{#activity-labeling}

Durante lo sviluppo del flusso di lavoro, viene generato un nome per ogni attività, come per tutti gli oggetti Adobe Campaign. Mentre il nome di un'attività è generato dallo strumento e non può essere modificato, consigliamo di etichettarlo con un nome esplicito al momento della configurazione.

### Duplicazione delle attività{#activity-duplicating}

Per duplicare le attività esistenti, potete utilizzare copy-paste. In tal modo vengono mantenute le impostazioni definite originariamente. Per ulteriori informazioni, consultate [Duplicazione delle attività del flusso di lavoro](../../automating/using/workflow-interface.md).

### Attività del pianificatore{#acheduler-activity}

Durante la creazione del flusso di lavoro, è necessario usarne uno **[!UICONTROL Scheduler activity]** solo per ramo. Se lo stesso ramo di un flusso di lavoro dispone di diversi pianificatori (collegati l'uno all'altro), il numero di attività da eseguire verrà moltiplicato esponenzialmente, il che comporterebbe un sovraccarico significativo del database.

Fai clic su **[!UICONTROL Preview next executions]** un'anteprima delle dieci esecuzioni successive dei tuoi flussi di lavoro.

![](assets/preview_scheduler.png)

Per ulteriori informazioni, consultate Attività [del pianificatore](../../automating/using/scheduler.md).

## Chiamata di workflow con parametri{#workflow-with-parameters}

Accertatevi che nome e numero di parametri siano identici a quelli definiti durante la chiamata del flusso di lavoro (consultate [Definizione dei parametri durante la chiamata del flusso di lavoro](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). I tipi di parametri devono anche essere coerenti con i valori previsti.

Accertatevi che tutti i parametri siano stati dichiarati nel **[!UICONTROL External signal activity]**. In caso contrario, si verificherà un errore durante l'esecuzione dell'attività.

Per ulteriori informazioni, consultate [Chiamata di un flusso di lavoro con parametri esterni](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Esportazione di pacchetti{#exporting-packages}

Per esportare i pacchetti, le risorse esportate non devono contenere ID predefiniti. Pertanto, gli ID di risorse opuscole devono essere modificati utilizzando un nome diverso dai modelli forniti come standard da Adobe Campaign Standard.
Per ulteriori informazioni, consulta [Gestione dei pacchetti](../../automating/using/managing-packages.md).

## Esportazione di elenchi{#exporting-lists}

L'opzione Elenco di esportazione consente di esportare un massimo di 100,000 righe per impostazione predefinita e definite dall'opzione **Nms_ exportlistlimit**. Questa opzione può essere gestita dall'amministratore funzionale, in **Amministrazione** &gt; **Impostazioni applicazione** &gt; **Opzioni**.
Per ulteriori informazioni, consultate [Esportazione di elenchi](../../automating/using/exporting-lists.md).

## Risoluzione dei problemi{#workflow-troubleshooting}

Adobe Campaign offre vari registri per comprendere meglio i problemi del flusso di lavoro.

### Utilizzo dei registri di workflow{#using-workflow-logs}

Potete accedere ai registri di workflow per monitorare l'esecuzione delle attività. Indicizza le operazioni eseguite e gli errori di esecuzione in base all'ordine cronologico. La scheda Registri è costituita dalla cronologia dell'esecuzione di tutte o alcune attività selezionate.
La scheda Attività descrive la sequenza di esecuzione delle attività. Per ottenere ulteriori informazioni su un'attività, fate clic su un'attività.
Per ulteriori informazioni, consultate [Monitorare l'esecuzione del flusso di lavoro](../../automating/using/executing-a-workflow.md#monitoring).

#### Risoluzione dei problemi delle attività di gestione dei dati{#troubleshooting-data-management-activities}

Potete analizzare le query SQL nella scheda Registro.

1. Nell'area di lavoro del flusso di lavoro, fate clic **su Modifica proprietà**.
1. **In Generale** &gt; **Esegui**, controllate **le query SQL nel registro** ed **Esegui nelle opzioni del motore** e fate clic **su Conferma**.

**Per visualizzare le query SQL nel registro:**
1. Fate clic **su Registro e attività**.
1. Nella scheda **Registro** , aprite il **pannello Ricerca** .
1. Selezionate **Visualizza solo registri SQL**.

La query viene visualizzata nella colonna **Messaggio** dei registri.

### Utilizzo dei registri di distribuzione{#using-delivery-logs}

I registri di distribuzione consentono di monitorare il successo delle consegne. I registri di esclusione restituiscono messaggi esclusi durante la preparazione dell'invio. L'invio di registri fornisce lo stato della consegna per ogni profilo.
Per ulteriori informazioni, consulta [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md).

### Utilizzo degli avvisi sulla distribuzione{#delivery-alerting}

La funzione di avvisi sulla distribuzione è un sistema di gestione avvisi che consente a un gruppo di utenti di ricevere automaticamente le notifiche relative all'esecuzione delle consegne.
Per ulteriori informazioni, fare riferimento agli avvisi [sulla distribuzione](../../sending/using/receiving-alerts-when-failures-happen.md).

**Argomenti correlati:**

* [Gestione degli errori](../../automating/using/executing-a-workflow.md#error-management)
