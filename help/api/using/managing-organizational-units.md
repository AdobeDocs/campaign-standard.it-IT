---
title: Gestione delle unità organizzative
description: Scoprite come gestire le unità aziendali con le API.
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Gestione delle unità organizzative {#managing-organizational-units}

L'endpoint **orgUnitBase** consente di interagire con le unità organizzative, consentendo, ad esempio, di aggiornare i loro attributi o di aggiornare l'unità organizzativa di un profilo. Per ulteriori informazioni sulle unità organizzative in Campaign, consulta la documentazione [relativa alla](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html)campagna.

Il campo Unità **** organizzativa viene aggiunto a un profilo quando si estende la risorsa del profilo. Come risultato, ricordati di utilizzare sempre l'endpoint **profileAndServicesExt** per interagire con le unità geografiche. Per ulteriori informazioni sull'estensione delle risorse del profilo, consulta la documentazione relativa alla [campagna](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).

## Recupero dell'unità organizzativa di un profilo

1. Eseguite una richiesta GET sul profilo PKey per recuperare l'URL **orgUnit** .
1. Eseguite una richiesta GET sull'URL per recuperare ulteriori dettagli sull'unità organizzativa.

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

Eseguite una richiesta GET sull'URL per recuperare ulteriori informazioni.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce i dettagli sull'unità organizzativa.

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

## Aggiornamento dell'unità organizzativa di un profilo

1. Eseguire una richiesta GET sulla risorsa **orgUnitBase** per recuperare l'unità organizzativa PKey
1. Eseguite una richiesta PATCH sul profilo PKey, con l'unità organizzativa desiderata PKey nel payload.

<br/>

***Richiesta di esempio***

Recuperare l'elenco delle unità organizzative.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce tutte le unità organizzative. Recuperare il PKey dell'unità a cui si desidera assegnare il profilo.

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

Eseguite una richiesta PATCH sul profilo, con il PKey dell'unità organizzativa desiderata nel payload.

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

## Aggiornamento degli attributi di un'unità organizzativa

1. Eseguite una richiesta GET sulla risorsa **orgUnitBase** per recuperare l'unità organizzativa PKey.
1. Eseguite una richiesta PATCH sull'unità organizzativa, con gli attributi da aggiornare nel payload.

<br/>

***Richiesta di esempio***

Recuperare l'elenco delle unità organizzative.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/orgUnitBase/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce tutte le unità organizzative. Recuperare il PKey dell'unità desiderata.

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

Eseguite una richiesta PATCH sull'unità organizzativa, con gli attributi da aggiornare nel payload.

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
