---
solution: Campaign Standard
product: campaign
title: Aggiornamento dell’unità geografica di un profilo
description: Scopri come gestire le unità geografiche con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 11%

---


# Aggiornamento dell’unità geografica di un profilo {#updating-a-geographical-unit}

1. Esegui una richiesta di GET sulla risorsa **geoUnitBase** per recuperare l&#39;unità geografica PKey.
1. Esegui una richiesta PATCH sul profilo PKey, con l&#39;unità geografica desiderata PKey nel payload.

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

Restituisce tutte le unità geografiche. Recupera il PKey dell’unità a cui desideri assegnare il profilo.

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

Esegui una richiesta PATCH sul profilo, con il PKey dell’unità geografica desiderata nel payload.

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
