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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 22%

---

# Creazione di una richiesta di accesso a dati personali {#creating-a-privacy-request}

>[!CAUTION]
>
>L’ [Integrazione di base del servizio Privacy](https://adobe.io/apis/cloudplatform/gdpr.html?lang=it) è il metodo da utilizzare per tutte le richieste di accesso e di cancellazione. A partire dalla versione 19.4, l’utilizzo dell’API e dell’interfaccia di Campaign per le richieste di accesso ed eliminazione diventa obsoleto. Per ulteriori informazioni sulle funzioni obsolete e rimosse da Campaign Standard, consulta [questa pagina](../../rn/using/deprecated-features.md).

Le richieste di privacy vengono create utilizzando una richiesta **POST**.

Prima di creare le richieste, devi definire lo spazio dei nomi da utilizzare. Per ulteriori informazioni, consulta la [documentazione sulla gestione della privacy](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#ManagingPrivacyRequests).

Il payload deve contenere i seguenti parametri:

* **nome**: un nome interno univoco
* **namespace**: nome dello spazio dei nomi configurato nell’interfaccia di Campaign Standard
* **riconciliazioneValue**: il valore di riconciliazione basato sulla chiave di riconciliazione definita nello spazio dei nomi
* **etichetta**: l’etichetta della richiesta
* **tipo**: il tipo di richiesta. I valori accettati sono &quot;access&quot; o &quot;delete&quot;.
* **regolamento**: il tipo di regolamento. Esempio: &quot;RGPD&quot;, &quot;CCPA&quot;. Questo parametro è obbligatorio ed è disponibile a partire dalla versione 19.4 di Campaign Standard. Se utilizzi una build precedente, non è necessario aggiungerla al payload.

<br/>

***Richiesta di esempio***

Questa richiesta di POST crea una richiesta di accesso a dati personali basata su una chiave di riconciliazione e-mail definita nello spazio dei nomi AMCDS2:

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
