---
title: Pianificazione
description: L'attività Scheduler consente di pianificare quando viene avviato un flusso di lavoro o un'attività.
page-status-flag: mai attivato
uuid: f5e50a11-8dc9-4d98-9531-024c0fb3f7da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di esecuzione
discoiquuid: 0fb16cea-3941-404f-899c-33f81ced4ed5
context-tags: pianificazione,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Pianificazione{#scheduler}

## Descrizione {#description}

![](assets/scheduler.png)

L' **[!UICONTROL Scheduler]** attività consente di pianificare quando viene avviato un flusso di lavoro o un'attività.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL Scheduler]** attività deve essere considerata come un inizio pianificato. Le regole di posizionamento dell'attività all'interno del grafico sono le stesse dell' **[!UICONTROL Start]** attività. Questa attività non deve avere una transizione in entrata.

Durante la creazione del flusso di lavoro, utilizzate una sola **[!UICONTROL Scheduler]** attività per ramo e ricordate di impostare un fuso orario. In caso contrario verrà impostato per l'esecuzione nel fuso orario del server.

>[!CAUTION]
>
>La durata **[!UICONTROL Repetition frequency]** dell'attività non può essere inferiore a 10 minuti. Ciò significa che non è possibile eseguire automaticamente un flusso di lavoro più volte ogni 10 minuti.

## Configurazione {#configuration}

1. Trascinate e rilasciate un' **[!UICONTROL Scheduler]** attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Specificate **[!UICONTROL Execution frequency]**:

   * **[!UICONTROL Once]**: il flusso di lavoro viene eseguito una sola volta.
   * **[!UICONTROL Several times a day]**: il flusso di lavoro viene eseguito regolarmente più volte al giorno. Potete impostare le esecuzioni in orari specifici o periodicamente.
   * **[!UICONTROL Daily]**: il flusso di lavoro viene eseguito una volta al giorno in un momento specifico.
   * **[!UICONTROL Weekly]**: il flusso di lavoro viene eseguito in un momento specificato, una o più volte alla settimana.
   * **[!UICONTROL Monthly]**: il flusso di lavoro viene eseguito in un momento specificato, una o più volte al mese. Potete selezionare i mesi, quando è necessario eseguire il flusso di lavoro. Potete anche impostare le esecuzioni in un giorno feriale specifico del mese, ad esempio il secondo martedì del mese.
   * **[!UICONTROL Yearly]**: il flusso di lavoro viene eseguito in un momento specificato, una o più volte all'anno.

1. Definire i dettagli di esecuzione in base alla frequenza selezionata. I campi di dettaglio possono variare a seconda della frequenza utilizzata (tempo, frequenza di ripetizione, giorni specificati, ecc.).

   >[!NOTE]
   >
   >Il **[!UICONTROL Repetition frequency]** campo consente di posizionare gli spazi vuoti quando viene attivato il flusso di lavoro. Ad esempio, se selezionate un periodo di esecuzione giornaliero e la frequenza di ripetizione è impostata su **2** (giorni), il flusso di lavoro verrà attivato ogni due giorni. Non può essere inferiore a 10 minuti. Se la frequenza di ripetizione è impostata su **0** (anche il valore predefinito), questa opzione non viene presa in considerazione e il flusso di lavoro viene eseguito in base alla frequenza di esecuzione specificata.

1. Specificate quando scade l'esecuzione:

   * **[!UICONTROL Never]**: il flusso di lavoro verrà eseguito, in base alla frequenza specificata, senza alcun limite all'intervallo di tempo o al numero di iterazioni.
   * **[!UICONTROL After a certain number of iterations]**: il flusso di lavoro verrà eseguito in base alla frequenza specificata, fino al raggiungimento del limite di **X** . Occorre pertanto **[!UICONTROL Number of iterations]** precisare le misure.
   * **[!UICONTROL On a specific date]**: il flusso di lavoro verrà eseguito in base alla frequenza specificata, fino a una data specifica. Occorre pertanto precisare il termine per l'esecuzione.

1. Controlla la pianificazione delle dieci esecuzioni successive del flusso di lavoro facendo clic su **[!UICONTROL Preview next executions]**.

1. Nella **[!UICONTROL Execution options]** scheda, impostare il fuso orario per il pianificatore nel **[!UICONTROL Time zone]** campo. Questo consente di avviare il flusso di lavoro in un fuso orario specifico, altrimenti il flusso di lavoro verrà eseguito nel fuso orario del server per impostazione predefinita.

   Per ulteriori informazioni sull'invio della consegna in base al fuso orario del destinatario, consulta questa [sezione](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md) o questo [esempio](../../automating/using/push-notification-delivery.md#sending-a-recurring-push-notification-with-a-workflow) di flusso di lavoro periodico.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Esempio {#example}

Nell'esempio seguente, l'attività è configurata in modo che avvii il flusso di lavoro settimanalmente, ogni due lunedì alle 7 del mattino, per una durata indeterminata.

![](assets/wkf_scheduler_example.png)

