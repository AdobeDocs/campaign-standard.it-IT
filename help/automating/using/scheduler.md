---
title: Scheduler
description: L’attività Scheduler ti consente di pianificare quando viene avviato un flusso di lavoro o un’attività.
page-status-flag: never-activated
uuid: f5e50a11-8dc9-4d98-9531-024c0fb3f7da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 0fb16cea-3941-404f-899c-33f81ced4ed5
context-tags: schedule,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 97%

---


# Scheduler{#scheduler}

## Descrizione {#description}

![](assets/scheduler.png)

L’attività **[!UICONTROL Scheduler]** ti consente di pianificare quando viene avviato un flusso di lavoro o un’attività.

## Contesto di utilizzo {#context-of-use}

Dovresti considerare l’attività **[!UICONTROL Scheduler]** come un inizio pianificato. Le regole di posizionamento dell’attività all’interno del grafico sono le stesse dell’attività **[!UICONTROL Start]**. Questa attività non deve avere una transizione in entrata.

Durante la creazione del flusso di lavoro, utilizza una sola attività **[!UICONTROL Scheduler]** per ramo e ricorda di impostare un fuso orario. In questo modo puoi avviare il flusso di lavoro in un fuso orario specifico, altrimenti il flusso di lavoro viene eseguito nel fuso orario definito nelle relative proprietà (consulta [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)).

>[!CAUTION]
>
>La **[!UICONTROL Repetition frequency]** dell’attività non può essere inferiore a 10 minuti. Ciò significa che non è possibile eseguire automaticamente un flusso di lavoro più di una volta ogni 10 minuti.

**Argomenti correlati:**

* [Caso di utilizzo: Creazione di consegne sulla data di creazione dei profili](../../automating/using/workflow-creation-date-query.md)
* [Caso di utilizzo: Creazione di una consegna tramite e-mail ogni martedì](../../automating/using/workflow-weekly-offer.md)

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Scheduler]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Specifica la **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: il flusso di lavoro viene eseguito una sola volta.
   * **[!UICONTROL Several times a day]**: il flusso di lavoro viene eseguito regolarmente più volte al giorno. Puoi impostare esecuzioni in orari specifici o periodicamente.
   * **[!UICONTROL Daily]**: il flusso di lavoro viene eseguito una volta al giorno a un’ora specifica.
   * **[!UICONTROL Weekly]**: il flusso di lavoro viene eseguito in un determinato momento, una o più volte alla settimana.
   * **[!UICONTROL Monthly]**: il flusso di lavoro viene eseguito in un determinato momento, una o più volte al mese. Puoi selezionare i mesi, quando devi eseguire il flusso di lavoro. Puoi anche impostare le esecuzioni in un giorno feriale specifico del mese, ad esempio il secondo martedì del mese.
   * **[!UICONTROL Yearly]**: il flusso di lavoro viene eseguito in un determinato momento, una o più volte all’anno.

1. Definisci i dettagli di esecuzione in base alla frequenza selezionata. I campi dettagliati possono variare a seconda della frequenza utilizzata (tempo, frequenza di ripetizione, giorni specificati, ecc.).

   >[!NOTE]
   >
   >Il campo **[!UICONTROL Repetition frequency]** ti consente di intervallare i momenti in cui viene attivato il flusso di lavoro. Ad esempio, se selezioni un periodo di esecuzione giornaliero e la frequenza di ripetizione è impostata su **2** (giorni), il flusso di lavoro viene attivato ogni due giorni. Non può essere inferiore a 10 minuti. Se la frequenza di ripetizione è impostata su **0** (che è anche il valore predefinito), questa opzione non viene considerata e il flusso di lavoro viene eseguito in base alla frequenza di esecuzione specificata.

1. Specifica quando scade l’esecuzione:

   * **[!UICONTROL Never]**: il flusso di lavoro viene eseguito, in base alla frequenza specificata, senza alcun limite all’intervallo di tempo o al numero di iterazioni.
   * **[!UICONTROL After a certain number of iterations]**: il flusso di lavoro viene eseguito in base alla frequenza specificata, fino al raggiungimento del limite di **X**. Occorre pertanto specificare il **[!UICONTROL Number of iterations]**.
   * **[!UICONTROL On a specific date]**: il flusso di lavoro viene eseguito in base alla frequenza specificata, fino a una data specifica. Occorre pertanto precisare il termine per l’esecuzione.

1. Controlla la pianificazione delle dieci esecuzioni successive del flusso di lavoro facendo clic su **[!UICONTROL Preview next executions]**.

1. Nella scheda **[!UICONTROL Execution options]**, imposta il fuso orario per la pianificazione nel campo **[!UICONTROL Time zone]**.

   Per ulteriori informazioni sull’invio della consegna in base al fuso orario del destinatario, consulta questa [sezione](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) o questo [esempio](../../automating/using/recurring-push-notifications.md) di flusso di lavoro ricorrente.

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

## Esempio {#example}

Nell’esempio seguente, l’attività è configurata in modo che avvii il flusso di lavoro settimanalmente, ogni due lunedì alle 7, per una durata indeterminata.

![](assets/wkf_scheduler_example.png)

