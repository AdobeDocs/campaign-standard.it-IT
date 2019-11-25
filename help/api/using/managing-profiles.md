---
title: Gestione dei profili
description: Scopri come gestire i profili con le API.
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Gestione dei profili {#managing-profiles}

## Recupero dei profili

Il recupero dei profili viene eseguito con una richiesta **GET** .

Potete quindi perfezionare la ricerca utilizzando filtri, ordine e impaginazione. Per ulteriori informazioni, consulta la sezione [Ulteriori operazioni](../../api/using/sorting.md) .

<br/>

***Richieste di esempio***

* Esempio di richiesta GET per recuperare tutti i profili.

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

* Esempio di richiesta GET per recuperare i primi 10 valori e-mail.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Risposta alla richiesta. Il nodo "successivo" restituisce l’URL che consente di accedere ai 10 valori e-mail successivi.

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

## Aggiornamento profili

L'aggiornamento dei profili viene eseguito con una richiesta **PATCH** .

`https://mc.adobe.io/<ORGANIZATION>/campaign/<apiName>/<resourceName>/<PKEY>`

1. Il primo passaggio consiste nel **recuperare il profilo**.

1. In una seconda richiesta, eseguiremo una richiesta **** PATCH sul profilo con le informazioni completate nel payload.

1. Per verificare se la richiesta PATCH ha aggiornato il profilo, possiamo eseguire una richiesta GET finale.

<br/>

***Richiesta di esempio***

Esempio di richiesta GET per recuperare un profilo.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY>\
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
            "firstName": "Amy",
            "lastName":"Dakota",
            "birthDate": "1980-10-24",
            ...
        }
    ]
}
```

Richiesta PATCH per aggiornare l'attributo "phone".

```
-X PATCH https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/<PKEY> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-d '{"phone":"3301020304"}'
```

Restituisce l’PKEY e l’URL per recuperare il profilo aggiornato.

```
{
    "PKey": "<PKEY>",
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/@2v1dr3ZKJveMDhAdh0MPnh9hNQQ93qb7AW6BNVVKknjwXvTZRBAgUqz1SNcB4ZndgjqOofx3BwBZYBftlmObISoM3rs"
}
```

## Creazione di profili

La creazione dei profili viene eseguita con una richiesta **POST** sulla risorsa del profilo.

>[!CAUTION]
>
>Se si desidera associare un <b>orgUnit</b> al profilo creato, è necessario estendere la risorsa del profilo a questo campo e, dopo la pubblicazione dell'estensione, eseguire una richiesta POST sull'endpoint <b>ProfileAndServicesExt</b> .
>
>Per ulteriori informazioni sull'estensione delle risorse del profilo, consulta la documentazione relativa alla <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">campagna</a>.

<br/>

***Richiesta di esempio***

Esempio di richiesta POST per creare un profilo con l’e-mail "john.doe@mail.com".

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Restituisce il profilo appena creato, con l'indirizzo e-mail "john.doe@mail.com".

```
{
    "PKey": "<PKEY>",
    "firstName": "John",
    "lastName":"Doe",
    "birthDate": "1980-10-24",
    "email": "john.doe@mail.com",
    ...
}
```
