---
title: File di trasferimento
seo-title: File di trasferimento
description: File di trasferimento
seo-description: L'attività File di trasferimento consente di ricevere o inviare file, verificare se sono presenti file o elencare i file in Adobe Campaign.
page-status-flag: never-activated
uuid: a 2 f 18118-b 681-4310-aee 0-9 e 82179 d 2032
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: gestione dati-attività
discoiquuid: 752 f 2 aed-f 897-485 e-b 329-f 3 cc 1756 ee 8 e
context-tags: Filetransfer, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0fcedd464ae2074e7eda793bbf20cc53ce04f324

---


# Transfer file{#transfer-file}

## Description {#description}

![](assets/file_transfer.png)

The **[!UICONTROL Transfer file]** activity allows you to receive or send files, test whether there are files present, or list files in Adobe Campaign.

## Context of use {#context-of-use}

Il modo in cui i dati vengono estratti viene definito quando l'attività è configurata. Ad esempio, il file da caricare può essere un elenco di contatti.

You can use this activity to recover data that will then be structured with the **[!UICONTROL Load file]** activity.

## Configuration {#configuration}

1. Drop a **[!UICONTROL Transfer file]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Use the drop-down list in the **[!UICONTROL Action]** field to select one of the following activity actions:

   ![](assets/wkf_file_transfer_01.png)

   * **Download file**: consente di scaricare un file.
   * **Caricamento file**: consente di caricare un file. Uploading a file from Adobe Campaign file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.
   * **Verificate se il file esiste**: consente di verificare se è presente un file.
   * **Elenco dei file**: consente di elencare i file presenti in Adobe Campaign.
   A seconda dell'azione selezionata, sono disponibili uno o più protocolli:

   * **HTTP**: questo protocollo consente di iniziare a scaricare un file da un account esterno o da un URL.

      * Click the **[!UICONTROL Use connection parameters defined in an external account]** option, then select the account you would like and specify the path of the file to download.

         ![](assets/wkf_file_transfer_03.png)

      * Click the **[!UICONTROL Quick configuration]** option, then enter the URL in the field that appears.

         ![](assets/wkf_file_transfer_04.png)
   * **S 3**: questo protocollo consente di iniziare a scaricare un file da un URL o un account esterno tramite Amazon Simple Storage Service (S 3).

      * Selezionate l'account esterno e specificate il percorso del file da scaricare.

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP**: questo protocollo consente di iniziare a scaricare un file da un URL o da un account esterno.

      * Click the **[!UICONTROL Use connection parameters defined in an external account]** option, then select the account you would like and specify the path of the file to download.

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >Sono supportati i caratteri jolly.

      * Click the **[!UICONTROL Quick configuration]** option, then enter the URL in the field that appears.
      * If you want to sort the imported files, select the **[!UICONTROL Sort alphanumerically]** option from the **[!UICONTROL Additional options]** section. I file verranno quindi elaborati in ordine sequenziale.

         ![](assets/wkf_file_transfer_sort.png)
   * **File presenti sul server Adobe Campaign**: questo protocollo corrisponde all'archivio che contiene i file da recuperare.

      Caratteri o caratteri jolly (ad esempio * o?) può essere usato per filtrare i file.

      Compilare questo campo e confermare l'attività per utilizzare questo protocollo.

      >[!NOTE]
      >
      >Il percorso deve essere relativo alla directory dello spazio di archiviazione del server Adobe Campaign. I file si trovano nella directory** sftp &lt; yourinstancename &gt;/**. Inoltre, non potete sfogliare le directory sopra lo spazio di archiviazione. For example: **user&lt;yourinstancename&gt;/my_recipients.csv** is correct. **../hello/my_recipients.csv** non è corretta. **//myserver/hello/myrecipients.csv** non è corretta.
   Selezionate il protocollo e completate i campi associati.

   The **[!UICONTROL Use a dynamic file path]** option, available for each protocol, lets you use a standard expression and events variables to personalize the name of the file to transfer. For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

1. **[!UICONTROL Additional options]** La sezione, disponibile a seconda del protocollo selezionato, consente di aggiungere parametri al protocollo. Potete:

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**: questa opzione è disponibile quando si seleziona l **[!UICONTROL File listing]** 'azione. It allows you to index all the files present on the server in the **vars.filenames** event variable in which the file names are separated by the **'n'** characters.

1. The **[!UICONTROL If no files are found]** section of the **[!UICONTROL Advanced options]** tab allows you to configure specific actions if any errors or inexistent files are detected when the activity is started.

   Potete anche definire dei tentativi. I diversi tentativi vengono visualizzati nel registro dell'esecuzione del flusso di lavoro.

   ![](assets/wkf_file_transfer_09.png)

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Historization settings {#historization-settings}

Every time a **[!UICONTROL Transfer file]** activity is executed, it stores the uploaded or downloaded files in a dedicated folder. One folder is created for each **[!UICONTROL Transfer file]** activity of a workflow. Pertanto, è importante limitare le dimensioni di questa cartella per mantenere spazio fisico sul server.

To do that, you can define **[!UICONTROL Historization settings]** in the **[!UICONTROL Advanced options]** of the **[!UICONTROL Transfer File]** activity.

**[!UICONTROL Historization settings]** consente di definire un numero massimo di file o di dimensioni totali per la cartella dell'attività. Per impostazione predefinita, 100 file e 50 MB sono autorizzati.

Ogni volta che l'attività viene eseguita, la cartella viene controllata come segue:

* Solo i file creati più di 24 ore prima dell'esecuzione dell'attività.
* If the number of files taken into account is greater than the value of the **[!UICONTROL Maximum number of files]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum number of files]** allowed is reached.
* If the total size of files taken into account is greater than the value of the **[!UICONTROL Maximum size (in MB)]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum size (in MB)]** allowed is reached.

>[!NOTE]
Se l'attività non viene eseguita di nuovo, la sua cartella non verrà controllata né eliminata. Con questo approccio, prestate attenzione durante il trasferimento di file di grandi dimensioni.

## Example {#example}

The following example shows the configuration of a **File transfer** activity which will then be followed by a **Load file** activity then an **Update data** activity. L'obiettivo di questo flusso di lavoro è quello di aggiungere o aggiornare i profili di database di Adobe Campaign con i dati recuperati dal flusso di lavoro.

1. Drag and drop a **Transfer file** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. In the **[!UICONTROL Protocol]** tab, select **SFTP**.
1. Select the **Use connection parameters defined in an external account** option.
1. Immettete il nome dell'account esterno.
1. Enter the **File path on the remote server**.

   ![](assets/wkf_file_transfer_07.png)

1. Confermate l'attività e salvate il flusso di lavoro.

