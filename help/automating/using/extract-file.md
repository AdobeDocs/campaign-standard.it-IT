---
title: Estrai file
seo-title: Estrai file
description: Estrai file
seo-description: L'attività Estrai file consente di esportare dati da Adobe Campaign sotto forma di file esterno.
page-status-flag: never-activated
uuid: 631 f 0 fbd -9 e 8 d -4 f 77-a 338-fcb 7 f 4 fc 1774
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: gestione dati-attività
discoiquuid: a 06509 f 9-4731-4187-b 43 d -3 bfa 361284 d 3
context-tags: Fileexport, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Extract file{#extract-file}

## Description {#description}

![](assets/export.png)

The **[!UICONTROL Extract file]** activity allows you to export data from Adobe Campaign in the form of an external file.

## Context of use {#context-of-use}

Il modo in cui i dati vengono estratti viene definito durante la configurazione dell'attività.

>[!CAUTION]
>
>The **[!UICONTROL Extract file]** activity must be placed after a **[!UICONTROL Query]** activity in order to be used.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Extract file]** activity into your workflow.

   ![](assets/wkf_data_export1.png)

1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Enter the label of the **Output file**. L'etichetta del file verrà compilata automaticamente con la data e l'ora in cui è stata creata. Ad esempio: recipients_20150815_081532.txt per un file generato il 15 agosto 2015 alle 08:15:32.

   >[!NOTE]
   >
   >It is possible to use the **[!UICONTROL formatDate]** function in this field to specify the file name.

1. If you like, you can zip the output file by selecting **[!UICONTROL Compression]** in the **[!UICONTROL Add a pre-processing step]** field. Il file di output verrà compresso in un file GZIP (.gz).
1. Click the ![](assets/add_darkgrey-24px.png) or **[!UICONTROL Add an element]** button to add an output column.

   ![](assets/wkf_data_export2.png)

   Viene aperta una nuova finestra.

   ![](assets/wkf_data_export3.png)

1. Immettete un'espressione. To do this, you can select an existing expression or create a new one using the **expression editor**.
1. Confermare l'espressione.

   L'espressione viene aggiunta alle colonne di output.

1. Create tutte le colonne necessarie. Potete modificare le colonne facendo clic sulle relative espressioni ed etichette.

   Se esportate i profili e desiderate utilizzarli in uno strumento esterno, accertatevi di esportare un unico identificatore. Per impostazione predefinita, non tutti i profili hanno un identificatore univoco, a seconda del modo in cui vengono aggiunti al database. For more information, refer to the [Generating a unique ID for profiles](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) section.

1. Click the **[!UICONTROL File structure]** tab to configure the output, date, and number formats for the file that will be exported.

   Check the **[!UICONTROL Export labels instead of internal values of enumerations]** option in case you export enumeration values. Questa opzione consente di ottenere etichette più brevi facili da comprendere invece di ID.

1. In the **[!UICONTROL Properties]** tab, select the **[!UICONTROL Do not generate a file if the inbound transition is empty]** option to avoid creating and uploading empty files on SFTP servers if the inbound transition is empty.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example {#example}

The following example illustrates how to configure an **[!UICONTROL Extract file]** activity after a **[!UICONTROL Query]** activity.

Questo flusso di lavoro consente di esportare un elenco di profili sotto forma di file esterno, in modo che i dati possano essere utilizzati all'esterno di Adobe Campaign.

1. Drag and drop an **[!UICONTROL Extract file]** activity into your workflow and place it after the **[!UICONTROL Query]** activity.

   In questo esempio, la query viene eseguita su tutti i profili da 18 a 30.

1. Aprite l'attività Estrai file per modificarla.
1. Denominate il file di output.
1. Aggiungere colonne di output.

   In questo esempio, l'e-mail, l'età, la data di nascita, il nome e il cognome dei profili vengono aggiunti come colonne di output.

   ![](assets/wkf_data_export6.png)

1. Click the **[!UICONTROL File structure]** tab to define:

   * Formato di output CSV

      ![](assets/wkf_data_export7.png)

   * Formato data

      ![](assets/wkf_data_export9.png)

1. Confermate l'attività.
1. Drag and drop a **[!UICONTROL Transfer file]** activity after the **[!UICONTROL Extract file]** activity to recover the extract file on an external account.
1. Open the activity and choose the **[!UICONTROL File upload]** action.

   ![](assets/wkf_data_export11.png)

1. Selezionate l'account esterno e immettete il percorso della cartella sul server.

   ![](assets/wkf_data_export12.png)

1. Confermate l'attività e salvate il flusso di lavoro.
1. Avviate il flusso di lavoro.

   Quando il flusso di lavoro è stato eseguito correttamente, il file estratto è disponibile sull'account esterno.

