---
solution: Campaign Standard
product: campaign
title: Aggiornamento dell’unità organizzativa di un profilo
description: Scopri come aggiornare l’unità organizzativa di un profilo con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '100'
ht-degree: 11%

---


# Aggiornamento dell’unità organizzativa di un profilo {#managing-organizational-units}

1. Esegui una richiesta di GET sulla risorsa **orgUnitBase** per recuperare l&#39;unità organizzativa PKey
1. Esegui una richiesta PATCH sul profilo PKey, con l’unità organizzativa desiderata PKey nel payload.

<br/>

***Richiesta di esempio***

Recupera l’elenco delle unità organizzative.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce tutte le unità organizzative. Recupera il PKey dell’unità a cui desideri assegnare il profilo.

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

Esegui una richiesta di PATCH sul profilo con il PKey dell’unità organizzativa desiderata nel payload.

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
