---
title: Best practice sui flussi di lavoro
description: Scopri come applicare le best practice ai flussi di lavoro.
page-status-flag: mai attivato
uuid: ff02b74e-53e8-49c6-bf8e-0c729eaa7d25
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: workflow generale
context-tags: flusso di lavoro,panoramica;flusso di lavoro,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Procedure consigliate per i flussi di lavoro{#workflow-best-practices}

Con Adobe Campaign, puoi impostare tutti i tipi di flusso di lavoro per eseguire un'ampia gamma di attività. Tuttavia, durante la progettazione e l'esecuzione dei flussi di lavoro, è necessario essere molto cauti in quanto una cattiva implementazione può portare a prestazioni sbagliate, errori e problemi di piattaforma. Di seguito è riportato un elenco delle procedure ottimali e dei suggerimenti per la risoluzione dei problemi.

>[!NOTE]
>
>La progettazione e l'esecuzione del flusso di lavoro devono essere eseguite da un utente avanzato di Adobe Campaign.

## Denominazione{#naming}

Per semplificare la risoluzione dei problemi del flusso di lavoro, Adobe consiglia di assegnare un nome ed un'etichetta ai flussi di lavoro in modo esplicito. Compilare il campo di descrizione del flusso di lavoro per riepilogare il processo da eseguire in modo che l'operatore possa capirlo facilmente.
Se il flusso di lavoro fa parte di un processo che coinvolge più flussi di lavoro, puoi utilizzare i numeri quando immetti un'etichetta per ordinarli chiaramente.

Ad esempio:

* 001 - Importazione - Destinatari importazione
* 002 - Importazione - Vendite all'importazione
* 003 - Importazione - Dettagli vendita importazione
* 010 - Esporta - Registri di consegna delle esportazioni
* 011 - Esporta - Registri di registrazione delle esportazioni

## Duplicazione dei flussi di lavoro{#duplicating-workflows}

Puoi duplicare i flussi di lavoro. In **[!UICONTROL Marketing Activities]**, passate il mouse sul flusso di lavoro e fate clic su **[!UICONTROL Duplicate element]**. Una volta duplicate, le modifiche del flusso di lavoro non vengono riportate nella copia del flusso di lavoro. È possibile modificare la copia del flusso di lavoro.

![](assets/duplicating_workflow.png)

## Esecuzione{#execution}

### Numero di flussi di lavoro

Per impostazione predefinita, si consiglia di non eseguire più di 20 esecuzioni di flussi di lavoro attive contemporaneamente. Una volta raggiunto tale limite, i flussi di lavoro verranno messi in coda per non influenzare le prestazioni. Allo stesso modo, Adobe consiglia di distribuire nel tempo l’esperienza del flusso di lavoro.
In contesti specifici, potrebbe essere necessario eseguire più di 20 flussi di lavoro. Non si applica ai flussi di lavoro in attesa di un'esecuzione pianificata.  In tal caso, devi consultare un esperto di Campaign e contattare l'Assistenza clienti Adobe per aumentare il limite.

### Frequenza

Un flusso di lavoro non può essere eseguito automaticamente più volte ogni dieci minuti.
La frequenza di ripetizione dell'attività non può essere inferiore a 10 minuti. Se la frequenza di ripetizione è impostata su 0 (anche il valore predefinito), questa opzione non viene presa in considerazione e il flusso di lavoro viene eseguito in base alla frequenza di esecuzione.

### Flussi di lavoro in pausa

I flussi di lavoro in stato di pausa o di mancata riuscita per più di 7 giorni vengono interrotti per ridurre lo spazio su disco. L’attività di pulizia viene visualizzata nei registri del flusso di lavoro.

### Transizioni

È comunque possibile eseguire un flusso di lavoro contenente transizioni non interrotte: genererà un messaggio di avviso e il flusso di lavoro verrà messo in pausa una volta raggiunta la transizione, ma non genererà un errore. Potete anche avviare un flusso di lavoro senza una progettazione completa e completarlo man mano che proseguite.

Per ulteriori informazioni, vedere [Esecuzione di flussi di lavoro](../../automating/using//executing-a-workflow.md).

## Attività{#activity}

### Progettazione flussi di lavoro

Per garantire il corretto completamento del flusso di lavoro, utilizzate un **[!UICONTROL End activity]**. Evitate di lasciare l’ultima transizione di un flusso di lavoro per conto proprio.

Per accedere alla visualizzazione dettagliata delle transizioni, selezionate l' **[!UICONTROL Keep interim results]** opzione nella sezione Esecuzione delle proprietà del flusso di lavoro.

>[!CAUTION]
>
>Questa opzione consuma molto spazio su disco ed è progettata per consentire la creazione di un flusso di lavoro e garantire la corretta configurazione e comportamento. Lasciatela deselezionata sulle istanze di produzione.

![](assets/keep_interim_best_practices.png)


### Attività di etichettatura{#activity-labeling}

Durante lo sviluppo del flusso di lavoro, viene generato un nome per ogni attività, come per tutti gli oggetti Adobe Campaign. Mentre il nome di un'attività viene generato dallo strumento e non può essere modificato, al momento della configurazione è consigliabile assegnargli un nome esplicito.

### Duplicazione delle attività{#activity-duplicating}

Per duplicare le attività esistenti, potete utilizzare il comando Copia-Incolla. In questo modo, potete mantenere le impostazioni originariamente definite. Per ulteriori informazioni, vedere [Duplicazione delle attività](../../automating/using/workflow-interface.md)del flusso di lavoro.

### Attività di pianificazione{#acheduler-activity}

Durante la creazione del flusso di lavoro, usate solo un **[!UICONTROL Scheduler activity]** ramo per ramo. Se lo stesso ramo di un flusso di lavoro include più pianificatori (collegati tra loro), il numero di attività da eseguire verrà moltiplicato in modo esponenziale, con conseguente notevole sovraccarico del database.

Puoi visualizzare in anteprima le dieci esecuzioni successive dei flussi di lavoro facendo clic su **[!UICONTROL Preview next executions]**.

![](assets/preview_scheduler.png)

Per ulteriori informazioni, fare riferimento a Attività [](../../automating/using/scheduler.md)Scheduler.

## Chiamata del flusso di lavoro con i parametri{#workflow-with-parameters}

Accertatevi che il nome e il numero di parametri siano identici a quelli definiti per la chiamata al flusso di lavoro (consultate [Definizione dei parametri per la chiamata al flusso di lavoro](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). Anche i tipi di parametri devono essere coerenti con i valori previsti.

Verificate che tutti i parametri siano stati dichiarati nella **[!UICONTROL External signal activity]**. In caso contrario, si verificherà un errore durante l'esecuzione dell'attività.

Per ulteriori informazioni, consultate [Chiamata di un flusso di lavoro con parametri](../../automating/using/calling-a-workflow-with-external-parameters.md)esterni.

## Esportazione di pacchetti{#exporting-packages}

Per esportare i pacchetti, le risorse esportate non devono contenere ID predefiniti. Pertanto, gli ID delle risorse esportabili devono essere modificati utilizzando un nome diverso dai modelli forniti come standard da Adobe Campaign Standard.
Per ulteriori informazioni, consultate [Gestione dei pacchetti](../../automating/using/managing-packages.md).

## Esportazione di elenchi{#exporting-lists}

L’opzione di elenco di esportazione consente di esportare un massimo di 100.000 righe per impostazione predefinita e definita dall’opzione **** Nms_ExportListLimit. Questa opzione può essere gestita dall'amministratore funzionale, in **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]**.
Per ulteriori informazioni, vedere [Esportazione di elenchi](../../automating/using/exporting-lists.md).

## Risoluzione dei problemi{#workflow-troubleshooting}

Adobe Campaign offre diversi registri per comprendere meglio i problemi dei flussi di lavoro.

### Utilizzo dei registri di flusso di lavoro{#using-workflow-logs}

Potete accedere ai registri del flusso di lavoro per monitorare l’esecuzione delle attività. Esso indicizza le operazioni eseguite e gli errori di esecuzione in ordine cronologico. La scheda Registri è costituita dalla cronologia dell’esecuzione di tutte o di alcune attività selezionate.
Nella scheda Attività viene illustrata la sequenza di esecuzione delle attività. Per ottenere ulteriori informazioni su un'attività, fate clic su un'attività.
Per ulteriori informazioni, vedere Esecuzione [del flusso di lavoro di](../../automating/using/executing-a-workflow.md#monitoring)monitoraggio.

#### Troubleshooting data management activities{#troubleshooting-data-management-activities}

È possibile analizzare le query SQL nella scheda Registro.

1. Nell’area di lavoro del flusso di lavoro, fate clic su **[!UICONTROL Edit properties]**.
1. In **[!UICONTROL General]** &gt; **[!UICONTROL Execution]**, selezionate le **[!UICONTROL Save SQL queries in the log]** opzioni e **[!UICONTROL Execute in the engine]** fate clic su **[!UICONTROL Confirm]**.

**Per visualizzare le query SQL nel registro:**
1. Click **[!UICONTROL Log and Tasks]**.
1. Nella **[!UICONTROL Logs]** scheda, aprite il **[!UICONTROL Search]** pannello.
1. Controlla **[!UICONTROL Display SQL logs only]**.

La query viene visualizzata nella **[!UICONTROL Message]** colonna dei registri.

### Utilizzo dei registri di consegna{#using-delivery-logs}

I registri di consegna consentono di monitorare il successo delle consegne. I registri di esclusione restituiscono i messaggi esclusi durante la preparazione dell'invio. I registri di invio forniscono lo stato della consegna per ciascun profilo.
Per ulteriori informazioni, vedere [Informazioni sugli errori](../../sending/using/understanding-delivery-failures.md)di consegna.

### Utilizzo degli avvisi sulla consegna{#delivery-alerting}

La funzione di avviso sulla distribuzione è un sistema di gestione degli avvisi che consente a un gruppo di utenti di ricevere automaticamente le notifiche contenenti informazioni sull’esecuzione delle consegne.
Per ulteriori informazioni, consulta [Avviso](../../sending/using/receiving-alerts-when-failures-happen.md)sulla consegna.

**Argomenti correlati:**

* [Gestione errori](../../automating/using/executing-a-workflow.md#error-management)
