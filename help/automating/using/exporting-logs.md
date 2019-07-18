---
title: Esportazione dei registri
seo-title: Esportazione dei registri
description: Esportazione dei registri
seo-description: I dati del registro, relativi alle consegne o alle iscrizioni, possono essere esportati mediante un semplice flusso di lavoro.
page-status-flag: never-activated
uuid: 954 e 919 c -0 a 33-47 c 3-9 a 3 c -63 c 7 a 2 a 4 edc 4
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: import-and-exporting-data
discoiquuid: ca 8 a 95 d 8-523 f -4085-a 2 fc-e 1 d 8262 cfbae
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Exporting logs{#exporting-logs}

I dati del registro, relativi alle consegne o alle iscrizioni, possono essere esportati mediante un semplice flusso di lavoro. Consente di analizzare i risultati delle campagne mediante il reporting o lo strumento BI.

By using an **[!UICONTROL Incremental query]** that only retrieves new logs every time the workflow is executed and a simple **[!UICONTROL Extract file]** activity to define the output columns, you can get a file with the format and all the data you need. Then use a **[!UICONTROL Transfer file]** activity to retrieve the final file. Each workflow execution is planned by a **[!UICONTROL Scheduler]**.

L'operazione di registro di esportazione può essere eseguita da utenti standard. Private resources such as: broadlogs, tracking logs, exclusion logs subscription logs and subscription history logs on **Profiles** can only be managed by functional administrator.

1. Create a new workflow as detailed in [this section](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Add a **[!UICONTROL Scheduler]** activity and set it according to your needs. Di seguito è riportato un esempio di esecuzione mensile.

   ![](assets/export_logs_scheduler.png)

1. Add an **[!UICONTROL Incremental query]** activity and configure it so that it selects the logs you need. Ad esempio, per selezionare tutti i registri iniziali nuovi o aggiornati (registri di distribuzione profili):

   * In the **[!UICONTROL Properties]** tab, change the target resource to **Delivery logs** (broadLogRcp).

      ![](assets/export_logs_query_properties.png)

   * In the **[!UICONTROL Target]** tab, set a condition to retrieve all delivery logs that correspond to deliveries sent in 2016 or after. For more information, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

      ![](assets/export_logs_query_target.png)

   * In the **[!UICONTROL Processed data]** tab, select **[!UICONTROL Use a date field]** and choose the **lastModified** field. Nelle successive esecuzioni del flusso di lavoro, sono disponibili solo i registri che saranno stati modificati o creati dopo l'ultima esecuzione.

      ![](assets/export_logs_query_processeddata.png)

      Dopo la prima esecuzione del flusso di lavoro, puoi vedere in questa scheda l'ultima data di esecuzione che verrà utilizzata per l'esecuzione successiva. Viene aggiornato automaticamente ogni volta che il flusso di lavoro viene eseguito. È comunque possibile ignorare questo valore immettendo manualmente un nuovo elemento in modo da adattarlo alle proprie esigenze.

1. Add an **[!UICONTROL Extract file]** activity that will export the queried data in a file:

   * In the **[!UICONTROL Extraction]** tab, specify the name of the file. Questo nome verrà completato automaticamente con la data dell'esportazione per verificare che tutti i file estratti siano univoci.

      Selezionate le colonne da esportare nel file. Potete selezionare qui i dati provenienti da risorse correlate, ad esempio consegna o informazioni sul profilo. Per organizzare il file finale, potete applicare un ordinamento. Ad esempio nella data di registro, come mostrato nell'esempio di seguito.

      ![](assets/export_logs_extractfile_extraction.png)

      >[!NOTE]
      >
      >Non è possibile esportare identificatori univoci (chiavi principali) delle risorse di registro.

   * In the **[!UICONTROL File structure]** tab, define the format of the output file to match your needs.

      Check the **[!UICONTROL Export labels instead of internal values of enumerations]** option in case you export enumeration values. Questa opzione consente di ottenere etichette più brevi facili da comprendere invece di ID.

1. Add a **[!UICONTROL Transfer file]** activity and configure it to transfer the newly created file from the Adobe Campaign server to another location where you can access it, such as a SFTP server.

   * In the **[!UICONTROL General]** tab, select **[!UICONTROL File upload]** as the purpose is to send the file from Adobe Campaign to another server.
   * In the **[!UICONTROL Protocol]** tab, specify the transfer parameters and select the [external account](../../administration/using/external-accounts.md#creating-an-external-account) to use.

1. Add an **[!UICONTROL End]** activity to make sure it properly ends and save your workflow.

   ![](assets/export_logs_example_workflow.png)

Ora potete eseguire il flusso di lavoro e recuperare il file di output sul server esterno.

**Argomento correlato:**

[Flussi di lavoro](../../automating/using/discovering-workflows.md)
