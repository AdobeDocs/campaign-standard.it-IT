---
title: Ordinamento
description: Scopri come eseguire le operazioni di ordinamento
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 7db25b8d-a6f1-4151-bf37-c47e9991ae48
source-git-commit: 0c8710b3e1cc679fa907758a4bf5542d892c737c
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 11%

---

# Ordinamento

L’ordinamento è disponibile in ordine crescente o decrescente. A tale scopo, utilizza **%20desc** o **%20asc** parametro della richiesta.

Per sapere se un campo può essere ordinato, controlla il parametro &quot;sortable&quot; nei metadati della risorsa. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/metadata-mechanism.md).

<br/>

***Richieste di esempio***

* Richiesta di GET di esempio per recuperare le e-mail nel database in ordine alfabetico.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20asc \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Risposta alla richiesta.

  ```
  {
  "content": [
      "adam@email.com",
      "allison.durance@example.com",
      "amy.dakota@mail.com",
      "andrea.johnson@mail.com",
      ...
  ]
  ...
  }
  ```

* Richiesta di GET di esempio per recuperare l’e-mail nel database in ordine alfabetico decrescente.

  ```
  -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_order=email%20desc \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>'
  ```

  Risposta alla richiesta.

  ```
  {
  "content": [
      "tombinder@example.com",
      "tombinder@example.com",
      "timross@example.com",
      "john.smith@example.com",
      ...
  ]
  }
  ```
