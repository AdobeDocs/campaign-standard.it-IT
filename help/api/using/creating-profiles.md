---
solution: Campaign Standard
product: campaign
title: Creazione di profili
description: Scopri come creare profili con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 3%

---


# Creazione di profili {#creating-profiles}

La creazione dei profili viene eseguita con una richiesta **POST** sulla risorsa del profilo.

>[!CAUTION]
>
>Se si desidera associare una <b>orgUnit</b> al profilo creato, è necessario estendere la risorsa del profilo a questo campo e, dopo la pubblicazione dell&#39;estensione, eseguire una richiesta POST sull&#39;endpoint <b>ProfileAndServicesExt</b>.
>
>Per ulteriori informazioni sull&#39;estensione delle risorse del profilo, fare riferimento alla <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Documentazione campagna</a>.

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
