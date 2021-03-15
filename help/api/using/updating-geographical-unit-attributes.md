---
solution: Campaign Standard
product: campaign
title: Aggiornamento degli attributi di un’unità geografica
description: Scopri come aggiornare gli attributi di un’unità geografica con le API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 12%

---


# Aggiornamento degli attributi di un’unità geografica {#managing-geographical-units}

1. Esegui una richiesta di GET sulla risorsa **geoUnitBase** per recuperare l&#39;unità geografica PKey.
1. Esegui una richiesta di PATCH sull’unità geografica, con gli attributi da aggiornare nel payload.

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

Restituisce tutte le unità geografiche. Recuperare il PKey dell&#39;unità desiderata.

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

Esegui una richiesta di PATCH sull’unità geografica, con gli attributi da aggiornare nel payload.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"Asia",
-d "name":"asia"
-d }
```

<!-- + réponse -->
