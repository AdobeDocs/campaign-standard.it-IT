---
title: Creazione di una richiesta di accesso a dati personali
description: Scopri come creare una richiesta di accesso a dati personali con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 4%

---

# Creazione di una richiesta di accesso a dati personali {#creating-a-privacy-request}

>[!CAUTION]
>
>Il [Servizio core per la privacy](https://developer.adobe.com/experience-platform-apis/references/privacy-service) L’integrazione è il metodo da utilizzare per tutte le richieste di accesso ed eliminazione. <!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

Le richieste di accesso ai dati personali vengono create utilizzando **POST** richiesta.

Prima di creare le richieste, devi definire lo spazio dei nomi che userai. Per ulteriori informazioni, consulta [Documentazione sulla gestione della privacy](../../start/using/privacy-requests.md).

Il payload deve contenere i seguenti parametri:

* **nome**: nome interno univoco
* **namespace**: nome dello spazio dei nomi configurato nell’interfaccia di Campaign Standard
* **conciliationValue**: il valore di riconciliazione basato sulla chiave di riconciliazione definita nello spazio dei nomi
* **etichetta**: l’etichetta della richiesta
* **tipo**: tipo di richiesta. I valori accettati sono &quot;access&quot; o &quot;delete&quot;.
* **regolamento**: tipo di regolamento. Esempio: &quot;RGPD&quot;, &quot;CCPA&quot;. Questo parametro è obbligatorio e disponibile a partire dalla versione 19.4 di Campaign Standard. Se utilizzi una build precedente, non è necessario aggiungerla al payload.

<br/>

***Richiesta di esempio***

Questa richiesta POST crea una richiesta di accesso a dati personali basata su una chiave di riconciliazione e-mail definita nello spazio dei nomi AMCDS2:

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
