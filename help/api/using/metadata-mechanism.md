---
title: Meccanismo metadati
description: Ulteriori informazioni sul meccanismo dei metadati.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 58ec0999-b28a-4198-8d57-729b074c6a6d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---

# Meccanismo metadati {#metadata-mechanism}

Puoi recuperare i metadati delle risorse utilizzando **resourceType** in una richiesta GET:

`GET /profileAndServices/resourceType/<resourceName>`

La risposta restituisce i metadati principali dalla risorsa (tutti gli altri campi sono descrittivi o interni):

* Il nodo **Content** restituisce i campi della risorsa. Per ogni campo del nodo **content**, possiamo trovare i campi seguenti:

   * &quot;apiName&quot;: nome dell’attributo utilizzato nelle API.
   * &quot;type&quot;: si tratta della definizione di tipo di livello elevato (stringa, numero, collegamento, raccolta, enumerazione...).
   * &quot;dataPolicy&quot;: il valore del campo deve seguire le regole dei criteri specificate. Ad esempio, se la regola dataPolicy è impostata su &quot;email&quot;, il valore deve essere un&#39;e-mail valida. Durante un PATCH o un POST, dataPolicy può controllare il valore o modificare il valore da trasformare (ad esempio, smartCase).
   * &quot;categoria&quot;: fornisce la categoria del campo nell’editor delle query.
   * &quot;resType&quot;: questo è il tipo tecnico.

      Se &quot;type&quot; viene completato con il valore &quot;link&quot; o &quot;collection&quot;, il valore resTarget corrisponde al nome della risorsa oggetto del collegamento.
Se &quot;type&quot; viene completato con il valore &quot;enumeration&quot;, viene aggiunto un campo &quot;values&quot; e ogni valore di enumerazione è descritto nel nodo **values** .

* Il nodo **Filtri** restituisce l&#39;URL per recuperare i filtri associati. Per ulteriori informazioni sui filtri, consulta [questa sezione](../../api/using/filtering.md) .

<!-- créer une section au même niveau sur les liens -->
<!-- dans l'exemple: birthdate, email +  mettre 2 liens : un de type 1-1 , 1-N
si on prend l'exemple de l'org unit, on aura un bon exemple lien -->
<!-- plus reparler du node Data -->

<br/>

***Richiesta di esempio***

Esegui una richiesta di GET sulla risorsa.

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
