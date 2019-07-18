---
title: Aggiorna dati
seo-title: Aggiorna dati
description: Aggiorna dati
seo-description: L'attività di dati Aggiorna consente di eseguire un aggiornamento di massa sui campi del database.
page-status-flag: never-activated
uuid: 1 dc 55 db 5-affd -4688-b 673-adfb 8 c 1338 b 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: gestione dati-attività
discoiquuid: 4 db 83 c 95-4 b 75-4 a 16-8 dbf-bd 8940431 fa 9
context-tags: writer, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Update data{#update-data}

## Description {#description}

![](assets/data_update.png)

The **[!UICONTROL Update data]** activity allows you to perform a mass update on fields in the database.

## Context of use {#context-of-use}

The **Update data** activity can be used after importing a file in order to insert the data recovered into the Adobe Campaign database. Diverse opzioni consentono di personalizzare i dati.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Update data]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Operation type]** to be carried out:

   * **[!UICONTROL Insert or update]**: inserire dati o aggiornarli se sono già presenti nel database.
   * **[!UICONTROL Insert only]**: inserire solo dati. I record già esistenti non vengono aggiornati. Se sono definiti criteri di riconciliazione, verranno aggiunti solo i record non riconciliati.

      Check the **[!UICONTROL Generate an outbound transition for rejects]** box if the data imported contains certain records that already exist in the database to avoid any possible errors.

   * **[!UICONTROL Update]**: aggiornare i dati dei record già esistenti nel database.
   * **[!UICONTROL Delete]**: eliminare i dati.
   >[!NOTE]
   >
   >**[!UICONTROL Batch size]** Il campo consente di definire la dimensione batch massima per i dati da caricare.

1. In the **[!UICONTROL Identification]** tab, specify how to identify the records in the database:

   * **[!UICONTROL Using the targeting dimension]**: selezionate quindi **[!UICONTROL Dimension to update]** il **[!UICONTROL Keys for finding records]** nome. For more this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * If the data entered matches an existing targeting dimension, select the **[!UICONTROL Using one or more links]** option. Then select the **[!UICONTROL Dimension to update]**.
   Se il tipo di operazione selezionato richiede un aggiornamento, è necessario utilizzare le chiavi di riconciliazione.

1. In the **[!UICONTROL Fields to update]** tab, specify the fields on which the update will be applied and, if necessary, add conditions so that this update is carried out. To do this, use the **[!UICONTROL Taken into account if]** column. Le condizioni vengono applicate una dopo l'altra nell'ordine degli elenchi. Usate le frecce a destra per modificare l'ordine degli aggiornamenti. Potete usare più volte lo stesso campo di destinazione.

   You can automatically link fields using the ![](assets/wkf_magic_wand-24px.png) button. Il collegamento automatico rileva i campi con lo stesso nome.

   During an **[!UICONTROL Insert or update]** type operation, you can individually select the operation to apply for each field. To do this, select the value you would like in the **[!UICONTROL Operation]** column.

   >[!NOTE]
   >
   >**Gestione degli aggiornamenti** I **[!UICONTROL lastModified]** campi e **[!UICONTROL modifiedBy]****[!UICONTROL created]** vengono **[!UICONTROL createdBy]** aggiornati automaticamente quando viene eseguita un'attività dati di aggiornamento, a meno che la relativa configurazione non venga eseguita esplicitamente nella tabella di aggiornamento del campo. L'aggiornamento viene eseguito solo nei record in cui è stata rilevata almeno una differenza. Se i valori sono identici, non viene eseguito nessun aggiornamento.

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.

   If you have selected **[!UICONTROL Insert only]** and the data imported may contain records that are already present in the database, check the **[!UICONTROL Generate an outbound transition for the rejects]** box to avoid any possible errors.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example {#example}

The following activity shows the configuration of an **[!UICONTROL Update data]** activity following a **[!UICONTROL Load file]** activity. Questo flusso di lavoro consente di aggiungere o aggiornare profili al database Adobe Campaign con i dati recuperati dal file. La chiave di riconciliazione utilizzata è l'indirizzo e-mail.

The file loaded is a **.txt** format file containing the following example data:

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

The **[!UICONTROL Update data]** activity is configured as follows:

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

