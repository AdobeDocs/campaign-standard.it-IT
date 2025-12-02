---
title: Attivazione dell’acquisizione dati tramite API
description: Scopri come attivare l’acquisizione dei dati tramite API.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 6%

---

# Attivazione dell’acquisizione dati tramite API {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector è attualmente in versione beta, che potrebbe essere soggetta a frequenti aggiornamenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Per accedere, contatta l’Assistenza clienti di Adobe.

Adobe Campaign Standard ti consente di attivare l’acquisizione immediata delle mappature dati tramite API e di recuperare lo stato delle richieste di acquisizione.

Questa pagina descrive come attivare e recuperare lo stato di acquisizione delle mappature dati. Per informazioni globali sulle API di Campaign Standard, consulta [questa sezione](../../api/using/get-started-apis.md).

## Prerequisiti {#prerequisites}

Prima di utilizzare le API, la mappatura dei dati deve essere stata configurata e pubblicata nell’interfaccia di Campaign Standard. Per ulteriori informazioni, consulta queste sezioni:

* [Definizione mappature](../../integrating/using/aep-mapping-definition.md)
* [Attivazione delle mappature](../../integrating/using/aep-mapping-activation.md)

Una volta creata la mappatura dati, devi interromperne l’esecuzione in modo da poterla attivare dalle API in qualsiasi momento. Per farlo, segui questi passaggi:

1. In Campaign Standard, vai al menu **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]**.

1. Fare doppio clic sul mapping dei dati per aprirlo, quindi fare clic sul pulsante **[!UICONTROL Stop]**.

   ![](assets/aep_datamapping_stop.png)

1. Salva le modifiche

L’esecuzione della mappatura dei dati è ora interrotta. Puoi utilizzare le API di Campaign Standard per attivarlo manualmente.

## Avvio dell’acquisizione immediata della mappatura dei dati {#starting-immediate-ingestion}

L’acquisizione immediata di una mappatura XDM in Adobe Experience Platform viene attivata con un’operazione POST:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Per eseguire la chiamata API di acquisizione POST, l&#39;utente deve avere un ruolo **Esecuzione funzione SQL**, che può essere fornito da un amministratore di Campaign Standard eseguendo lo script JS seguente:
>
>```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```
>

L&#39;operazione POST restituisce informazioni relative allo stato della richiesta creata:

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

Lo stato di una richiesta di acquisizione può essere recuperato con un’operazione GET e l’ID richiesta desiderato nei parametri:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>Informazioni dettagliate sullo stato della richiesta di mappatura XDM e dei relativi processi sono disponibili nell&#39;interfaccia di Campaign Standard, nel menu **[!UICONTROL Status of data export to platform]** (vedi [Attivazione mappatura](../../integrating/using/aep-mapping-activation.md)).

L’operazione GET restituisce le informazioni seguenti:

* **batchId**: questo campo viene popolato solo se si è verificato un errore dopo la preparazione e il caricamento del batch,
* **info**: ID mappatura XDM,
* **numRecords**: il numero di record che sono stati acquisiti (solo stato di completamento),
* **stato**: stato della richiesta di acquisizione (riuscita/non riuscita/in corso)

Le possibili risposte all’operazione GET sono:

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
