---
title: Creazione di un servizio con API
description: Scopri come creare un servizio con API
feature: API
role: Data Engineer
level: Experienced
exl-id: 91bbce9e-a618-4be2-840b-c7d021271f4e
source-git-commit: 02f1ef1f960cf98b5277b2db960e61ae20e22209
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 0%

---

# Creazione di un servizio con API{#creating-a-service-api}

Creazione di servizi eseguita con una richiesta **POST** nella risorsa del servizio.

Se desideri creare il servizio con attributi specifici, aggiungili al payload. In caso contrario, il nuovo servizio verrà creato con quelli predefiniti.

<br/>

***Richiesta di esempio***

Esempio di richiesta POST per creare un servizio con attributi specifici.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/ \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
-i
-d {
-d "label": "My newsletter",
-d "messageType": "email",
-d "name": "email_newsletter",
-d "start": "2019-10-06"
-d }
```

Restituisce il servizio appena creato con gli attributi aggiornati.

```
{
    "PKey": "<PKEY>",
    "builtIn": false,
    "created": "2019-09-26 12:00:37.005Z",
    "href": "https://mc.adobe.io/<ORGANIZATION>/profileAndServices/service/@NLscZuVHxdVu9rPftvrMWFfR1zRIxQGswSOmGLrK09JTF_iWhB0JCUHEndA_vvy__k9mzOYa5NVkcWDcrK8qGh0wygahX9kRcD44kiWWSEceShn3",
    "label": "My newsletter",
    ...
}
```
