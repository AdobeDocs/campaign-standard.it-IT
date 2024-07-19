---
title: Scheduler
description: L’attività Scheduler ti consente di pianificare quando viene avviato un flusso di lavoro o un’attività.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: schedule,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 39f7b216-b3cd-4aa6-b5df-23e6805076df
source-git-commit: 6107f5e43b25037f7f5a7f130922a3a22d0047af
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 52%

---

# Modulo di pianificazione{#scheduler}

## Descrizione {#description}

![](assets/scheduler.png)

L’attività **[!UICONTROL Scheduler]** ti consente di pianificare quando viene avviato un flusso di lavoro o un’attività.

## Contesto di utilizzo {#context-of-use}

Dovresti considerare l’attività **[!UICONTROL Scheduler]** come un inizio pianificato. Le regole di posizionamento dell’attività all’interno del grafico sono le stesse dell’attività **[!UICONTROL Start]**. Questa attività non deve avere una transizione in entrata.

Durante la creazione del flusso di lavoro, utilizza una sola attività **[!UICONTROL Scheduler]** per ramo e ricorda di impostare un fuso orario. In questo modo puoi avviare il flusso di lavoro in un fuso orario specifico, altrimenti il flusso di lavoro viene eseguito nel fuso orario definito nelle relative proprietà (consulta [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)).

>[!CAUTION]
>
>La **[!UICONTROL Repetition frequency]** dell’attività non può essere inferiore a 10 minuti. Ciò significa che non è possibile eseguire automaticamente un flusso di lavoro più di una volta ogni 10 minuti.

Durante la progettazione di un flusso di lavoro pianificato che include più attività, è necessario assicurarsi che il flusso di lavoro non venga ripianificato fino al suo completamento. A questo scopo, devi configurare il flusso di lavoro per impedirne l’esecuzione se una o più attività di un’esecuzione precedente sono ancora in sospeso. Per ulteriori informazioni, consulta [questa pagina](../../automating/using/scheduled-workflows-execution.md).

**Argomenti correlati:**

* [Caso di utilizzo: creazione di consegne nella data di creazione dei profili](../../automating/using/workflow-creation-date-query.md)
* [Caso di utilizzo: creazione di una consegna e-mail ogni martedì](../../automating/using/workflow-weekly-offer.md)

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Scheduler]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Specifica la **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: il flusso di lavoro viene eseguito una sola volta.
   * **[!UICONTROL Several times a day]**: il flusso di lavoro viene eseguito regolarmente più volte al giorno.
   * **[!UICONTROL Daily]**: il flusso di lavoro viene eseguito una volta al giorno a un’ora specifica.
   * **[!UICONTROL Weekly]**: il flusso di lavoro viene eseguito in un determinato momento, una o più volte alla settimana.
   * **[!UICONTROL Monthly]**: il flusso di lavoro viene eseguito in un determinato momento, una o più volte al mese. Puoi selezionare i mesi, quando devi eseguire il flusso di lavoro. Puoi anche impostare le esecuzioni in un giorno feriale specifico del mese, ad esempio il secondo martedì del mese.
   * **[!UICONTROL Yearly]**: il flusso di lavoro viene eseguito in un determinato momento, una o più volte all’anno.

1. Configura le impostazioni di esecuzione in base alle tue esigenze. Le opzioni disponibili possono variare a seconda della frequenza di esecuzione selezionata (tempo o giorni di esecuzione, frequenza di ripetizione, ecc.).

   >[!NOTE]
   >
   >Il campo **[!UICONTROL Repetition frequency]** disponibile per le frequenze di esecuzione Giornaliera e Mensile consente di intervallare i momenti in cui viene attivato il flusso di lavoro. Ad esempio, se selezioni un periodo di esecuzione giornaliero e la frequenza di ripetizione è impostata su **2** (giorni), il flusso di lavoro viene attivato ogni due giorni. Non può essere inferiore a 10 minuti. Se la frequenza di ripetizione è impostata su **0** (che è anche il valore predefinito), questa opzione non viene considerata e il flusso di lavoro verrà eseguito in base alla frequenza di esecuzione specificata.

   Quando si imposta la frequenza di esecuzione su **[!UICONTROL Several times a day]**, è possibile scegliere se eseguire il flusso di lavoro in orari specifici del giorno o periodicamente durante il giorno.

