---
title: Aggiornamento dei dati in base a un download automatico del file
description: L’esempio seguente mostra il risultato di un’attività di caricamento file scaricata automaticamente tramite un’attività di trasferimento file, seguita da un’attività di aggiornamento dei dati.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 2b21cf45-1c40-4e0e-ae2c-28c9f73e1964
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 79%

---

# Aggiornamento dei dati in base a un download automatico del file {#updating-data-automatic-file-download}

L’attività di caricamento file struttura principalmente i dati provenienti da un’attività del file di trasferimento, in modo da integrarli nei dati esistenti.

L’esempio seguente mostra il risultato di un’attività di caricamento file scaricata automaticamente tramite un’attività di trasferimento file, seguita da un’attività di aggiornamento dei dati. Questo flusso di lavoro mira ad arricchire il database di Adobe Campaign con nuovi profili o ad aggiornare quelli esistenti utilizzando i dati recuperati dal file importato.

![](assets/load_file_workflow_ex1.png)

Per creare il flusso di lavoro, effettua le seguenti operazioni:

1. Trascina e rilascia l’attività [Transfer file](../../automating/using/transfer-file.md) nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Configura l’attività in modo che recuperi il file desiderato. Nella scheda **[!UICONTROL Protocol]**, seleziona **SFTP**.
1. Seleziona l’opzione **Use connection parameters defined in an external account**.
1. Immetti il nome dell’account esterno.
1. Immetti il **percorso del file sul server remoto**.

   ![](assets/wkf_file_transfer_07.png)

1. Conferma l’attività.
1. Trascina una [Carica file](../../automating/using/load-file.md) attività nel flusso di lavoro e inseriscila dopo **[!UICONTROL Transfer file]** attività.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Nella sezione **[!UICONTROL File to load]** della scheda **[!UICONTROL Execution]**, seleziona l’opzione **[!UICONTROL Use the file specified in the inbound transition]**.

   ![](assets/wkf_file_loading8.png)

1. Configura l’attività come specificato in precedenza.
1. Trascina e rilascia una [Aggiorna dati](../../automating/using/update-data.md) attività nel flusso di lavoro e inseriscila dopo **[!UICONTROL Load file]** attività, quindi configurala.

Una volta avviato il flusso di lavoro, i dati del file caricato vengono estratti e quindi utilizzati per arricchire il database di Adobe Campaign.
