---
solution: Campaign Standard
product: campaign
title: Monitoraggio di una richiesta di accesso a dati personali
description: Scopri come monitorare una richiesta di accesso a dati personali con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '58'
ht-degree: 25%

---


# Monitoraggio di una richiesta di accesso a dati personali {#monitoring-a-privacy-request}

Puoi monitorare le informazioni su una richiesta di accesso a dati personali creata utilizzando una richiesta **GET**.

La descrizione dell&#39;elenco di stato è disponibile nella [documentazione sulla gestione della privacy](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#ManagingPrivacyRequests).

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
