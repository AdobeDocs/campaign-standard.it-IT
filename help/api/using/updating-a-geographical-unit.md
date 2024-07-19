---
title: Aggiornamento dell’unità geografica di un profilo
description: Scopri come gestire le unità geografiche con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9dc07d86-00b2-4885-b6ac-0a6f9bc45236
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 10%

---

# Aggiornamento dell’unità geografica di un profilo {#updating-a-geographical-unit}

1. Eseguire una richiesta di GET sulla risorsa **geoUnitBase** per recuperare l&#39;unità geografica PKey.
1. Esegui una richiesta PATCH sul profilo PKey, con l’unità geografica PKey desiderata nel payload.

<br/>

***Richiesta di esempio***

Recupera l’elenco delle unità geografiche.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce tutte le unità geografiche. Recuperate la chiave PK dell&#39;unità a cui desiderate assegnare il profilo.

```
{
 "PKey": "<PKEY>",
 "created": "2019-04-06 22:36:19.089Z",
 "desc": "",
 "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/geoUnitBase/<PKEY>",
 "label": "Europe",
 "lastModified": "2019-04-06 22:36:19.086Z",
 "name": "eu",
 "parentTitle": "All (all)",
 "title": "Europe (eu)"
},
```

Esegui una richiesta PATCH sul profilo, con la PKey dell’unità geografica desiderata nel payload.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "geoUnit":{
-d    "PKey":"<PKEY>"
-d  }
-d }
```

<!-- + réponse -->
