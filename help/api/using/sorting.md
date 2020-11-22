---
solution: Campaign Standard
product: campaign
title: Ordinamento
description: Ulteriori informazioni su come eseguire le operazioni di ordinamento
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 11%

---


# Ordinamento

L’ordinamento è disponibile in ordine crescente o decrescente. A questo scopo, utilizzate il parametro **%20desc** o **%20asc** per la richiesta.

Per verificare se è possibile ordinare un campo, controllate il parametro &quot;ordinabile&quot; nei metadati della risorsa. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/metadata-mechanism.md).

<br/>

***Richieste di esempio***

* Esempio di richiesta di GET per recuperare i messaggi e-mail nel database in ordine alfabetico.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email/email?_order=email \
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

* Esempio di richiesta di GET per recuperare l’e-mail nel database in ordine alfa decrescente.

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
