---
title: Meccanismo metadati
description: Ulteriori informazioni sul meccanismo di metadati.
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


# Meccanismo metadati {#metadata-mechanism}

Potete recuperare i metadati delle risorse utilizzando **resourceType** in una richiesta GET:

`GET /profileAndServices/resourceType/<resourceName>`

La risposta restituisce i metadati principali della risorsa (tutti gli altri campi sono descrittivi o interni):

* Il nodo **Contenuto** restituisce i campi della risorsa. Per ciascun campo nel nodo **contenuto** , sono disponibili i campi seguenti:

   * "apiName": nome dell'attributo utilizzato nelle API.
   * "type": si tratta della definizione del tipo ad alto livello (stringa, numero, collegamento, raccolta, enumerazione...).
   * "dataPolicy": il valore del campo deve seguire le regole del criterio specificate. Ad esempio, se la regola dataPolicy è impostata su "email", il valore deve essere un'e-mail valida. Durante un PATCH o un POST, dataPolicy può controllare il valore o modificare il valore da trasformare (ad esempio, smartCase).
   * "category": fornisce la categoria del campo nell'editor di query.
   * "resType": questo è il tipo tecnico.

      Se "type" viene completato con il valore "link" o "collection", il valore resTarget è il nome della risorsa di destinazione del collegamento.
Se "type" viene completato con il valore "enumeration", viene aggiunto un campo "values" e ogni valore di enumerazione è dettagliato nel nodo **values** .

* Il nodo **Filtri** restituisce l'URL per recuperare i filtri associati. For more on filters, refer to [this section](../../api/using/filtering.md) section.

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***Richiesta di esempio***

Eseguite una richiesta GET sulla risorsa.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce la descrizione completa della risorsa profilo.

```
{
...
"content": {
  "email": {...},
    ...
    },
"data": "/profileAndServices/profile/",
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>"
    },
"help": "Identified profiles",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/metadata",
"label": "Profiles",
"mandatory": false,
"name": "profile",
"pkgStatus": "never",
"readOnly": false,
"schema": "nms:recipient",
"type": "item"
}
```
