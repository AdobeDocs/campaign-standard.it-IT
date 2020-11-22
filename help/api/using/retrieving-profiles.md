---
solution: Campaign Standard
product: campaign
title: Recupero profili
description: Ulteriori informazioni su come recuperare i profili con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 4%

---


# Recupero profili {#retrieving-profiles}

Il recupero dei profili viene eseguito con una richiesta di **GET** .

Potete quindi perfezionare la ricerca utilizzando filtri, ordine e impaginazione. For more on this, refer to the [Additional operations](../../api/using/sorting.md) section.

<br/>

***Richieste di esempio***

* Esempio di richiesta di GET per recuperare tutti i profili.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
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
           },
           ...
   }
   ```

* Esempio di richiesta di GET per recuperare i primi 10 valori e-mail.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Risposta alla richiesta. Il nodo &quot;successivo&quot; restituisce l’URL che consente di accedere ai 10 valori e-mail successivi.

   ```
   {
   "content": [
       "amy.dakota@mail.com",
       "kristen.smith@mail.com",
       "omalley@mail.com",
       "xander.harrys@mail.com",
       "jane.summer@mail.com",
       "gloria.boston@mail.com",
       "edward.snow@mail.com",
       "dorian.simons@mail.com",
       "peter.paolini@mail.com",
       "mingam+test08@adobe.com"
   ],
   "next": {
       "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
       lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
   }
   }
   ```
