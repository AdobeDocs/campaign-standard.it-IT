---
solution: Campaign Standard
product: campaign
title: Aggiornamento dell’unità organizzativa di un profilo
description: Scopri come aggiornare l'unità organizzativa di un profilo con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%

---


# Aggiornamento dell’unità organizzativa di un profilo {#managing-organizational-units}

1. Eseguire una richiesta di GET sulla risorsa **orgUnitBase** per recuperare l&#39;unità organizzativa PKey
1. Eseguite una richiesta PATCH sul profilo PKey, con l&#39;unità organizzativa desiderata PKey nel payload.

<br/>

***Richiesta di esempio***

Recuperare l&#39;elenco delle unità organizzative.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce tutte le unità organizzative. Recuperare il PKey dell&#39;unità a cui si desidera assegnare il profilo.

```
{
  "PKey": "<PKEY>",
  "created": "2019-04-02 22:36:13.252Z",
  "desc": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY>",
  "label": "Brand 4",
  "lastModified": "2019-04-03 07:34:56.579Z",
  "name": "brand4",
  "parentTitle": "All (all)",
  "title": "Brand 4 (brand1)"
},
```

Eseguite una richiesta PATCH sul profilo con il PKey dell&#39;unità organizzativa desiderata nel payload.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "orgUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->
