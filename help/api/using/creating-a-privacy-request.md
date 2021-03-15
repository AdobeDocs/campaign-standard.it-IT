---
solution: Campaign Standard
product: campaign
title: Creazione di una richiesta di accesso a dati personali
description: Scopri come creare una richiesta di accesso a dati personali con API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 7%

---


# Creazione di una richiesta di accesso a dati personali {#creating-a-privacy-request}

>[!CAUTION]
>
>L’ [Integrazione di base del servizio Privacy](https://adobe.io/apis/cloudplatform/gdpr.html) è il metodo da utilizzare per tutte le richieste di accesso e di cancellazione. A partire dalla versione 19.4, l’utilizzo dell’API e dell’interfaccia di Campaign per le richieste di accesso ed eliminazione è diventato obsoleto. Per ulteriori informazioni sulle funzioni obsolete e rimosse di Campaign Standard, consulta [questa pagina](../../rn/using/deprecated-features.md).

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
