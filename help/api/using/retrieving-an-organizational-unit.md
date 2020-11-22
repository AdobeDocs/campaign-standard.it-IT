---
solution: Campaign Standard
product: campaign
title: Recupero unità organizzativa di un profilo
description: Scopri come utilizzare le API per l'unità organizzativa di un profilo.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 12%

---


# Recupero unità organizzativa di un profilo {#retrieving-organizational-units}

1. Eseguite una richiesta di GET sul profilo PKey per recuperare l’URL **orgUnit** .
1. Eseguite una richiesta di GET sull&#39;URL per recuperare ulteriori dettagli sull&#39;unità organizzativa.

<br/>

***Richiesta di esempio***

Recupera il record del profilo.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l’URL orgUnit per il profilo.

```
{
  ...
  "orgUnit": {
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
    "title": "All (all)"
    },
  ...
}
```

Eseguite una richiesta di GET sull’URL per recuperare ulteriori informazioni.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce i dettagli sull&#39;unità organizzativa.

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "label": "Brand 4",
  "lastModified": "2019-04-03 08:17:19.100Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand4)"
}
```
