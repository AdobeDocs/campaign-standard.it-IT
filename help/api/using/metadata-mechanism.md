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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---


# Meccanismo metadati {#metadata-mechanism}

Potete recuperare i metadati delle risorse utilizzando **resourceType** in una richiesta di GET:

`GET /profileAndServices/resourceType/<resourceName>`

La risposta restituisce i metadati principali della risorsa (tutti gli altri campi sono descrittivi o interni):

* Il nodo **Contenuto** restituisce i campi della risorsa. Per ciascun campo nel nodo **contenuto** , sono disponibili i campi seguenti:

   * &quot;apiName&quot;: nome dell&#39;attributo utilizzato nelle API.
   * &quot;type&quot;: si tratta della definizione del tipo ad alto livello (stringa, numero, collegamento, raccolta, enumerazione...).
   * &quot;dataPolicy&quot;: il valore del campo deve seguire le regole del criterio specificate. Ad esempio, se la regola dataPolicy è impostata su &quot;email&quot;, il valore deve essere un&#39;e-mail valida. Durante un PATCH o un POST, dataPolicy può controllare il valore o modificare il valore da trasformare (ad esempio, smartCase).
   * &quot;category&quot;: fornisce la categoria del campo nell&#39;editor di query.
   * &quot;resType&quot;: questo è il tipo tecnico.

      Se &quot;type&quot; viene completato con il valore &quot;link&quot; o &quot;collection&quot;, il valore resTarget è il nome della risorsa di destinazione del collegamento.
Se &quot;type&quot; viene completato con il valore &quot;enumeration&quot;, viene aggiunto un campo &quot;values&quot; e ogni valore di enumerazione è dettagliato nel nodo **dei valori** .

* Il nodo **Filtri** restituisce l&#39;URL per recuperare i filtri associati. For more on filters, refer to [this section](../../api/using/filtering.md) section.

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***Richiesta di esempio***

Eseguite una richiesta di GET sulla risorsa.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce la descrizione completa della risorsa del profilo.

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
