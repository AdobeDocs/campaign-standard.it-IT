---
title: Gestione dell’opt-out CCPA
description: Scopri come gestire la rinuncia al CCPA con le API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: bfc52511-f66f-4948-a939-d0d77e8ef03c
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 6%

---

# Gestione dell’opt-out CCPA {#managing-ccpa-optout}

Lo stato di rinuncia CCPA di un profilo può essere monitorato e gestito utilizzando l&#39;attributo di profilo **ccpaOptOut** e i valori &quot;true&quot; o &quot;false&quot;:

`"ccpaOptOut": <value>`

* **true**: impedisce la vendita di informazioni personali.
* **false**: autorizza la vendita di informazioni personali.

<!--The “CCPA Opt-Out” attribute is only available starting 19.4. For 19.3 environments, you need to extend the Profiles resource and add a boolean field. This field will be added to the API with the chosen label. We suggest you use “Opt-Out for CCPA”.
>
>For more on this, refer to the [Managing Privacy requests documentation](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).-->

<br/>

***Richieste di esempio***

* Richiesta di GET di esempio per recuperare lo stato di rinuncia CCPA di un profilo.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8'
  ```

  Risposta alla richiesta di GET.

  ```
  {
  "PKey": "<PKEY>",
    "ccpaOptOut": false,
    "firstName": "John",
    "lastName": "Doe",
  ...
  }
  ```

* Richiesta POST di esempio per contrassegnare un profilo per la rinuncia CCPA.

  ```
  -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/ \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8'
  -i
  -d {
  -d  "firstName": "John",
  -d  "lastName": "Doe",
  -d  "email": "jdoe@mail.com",
  -d  "ccpaOptOut": true
  -d }'
  ```

  Risposta alla richiesta di GET.

  ```
  {
      ...
      "email": "john.doe@mail.com",
      "firstName": "John",
      "lastName": "Doe",
      "ccpaOptOut": true,
      ...
  }
  ```

* Richiesta PATCH di esempio per aggiornare un profilo per la rinuncia CCPA.

  ```
  -X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profilesAndServices/profile/<PKEY> \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8'
  -i
  -d {
  -d  "ccpaOptOut": true
  -d }'
  ```

  Risposta alla richiesta di GET.

  ```
  {
      ...
      "email": "john.doe@mail.com",
      "firstName": "John",
      "lastName": "Doe",
      "ccpaOptOut": true,
      ...
  }
  ```
