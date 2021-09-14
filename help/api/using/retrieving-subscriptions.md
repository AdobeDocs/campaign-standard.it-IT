---
title: Recupero di abbonamenti
description: Scopri come recuperare gli abbonamenti con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 6d935074-3196-45c5-97cd-ccb7c80bbba8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 2%

---

# Recupero di abbonamenti {#retrieving-subscriptions}

## Recupero dei profili abbonati a un servizio

Questa è una procedura in due fasi.

1. Recupera l’URL delle sottoscrizioni per il servizio desiderato.
1. Esegui una richiesta di GET sull’URL delle sottoscrizioni. Restituisce l’elenco delle sottoscrizioni per il servizio, con ciascun profilo associato.

>[!CAUTION]
>
>L’API REST restituisce la proprietà &quot;href&quot;, che contiene l’URL da utilizzare. <b>Utilizza sempre l’URL contenuto nella risposta per effettuare la successiva richiesta</b> API.

<br/>

***Richiesta di esempio***

Esegui una richiesta GET per recuperare il servizio.

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
    "name": "SVC1",
    "subscriptions": {
                "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>/subscriptions/"
    },
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

Viene visualizzato l’elenco degli abbonamenti al servizio, con ciascun profilo associato.

```
  {
    ...
    "service": ...,
    "serviceName": "SVC3",
    "subscriber": {
        "PKey": "<PKEY>",
        "email": "",
        "firstName": "John",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>",
        "lastName": "Doe",
    },
  }
```

## Recupero dei servizi a cui si è iscritto un profilo

Questa è una procedura in due fasi.

1. Recupera l’URL delle sottoscrizioni per un determinato profilo.
1. Esegui una richiesta di GET sull’URL. Restituisce l’elenco delle sottoscrizioni per il profilo, con ogni servizio associato.

<br/>

***Richiesta di esempio***

Esegui una richiesta di GET per recuperare il profilo.

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
    ...
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

Restituisce l’elenco dei servizi a cui il profilo si è iscritto.

```
  {
    ...
    "PKey": "<PKEY>",
    "created": "2017-03-03 10:54:00.363Z",
    "service": {
      "PKey": "<PKEY>",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
      "label": "Sport Newsletter",
      "name": "SVC1",
      "title": "Sport Newsletter (SVC1)"
    },
    ...
  }
```
