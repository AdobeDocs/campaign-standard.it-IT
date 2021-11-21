---
title: Creazione di un servizio
description: Scopri come creare un servizio con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 91bbce9e-a618-4be2-840b-c7d021271f4e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 8%

---

# Creazione di un servizio {#creating-a-service}

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
