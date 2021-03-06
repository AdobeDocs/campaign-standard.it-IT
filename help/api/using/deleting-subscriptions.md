---
title: Eliminazione di abbonamenti
description: Scopri come eliminare gli abbonamenti con le API
feature: API
role: Data Engineer
level: Experienced
exl-id: 76e2d102-c877-41a6-af87-2f407201a572
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 0%

---

# Eliminazione di abbonamenti con API {#mdeleting-subscriptions-api}

<!--NOTE TO WRITER: There are two duplicate headings that seem to have the same content. Delete one? Rename if different?-->

## Eliminazione di una sottoscrizione di servizio per un profilo specifico {#deleting-service-subscription}

Questa è una procedura in tre fasi.

1. Recupera l’URL delle sottoscrizioni per il profilo desiderato.
1. Esegui una richiesta di GET sull’URL delle sottoscrizioni.
1. Esegui una richiesta DELETE sull’URL di servizio desiderato.

Se la richiesta di cancellazione ha esito positivo, lo stato della risposta è 204 Nessun contenuto.

<br/>

***Richiesta di esempio***

I payload di esempio riportati di seguito mostrano come annullare l’abbonamento di un profilo a un servizio. Esegui prima una richiesta GET per recuperare il profilo.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l’URL delle sottoscrizioni per il profilo.

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

Esegui una richiesta di GET sull’URL delle sottoscrizioni.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l’elenco delle sottoscrizioni per il profilo selezionato, con un URL per ogni servizio con sottoscrizione.

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

Esegui una richiesta DELETE sull’URL di servizio desiderato.

```
-X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- + réponse -->

## Eliminazione di una sottoscrizione di servizio per un profilo specifico

Questa è una procedura in tre fasi.

1. Recupera il servizio desiderato e il relativo URL di abbonamento.
1. Esegui una richiesta di GET sull’URL delle sottoscrizioni per recuperare tutte le sottoscrizioni di profili.
1. Esegui una richiesta di DELETE sull’URL di sottoscrizione del profilo desiderato.

Se la richiesta di cancellazione ha esito positivo, lo stato della risposta è 204 Nessun contenuto.

<br/>

***Richiesta di esempio***

Recupera il record del servizio.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l’URL delle sottoscrizioni per il servizio.

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

Esegui una richiesta di GET sull’URL delle sottoscrizioni.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l’elenco delle sottoscrizioni per il servizio selezionato, con un URL (href) per ogni abbonamento al profilo.

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

Esegui una richiesta di DELETE sull’URL di sottoscrizione del profilo desiderato.

```
-X DELETE https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- + réponse -->
