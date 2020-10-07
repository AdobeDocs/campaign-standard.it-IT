---
title: Extract file
description: L’attività Extract file ti consente di esportare dati da Adobe Campaign sotto forma di un file esterno.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 91%

---


# Extract file{#extract-file}

## Descrizione {#description}

![](assets/export.png)

L’attività **[!UICONTROL Extract file]** ti consente di esportare dati da Adobe Campaign sotto forma di un file esterno.

## Contesto di utilizzo {#context-of-use}

La modalità di estrazione dei dati viene definita durante la configurazione dell’attività.

>[!CAUTION]
>
>Per utilizzare l’attività **[!UICONTROL Extract file]**, devi inserirla dopo un’attività **[!UICONTROL Query]**.

**Argomenti correlati:**

* [Caso di utilizzo: Esportazione di profili in un file esterno](../../automating/using/exporting-profiles-in-file.md)

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Extract file]** nel flusso di lavoro.

   ![](assets/wkf_data_export1.png)

1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Immetti l’etichetta del **file di output**. L’etichetta del file viene automaticamente completata con la data e l’ora di creazione, in modo che sia univoca. Ad esempio: destinatari_15082015_81532.txt per un file generato il 15 agosto 2015 alle 8.15.32.

   >[!NOTE]
   >
   >È possibile utilizzare la funzione **[!UICONTROL formatDate]** in questo campo per specificare il nome del file.

1. Se lo desideri, puoi comprimere il file di output selezionando **[!UICONTROL Compression]** nel campo **[!UICONTROL Add a pre-processing step]**. Il file di output viene compresso in un file GZIP (.gz).

   Il **[!UICONTROL Add a pre-processing step]** campo consente inoltre di cifrare un file prima di estrarlo. Per ulteriori informazioni su come utilizzare i file crittografati, consulta [questa sezione](../../automating/using/managing-encrypted-data.md)

1. Fai clic sul pulsante ![](assets/add_darkgrey-24px.png) o su **[!UICONTROL Add an element]** per aggiungere una colonna di output.

   ![](assets/wkf_data_export2.png)

   Viene visualizzata una nuova finestra.

   ![](assets/wkf_data_export3.png)

1. Immetti un’espressione. A questo scopo, puoi selezionare un’espressione esistente o crearne una nuova utilizzando l’**editor espressioni**.
1. Conferma l’espressione.

   L’espressione viene aggiunta alle colonne di output.

1. Crea tutte le colonne necessarie. Puoi modificare le colonne facendo clic sulle relative espressioni ed etichette.

   Se esporti i profili e desideri utilizzarli in uno strumento esterno, accertati di esportare un identificatore univoco. Per impostazione predefinita non tutti i profili hanno un identificatore univoco, a seconda della modalità di aggiunta al database. Per ulteriori informazioni, consulta la sezione [Generazione di un ID univoco per i profili](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

1. Fai clic sulla scheda **[!UICONTROL File structure]** per configurare i formati di output, data e numero per il file da esportare.

   Seleziona l’opzione **[!UICONTROL Export labels instead of internal values of enumerations]** nel caso dell’esportazione di valori di enumerazione. Questa opzione ti consente di recuperare etichette più brevi che sono più facili da comprendere rispetto agli ID.

1. Nella scheda **[!UICONTROL Properties]**, seleziona l’opzione **[!UICONTROL Do not generate a file if the inbound transition is empty]** per evitare di creare e caricare file vuoti sui server SFTP se la transizione in entrata è vuota.
1. Conferma la configurazione dell’attività e salva il flusso di lavoro.
