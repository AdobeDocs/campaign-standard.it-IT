---
title: Creazione di una richiesta di accesso a dati personali
description: Scopri come creare una richiesta di accesso a dati personali con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 06ad2e13-922b-4f35-8726-007427125c63
TQID: https://experienceleague.adobe.com/KInaFaQrwA5FKro44yFABqmDDvefY5mhJIl2OtBCrFc
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 179
ht-degree: 4%

---

# Creazione di una richiesta di accesso a dati personali {#creating-a-privacy-request}

>[!CAUTION]
>
>L&#39;integrazione del [servizio core per la privacy](https://developer.adobe.com/experience-platform-apis/references/privacy-service) è il metodo da utilizzare per tutte le richieste di accesso ed eliminazione. <!--Starting 19.4, the use of the Campaign API and interface for access and delete requests is deprecated. For more on Campaign Standard deprecated and removed features, refer to [this page](../../rn/using/deprecated-features.md).-->

Le richieste di accesso a dati personali vengono create utilizzando una richiesta **POST**.

Prima di creare le richieste, devi definire lo spazio dei nomi che userai. Per ulteriori informazioni, consulta la [documentazione sulla gestione della privacy](../../start/using/privacy-requests.md).

Il payload deve contenere i seguenti parametri:

* **name**: nome interno univoco
* **namespace**: il nome dello spazio dei nomi configurato nell&#39;interfaccia di Campaign Standard
* **conciliationValue**: il valore di riconciliazione basato sulla chiave di riconciliazione definita nello spazio dei nomi
* **label**: l&#39;etichetta della richiesta
* **type**: il tipo di richiesta. I valori accettati sono &quot;access&quot; o &quot;delete&quot;.
* **regulation**: tipo di regolamento. Esempio: &quot;RGPD&quot;, &quot;CCPA&quot;. Questo parametro è obbligatorio e disponibile a partire dalla versione 19.4 di Campaign Standard. Se utilizzi una build precedente, non è necessario aggiungerla al payload.

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
