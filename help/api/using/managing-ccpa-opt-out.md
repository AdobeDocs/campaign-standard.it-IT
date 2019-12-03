---
title: Gestione del rifiuto CCPA
description: Scoprite come gestire il rifiuto CCPA con le API
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Gestione del rifiuto CCPA {#managing-ccpa-optout}

Lo stato di rifiuto CCPA di un profilo può essere monitorato e gestito utilizzando l'attributo di profilo **ccpaOptOut** e i valori "true" o "false":

`"ccpaOptOut": <value>`

* **true**:  vieta la vendita di informazioni personali.
* **false**: autorizza la vendita di informazioni personali.

>[!CAUTION]
>
>L'attributo "Rinuncia CCPA" è disponibile solo a partire dalla versione 19.4. Per gli ambienti 19.3, è necessario estendere la risorsa Profili e aggiungere un campo booleano. Questo campo verrà aggiunto all'API con l'etichetta selezionata. Vi consigliamo di utilizzare "Opt-Out for CCPA".
>
>Per ulteriori informazioni, consulta la documentazione [sulla gestione della](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa)privacy.

<br/>

***Richieste di esempio***

* Esempio di richiesta GET per recuperare lo stato di rifiuto CCPA di un profilo.

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

* Esempio di richiesta POST per contrassegnare un profilo per la rinuncia CCPA.

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

* Richiesta PATCH di esempio per aggiornare un profilo per il rifiuto CCPA.

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
