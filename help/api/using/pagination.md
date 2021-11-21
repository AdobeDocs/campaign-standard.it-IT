---
title: Paginazione
description: Scopri come eseguire le operazioni di impaginazione.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d6ebce3c-1e84-4b3b-a68d-90df4680af64
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---

# Paginazione

Per impostazione predefinita, in un elenco vengono caricate 25 risorse.

La **_lineCount** ti consente di limitare il numero di risorse elencate nella risposta.  È quindi possibile utilizzare la **next** per visualizzare i risultati successivi.

>[!NOTE]
>
>Utilizza sempre il valore URL restituito nel **next** nodo per eseguire una richiesta di impaginazione.
>
>La **_lineStart** La richiesta viene calcolata e deve sempre essere utilizzata all’interno dell’URL restituito nel **next** nodo.

<br/>

***Richiesta di esempio***

Richiesta di GET di esempio per visualizzare 1 record della risorsa profilo.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Risposta alla richiesta, con il **next** nodo per eseguire l&#39;impaginazione.

```
{
    "content": [
        {
            "PKey": "<PKEY>",
            "firstName": "John",
            "lastName":"Doe",
            "birthDate": "1980-10-24",
            ...
        }
    ],
    "next": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
        lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
    }
    ...
}
```

Per impostazione predefinita, la **next** nodo non disponibile quando si interagisce con tabelle con grandi quantità di dati. Per poter eseguire l’impaginazione, è necessario aggiungere la variabile **_forcePagination=true** all&#39;URL della chiamata.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>In Campaign Standard è definito il numero di record al di sopra dei quali una tabella è considerata grande **XtkBigTableThreshold** opzione . Il valore predefinito è 100.000 record.
