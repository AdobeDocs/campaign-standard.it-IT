---
solution: Campaign Standard
product: campaign
title: Esportazione dei registri
description: I dati di registro, siano essi relativi a consegne o abbonamenti, possono essere esportati tramite un semplice flusso di lavoro.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Flussi di lavoro
role: Architetto dati
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 14%

---


# Esportazione dei registri{#exporting-logs}

I dati di registro, siano essi relativi a consegne o abbonamenti, possono essere esportati tramite un semplice flusso di lavoro. Consente di analizzare i risultati delle campagne nel proprio strumento di reporting o BI.

>[!CAUTION]
>
>Solo gli amministratori [funzionali](../../administration/using/users-management.md#functional-administrators) con il ruolo **[!UICONTROL Administration]** e l&#39;accesso alle unità **All** possono accedere ai registri di invio, ai registri dei messaggi, ai registri di tracciamento, ai registri di esclusione o di abbonamento. Un utente non amministratore può eseguire il targeting di questi registri ma partendo da una tabella collegata (profili, consegna).

Utilizzando un **[!UICONTROL Incremental query]** che recupera i nuovi registri solo ogni volta che il flusso di lavoro viene eseguito e una semplice attività **[!UICONTROL Extract file]** per definire le colonne di output, puoi ottenere un file con il formato e tutti i dati necessari. Quindi utilizza un’attività **[!UICONTROL Transfer file]** per recuperare il file finale. Ogni esecuzione del flusso di lavoro è pianificata da un **[!UICONTROL Scheduler]**.

L’operazione dei registri di esportazione può essere eseguita da utenti standard. Risorse private quali: i registri di trasmissione, i registri di tracciamento, i registri di esclusione e i registri della cronologia di abbonamento su **Profiles** possono essere gestiti solo dall&#39;amministratore funzionale.

1. Crea un nuovo flusso di lavoro come descritto in [questa sezione](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Aggiungi un’attività **[!UICONTROL Scheduler]** e impostala in base alle tue esigenze. Di seguito è riportato un esempio di esecuzione mensile.

   ![](assets/export_logs_scheduler.png)

1. Aggiungi un’attività **[!UICONTROL Incremental query]** e configurala in modo da selezionare i registri necessari. Ad esempio, per selezionare tutti i registri di trasmissione nuovi o aggiornati (registri di consegna profilo):

   * Nella scheda **[!UICONTROL Properties]** , modifica la risorsa di destinazione in **Log di consegna** (wideLogRcp).

      ![](assets/export_logs_query_properties.png)

   * Nella scheda **[!UICONTROL Target]** , imposta una condizione per recuperare tutti i registri di consegna corrispondenti alle consegne inviate nel 2016 o versioni successive. Per ulteriori informazioni, consulta la sezione [Modifica delle query](../../automating/using/editing-queries.md#creating-queries) .

      ![](assets/export_logs_query_target.png)

   * Nella scheda **[!UICONTROL Processed data]** , seleziona **[!UICONTROL Use a date field]** e scegli il campo **lastModified** . Nelle esecuzioni successive del flusso di lavoro, verranno recuperati solo i registri che saranno stati modificati o creati dopo l’ultima esecuzione.

      ![](assets/export_logs_query_processeddata.png)

      Dopo la prima esecuzione del flusso di lavoro, in questa scheda puoi vedere l’ultima data di esecuzione che verrà utilizzata per l’esecuzione successiva. Viene aggiornata automaticamente ogni volta che il flusso di lavoro viene eseguito. Puoi comunque ignorare questo valore immettendone manualmente uno nuovo in modo tale che sia adatto alle tue esigenze.

1. Aggiungi un’attività **[!UICONTROL Extract file]** che esporta i dati interrogati in un file:

   * Nella scheda **[!UICONTROL Extraction]** , specifica il nome del file.

      Se selezioni l’opzione **[!UICONTROL Add date and time to the file name]** , questo nome verrà completato automaticamente con la data dell’esportazione per garantire che tutti i file estratti siano univoci. Selezionare le colonne da esportare nel file. Puoi selezionare qui i dati provenienti da risorse correlate, ad esempio informazioni sulla consegna o sul profilo.

      >[!NOTE]
      >
      >Per esportare un identificatore univoco per ciascun registro, seleziona l’elemento **[!UICONTROL Delivery log ID]** .

      Per organizzare il file finale, puoi applicare un ordinamento. Ad esempio sulla data del registro, come illustrato nell’esempio seguente.

      ![](assets/export_logs_extractfile_extraction.png)

   * Nella scheda **[!UICONTROL File structure]** , definisci il formato del file di output in base alle tue esigenze.

      Seleziona l’opzione **[!UICONTROL Export labels instead of internal values of enumerations]** nel caso dell’esportazione di valori di enumerazione. Questa opzione ti consente di recuperare etichette più brevi che sono più facili da comprendere rispetto agli ID.

1. Aggiungi un’attività **[!UICONTROL Transfer file]** e configurala per trasferire il file appena creato dal server Adobe Campaign a un’altra posizione in cui puoi accedervi, ad esempio un server SFTP.

   * Nella scheda **[!UICONTROL General]** , seleziona **[!UICONTROL File upload]** in quanto lo scopo è quello di inviare il file da Adobe Campaign a un altro server.
   * Nella scheda **[!UICONTROL Protocol]** , specifica i parametri di trasferimento e seleziona l’ [account esterno](../../administration/using/external-accounts.md#creating-an-external-account) da utilizzare.

1. Aggiungi un’attività **[!UICONTROL End]** per assicurarti che termini correttamente e salva il flusso di lavoro.

   ![](assets/export_logs_example_workflow.png)

Ora puoi eseguire il flusso di lavoro e recuperare il file di output sul server esterno.

**Argomento correlato:**

[Flussi di lavoro](../../automating/using/get-started-workflows.md)
