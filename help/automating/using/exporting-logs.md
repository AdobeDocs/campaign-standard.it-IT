---
title: Esportazione dei registri
description: I dati di registro, relativi alle consegne o alle iscrizioni, possono essere esportati tramite un semplice flusso di lavoro.
page-status-flag: never-activated
uuid: 954e919c-0a33-47c3-9a3c-63c7a2a4edc4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: ca8a95d8-523f-4085-a2fc-e1d8262cfbae
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 14%

---


# Esportazione dei registri{#exporting-logs}

I dati di registro, relativi alle consegne o alle iscrizioni, possono essere esportati tramite un semplice flusso di lavoro. Consente di analizzare i risultati delle campagne con il proprio strumento di reporting o BI.

>[!CAUTION]
>
>Solo [gli amministratori](../../administration/using/users-management.md#functional-administrators)funzionali, con **[!UICONTROL Administration]** ruolo e accesso a **Tutte** le unità, possono accedere ai registri di invio, ai log dei messaggi, ai registri di monitoraggio, ai registri di esclusione o ai registri di iscrizione. Un utente non amministratore può eseguire il targeting di questi registri ma iniziare da una tabella collegata (profili, consegna).

Utilizzando un file **[!UICONTROL Incremental query]** che recupera nuovi registri solo ogni volta che il flusso di lavoro viene eseguito e una semplice **[!UICONTROL Extract file]** attività per definire le colonne di output, potete ottenere un file con il formato e tutti i dati necessari. Quindi utilizzate un&#39; **[!UICONTROL Transfer file]** attività per recuperare il file finale. Ogni esecuzione del flusso di lavoro è pianificata da un **[!UICONTROL Scheduler]**.

L’operazione dei registri di esportazione può essere eseguita dagli utenti standard. Risorse private come: i registri di trasmissione, i registri di monitoraggio, i registri di esclusione dei registri di iscrizione e i registri della cronologia di iscrizione nei **profili** possono essere gestiti solo dall&#39;amministratore funzionale.

1. Create un nuovo flusso di lavoro come descritto in [questa sezione](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Aggiungete un&#39; **[!UICONTROL Scheduler]** attività e impostatela in base alle vostre esigenze. Di seguito è riportato un esempio di esecuzione mensile.

   ![](assets/export_logs_scheduler.png)

1. Aggiungete un&#39; **[!UICONTROL Incremental query]** attività e configuratela in modo da selezionare i registri necessari. Ad esempio, per selezionare tutti i log di trasmissione nuovi o aggiornati (log di distribuzione dei profili):

   * Nella **[!UICONTROL Properties]** scheda, imposta la risorsa di destinazione sui registri **di** consegna (wideLogRcp).

      ![](assets/export_logs_query_properties.png)

   * Nella **[!UICONTROL Target]** scheda, imposta una condizione per recuperare tutti i registri di consegna corrispondenti alle consegne inviate nel 2016 o successivamente. For more information, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

      ![](assets/export_logs_query_target.png)

   * Nella **[!UICONTROL Processed data]** scheda, selezionare **[!UICONTROL Use a date field]** e scegliere il campo **lastModified** . Nelle esecuzioni successive del flusso di lavoro, verranno recuperati solo i registri che saranno stati modificati o creati dopo l&#39;ultima esecuzione.

      ![](assets/export_logs_query_processeddata.png)

      Dopo la prima esecuzione del flusso di lavoro, in questa scheda puoi vedere l’ultima data di esecuzione che verrà utilizzata per l’esecuzione successiva. Viene aggiornata automaticamente ogni volta che il flusso di lavoro viene eseguito. Puoi comunque ignorare questo valore immettendone manualmente uno nuovo in modo tale che sia adatto alle tue esigenze.

1. Aggiungete un&#39; **[!UICONTROL Extract file]** attività che esporterà i dati interrogati in un file:

   * Nella **[!UICONTROL Extraction]** scheda, specificate il nome del file.

      Se selezionate l’ **[!UICONTROL Add date and time to the file name]** opzione, questo nome verrà completato automaticamente con la data dell’esportazione per garantire che tutti i file estratti siano univoci. Selezionate le colonne da esportare nel file. È possibile selezionare qui i dati provenienti da risorse correlate, ad esempio le informazioni sulla consegna o sul profilo.

      >[!NOTE]
      >
      >Per esportare un identificatore univoco per ciascun registro, selezionate l’ **[!UICONTROL Delivery log ID]** elemento.

      Per organizzare il file finale, potete applicare un ordinamento. Ad esempio nella data del registro, come illustrato nell’esempio seguente.

      ![](assets/export_logs_extractfile_extraction.png)

   * Nella **[!UICONTROL File structure]** scheda, definire il formato del file di output in base alle esigenze.

      Seleziona l’opzione **[!UICONTROL Export labels instead of internal values of enumerations]** nel caso dell’esportazione di valori di enumerazione. Questa opzione ti consente di recuperare etichette più brevi che sono più facili da comprendere rispetto agli ID.

1. Aggiungete un&#39; **[!UICONTROL Transfer file]** attività e configuratela per trasferire il file appena creato dal server Adobe Campaign  a un&#39;altra posizione in cui potete accedervi, ad esempio un server SFTP.

   * Nella **[!UICONTROL General]** scheda, selezionare **[!UICONTROL File upload]** come scopo l&#39;invio del file da  Adobe Campaign a un altro server.
   * Nella **[!UICONTROL Protocol]** scheda, specificate i parametri di trasferimento e selezionate l&#39;account [](../../administration/using/external-accounts.md#creating-an-external-account) esterno da utilizzare.

1. Aggiungete un&#39; **[!UICONTROL End]** attività per assicurarvi che termini correttamente e salvate il flusso di lavoro.

   ![](assets/export_logs_example_workflow.png)

Ora potete eseguire il flusso di lavoro e recuperare il file di output sul server esterno.

**Argomento correlato:**

[Flussi di lavoro](../../automating/using/get-started-workflows.md)
