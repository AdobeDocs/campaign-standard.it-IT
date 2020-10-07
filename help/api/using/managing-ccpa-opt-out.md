---
title: Gestione dell’opt-out CCPA
description: Scoprite come gestire il rifiuto CCPA con le API
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
source-wordcount: '153'
ht-degree: 3%

---


# Gestione dell’opt-out CCPA {#managing-ccpa-optout}

Lo stato di rifiuto CCPA di un profilo può essere monitorato e gestito utilizzando l&#39;attributo di profilo **ccpaOptOut** e i valori &quot;true&quot; o &quot;false&quot;:

`"ccpaOptOut": <value>`

* **true**:  vieta la vendita di informazioni personali.
* **false**: autorizza la vendita di informazioni personali.

>[!CAUTION]
>
>L&#39;attributo &quot;Rinuncia CCPA&quot; è disponibile solo a partire dalla versione 19.4. Per gli ambienti 19.3, è necessario estendere la risorsa Profili e aggiungere un campo booleano. Questo campo verrà aggiunto all&#39;API con l&#39;etichetta selezionata. Vi consigliamo di utilizzare &quot;Opt-Out for CCPA&quot;.
>
>For more on this, refer to the [Privacy management documentation](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa).

<br/>

***Richieste di esempio***

* Richiesta di GET di esempio per recuperare lo stato di rifiuto CCPA di un profilo.

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

* Esempio di richiesta di POST per contrassegnare un profilo per la rinuncia CCPA.

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

* Esempio di richiesta di PATCH per aggiornare un profilo per la rinuncia CCPA.

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
