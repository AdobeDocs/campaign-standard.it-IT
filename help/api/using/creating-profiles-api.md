---
title: Creazione di profili con API
description: Scopri come creare profili con API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 69e8d034-6bdd-4b82-bcd7-1ef4be0a59b3
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '108'
ht-degree: 0%

---

# Creazione di profili con API {#creating-profiles-api}

La creazione di profili viene eseguita con un **POST** nella risorsa profilo.

>[!CAUTION]
>
>Per associare un <b>orgUnit</b> al profilo creato, devi estendere la risorsa profilo con questo campo e, dopo la pubblicazione dell’estensione, eseguire una richiesta POST sul <b>ProfileAndServicesExt</b> punto finale.
>
>Per ulteriori informazioni sull’estensione della risorsa del profilo, consulta la <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles">Documentazione di Campaign</a>.

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
