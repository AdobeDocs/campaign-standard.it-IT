---
title: Creazione di profili
description: Scopri come creare profili con le API.
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


# Creazione di profili {#creating-profiles}

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
