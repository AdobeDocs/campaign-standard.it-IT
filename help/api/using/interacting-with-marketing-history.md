---
title: Interazione con lo storico dei dati marketing
description: Scopri come interagire con la cronologia di marketing dei profili
feature: API
role: Data Engineer
level: Experienced
exl-id: 67282d21-b4ed-4af5-b751-848a6d705118
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%

---

# Interazione con lo storico dei dati marketing{#interacting-with-marketing-history}

L&#39;endpoint **history** ti consente di interagire con la cronologia di marketing di un profilo.
In questo modo, ad esempio, puoi recuperare facilmente la pagina speculare per una consegna inviata a un profilo. A questo scopo, segui la procedura indicata di seguito:

1. Esegui un GET con l&#39;endpoint **history** e la chiave primaria del profilo.
1. Esegui una richiesta GET per i **eventi** href restituiti.
1. Restituisce l&#39;elenco degli eventi per il profilo con collegamenti alle pagine mirror nel nodo **mirrorPage**.

<br/>

***Richiesta di esempio***

Recupera la cronologia di marketing del profilo con una richiesta GET.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Il nodo &quot;events&quot; restituisce l’URL che ti consente di accedere agli eventi sul profilo.

```
{
  "PKey": "<PKEY>",
  "firstName": "John",
  "lastName":"Doe",
  "birthDate": "1980-10-24",
  "events": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/",
    "metadata": "subHisto"
    },
}
```

Eseguire una richiesta GET sugli eventi href restituiti.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l’elenco degli eventi per il profilo con collegamenti alle pagine mirror nel nodo &quot;mirrorPage&quot;.

```
    {
      "PKey": "<PKEY>",
      "category": "email",
      "date": "2018-05-17 08:44:49.366Z",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>",
      "label": "Send via email",
      "mirrorPage": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>/mirrorPage/"
      },
      "type": "outbound"
    }
```
