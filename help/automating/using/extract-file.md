---
title: Estrarre file
description: L'attività del file Extract consente di esportare dati da  Adobe Campaign sotto forma di file esterno.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 15e5aebdd67e8f5ddee89506c0469a101d94d2e8
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 1%

---


# Estrarre file{#extract-file}

## Descrizione {#description}

![](assets/export.png)

L&#39; **[!UICONTROL Extract file]** attività consente di esportare dati da  Adobe Campaign sotto forma di file esterno.

## Contesto di utilizzo {#context-of-use}

Il modo in cui verranno estratti i dati viene definito al momento della configurazione dell&#39;attività.

>[!CAUTION]
>
>L&#39; **[!UICONTROL Extract file]** attività deve essere collocata dopo un&#39; **[!UICONTROL Query]** attività per essere utilizzata.

**Argomenti correlati:**

* [Caso di utilizzo: Esportazione di profili in un file esterno](../../automating/using/exporting-profiles-in-file.md)

## Configurazione {#configuration}

1. Trascinate e rilasciate un&#39; **[!UICONTROL Extract file]** attività nel flusso di lavoro.

   ![](assets/wkf_data_export1.png)

1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Immettere l&#39;etichetta del file **** Output. L&#39;etichetta del file verrà automaticamente completata con la data e l&#39;ora in cui è stato creato, in modo che sia univoca. Ad esempio: Recipients_20150815_081532.txt per un file ha generato il 15 agosto 2015 alle 08:15:32.

   >[!NOTE]
   >
   >È possibile utilizzare la **[!UICONTROL formatDate]** funzione in questo campo per specificare il nome del file.

1. Se lo desideri, puoi comprimere il file di output selezionando **[!UICONTROL Compression]** nel **[!UICONTROL Add a pre-processing step]** campo. Il file di output verrà compresso in un file GZIP (.gz).

   Il **[!UICONTROL Add a pre-processing step]** campo consente inoltre di cifrare un file prima di estrarlo. Per ulteriori informazioni su come utilizzare i file crittografati, consulta [questa sezione](../../automating/using/managing-encrypted-data.md)

1. Fate clic sul ![](assets/add_darkgrey-24px.png) pulsante o **[!UICONTROL Add an element]** per aggiungere una colonna di output.

   ![](assets/wkf_data_export2.png)

   Si aprirà una nuova finestra.

   ![](assets/wkf_data_export3.png)

1. Immettere un&#39;espressione. A questo scopo, è possibile selezionare un&#39;espressione esistente o crearne una nuova utilizzando l&#39;editor **di** espressioni.
1. Confermate l&#39;espressione.

   L&#39;espressione viene aggiunta alle colonne di output.

1. Create tutte le colonne necessarie. Per modificare le colonne, fare clic sulle relative espressioni ed etichette.

   Se esportate i profili e desiderate utilizzarli in uno strumento esterno, accertatevi di esportare un identificatore univoco. Per impostazione predefinita, non tutti i profili hanno un identificatore univoco, a seconda del modo in cui vengono aggiunti al database. Per ulteriori informazioni, consulta la sezione [Generazione di un ID univoco per i profili](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources) .

1. Fare clic sulla **[!UICONTROL File structure]** scheda per configurare i formati di output, data e numero per il file che verrà esportato.

   Selezionare l&#39; **[!UICONTROL Export labels instead of internal values of enumerations]** opzione nel caso in cui si esportino i valori di enumerazione. Questa opzione consente di recuperare etichette più brevi che possono essere facilmente comprensibili al posto degli ID.

1. Nella **[!UICONTROL Properties]** scheda, selezionate l&#39; **[!UICONTROL Do not generate a file if the inbound transition is empty]** opzione per evitare di creare e caricare file vuoti sui server SFTP se la transizione in entrata è vuota.
1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.
