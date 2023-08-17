---
title: Attivazione dell’acquisizione dati tramite API
description: Scopri come attivare l’acquisizione dei dati tramite API.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 6%

---

# Attivazione dell’acquisizione dati tramite API {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector è attualmente in versione beta, che potrebbe essere soggetta a frequenti aggiornamenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Contatta l’Assistenza clienti di Adobe se desideri accedervi.

Adobe Campaign Standard ti consente di attivare l’acquisizione immediata delle mappature dati tramite API e di recuperare lo stato delle richieste di acquisizione.

Questa pagina descrive come attivare e recuperare lo stato di acquisizione delle mappature dati. Per informazioni globali sulle API di Campaign Standard, consulta [questa sezione](../../api/using/get-started-apis.md).

## Prerequisiti {#prerequisites}

Prima di utilizzare le API, la mappatura dei dati deve essere stata configurata e pubblicata nell’interfaccia di Campaign Standard. Per ulteriori informazioni, consulta queste sezioni:

* [Definizione mappature](../../integrating/using/aep-mapping-definition.md)
* [Attivazione delle mappature](../../integrating/using/aep-mapping-activation.md)

Una volta creata la mappatura dati, devi interromperne l’esecuzione in modo da poterla attivare dalle API in qualsiasi momento. Per farlo, segui questi passaggi:

1. In Campaign Standard, vai a **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** menu.

1. Fai doppio clic sulla mappatura dei dati per aprirla, quindi fai clic sul pulsante **[!UICONTROL Stop]** pulsante.

   ![](assets/aep_datamapping_stop.png)

1. Salva le modifiche

L’esecuzione della mappatura dei dati è ora interrotta. Puoi utilizzare le API di Campaign Standard per attivarlo manualmente.

## Avvio dell’acquisizione immediata della mappatura dei dati {#starting-immediate-ingestion}

L’acquisizione immediata di una mappatura XDM in Adobe Experience Platform viene attivata con un’operazione POST:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Per eseguire la chiamata API di ingest POST, l’utente deve disporre di un’ **Esecuzione funzione SQL** ruolo, che può essere fornito da un amministratore Campaign Standard eseguendo il comando seguente JS Script:
>
>```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```
>

L’operazione POST restituisce informazioni relative allo stato della richiesta creata:

* Richiesta inviata correttamente per il mapping XDM:

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* Richiesta già in corso per il mapping XDM:

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* Richiesta non riuscita perché il mapping XDM non è pubblicato o è interrotto:

```
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not stopped",
"status": "Failed"
}
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not published",
"status": "Failed"
}
```

## Recupero dello stato di una richiesta di acquisizione {#retrieving-status}

Lo stato di una richiesta di acquisizione può essere recuperato con un’operazione di GET e l’ID richiesta desiderato nei parametri:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>Informazioni dettagliate sullo stato della richiesta di mappatura XDM e dei relativi processi sono disponibili nell’interfaccia di Campaign Standard, nel **[!UICONTROL Status of data export to platform]** menu (vedere [Attivazione mappatura](../../integrating/using/aep-mapping-activation.md)).

L&#39;operazione di GET restituisce le informazioni seguenti:

* **batchId**: questo campo viene compilato solo se si è verificato un errore dopo la preparazione e il caricamento del batch,
* **info**: ID mappatura XDM,
* **numRecord**: numero di record che sono stati acquisiti (solo stato di successo),
* **stato**: stato della richiesta di acquisizione (riuscita/non riuscita/in corso)

Le possibili risposte all’operazione di GET sono:

* Richiesta di acquisizione riuscita:

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. ",
  "numRecords": 15,
  "requestId": 3520,
  "status": "Success"
  }
  ```

* Richiesta di acquisizione non riuscita con 0 record acquisito:

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
  "numRecords": 0,
  "requestId": 3520,
  "status": "Failed"
  }
  ```

* Richiesta di acquisizione non riuscita, con alcuni record caricati in un batch:

  ```
  {
  "batchId": "<value>",
  "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
  "numRecords": 0,
  "requestId": <value>,
  "status": "Failed"
  }
  ```

* Richiesta di acquisizione interrotta dopo l’acquisizione di alcuni record (ciò può verificarsi in scenari di arresto anomalo):

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
  "numRecords": 0,
  "requestId": <value>,
  "status": "Aborted"
  }
  ```

* Acquisizione richiesta in corso (quando la richiesta ha caricato i dati in un batch o quando il batch viene preparato per la richiesta):

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>.",
  "numRecords": 0,
  "requestId": <value>,
  "status": "In Progress"
  }
  ```
