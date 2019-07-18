---
title: Carica file
seo-title: Carica file
description: Carica file
seo-description: L'attività Carica file consente di importare dati in un modulo strutturato per utilizzare tali dati in Adobe Campaign.
page-status-flag: never-activated
uuid: 69 af 12 cc -6 f 82-4977-9 f 53-aa 7 bc 26 f 5 d 7 e
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: gestione dati-attività
discoiquuid: 584 ff 893-9 b 1 b -46 c 9-9628-714 ab 349 ab 88
context-tags: Fileimport, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Load file{#load-file}

## Description {#description}

![](assets/data_loading.png)

The **[!UICONTROL Load file]** activity allows you to import data in one structured form to use this data in Adobe Campaign. I dati vengono importati temporaneamente e un'altra attività è necessaria per integrarla definitivamente nel database di Adobe Campaign.

## Context of use {#context-of-use}

Il modo in cui i dati vengono estratti viene definito quando l'attività è configurata. Ad esempio, il file da caricare può essere un elenco di contatti.

>[!CAUTION]
>
>Sono inclusi solo i file di struttura «flat», ad esempio i file.txt. csv, ecc., i file.

Potete:

* Use the file structure to apply it to another file's data (recovered using the **[!UICONTROL Transfer file]** activity) or,
* Utilizza la struttura e i dati del file per importarli in Adobe Campaign.

## Configuration {#configuration}

La configurazione dell'attività prevede due passaggi. Innanzitutto, è necessario definire la struttura del file prevista caricando un file di esempio. Una volta effettuata questa operazione, potete specificare l'origine del file i cui dati verranno importati.

>[!NOTE]
>
>I dati del file di esempio vengono utilizzati per configurare l'attività ma non vengono importati. È consigliabile utilizzare un file di esempio contenente piccoli dati.

1. Drag and drop a **[!UICONTROL Load file]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Caricate il file di esempio che vi consentirà di definire la struttura prevista durante l'importazione del file finale.

   ![](assets/wkf_file_loading.png)

   Once the data file is uploaded, two new tabs appear in the activity: **[!UICONTROL File structure]** and **[!UICONTROL Column definition]**.

1. Go to the **[!UICONTROL File structure]** tab to view the structure that is automatically detected from the sample file.

   Se la struttura del file è stata rilevata in modo errato, è possibile correggere eventuali errori possibili:

   * You can choose to use the structure of another file by selecting the **[!UICONTROL Detect structure from a new file]** option.
   * Potete modificare i parametri di rilevamento predefiniti per adattarli al file. **[!UICONTROL File type]** Il campo consente di specificare se il file da importare è composto da colonne con lunghezza fissa. In that case, you must also specify the maximum number of characters for each column in the **[!UICONTROL Column definition]** tab.

      All of the detection options necessary to correctly recover the data from the file are regrouped in **[!UICONTROL File format]**. Potete modificarle e quindi ririlevare la struttura dell'ultimo file caricato nell'attività tenendo conto di queste nuove impostazioni. To do this, use the **[!UICONTROL Apply configuration]** button. Ad esempio, è possibile specificare un separatore di colonna diverso.

      >[!NOTE]
      >
      >Questa operazione prende in considerazione l'ultimo file caricato nell'attività. Se il file rilevato è di grandi dimensioni, l'anteprima dati mostrerà solo le prime 30 righe.

      ![](assets/wkf_file_loading3.png)

      In the **[!UICONTROL File format]** section, the **[!UICONTROL Check columns from file against column definitions]** option lets you verify that the columns of the file you are uploading correspond to the column definition.

      Se il numero e/o il nome delle colonne non corrisponde alla definizione della colonna, durante l'esecuzione del flusso di lavoro viene visualizzato un messaggio di errore. Se l'opzione non è attivata, gli avvisi vengono visualizzati nel file di registro.

      ![](assets/wkf_file_loading_check.png)

1. Go to the **[!UICONTROL Column definition]** tab to check the data format for each column and adjust the parameters if necessary.

   The **[!UICONTROL Column definition]** tab allows you to precisely specify the data structure of each column in order to import data that does not contain any errors (for example, using null management) and make it match the types that are already present in the Adobe Campaign database for future operations.

   Ad esempio, è possibile modificare l'etichetta di una colonna, selezionandone il tipo (stringa, numero intero, data, ecc.) oppure specifica anche l'elaborazione degli errori.

   For more information, refer to the [Column format](../../automating/using/load-file.md#column-format) section.

   ![](assets/wkf_file_loading4.png)

1. In the **[!UICONTROL Execution]** tab, specify whether the file is to be processed for loading data:

   * Deriva da una transizione in ingresso nel flusso di lavoro.
   * È quello caricato durante il passaggio precedente.
   * È un nuovo file da caricare dal computer locale. The **[!UICONTROL Upload a new file from local machine]** option appears if uploading a first file was already defined in the workflow. Questo consente di caricare un altro file da elaborare se il file corrente non è adatto alle vostre esigenze.

      ![](assets/wkf_file_loading1.png)

1. If the file that you want to load the data from is compressed into a GZIP file (.gz), select the **[!UICONTROL Decompression]** option in the **[!UICONTROL Add a pre-processing step]** field. Questo consente di decomprimere il file prima di caricare i dati. Questa opzione è disponibile solo se il file proviene dalla transizione in entrata dell'attività.
1. The **[!UICONTROL Keep the rejects in a file]** option enables you to download a file containing errors that occurred during the import, and to apply to it a post-processing stage.

   >[!NOTE]
   >
   >The **[!UICONTROL Add date and time to the file name]** option lets you add a timestamp the name of the file containing the rejects.

   ![](assets/wkf_file_loading_keeprejects.png)

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Column format {#column-format}

Quando si carica un file di esempio, il formato della colonna viene rilevato automaticamente con i parametri predefiniti per ogni tipo di dati. Potete modificare questi parametri predefiniti per specificare i processi particolari da applicare ai dati, in particolare in presenza di un errore o di un valore vuoto.

To do this, select **[!UICONTROL Edit properties]** from the quick actions of the column whose format you would like to define. Viene aperta la finestra dei dettagli del formato colonna.

![](assets/wkf_file_loading4.png)

È quindi possibile modificare la formattazione di ogni colonna.

La formattazione delle colonne consente di definire l'elaborazione dei valori di ciascuna colonna:

* **[!UICONTROL Ignore column]**: non elabora questa colonna durante il caricamento dei dati.
* **[!UICONTROL Data type]**: specifica il tipo di dati previsto per ogni colonna.
* **[!UICONTROL Format and separators]**, **Proprietà**: specificare le proprietà di un testo, l'ora, la data e il formato numerico, nonché il separatore specificato dal contesto della colonna.

   * **[!UICONTROL Maximum number of characters]**: specifica il numero massimo di caratteri per le colonne del tipo di stringa.

      Questo campo deve essere compilato quando si caricano i file composti da colonne con lunghezza fissa.

   * **[!UICONTROL Letter case management]**: definisce se è necessario applicare un processo maiuscolo/minuscolo ai **dati Testo** .
   * **[!UICONTROL White space management]**: specifica se alcuni spazi devono essere ignorati in una stringa per **i dati Testo** .
   * **[!UICONTROL Time format]****[!UICONTROL Date format]**: specificare il formato per **Data**, **Ora** e **Data e ora** .
   * **[!UICONTROL Format]**: consente di definire il formato dei valori numerici per **Integer** e **i dati Numero** mobile.
   * **[!UICONTROL Separator]**: definisce il separatore specificato dal contesto della colonna (separatore delle migliaia o separatore decimale per valori numerici, separatore per date e ora) per **Data**, **Ora**, **Data e ora**, **Integer** e Numero **di numeri** Mobile.

* **[!UICONTROL Remapping of values]**: questo campo è disponibile solo nella configurazione dei dettagli delle colonne. Consente di trasformare alcuni valori durante l'importazione. Ad esempio, potete trasformare «tre» in «3».
* **[!UICONTROL Error processing]**: definisce il comportamento se viene rilevato un errore.

   * **[!UICONTROL Ignore the value]**: il valore viene ignorato. Un avviso viene generato nel registro dell'esecuzione del flusso di lavoro.
   * **[!UICONTROL Reject the line]**: l'intera riga non viene elaborata.
   * **[!UICONTROL Use a default value]**: sostituisce il valore che causava l'errore con un valore predefinito, definito nel **[!UICONTROL Default value]** campo.
   * **[!UICONTROL Use a default value in case the value is not remapped]**: sostituisce il valore che causava l'errore con un valore predefinito definito nel **[!UICONTROL Default value]** campo, a meno che non sia stata definita una mappatura per il valore errato (consultate **[!UICONTROL Remapping of values]** l'opzione sopra).
   * **[!UICONTROL Reject the line when there is no remapping value]**: l'intera riga non viene elaborata a meno che non sia stata definita una mappatura per il valore errato (consultate **[!UICONTROL Remapping of values]** l'opzione sopra).
   >[!NOTE]
   >
   >**[!UICONTROL Error processing]** problemi relativi ai valori nel file importato. Ad esempio, un tipo di dati difettoso rilevato («quattro» in lettere per una colonna «Integer»), una stringa contenente più caratteri del numero massimo consentito, una data con separatori difettosi e così via. Tuttavia, questa opzione non riguarda gli errori generati dalla gestione dei valori vuota.

* **[!UICONTROL Default value]**: specifica il valore predefinito in base all'elaborazione degli errori scelta.
* **[!UICONTROL Empty value management]**: specifica come gestire valori vuoti durante il caricamento dei dati.

   * **[!UICONTROL Generate an error for numerical fields]**: genera un errore solo per i campi numerici, in caso contrario inserisce un valore NULL.
   * **[!UICONTROL Insert NULL in the corresponding field]**: autorizza valori vuoti. Il valore NULL viene quindi inserito.
   * **[!UICONTROL Generate an error]**: genera un errore se un valore è vuoto.

## Example {#example}

L'attività dei file di caricamento struttura principalmente i dati recuperati da un'attività del file di trasferimento per integrarlo nei dati esistenti.

L'esempio seguente mostra il risultato di un'attività di caricamento caricato automaticamente tramite un'attività di trasferimento di file, seguita da un'attività di dati update. Questo flusso di lavoro intende arricchire il database Adobe Campaign con nuovi profili o aggiornare i profili esistenti utilizzando i dati recuperati dal file importato.

1. Drag and drop a **[!UICONTROL Transfer file]** activity into your workflow and configure it in a way so that it recovers the file you would like.
1. Drag and drop a **[!UICONTROL Load file]** activity into your workflow and place it after the **[!UICONTROL Transfer file]** activity.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. In the **[!UICONTROL File to load]** section of the **[!UICONTROL Execution]** tab, check the **[!UICONTROL Use the file specified in the inbound transition]** option.

   ![](assets/wkf_file_loading8.png)

1. Configurate l'attività come specificato precedentemente.
1. Drag and drop an **[!UICONTROL Update data]** activity into your workflow and place it after the **[!UICONTROL Load file]** activity, then configure it. Refer to [Update data](../../automating/using/update-data.md).

Una volta iniziato il flusso di lavoro, i dati del file caricato vengono estratti e utilizzati per arricchire il database Adobe Campaign.
