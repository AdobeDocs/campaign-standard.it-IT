---
title: Creazione di un servizio
description: Scopri come creare un servizio con le API
feature: API
role: Data Engineer
level: Experienced
exl-id: 91bbce9e-a618-4be2-840b-c7d021271f4e
source-git-commit: 64f24fb692754973331b4fb2f7b95e9a6f31cd0d
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 4%

---

# Creazione di un servizio con API{#creating-a-service-api}

La creazione di servizi viene eseguita con un **POST** richiesta sulla risorsa del servizio.

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
