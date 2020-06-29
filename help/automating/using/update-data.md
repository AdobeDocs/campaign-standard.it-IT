---
title: Aggiornare dati
description: L'attività Aggiorna dati consente di eseguire un aggiornamento di massa sui campi del database.
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
ht-degree: 1%

---


# Aggiornare dati{#update-data}

## Descrizione {#description}

![](assets/data_update.png)

L&#39; **[!UICONTROL Update data]** attività consente di eseguire un aggiornamento di massa sui campi del database.

## Contesto di utilizzo {#context-of-use}

L&#39;attività **Aggiorna dati** può essere utilizzata dopo l&#39;importazione di un file per inserire i dati recuperati nel database del Adobe Campaign . Diverse opzioni consentono di personalizzare l&#39;aggiornamento dei dati.

**Argomenti correlati:**

* [Caso di utilizzo: Aggiornamento dei dati in base a un file](../../automating/using/update-database-file.md)
* [Aggiornamento dei dati in base a un download automatico del file](../../automating/using/update-data-automatic-download.md)

## Configurazione {#configuration}

1. Trascinate e rilasciate un&#39; **[!UICONTROL Update data]** attività nel flusso di lavoro.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Specificare le modalità **[!UICONTROL Operation type]** da eseguire:

   * **[!UICONTROL Insert or update]**: inserire dati o aggiornarli se i record esistono già nel database.
   * **[!UICONTROL Insert only]**: inserire solo i dati. I record già esistenti non vengono aggiornati. Se vengono definiti i criteri di riconciliazione, verranno aggiunti solo i record non riconciliati.

      Selezionare la **[!UICONTROL Generate an outbound transition for rejects]** casella se i dati importati contengono alcuni record già presenti nel database per evitare possibili errori.

   * **[!UICONTROL Update]**: aggiornare i dati dei record già esistenti solo nel database.
   * **[!UICONTROL Delete]**: eliminare i dati.
   >[!NOTE]
   >
   >Il **[!UICONTROL Batch size]** campo consente di definire la dimensione batch massima per i dati da caricare.

1. Nella **[!UICONTROL Identification]** scheda, specificare come identificare i record nel database:

   * **[!UICONTROL Using the targeting dimension]**: selezionate il **[!UICONTROL Dimension to update]** pulsante e specificate il **[!UICONTROL Keys for finding records]**. Per ulteriori informazioni, consulta [Impostazione del targeting di dimensioni e risorse](../../automating/using/query.md#targeting-dimensions-and-resources).
   * Se i dati immessi corrispondono a una dimensione di targeting esistente, selezionate l&#39; **[!UICONTROL Using one or more links]** opzione. Quindi selezionate il **[!UICONTROL Dimension to update]**.
   Se il tipo di operazione selezionato richiede un aggiornamento, è necessario utilizzare le chiavi di riconciliazione.

1. Nella **[!UICONTROL Fields to update]** scheda, specificate i campi in cui verrà applicato l&#39;aggiornamento e, se necessario, aggiungete le condizioni in modo da eseguire l&#39;aggiornamento. A questo scopo, utilizzare la **[!UICONTROL Taken into account if]** colonna. Le condizioni vengono applicate una dopo l&#39;altra in ordine di elenco. Utilizzate le frecce a destra per cambiare l&#39;ordine degli aggiornamenti. È possibile utilizzare lo stesso campo di destinazione più volte.

   È possibile collegare automaticamente i campi utilizzando il ![](assets/wkf_magic_wand-24px.png) pulsante . Il collegamento automatico rileva i campi con lo stesso nome.

   Durante un&#39;operazione di **[!UICONTROL Insert or update]** tipo, è possibile selezionare singolarmente l&#39;operazione da applicare a ciascun campo. A questo scopo, selezionate il valore desiderato nella **[!UICONTROL Operation]** colonna.

   >[!NOTE]
   >
   >**Gestione degli aggiornamenti** I **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]**, **[!UICONTROL created]** e **[!UICONTROL createdBy]** i campi vengono aggiornati automaticamente all&#39;esecuzione di un&#39;attività di aggiornamento dei dati, a meno che la loro configurazione non venga eseguita esplicitamente nella tabella di aggiornamento dei campi. L&#39;aggiornamento viene eseguito solo sui record in cui è stata rilevata almeno una differenza. Se i valori sono identici, non viene effettuato alcun aggiornamento.

1. Se necessario, gestite le [Transizioni](../../automating/using/activity-properties.md) dell&#39;attività per accedere alle opzioni avanzate per la popolazione in uscita.

   Se avete selezionato **[!UICONTROL Insert only]** e i dati importati possono contenere record già presenti nel database, selezionate la **[!UICONTROL Generate an outbound transition for the rejects]** casella per evitare eventuali errori.

1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.
