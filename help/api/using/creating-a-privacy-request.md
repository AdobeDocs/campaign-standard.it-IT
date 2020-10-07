---
title: Creazione di una richiesta di accesso a dati personali
description: Informazioni su come creare una richiesta di privacy con le API
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 8%

---


# Creazione di una richiesta di accesso a dati personali {#creating-a-privacy-request}

>[!CAUTION]
>
>L&#39;integrazione del servizio [di base per la](https://adobe.io/apis/cloudplatform/gdpr.html) privacy è il metodo da utilizzare per tutte le richieste di accesso ed eliminazione. A partire dalla versione 19.4, l&#39;utilizzo dell&#39;API e dell&#39;interfaccia di Campaign per le richieste di accesso ed eliminazione è diventato obsoleto. Per ulteriori informazioni sulle funzioni obsolete e rimosse dei Campaign Standard, consultate [questa pagina](https://helpx.adobe.com/it/campaign/kb/acs-deprecated-and-removed-features.html).

Le richieste di privacy vengono create utilizzando una richiesta **POST** .

Prima di creare le richieste, è necessario definire lo spazio nomi che verrà utilizzato. Per ulteriori informazioni, consulta la documentazione [sulla gestione della](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)privacy.

Il payload deve contenere i seguenti parametri:

* **name**: un nome interno univoco
* **namespace**: il nome dello spazio dei nomi configurato nell&#39;interfaccia Campaign Standard
* **riconciliazioneValue**: il valore di riconciliazione basato sulla chiave di riconciliazione definita nello spazio dei nomi
* **label**: l’etichetta della richiesta
* **type**: il tipo di richiesta. I valori accettati sono &quot;access&quot; o &quot;delete&quot;.
* **regolamento**: il tipo di regolazione. Esempio: &quot;GDPR&quot;, &quot;CCPA&quot;. Questo parametro è obbligatorio e disponibile a partire dalla versione Campaign Standard 19.4. Se siete su una build precedente, non è necessario aggiungerla al payload.

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
