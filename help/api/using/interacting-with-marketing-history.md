---
title: Interazione con la cronologia di marketing
description: Scopri come interagire con la cronologia di marketing dei profili.
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
source-git-commit: e60ec7790da46d234b66baf4c3db23815056b9fb

---


# Interazione con la cronologia di marketing {#interacting-with-marketing-history}

L&#39;endpoint **della cronologia** consente di interagire con la cronologia marketing di un profilo.
In questo modo, ad esempio, è possibile recuperare facilmente la pagina mirror per una consegna inviata a un profilo. A questo scopo, effettuate le seguenti operazioni:

1. Eseguire un GET con l&#39;endpoint **cronologia** e la chiave primaria del profilo.
1. Eseguire una richiesta GET per gli **eventi** href restituiti.
1. Restituisce l&#39;elenco degli eventi per il profilo con i collegamenti alle pagine mirror nel nodo **mirrorPage** .

<br/>

***Richiesta di esempio ***

Recupera la cronologia di marketing del profilo con una richiesta GET.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Il nodo &quot;eventi&quot; restituisce l&#39;URL che consente di accedere agli eventi del profilo.

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

Restituisce l&#39;elenco degli eventi per il profilo con i collegamenti alle pagine mirror nel nodo &quot;mirrorPage&quot;.

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
