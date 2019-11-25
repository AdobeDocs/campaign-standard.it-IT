---
title: Gestione della privacy
description: Ulteriori informazioni sulla gestione della privacy con le API
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Gestione della privacy {#privacy-management}

Le API Campaign Standard forniscono funzionalità che consentono il processo automatico delle richieste relative alle normative sulla privacy come GDPR e CCPA.

Potete eseguire le seguenti operazioni:

* Crea una nuova richiesta di privacy,
* Monitorare una richiesta di privacy,
* Recuperare un file di dati sulla privacy,
* Gestire lo stato di rifiuto CCPA di un profilo.

L’endpoint API per la privacy è **/privacy/privacyTool**. La descrizione delle risorse di PrivacyTool e i relativi filtri sono disponibili nei metadati delle risorse. Consultate Meccanismo [](../../api/using/metadata-mechanism.md)metadati.

Il rifiuto CCPA viene gestito utilizzando l'attributo di profilo **ccpaOptOut** .

Per ulteriori informazioni su Adobe Campaign Standard e sulla conformità alla privacy, consulta la documentazione [](https://helpx.adobe.com/campaign/kb/acs-privacy.html)dedicata.

## Creazione di una richiesta di privacy {#creating-a-privacy-request}

>[!CAUTION]
>
>L'integrazione del servizio [di base per la](https://adobe.io/apis/cloudplatform/gdpr.html) privacy è il metodo da utilizzare per tutte le richieste di accesso ed eliminazione. A partire dalla versione 19.4, l'utilizzo dell'API Campaign e dell'interfaccia per le richieste di accesso ed eliminazione è diventato obsoleto. Per ulteriori informazioni sulle funzioni obsolete e rimosse di Campaign Standard, consulta [questa pagina](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

Le richieste di privacy vengono create utilizzando una richiesta **POST** .

Prima di creare le richieste, è necessario definire lo spazio nomi che verrà utilizzato. Per ulteriori informazioni, consulta la documentazione [sulla gestione della](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)privacy.

Il payload deve contenere i seguenti parametri:

* **name**: un nome interno univoco
* **namespace**: il nome dello spazio dei nomi configurato nell'interfaccia di Campaign Standard
* **riconciliazioneValue**: il valore di riconciliazione basato sulla chiave di riconciliazione definita nello spazio dei nomi
* **label**: l’etichetta della richiesta
* **type**: il tipo di richiesta. I valori accettati sono "access" o "delete".
* **regolamento**: il tipo di regolazione. Esempio: "GDPR", "CCPA". Questo parametro è obbligatorio e disponibile a partire dalla release Campaign Standard 19.4. Se siete su una build precedente, non è necessario aggiungerla al payload.

<br/>

***Richiesta di esempio***

Questa richiesta POST crea una richiesta di privacy basata su una chiave di riconciliazione e-mail definita nello spazio dei nomi AMCDS2:

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"delete"
}
```

Risposta alla richiesta POST.

```
{
    "PKey": "<PKEY>",
    "audit": "",
    "created": "2018-03-21 10:41:58.570Z",
    "desc": "",
    "gdprRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/head/privacyTool/<PKEY>/gdprRequestData/"
    },
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
    "label": "Delete customers",
    "lastModified": "2018-03-21 10:41:58.570Z",
    "name": "PT11832",
    "namespace": {
        "PKey": "<PKEY>",
        "title": "Doc (AMCDS2)"
    },
    "namespaceName": "AMCDS2",
    "reconciliationValue": "customers@adobe.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "new",
    "title": "Delete customers (PT11832)",
    "type": "delete"
}
```

## Monitoraggio di una richiesta di privacy

Puoi monitorare le informazioni su una richiesta di privacy creata utilizzando una richiesta **GET** .

La descrizione dell'elenco di stato è disponibile nella documentazione [sulla gestione della](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)privacy.

<br/>

***Richiesta di esempio***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>'
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

Risposta alla richiesta GET.

```
{
            "PKey": "<PKEY>",
            "audit": "",
            "created": "2018-03-09 12:28:37.319Z",
            "desc": "",
            "gdprRequestData": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/gdprRequestData/"
            },
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>",
            "label": "Delete customer profile",
            "lastModified": "2018-03-09 12:39:21.232Z",
            "name": "GDPR6",
            "namespace": {
                "PKey": "<PKEY>",
                "title": "Email (defaultNamespace1)"
            },
            "namespaceName": "defaultNamespace1",
            "reconciliationValue": "customers@adobe.com",
            "regulation": "gdpr",
            "retryCount": 0,
            "status": "errorDataNotFound",
            "title": "Delete customer profile (GDPR6)",
            "type": "delete"
        }
```

## Recupero di un file di dati sulla privacy

>[!CAUTION]
>
>L'integrazione del servizio [di base per la](https://adobe.io/apis/cloudplatform/gdpr.html) privacy è il metodo da utilizzare per tutte le richieste di accesso ed eliminazione. A partire dalla versione 19.4, l'utilizzo dell'API Campaign e dell'interfaccia per le richieste di accesso ed eliminazione è diventato obsoleto. Per ulteriori informazioni sulle funzioni obsolete e rimosse di Campaign Standard, consulta [questa pagina](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

Per recuperare il file che contiene tutte le informazioni associate a un valore di riconciliazione, procedere come segue:

1. Eseguite una richiesta **POST** per creare una nuova richiesta con l’attributo **type="access"**, consultate [Creazione di una nuova richiesta](#creating-a-privacy-request)di privacy.

1. Eseguite una richiesta **GET** per recuperare informazioni sulla richiesta.

1. Recuperare il file di dati eseguendo una richiesta **POST** sull'URL **privacyRequestData** restituito, con il nome interno della richiesta di privacy all'interno del payload. Ad esempio: {"name":"PT17"}.

<br/>

***Richiesta di esempio***

Create una richiesta di privacy con l'attributo type="access".

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'

{
"name":"PT11832",
"namespaceName": "AMCDS2",
"reconciliationValue": "customers@adobe.com",
"regulation": "gdpr",
"label":"Delete customers",
"type":"access"
}
```

