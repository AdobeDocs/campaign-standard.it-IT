---
title: Aggiornamento dei dati in base a un download automatico del file
description: 'L''esempio seguente mostra il risultato di un''attività del file di caricamento scaricata automaticamente tramite un''attività del file di trasferimento, seguita da un''attività di aggiornamento dei dati. '
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---


# Aggiornamento dei dati in base a un download automatico del file {#updating-data-automatic-file-download}

L&#39;attività del file di caricamento struttura principalmente i dati provenienti da un&#39;attività del file di trasferimento al fine di integrarlo nei dati esistenti.

L&#39;esempio seguente mostra il risultato di un&#39;attività del file di caricamento scaricata automaticamente tramite un&#39;attività del file di trasferimento, seguita da un&#39;attività di aggiornamento dei dati. Questo flusso di lavoro mira ad arricchire il database del Adobe Campaign  con nuovi profili o ad aggiornare i profili esistenti utilizzando i dati recuperati dal file importato.

![](assets/load_file_workflow_ex1.png)

Per generare il flusso di lavoro, effettuate le seguenti operazioni:

1. Trascina e rilascia un’attività [Trasferisci file](../../automating/using/transfer-file.md) nel flusso di lavoro.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Configurate l&#39;attività in modo che recuperi il file desiderato. Nella **[!UICONTROL Protocol]** scheda, selezionate **SFTP**.
1. Selezionate i parametri di connessione **Usa definiti in un&#39;opzione di account** esterno.
1. Immettete il nome dell’account esterno.
1. Immettere il percorso del **file sul server** remoto.

   ![](assets/wkf_file_transfer_07.png)

1. Confermate l&#39;attività.
1. Trascinate e rilasciate un’attività [Carica file](../../automating/using/load-file.md) nel flusso di lavoro e inseritela dopo l’ **[!UICONTROL Transfer file]** attività.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Nella **[!UICONTROL File to load]** sezione della **[!UICONTROL Execution]** scheda, selezionare l&#39; **[!UICONTROL Use the file specified in the inbound transition]** opzione.

   ![](assets/wkf_file_loading8.png)

1. Configurate l&#39;attività come specificato in precedenza.
1. Trascinate e rilasciate un&#39;attività [Aggiorna dati](../../automating/using/update-data.md) **[!UICONTROL Load file]** nel flusso di lavoro e inseritela dopo l&#39;attività, quindi configuratela.

Una volta avviato il flusso di lavoro, i dati del file caricato vengono estratti e quindi utilizzati per arricchire il database del Adobe Campaign .
