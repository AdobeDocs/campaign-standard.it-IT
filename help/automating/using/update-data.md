---
title: Update data
description: L’attività Update data ti consente di eseguire un aggiornamento di massa sui campi del database.
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 96%

---


# Update data{#update-data}

## Descrizione {#description}

![](assets/data_update.png)

L’attività **[!UICONTROL Update data]** ti consente di eseguire un aggiornamento di massa sui campi del database.

## Contesto di utilizzo {#context-of-use}

L’attività **Update data** può essere utilizzata dopo l’importazione di un file per inserire i dati recuperati nel database di Adobe Campaign. Esistono varie opzioni per personalizzare l’aggiornamento dei dati.

**Argomenti correlati:**

* [Caso di utilizzo: Aggiornamento dei dati in base a un file](../../automating/using/update-database-file.md)
* [Aggiornamento dei dati in base a un download automatico del file](../../automating/using/update-data-automatic-download.md)

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Update data]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Specifica il **[!UICONTROL Operation type]** da eseguire:

   * **[!UICONTROL Insert or update]**: inserire dati o aggiornarli, se i record sono già presenti nel database.
   * **[!UICONTROL Insert only]**: inserire solo i dati. I record già esistenti non vengono aggiornati. Se vengono definiti i criteri di riconciliazione, verranno aggiunti solo i record non riconciliati.

      Se i dati importati contengono alcuni record già presenti nel database, seleziona la casella **[!UICONTROL Generate an outbound transition for rejects]** per evitare potenziali errori.

   * **[!UICONTROL Update]**: aggiorna i dati dei record che sono già presenti solo nel database.
   * **[!UICONTROL Delete]**: elimina i dati.

   >[!NOTE]
   >
   >Il campo **[!UICONTROL Batch size]** ti consente di definire la dimensione batch massima per i dati da caricare.

1. Nella scheda **[!UICONTROL Identification]**, specifica come identificare i record nel database:

   * **[!UICONTROL Using the targeting dimension]**: seleziona la **[!UICONTROL Dimension to update]**, quindi specifica le **[!UICONTROL Keys for finding records]**. Per ulteriori informazioni, consulta [Dimensioni di targeting e risorse](../../automating/using/query.md#targeting-dimensions-and-resources).
   * Se i dati immessi corrispondono a una dimensione di targeting esistente, seleziona l’opzione **[!UICONTROL Using one or more links]**. Quindi scegli la **[!UICONTROL Dimension to update]**.

   Se il tipo di operazione selezionato richiede un aggiornamento, devi utilizzare le chiavi di riconciliazione.

1. Nella scheda **[!UICONTROL Fields to update]**, specifica i campi in cui verrà applicato l’aggiornamento e, se necessario, aggiungi le condizioni per l’esecuzione. A questo scopo, utilizza la colonna **[!UICONTROL Taken into account if]**. Le condizioni vengono applicate in sequenza, secondo l’ordine dell’elenco. Utilizza le frecce a destra per cambiare l’ordine degli aggiornamenti. Puoi usare più volte lo stesso campo di destinazione.

   Puoi collegare automaticamente i campi utilizzando il pulsante ![](assets/wkf_magic_wand-24px.png). Il collegamento automatico rileva i campi con il medesimo nome.

   Durante un’operazione di tipo **[!UICONTROL Insert or update]**, puoi selezionare singolarmente l’operazione da applicare a ciascun campo. A questo scopo, seleziona il valore desiderato nella colonna **[!UICONTROL Operation]**.

   >[!NOTE]
   >
   >**Gestione degli aggiornamenti** I campi **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]**, **[!UICONTROL created]** e **[!UICONTROL createdBy]** vengono aggiornati automaticamente all’avvio di un’attività di aggiornamento dei dati, a meno che la loro configurazione non venga eseguita esplicitamente nella tabella di aggiornamento dei campi. L’aggiornamento viene eseguito solo sui record in cui è stata rilevata una minima differenza. Se i valori sono identici, non viene effettuato alcun aggiornamento.

1. Se necessario, gestisci le [Transizioni](../../automating/using/activity-properties.md) dell’attività per accedere alle opzioni avanzate per la popolazione in uscita.

   Se hai selezionato **[!UICONTROL Insert only]** e i dati importati possono contenere record già presenti nel database, seleziona la casella **[!UICONTROL Generate an outbound transition for the rejects]** per evitare eventuali errori.

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.