<!-- + réponse -->

Eseguite una richiesta GET per recuperare informazioni sulla richiesta.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
```

Restituisce l’attributo privacyRequestData con un URL associato.

```
{
    ...
    "name": "PR2",
    "namespace": ...,
    "namespaceName": "defaultNamespace1",
    "privacyRequestData": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData/"
    },
    "reconciliationValue": "johndoe@mail.com",
    "regulation": "gdpr",
    "retryCount": 0,
    "status": "complete",
    "title": "EPR (PR2)",
    "type": "access"
    ...
},
```

Eseguite una richiesta POST sull'URL privacyRequestData, con il nome interno della richiesta all'interno del payload.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/privacy/privacyTool/<PKEY>/privacyRequestData \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8'
-d '{"name": "PR1"}'
```

Restituisce il contenuto del file.

```
"{data:<gdprRequestData _cs=\" ()\" id=\"8565163\" reconciliationValue=\"'customer@adobe.com'\">\n  <table name=\"nms:recipient\">\n    <rowId='8569152'\n\t\tlastName='customer'\n\t\tfirstName='customer'\n\t\tgender='1'\n\t\temail='customer@adobe.com'\n\t\tcreatedBy-id='8565162'\n\t\tmodifiedBy-id='8565162'\n\t\tlastModified='2018-03-15 13:54:28.708Z'\n\t\tcreated='2018-03-15 13:54:28.708Z'\n\t\tthumbnail='/nl/img/thumbnails/defaultProfil.png'\n\t\temailFormat='2'</row>\n  </table>\n  <table name=\"nms:broadLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\tid='8003'\n\t\taddress='customer@adobe.com'\n\t\tstatus='1'\n\t\tmsg-id='1194'\n\t\teventDate='2018-03-15 13:58:34.726Z'\n\t\tlastModified='2018-03-15 13:59:02.008Z'\n\t\tvariant='default'\n\t\tdelivery-id='8569153'\n\t\tpublicId='1'\n\t\tprofile-id='8569152'</row>\n  </table>\n  <table name=\"nms:trackingLogRcp\">\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='-1178080215'\n\t\ttrackedDevice='pc'\n\t\tid='5000'\n\t\tlogDate='2018-03-15 14:00:51.650Z'\n\t\tsourceType='html'\n\t\tuserAgent='-1178080215'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n    <row>deliveryLabel='Send via email'\n\t\tdeliveryType='0'\n\t\tcontactDate='2018-03-15 13:58:31.667Z'\n\t\turlLabel='Open'\n\t\turlSource=''\n\t\tuserAgent='0'\n\t\ttrackedDevice=''\n\t\tid='6000'\n\t\tlogDate='2018-03-15 16:00:41.110Z'\n\t\tsourceType='html'\n\t\turl-id='1'\n\t\tdelivery-id='8569153'\n\t\tbroadLog-id='8003'\n\t\trecipient-id='8569152'</row>\n  </table>\n</gdprRequestData>}"
```

## Gestione del rifiuto CCPA

Lo stato di rifiuto CCPA di un profilo può essere monitorato e gestito utilizzando l'attributo di profilo **ccpaOptOut** e i valori "true" o "false":

`"ccpaOptOut": <value>`

* **true**:  vieta la vendita di informazioni personali.
* **false**: autorizza la vendita di informazioni personali.

>[!CAUTION]
>
>L'attributo "Rinuncia CCPA" è disponibile solo a partire dalla versione 19.4. Per gli ambienti 19.3, è necessario estendere la risorsa Profili e aggiungere un campo booleano. Questo campo verrà aggiunto all'API con l'etichetta selezionata. Vi consigliamo di utilizzare "Opt-Out for CCPA".
>
>Per ulteriori informazioni, consulta la documentazione [sulla gestione della](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)privacy.

<br/>

***Richieste di esempio***

* Esempio di richiesta GET per recuperare lo stato di rifiuto CCPA di un profilo.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   ```

   Risposta alla richiesta GET.

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* Esempio di richiesta POST per contrassegnare un profilo per la rinuncia CCPA.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/ \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "firstName": "John",
   -d  "lastName": "Doe",
   -d  "email": "jdoe@mail.com",
   -d  "ccpaOptOut": true
   -d }'
   ```

   Risposta alla richiesta GET.

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```

* Richiesta PATCH di esempio per aggiornare un profilo per il rifiuto CCPA.

   ```
   -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -H 'Content-Type: application/json;charset=utf-8'
   -i
   -d {
   -d  "ccpaOptOut": true
   -d }'
   ```

   Risposta alla richiesta GET.

   ```
   {
       ...
       "email": "john.doe@mail.com",
       "firstName": "John",
       "lastName": "Doe",
       "ccpaOptOut": true,
       ...
   }
   ```
