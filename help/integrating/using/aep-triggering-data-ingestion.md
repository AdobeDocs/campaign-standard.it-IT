---
solution: Campaign Standard
product: campaign
title: Attivazione dell’acquisizione dati tramite API
description: Scopri come attivare l’acquisizione dei dati tramite API.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Integrazione con Microsoft CRM
role: Architetto dati
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '470'
ht-degree: 5%

---


# Attivazione dell’acquisizione dati tramite API {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector è attualmente in versione beta, che potrebbe essere soggetta a frequenti aggiornamenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Per accedere, contatta l’Assistenza clienti di Adobe.

Adobe Campaign Standard ti consente di attivare l’acquisizione immediata delle mappature dati tramite API e di recuperare lo stato delle richieste di acquisizione.

Questa pagina descrive come attivare e recuperare lo stato di acquisizione delle mappature dati. Per informazioni globali sulle API di Campaign Standard, consulta [questa sezione](../../api/using/get-started-apis.md).

## Prerequisiti {#prerequisites}

Prima di utilizzare le API , la mappatura dei dati deve essere stata configurata e pubblicata nell’interfaccia di Campaign Standard. Per ulteriori informazioni, consulta queste sezioni:

* [Definizione mappature](../../integrating/using/aep-mapping-definition.md)
* [Attivazione mappature](../../integrating/using/aep-mapping-activation.md)

Una volta creata la mappatura dei dati, devi impedirne l’esecuzione in modo da poterla attivare dalle API ogni volta che lo desideri. Per farlo, esegui questi passaggi:

1. In Campaign Standard, vai al menu **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** .

1. Fai doppio clic sulla mappatura dati per aprirla, quindi fai clic sul pulsante **[!UICONTROL Stop]** .

   ![](assets/aep_datamapping_stop.png)

1. Salva le modifiche

L’esecuzione della mappatura dati viene ora interrotta. È possibile utilizzare le API di Campaign Standard per attivarle manualmente.

## Avvio dell&#39;acquisizione immediata della mappatura dei dati {#starting-immediate-ingestion}

L’acquisizione immediata di una mappatura XDM in Adobe Experience Platform viene attivata con un’operazione POST:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Per eseguire l’acquisizione della chiamata API POST, l’utente deve disporre di un ruolo **Esecuzione funzione SQL**, che può essere fornito da un amministratore Campaign Standard eseguendo il seguente script JS:
>
>
```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```

L&#39;operazione POST restituisce informazioni sullo stato della richiesta creata:

* Richiesta inviata correttamente per la mappatura XDM:

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* Richiesta già in corso per la mappatura XDM:

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* Richiesta non riuscita perché la mappatura XDM non è pubblicata o viene arrestata:

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

Lo stato di una richiesta di acquisizione può essere recuperato con un’operazione GET e l’ID di richiesta desiderato nei parametri:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>Informazioni dettagliate sullo stato della richiesta di mappatura XDM e i relativi processi sono disponibili nell’interfaccia di Campaign Standard, nel menu **[!UICONTROL Status of data export to platform]** (consulta [Attivazione mappatura](../../integrating/using/aep-mapping-activation.md)).

L&#39;operazione di GET restituisce le informazioni seguenti:

* **batchId**: questo campo viene compilato solo se si è verificato un errore dopo la preparazione e il caricamento del batch,
* **info**: ID mappatura XDM,
* **numRecords**: il numero di record acquisiti (solo stato di successo),
* **stato**: stato della richiesta di acquisizione (riuscito/fallito/in corso)

Le possibili risposte all&#39;operazione di GET sono:

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

* Richiesta di acquisizione interrotta dopo l’acquisizione di alcuni record (questo può accadere in scenari di arresto anomalo):

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* Inserire la richiesta in corso (quando la richiesta ha caricato i dati in un batch o quando il batch si prepara per la richiesta):

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
