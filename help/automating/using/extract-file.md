---
title: Extract file
description: L’attività Extract file ti consente di esportare dati da Adobe Campaign sotto forma di un file esterno.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ccf73563-f0f8-4397-ba96-7c5727562acd
TQID: 'https://experienceleague.adobe.com/NHN4AQinVIJsssfzhHhC6uKbcRBRPXq1h-ZZg8UIWkQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 78%
---
# Estrai file{#extract-file}

## Descrizione {#description}

![](assets/export.png)

L’attività **[!UICONTROL Extract file]** ti consente di esportare dati da Adobe Campaign sotto forma di un file esterno.

## Contesto di utilizzo {#context-of-use}

La modalità di estrazione dei dati viene definita durante la configurazione dell’attività.

>[!CAUTION]
>
>Per utilizzare l’attività **[!UICONTROL Extract file]**, devi inserirla dopo un’attività **[!UICONTROL Query]**.

**Argomenti correlati:**

* [Caso di utilizzo: esportazione di profili in un file esterno](../../automating/using/exporting-profiles-in-file.md)

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Extract file]** nel flusso di lavoro.

   ![](assets/wkf_data_export1.png)

1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Immetti l’etichetta del **file di output**. L’etichetta del file viene automaticamente completata con la data e l’ora di creazione, in modo che sia univoca. Ad esempio: recipients_20150815_081532.txt per un file generato il 15 agosto 2015 alle 08:15:32.

   >[!NOTE]
   >
   >È possibile utilizzare la funzione **[!UICONTROL formatDate]** in questo campo per specificare il nome del file.

1. Se lo desideri, puoi comprimere il file di output selezionando **[!UICONTROL Compression]** nel campo **[!UICONTROL Add a post-processing stage]**. Il file di output viene compresso in un file GZIP (.gz).

   Il campo **[!UICONTROL Add a post-processing stage]** consente inoltre di crittografare un file prima di estrarlo. Per ulteriori informazioni su come utilizzare i file crittografati, consulta [questa sezione](../../automating/using/managing-encrypted-data.md)

1. Fare clic sul pulsante **[!UICONTROL Create element]** per aggiungere una colonna di output.

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

   ![](assets/extract-file-file-structure.png)

   >[!NOTE]
   >
   >Se desideri estrarre i dati in un file CSV con una codifica specifica, seleziona innanzitutto il formato di output &quot;Testo&quot;. Scegli la codifica desiderata dall’elenco a discesa, quindi modifica il formato di output in &quot;CSV (Excel)&quot;.

1. Nella scheda **[!UICONTROL Properties]**, seleziona l’opzione **[!UICONTROL Do not generate a file if the inbound transition is empty]** per evitare di creare e caricare file vuoti sui server SFTP se la transizione in entrata è vuota.
1. Conferma la configurazione dell’attività e salva il flusso di lavoro.
