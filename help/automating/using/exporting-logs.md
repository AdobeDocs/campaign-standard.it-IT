---
title: Esportazione dei registri
description: I dati di registro, siano essi relativi a consegne o abbonamenti, possono essere esportati tramite un semplice flusso di lavoro.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 14%

---

# Esportazione dei registri{#exporting-logs}

I dati di registro, siano essi relativi a consegne o abbonamenti, possono essere esportati tramite un semplice flusso di lavoro. Consente di analizzare i risultati delle campagne nel proprio strumento di reporting o BI.

>[!CAUTION]
>
>Solo funzionale [amministratori](../../administration/using/users-management.md#functional-administrators)con **[!UICONTROL Administration]** ruolo e accesso **Tutto** Le unità possono accedere ai registri di invio, ai registri dei messaggi, ai registri di tracciamento, ai registri di esclusione o di abbonamento. Un utente non amministratore può eseguire il targeting di questi registri ma partendo da una tabella collegata (profili, consegna).

Utilizzando un **[!UICONTROL Incremental query]** che recupera i nuovi registri solo ogni volta che il flusso di lavoro viene eseguito e un semplice **[!UICONTROL Extract file]** per definire le colonne di output, puoi ottenere un file con il formato e tutti i dati necessari. Quindi utilizza un **[!UICONTROL Transfer file]** per recuperare il file finale. Ogni esecuzione del flusso di lavoro è pianificata da un **[!UICONTROL Scheduler]**.

L’operazione dei registri di esportazione può essere eseguita da utenti standard. Risorse private quali: registri di trasmissione, registri di tracciamento, registri di esclusione e registri di abbonamento **Profili** può essere gestito solo da un amministratore funzionale.

1. Crea un nuovo flusso di lavoro come descritto in [questa sezione](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Aggiungi un **[!UICONTROL Scheduler]** e impostalo in base alle tue esigenze. Di seguito è riportato un esempio di esecuzione mensile.

   ![](assets/export_logs_scheduler.png)

1. Aggiungi un **[!UICONTROL Incremental query]** e configuralo in modo che selezioni i registri necessari. Ad esempio, per selezionare tutti i registri di trasmissione nuovi o aggiornati (registri di consegna profilo):

   * In **[!UICONTROL Properties]** scheda , modifica la risorsa target in **Log di consegna** (wideLogRcp).

      ![](assets/export_logs_query_properties.png)

   * In **[!UICONTROL Target]** imposta una condizione per recuperare tutti i registri di consegna corrispondenti alle consegne inviate nel 2016 o versioni successive. Per ulteriori informazioni, consulta la [Modifica delle query](../../automating/using/editing-queries.md#creating-queries) sezione .

      ![](assets/export_logs_query_target.png)

   * In **[!UICONTROL Processed data]** scheda , seleziona **[!UICONTROL Use a date field]** e scegli la **lastModified** campo . Nelle esecuzioni successive del flusso di lavoro, verranno recuperati solo i registri che saranno stati modificati o creati dopo l’ultima esecuzione.

      ![](assets/export_logs_query_processeddata.png)

      Dopo la prima esecuzione del flusso di lavoro, in questa scheda puoi vedere l’ultima data di esecuzione che verrà utilizzata per l’esecuzione successiva. Viene aggiornata automaticamente ogni volta che il flusso di lavoro viene eseguito. Puoi comunque ignorare questo valore immettendone manualmente uno nuovo in modo tale che sia adatto alle tue esigenze.

1. Aggiungi un **[!UICONTROL Extract file]** attività che esporta i dati interrogati in un file:

   * In **[!UICONTROL Extraction]** , specifica il nome del file.

      Se selezioni la **[!UICONTROL Add date and time to the file name]** Questo nome verrà completato automaticamente con la data dell’esportazione per garantire che tutti i file estratti siano univoci. Selezionare le colonne da esportare nel file. Puoi selezionare qui i dati provenienti da risorse correlate, ad esempio informazioni sulla consegna o sul profilo.

      >[!NOTE]
      >
      >Per esportare un identificatore univoco per ciascun registro, seleziona la **[!UICONTROL Delivery log ID]** elemento.

      Per organizzare il file finale, puoi applicare un ordinamento. Ad esempio sulla data del registro, come illustrato nell’esempio seguente.

      ![](assets/export_logs_extractfile_extraction.png)

   * In **[!UICONTROL File structure]** , definisci il formato del file di output in base alle tue esigenze.

      Seleziona l’opzione **[!UICONTROL Export labels instead of internal values of enumerations]** nel caso dell’esportazione di valori di enumerazione. Questa opzione ti consente di recuperare etichette più brevi che sono più facili da comprendere rispetto agli ID.

1. Aggiungi un **[!UICONTROL Transfer file]** e configuralo per trasferire il file appena creato dal server Adobe Campaign a un’altra posizione in cui puoi accedervi, ad esempio un server SFTP.

   * In **[!UICONTROL General]** scheda , seleziona **[!UICONTROL File upload]** poiché lo scopo è quello di inviare il file da Adobe Campaign a un altro server.
   * In **[!UICONTROL Protocol]** , specifica i parametri di trasferimento e seleziona la [account esterno](../../administration/using/external-accounts.md#creating-an-external-account) da utilizzare.

1. Aggiungi un **[!UICONTROL End]** per assicurarti che termini correttamente e salva il flusso di lavoro.

   ![](assets/export_logs_example_workflow.png)

Ora puoi eseguire il flusso di lavoro e recuperare il file di output sul server esterno.

**Argomento correlato:**

[Flussi di lavoro](../../automating/using/get-started-workflows.md)
