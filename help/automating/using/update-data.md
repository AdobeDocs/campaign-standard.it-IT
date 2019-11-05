---
title: Aggiornare dati
description: L'attività Aggiorna dati consente di eseguire un aggiornamento di massa sui campi del database.
page-status-flag: mai attivato
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: gestione dei dati
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Aggiornare dati{#update-data}

## Descrizione {#description}

![](assets/data_update.png)

L' **[!UICONTROL Update data]** attività consente di eseguire un aggiornamento di massa sui campi del database.

## Contesto di utilizzo {#context-of-use}

L'attività **Aggiorna dati** può essere utilizzata dopo l'importazione di un file per inserire i dati recuperati nel database di Adobe Campaign. Diverse opzioni consentono di personalizzare l'aggiornamento dei dati.

## Configurazione {#configuration}

1. Trascinate e rilasciate un' **[!UICONTROL Update data]** attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Specificare le modalità **[!UICONTROL Operation type]** da eseguire:

   * **[!UICONTROL Insert or update]**: inserire dati o aggiornarli se i record esistono già nel database.
   * **[!UICONTROL Insert only]**: inserire solo i dati. I record già esistenti non vengono aggiornati. Se sono definiti criteri di riconciliazione, verranno aggiunti solo i record non riconciliati.

      Selezionare la **[!UICONTROL Generate an outbound transition for rejects]** casella se i dati importati contengono alcuni record già presenti nel database per evitare possibili errori.

   * **[!UICONTROL Update]**: aggiornare i dati dei record già esistenti solo nel database.
   * **[!UICONTROL Delete]**: eliminare i dati.
   >[!NOTE]
   >
   >Il **[!UICONTROL Batch size]** campo consente di definire la dimensione batch massima per i dati da caricare.

1. Nella **[!UICONTROL Identification]** scheda, specificare come identificare i record nel database:

   * **[!UICONTROL Using the targeting dimension]**: selezionate il **[!UICONTROL Dimension to update]** pulsante e specificate il **[!UICONTROL Keys for finding records]**. Per ulteriori informazioni, consulta [Impostazione del targeting di dimensioni e risorse](../../automating/using/query.md#targeting-dimensions-and-resources).
   * Se i dati immessi corrispondono a una dimensione di targeting esistente, selezionate l' **[!UICONTROL Using one or more links]** opzione. Quindi selezionate il **[!UICONTROL Dimension to update]**.
   Se il tipo di operazione selezionato richiede un aggiornamento, è necessario utilizzare le chiavi di riconciliazione.

1. Nella **[!UICONTROL Fields to update]** scheda, specificate i campi in cui verrà applicato l'aggiornamento e, se necessario, aggiungete le condizioni in modo da eseguire l'aggiornamento. A questo scopo, utilizzare la **[!UICONTROL Taken into account if]** colonna. Le condizioni vengono applicate una dopo l'altra in ordine di elenco. Utilizzate le frecce a destra per cambiare l'ordine degli aggiornamenti. È possibile utilizzare lo stesso campo di destinazione più volte.

   È possibile collegare automaticamente i campi utilizzando il ![](assets/wkf_magic_wand-24px.png) pulsante . Il collegamento automatico rileva i campi con lo stesso nome.

   Durante un'operazione di **[!UICONTROL Insert or update]** tipo, è possibile selezionare singolarmente l'operazione da applicare a ciascun campo. A questo scopo, selezionate il valore desiderato nella **[!UICONTROL Operation]** colonna.

   >[!NOTE]
   >
   >**Gestione degli aggiornamenti** I **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]**, **[!UICONTROL created]** e **[!UICONTROL createdBy]** i campi vengono aggiornati automaticamente all'esecuzione di un'attività di aggiornamento dei dati, a meno che la loro configurazione non venga eseguita esplicitamente nella tabella di aggiornamento dei campi. L'aggiornamento viene eseguito solo sui record in cui è stata rilevata almeno una differenza. Se i valori sono identici, non viene effettuato alcun aggiornamento.

1. Se necessario, gestite le [Transizioni](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) dell'attività per accedere alle opzioni avanzate per la popolazione in uscita.

   Se avete selezionato **[!UICONTROL Insert only]** e i dati importati possono contenere record già presenti nel database, selezionate la **[!UICONTROL Generate an outbound transition for the rejects]** casella per evitare eventuali errori.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Esempio {#example}

L'attività seguente mostra la configurazione di un' **[!UICONTROL Update data]** attività dopo un' **[!UICONTROL Load file]** attività. Lo scopo di questo flusso di lavoro è quello di aggiungere o aggiornare profili al database Adobe Campaign con i dati recuperati dal file. La chiave di riconciliazione utilizzata è l'indirizzo e-mail.

Il file caricato è un file in formato **.txt** contenente i dati di esempio seguenti:

```
lastname;firstname;email;birthdate
jackman;megan;megan.jackman@testmail.com;07/08/1975
phillips;edward;phillips@testmail.com;09/03/1986
weaver;justin;justin_w@testmail.com;11/15/1990
martin;babeth;babeth_martin@testmail.net;11/25/1964
reese;richard;rreese@testmail.com;02/08/1987
cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
grimes;daryl;daryl_890@testmail.com;12/06/1979
tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
```

L' **[!UICONTROL Update data]** attività è configurata come segue:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

