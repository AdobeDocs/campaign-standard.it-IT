---
title: Recupero dell’unità organizzativa di un profilo
description: Scopri come utilizzare le API per l’unità organizzativa di un profilo.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 37048884-bd03-46ea-8e2e-a73ad568153b
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 12%

---

# Recupero dell’unità organizzativa di un profilo {#retrieving-organizational-units}

1. Esegui una richiesta GET nel PKey del profilo per recuperare l&#39;URL **orgUnit**.
1. Esegui una richiesta GET sull’URL per recuperare ulteriori dettagli sull’unità organizzativa.

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

Restituisce l’URL orgUnit del profilo.

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

Esegui una richiesta GET sull’URL per recuperare ulteriori informazioni.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce dettagli sull’unità organizzativa.

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
