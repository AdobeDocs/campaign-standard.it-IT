---
title: Aggiornamento degli attributi di un’unità organizzativa
description: Scopri come aggiornare gli attributi di un’unità organizzativa
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 90841afd-ebc2-4b6a-895e-a96ef65740d7
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 0%

---

# Aggiornamento degli attributi di un’unità organizzativa {#updating-organizational-unit-attributes}

1. Eseguire una richiesta GET sulla risorsa **orgUnitBase** per recuperare l&#39;unità organizzativa PKey.
1. Esegui una richiesta PATCH sull’unità organizzativa, con gli attributi da aggiornare nel payload.

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

Restituisce tutte le unità organizzative. Recuperate la PKey dell&#39;unità desiderata.

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

Esegui una richiesta PATCH sull’unità organizzativa, con gli attributi da aggiornare nel payload.

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label":"brand1",
-d "name":"brand1"
-d }
```

<!-- + réponse -->