+++ Scopri come configurare una frequenza di esecuzione di **[!UICONTROL "Several times a day"]**

   * Per eseguire il flusso di lavoro più volte in orari specifici durante il giorno, attivare l&#39;opzione **[!UICONTROL Specific times]**, quindi fare clic su **[!UICONTROL Add an element]** per specificare il tempo di esecuzione desiderato. Aggiungi il numero di volte necessario per allinearlo ai requisiti.

   * Per eseguire periodicamente il flusso di lavoro nel corso della giornata, attiva l&#39;opzione **[!UICONTROL Periodic]** e configura la periodicità di esecuzione:

      1. Nel campo **[!UICONTROL Repeat processing according to the following frequency (e.g. 2h)]** specificare l&#39;intervallo di esecuzione del flusso di lavoro (ad esempio ogni 30 minuti, ogni 2 ore).

         >[!NOTE]
         >
         >Questa opzione consente anche di effettuare frequenze di ripetizione giornaliere, mensili o annuali. In questo caso, il flusso di lavoro non verrà eseguito più volte al giorno, ma in base alla frequenza specificata in questo campo.
         >
         > Se il flusso di lavoro non richiede più esecuzioni in un giorno ma deve essere eseguito su base giornaliera, mensile o annuale, è consigliabile utilizzare le opzioni **[!UICONTROL Daily]**, **[!UICONTROL Monthly]** o **[!UICONTROL Yearly]** disponibili nell&#39;elenco a discesa **[!UICONTROL Execution frequency]**.

      1. Definire l&#39;ora di inizio e di fine dell&#39;esecuzione del flusso di lavoro nei campi di ora **[!UICONTROL Start]**/**[!UICONTROL End]**.

         Se non viene specificato un orario di fine, l&#39;esecuzione termina alla mezzanotte 00:00:00 ore e l&#39;esecuzione successiva inizia il giorno successivo all&#39;orario di inizio specificato.

      1. Nel campo data **[!UICONTROL Start]**, selezionare la data in cui deve iniziare la prima esecuzione.

   Nell’esempio seguente, l’attività è configurata per eseguire il flusso di lavoro ogni 2 ore tra le 8 e le 17, a partire dal 1° marzo.

   ![](assets/wkf_scheduler_day.png)

+++

1. Specifica quando scade l’esecuzione:

   * **[!UICONTROL Never]**: il flusso di lavoro viene eseguito, in base alla frequenza specificata, senza alcun limite all’arco temporale o al numero di iterazioni.
   * **[!UICONTROL After a certain number of iterations]**: il flusso di lavoro viene eseguito in base alla frequenza specificata, fino al raggiungimento del limite di **X**. Occorre pertanto specificare il **[!UICONTROL Number of iterations]**.
   * **[!UICONTROL On a specific date]**: il flusso di lavoro viene eseguito in base alla frequenza specificata, fino a una data specifica. Occorre pertanto precisare il termine per l’esecuzione.

1. Controlla la pianificazione delle dieci esecuzioni successive del flusso di lavoro facendo clic su **[!UICONTROL Preview next executions]**.

1. Nella scheda **[!UICONTROL Execution options]**, imposta il fuso orario per la pianificazione nel campo **[!UICONTROL Time zone]**.

   Per ulteriori informazioni sull’invio della consegna in base al fuso orario del destinatario, consulta questa [sezione](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) o questo [esempio](../../automating/using/recurring-push-notifications.md) di flusso di lavoro ricorrente.

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

## Esempio {#example}

Nell’esempio seguente, l’attività è configurata in modo che avvii il flusso di lavoro settimanalmente, ogni due lunedì alle 7, per una durata indeterminata.

![](assets/wkf_scheduler_example.png)

