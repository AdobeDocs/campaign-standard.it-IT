---
title: Filtro
description: Scoprite come eseguire operazioni di filtro.
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
source-wordcount: '434'
ht-degree: 1%

---


# Filtro {#filtering}

## Recupero dei metadati dei filtri

Per ogni risorsa sono disponibili dei filtri. Per identificare i filtri associati a una risorsa, è necessario eseguire una richiesta di GET sui metadati della risorsa. Questa richiesta restituisce l’URL in cui tutti i filtri sono definiti per una determinata risorsa. For more on metadata, refer to [this section](../../api/using/metadata-mechanism.md).

Per identificare i metadati di un filtro e determinare come utilizzarlo, è necessario eseguire una richiesta di GET sull’URL restituito in precedenza.

<br/>

***Richiesta di esempio***

I payload di esempio riportati di seguito mostrano come recuperare i metadati del filtro &quot;byText&quot; per la risorsa &quot;profilo&quot;. Eseguire innanzitutto una richiesta di GET sulla metada delle risorse &quot;profilo&quot;.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l’URL in cui sono descritti i filtri.

```
{
"filters": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/resourceType/<PKEY>/filters/"
    }
  }
```

Eseguite una richiesta di GET sull’URL. Restituisce l&#39;elenco dei filtri per la risorsa del profilo, con i metadati associati a ciascun filtro.

```
{
"birthday": {
        "PKey": "@FL-CbDFXbnHbXcVpeCGWL46VXJLn1LqxLMPagt2vz8sCxQ52lvB15KiUaxXkxJYQw-tZXYrgUWG6K8QcB4gxVY9RKoba5bRFY3294YFshDmorRr8",
        "category": "0150_profile",
        "condition": ...,
        "data": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/birthday?type=$value&precision=$value&operator=$value&day=$value&month=$value&includeStart=$value&endDay=$value&endMonth=$value&includeEnd=$value&relativeValue=$value&nextUnitsValue=$value&previousUnitsValue=$value",
        "formType": "webPage",
        "fragmentName": "",
        "label": "Birthday",
}
```

## Filtra la struttura metadati

Per ciascun filtro è disponibile la stessa struttura di metadati:

* I campi **@formType** e **@webPage** sono campi tecnici.
* Il campo **dati** fornisce un esempio di come utilizzare il filtro.
* Il nodo **di metadati** descrive i parametri del filtro.
* Il nodo **condizione** descrive le operazioni che il filtro intende eseguire. I parametri di filtro descritti nel nodo di metadati vengono utilizzati per creare condizioni di filtro. Per ogni condizione del filtro, se **enabledSe** è true, viene applicato l&#39; **espressione** .

<br/>

Filtra esempio struttura metadati:

```
"byText": {
        "PKey": "...",
        "category": "99_none",
        "condition": ...,
        "data": "/profileAndServices/profile/byText?text=$value",
        "formType": "none",
        "fragmentName": "",
        "label": "By name or email",
    }
```

## Utilizzo dei filtri

Il filtraggio viene eseguito con la richiesta seguente:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/by<filterName>?<filterParam>=<filterValue>`

È possibile combinare più filtri in una singola richiesta:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/<resourceName>/<filter1name>/<filter2name>?<filter1param>=<filter1value>&<filter2param>=<filter2value>`

<br/>

***Richieste di esempio***

* Esempio di richiesta di GET per recuperare le risorse del &quot;servizio&quot; con il tipo &quot;email&quot;.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel?channel=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Risposta alla richiesta.

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "created": "2019-09-25 23:20:35.000Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/@I_FIiDush4OQPc0mbOVR9USoh36Tt5CsD35lATvQjdWlXrYc0lFkvle2XIwZUbD8GqTVvSp8AfWFUvjkGMe1fPe5nok",
               "label": "Marketing Newsletter",
               "lastModified": "2019-09-25 23:20:35.000Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               ...
           },
           ...
       ],
       ...
   }
   ```

* Esempio di richiesta di GET per recuperare le risorse &quot;profilo&quot; contenenti &quot;Doe&quot; nei campi e-mail o cognome (il filtro per testo consente di eseguire ricerche sia nei campi e-mail che nel campo del cognome).

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Doe \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Risposta alla richiesta.

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "firstName": "John",
               "lastName":"Doe",
               "birthDate": "1980-10-24",
               ...
           }
           ...
       ],
       ...
   }
   ```

* Esempio di richiesta di GET per recuperare le risorse dei servizi con il tipo &quot;email&quot; e l&#39;etichetta &quot;sport&quot;.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/byChannel/byText?channel=email&text=sport \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Risposta alla richiesta.

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "created": "2019-09-26 09:36:01.014Z",
               "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
               "label": "sport",
               "lastModified": "2019-09-26 09:36:01.014Z",
               "limitedDuration": false,
               "messageType": "email",
               "mode": "newsletter",
               "name": "SVC13",
               ...
           }
       ],
       ...
   }
   ```

## Filtri personalizzati

Se desiderate utilizzare un filtro personalizzato, dovete crearlo e personalizzarlo nell&#39;interfaccia Adobe Campaign Standard . Il filtro personalizzato avrà quindi lo stesso comportamento dei filtri out-of-the-box:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

Per ulteriori informazioni, consulta la documentazione Campaign Standard:

* [Configurazione della definizione del filtro](https://helpx.adobe.com/campaign/standard/developing/using/configuring-filter-definition.html).
* [Caso di utilizzo: Chiamata di una risorsa tramite una chiave](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/adding-or-extending-a-resource/uc-calling-resource-id-key.html)di identificazione composita.

<br/>

***Richiesta di esempio***

Richiesta di GET di esempio per recuperare le risorse &quot;profilo&quot; con importi di transazione pari o superiori a 100$. Il filtro &quot;byAmount&quot; è stato definito per la prima volta nell&#39;interfaccia Adobe Campaign Standard  e collegato alla tabella personalizzata &quot;Transaction&quot;.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byAmount?amount_parameter=100 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!--
Response to the request.

```

{
    "content": [
        {
            "PKey": "<PKEY>",
            "builtIn": false,
            "created": "2019-09-26 09:36:01.014Z",
            "desc": "",
            "end": "",
            "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
            ...
        }
    ],
}

```

-->

<!-- exemple à vérifier de bout en bout-->

<!--+category = query editor
privacy ?
displayFOrmat ?
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
-->





<!--
 if link ou collection.* resName +
* resTarget tout ca, ca va ensemble : le système de lien, resTarget va donner la ressource targetée par le lien. type
resType = type technique (long..) resType = link alors unbound='false' ou 'true'
If type = enumeration alors champ "values" rajouté et les valeurs sont dans values
pour faire un POST sur une enum, il faut lui passer le @name décrit dans le noeud values, chaque @name a une correspondance en format = au format définit par le resType
ail faut que la valeur poster soit conforme ,elle doit valider la dataPolicy . La dataPolicy peut soit controler la valeur (email invalide), soit transformé (cas du smartCase par exemple)
type dans les metadata = type de haut-niveau (nombre, text)
-->
