---
title: Esportazione di profili in un file esterno
description: Questo caso d’uso mostra come esportare un elenco di profili sotto forma di un file esterno in modo che i dati possano essere utilizzati al di fuori di Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3fc286a9-bba4-4e3d-95cd-600eed4943e7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 68%

---

# Esportazione di profili in un file esterno {#exporting-profiles-external-file}

L’esempio seguente illustra come configurare un’attività **[!UICONTROL Extract file]** dopo un’attività **[!UICONTROL Query]**.

Lo scopo di questo flusso di lavoro è esportare un elenco di profili sotto forma di un file esterno per poter utilizzare i dati al di fuori di Adobe Campaign.

1. Trascina e rilascia una [Extract file](../../automating/using/extract-file.md) attività nel flusso di lavoro e inseriscila dopo [Query](../../automating/using/query.md) attività.

   In questo esempio, la query viene eseguita su tutti i profili di età compresa tra i 18 e i 30 anni.

1. Apri **[!UICONTROL Extract file]** per modificarlo.
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
1. Trascina una [Trasferisci file](../../automating/using/transfer-file.md) attività dopo il **[!UICONTROL Extract file]** per recuperare il file di estrazione su un account esterno.
1. Apri l’attività e scegli l’azione **[!UICONTROL File upload]**.

   ![](assets/wkf_data_export11.png)

1. Seleziona l’account esterno e immetti il percorso della cartella sul server.

   ![](assets/wkf_data_export12.png)

1. Conferma l’attività e salva il flusso di lavoro.
1. Avvia il flusso di lavoro.

   Quando il flusso di lavoro è stato eseguito correttamente, il file estratto è disponibile sull’account esterno.
