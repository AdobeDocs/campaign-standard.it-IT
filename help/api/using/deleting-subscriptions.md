---
title: Eliminazione di abbonamenti
description: Scoprite come eliminare le iscrizioni con le API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: dd0ec1a114df43606f2ba7555bad6982047b640e
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%

---


# Eliminazione di abbonamenti {#mdeleting-subscriptions}

<!--NOTE TO WRITER: There are two duplicate headings that seem to have the same content. Delete one? Rename if different?-->

## Eliminazione di una sottoscrizione di servizio per un profilo specifico {#deleting-service-subscription}

Si tratta di una procedura in tre fasi.

1. Recuperate l&#39;URL delle iscrizioni per il profilo desiderato.
1. Eseguite una richiesta di GET sull&#39;URL delle iscrizioni.
1. Eseguite una richiesta DELETE sull&#39;URL del servizio desiderato.

Se la richiesta di eliminazione ha esito positivo, lo stato della risposta è 204 Nessun contenuto.

<br/>

***Richiesta di esempio***

I payload di esempio riportati di seguito mostrano come annullare l’iscrizione di un profilo da un servizio. Eseguire innanzitutto una richiesta di GET per recuperare il profilo.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l&#39;URL delle sottoscrizioni per il profilo.

```
  {
    ...
    "postalAddress":...,
    "preferredLanguage": "none",
    "subscriptions": {
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions/"
    },
  }
```

Eseguite una richiesta di GET sull&#39;URL delle iscrizioni.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l&#39;elenco delle sottoscrizioni per il profilo selezionato, con un URL per ciascun servizio con iscrizione.

```
...
"service": {
  "PKey": "<PKEY>",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
  "label": "Sport Newsletter",
  "name": "SVC1",
  "title": "Sport Newsletter (SVC1)"
},
...
```

Eseguite una richiesta DELETE sull&#39;URL del servizio desiderato.

```
-X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- + réponse -->

## Eliminazione di una sottoscrizione di servizio per un profilo specifico

Si tratta di una procedura in tre fasi.

1. Recuperate il servizio desiderato e il relativo URL di iscrizione.
1. Eseguite una richiesta di GET sull&#39;URL delle sottoscrizioni per recuperare tutte le sottoscrizioni di profili.
1. Eseguite una richiesta di DELETE sull&#39;URL di iscrizione profilo desiderato.

Se la richiesta di eliminazione ha esito positivo, lo stato della risposta è 204 Nessun contenuto.

<br/>

***Richiesta di esempio***

Recuperare il record del servizio.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l&#39;URL delle iscrizioni per il servizio.

```
{
  ...
  "messageType": "email",
  "mode": "newsletter",
  "name": "SVC3",
  "subScenarioEventType": "subscriptionEvent",
  "subscriptions": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
  },
  "targetResource": "profile",
  ...
},
```

Eseguite una richiesta di GET sull&#39;URL delle iscrizioni.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l&#39;elenco delle sottoscrizioni per il servizio selezionato, con un URL (href) per ogni iscrizione al profilo.

```
{
  "PKey": "<PKEY>",
  "created": "2019-03-26 08:58:04.764Z",
  "email": "",
  "expirationDate": "",
  "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/<PKEY>",
  "metadata": "subscriptionRcp",
  "service": ...,
  "serviceName": "SVC3",
  "subscriber": ...,
  ...
}
```

Eseguite una richiesta di DELETE sull&#39;URL di iscrizione profilo desiderato.

```
-X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- + réponse -->
