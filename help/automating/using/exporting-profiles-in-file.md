---
solution: Campaign Standard
product: campaign
title: Esportazione di profili in un file esterno
description: Questo caso d’uso mostra come esportare un elenco di profili sotto forma di file esterno in modo che i dati possano essere utilizzati al di fuori  Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 68%

---


# Esportazione di profili in un file esterno {#exporting-profiles-external-file}

L’esempio seguente illustra come configurare un’attività **[!UICONTROL Extract file]** dopo un’attività **[!UICONTROL Query]**.

Lo scopo di questo flusso di lavoro è esportare un elenco di profili sotto forma di un file esterno per poter utilizzare i dati al di fuori di Adobe Campaign.

1. Drag and drop an [Extract file](../../automating/using/extract-file.md) activity into your workflow and place it after the [Query](../../automating/using/query.md) activity.

   In questo esempio, la query viene eseguita su tutti i profili di età compresa tra i 18 e i 30 anni.

1. Open the **[!UICONTROL Extract file]** activity to edit it.
1. Denomina il file di output.
1. Aggiungi colonne di output.

   In questo esempio, e-mail, età, data di nascita, nome e cognome dei profili vengono aggiunti come colonne di output.

   ![](assets/wkf_data_export6.png)

1. Fai clic sulla scheda **[!UICONTROL File structure]** per definire:

   * Formato di output CSV

      ![](assets/wkf_data_export7.png)

   * Formato data

      ![](assets/wkf_data_export9.png)

1. Conferma l’attività.
1. Drag and drop a [Transfer file](../../automating/using/transfer-file.md) activity after the **[!UICONTROL Extract file]** activity to recover the extract file on an external account.
1. Apri l’attività e scegli l’azione **[!UICONTROL File upload]**.

   ![](assets/wkf_data_export11.png)

1. Seleziona l’account esterno e immetti il percorso della cartella sul server.

   ![](assets/wkf_data_export12.png)

1. Conferma l’attività e salva il flusso di lavoro.
1. Avvia il flusso di lavoro.

   Quando il flusso di lavoro è stato eseguito correttamente, il file estratto è disponibile sull’account esterno.
