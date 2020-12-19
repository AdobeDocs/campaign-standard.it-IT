---
solution: Campaign Standard
product: campaign
title: Numerazione delle pagine
description: Scoprite come eseguire le operazioni di impaginazione.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# Numerazione delle pagine

Per impostazione predefinita, in un elenco vengono caricate 25 risorse.

Il parametro **_lineCount** consente di limitare il numero di risorse elencate nella risposta.  È quindi possibile utilizzare il nodo **next** per visualizzare i risultati successivi.

>[!NOTE]
>
>Utilizzare sempre il valore URL restituito nel nodo **next** per eseguire una richiesta di impaginazione.
>
>La richiesta **_lineStart** viene calcolata e deve sempre essere utilizzata all&#39;interno dell&#39;URL restituito nel nodo **next**.

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

Risposta alla richiesta, con il nodo **next** per eseguire l&#39;impaginazione.

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

Per impostazione predefinita, il nodo **next** non è disponibile quando si interagisce con tabelle con grandi quantità di dati. Per poter eseguire l&#39;impaginazione, devi aggiungere il parametro **_forcePagination=true** all&#39;URL della chiamata.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_forcePagination=true \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

>[!NOTE]
>
>Il numero di record al di sopra dei quali una tabella viene considerata grande è definito nell&#39;opzione Campaign Standard **XtkBigTableThreshold**. Il valore predefinito è 100.000 record.
