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
ht-degree: 0%

---

# Interazione con risorse personalizzate {#interacting-with-custom-resources}

Il **/customResources** L’endpoint consente di esporre le risorse personalizzate di Campaign in REST. In base a questa API, è disponibile un’integrazione tra entità personalizzate ed endpoint esterni.

L’endpoint /customResources ha esattamente lo stesso comportamento dell’endpoint /profileAndServices.

Le risorse personalizzate esposte all’interno di questa API sono:

* tutte le entità non esposte in /profileAndServicesExt
* tutte le entità non collegate al profilo e, per tali entità, i figli e i nipoti.
* per impostazione predefinita, tutte le entità non collegate a nulla, nonché i relativi figli e nipoti.

>[!NOTE]
>Le risorse personalizzate disponibili in /profileAndServicesExt non sono esposte nell’API /customResources.


Di seguito è riportato un esempio per recuperare i metadati da una risorsa personalizzata:

```
GET /customResources/resourceType/<customResourceName>
```

Per eseguire una creazione, un aggiornamento o un’eliminazione, vengono utilizzati GET, POST, PATCH e DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>L’endpoint e i flussi di lavoro dell’API per la privacy (/privacy/privacyTool) non gestiscono le risorse personalizzate non collegate all’entità profilo.
>Avrai la responsabilità di gestire e ripulire eventuali PII per queste risorse personalizzate. Per ulteriori informazioni sullo strumento per la privacy, [fai clic qui](../../api/using/creating-a-privacy-request.md).
