---
solution: Campaign Standard
product: campaign
title: Creazione di profili
description: Scopri come creare profili con API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 4%

---


# Creazione di profili {#creating-profiles}

La creazione di profili viene eseguita con una richiesta **POST** sulla risorsa profilo.

>[!CAUTION]
>
>Se desideri associare un <b>orgUnit</b> al profilo creato, devi estendere la risorsa profilo a questo campo e, dopo la pubblicazione dell’estensione, eseguire una richiesta POST sull’endpoint <b>ProfileAndServicesExt</b> .
>
>Per ulteriori informazioni sull’estensione della risorsa del profilo, consulta la <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">documentazione della campagna</a>.

<br/>

***Richiesta di esempio***

Esempio di richiesta POST per creare un profilo con l’e-mail &quot;john.doe@mail.com&quot;.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{"email":"john.doe@mail.com"}'
```

Restituisce il profilo appena creato, con l’indirizzo e-mail &quot;john.doe@mail.com&quot;.

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
