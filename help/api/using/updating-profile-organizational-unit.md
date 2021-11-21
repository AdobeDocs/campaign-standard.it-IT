---
title: Aggiornamento dell’unità organizzativa di un profilo
description: Scopri come aggiornare l’unità organizzativa di un profilo con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 6ce49aeb-a113-43ee-bfe3-f26a4a9e2a56
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 10%

---

# Aggiornamento dell’unità organizzativa di un profilo {#managing-organizational-units}

1. Esegui una richiesta di GET sul **orgUnitBase** risorsa per recuperare l’unità organizzativa PKey
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
