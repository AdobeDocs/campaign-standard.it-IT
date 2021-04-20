---
solution: Campaign Standard
product: campaign
title: Gestione dell’opt-out CCPA
description: Scopri come gestire la rinuncia CCPA con le API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 4%

---


# Gestione dell’opt-out CCPA {#managing-ccpa-optout}

Lo stato di rinuncia CCPA di un profilo può essere monitorato e gestito utilizzando l&#39;attributo di profilo **ccpaOptOut** e i valori &quot;true&quot; o &quot;false&quot;:

`"ccpaOptOut": <value>`

* **true**: vieta la vendita di informazioni personali.
* **false**: autorizza la vendita di informazioni personali.

>[!CAUTION]
>
>L’attributo &quot;Rinuncia CCPA&quot; è disponibile solo a partire dalla versione 19.4. Per gli ambienti 19.3, è necessario estendere la risorsa Profiles e aggiungere un campo booleano. Questo campo verrà aggiunto all’API con l’etichetta selezionata. Ti consigliamo di utilizzare &quot;Rinuncia per CCPA&quot;.
>
>Per ulteriori informazioni, consulta la [documentazione sulla gestione delle richieste di accesso a dati personali](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa) .

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

   Risposta alla richiesta GET.

   ```
   {
   "PKey": "<PKEY>",
     "ccpaOptOut": false,
     "firstName": "John",
     "lastName": "Doe",
   ...
   }
   ```

* Esempio di richiesta POST per contrassegnare un profilo per la rinuncia a CCPA.

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

   Risposta alla richiesta GET.

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

* Esempio di richiesta PATCH per aggiornare un profilo per la rinuncia a CCPA.

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

   Risposta alla richiesta GET.

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
