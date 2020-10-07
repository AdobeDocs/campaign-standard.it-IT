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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 3%

---


# Creazione di profili {#creating-profiles}

La creazione dei profili viene eseguita con una richiesta **POST** sulla risorsa del profilo.

>[!CAUTION]
>
>Se si desidera associare un <b>orgUnit</b> al profilo creato, è necessario estendere la risorsa del profilo a questo campo e, dopo la pubblicazione dell&#39;estensione, eseguire una richiesta POST sull&#39;endpoint <b>ProfileAndServicesExt</b> .
>
>Per ulteriori informazioni sull&#39;estensione delle risorse del profilo, consulta la documentazione relativa alla <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">campagna</a>.

<br/>

***Richiesta di esempio***

Esempio di richiesta di POST per creare un profilo con l’e-mail &quot;john.doe@mail.com&quot;.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Restituisce il profilo appena creato, con l&#39;indirizzo e-mail &quot;john.doe@mail.com&quot;.

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
