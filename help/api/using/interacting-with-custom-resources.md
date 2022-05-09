---
title: Interazione con risorse personalizzate
description: Ulteriori informazioni sulla gestione delle risorse personalizzate con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 4%

---

# Interazione con risorse personalizzate {#interacting-with-custom-resources}

La **/customResources** l’endpoint ti consente di esporre le risorse personalizzate Campaign in REST. Based on this API, an integration between custom entities and external endpoints is available.

The /customResources endpoint has exactly the same behavior as /profileAndServices endpoint.

Le risorse personalizzate esposte in questa API sono:

* all the entities that are not exposed under /profileAndServicesExt
* tutte le entità che non sono collegate al profilo e, per queste entità, i loro figli e nipoti.
* by default, all entities that are not linked to anything, and their children and grandchildren.

>[!NOTE]
>Le risorse personalizzate disponibili in /profileAndServicesExt non sono esposte nell&#39;API /customResources.


Here is an example to retrieve the metadata from a custom resource:

```
GET /customResources/resourceType/<customResourceName>
```

To perform a creation, update or deletion, the GET, POST, PATCH, DELETE are used.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>L’endpoint e i flussi di lavoro API per la privacy (/privacy/privacyTool) non gestiscono le risorse personalizzate non collegate all’entità profilo.
>Sarà tua responsabilità gestire e ripulire eventuali PII per queste risorse personalizzate. For more information on privacy tool, [click here](../../api/using/creating-a-privacy-request.md).
