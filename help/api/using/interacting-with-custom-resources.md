---
title: Interazione con risorse personalizzate
description: Ulteriori informazioni sulla gestione delle risorse personalizzate con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 19bfeecb-da60-479c-a929-0cfb72ef59e3
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 0%
---
# Interazione con risorse personalizzate {#interacting-with-custom-resources}

L&#39;endpoint **/customResources** consente di esporre le risorse personalizzate di Campaign in REST. In base a questa API, è disponibile un’integrazione tra entità personalizzate ed endpoint esterni.

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

Per eseguire una creazione, un aggiornamento o un’eliminazione, vengono utilizzati GET, POST, PATCH, DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>L’endpoint e i flussi di lavoro dell’API per la privacy (/privacy/privacyTool) non gestiscono le risorse personalizzate non collegate all’entità profilo.
>Avrai la responsabilità di gestire e ripulire eventuali PII per queste risorse personalizzate. Per ulteriori informazioni sullo strumento per la privacy, [fai clic qui](../../api/using/creating-a-privacy-request.md).
