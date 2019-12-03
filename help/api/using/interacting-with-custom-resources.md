---
title: Risorse personalizzate
description: Ulteriori informazioni sulla gestione delle risorse personalizzate con API/
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff05128d664db7afba57b020f59b9a98fc656f56

---


# Interazione con risorse personalizzate {#interacting-with-custom-resources}

L'endpoint **/customResources** consente di esporre le entità personalizzate ACS in REST. In base a questa API, è disponibile un'integrazione tra entità personalizzate e endpoint esterni.

L'endpoint /customResources ha esattamente lo stesso comportamento dell'endpoint /profileAndServices.

Le entità personalizzate esposte in questa API sono:

* tutte le entità collegate all'entità profilo
* tutte le entità collegate agli elementi secondari dell'entità profilo
* tutte le entità che non sono collegate al profilo e, per queste entità, ai loro figli e nipoti.

>[!NOTE]
>Le entità personalizzate disponibili in /profileAndServicesExt non sono esposte nell'API /customResources.

Di seguito è riportato un esempio per recuperare i metadati da una risorsa personalizzata:

```
GET /customResources/resourceType/<customResourceName>
```

Per eseguire una creazione, un aggiornamento o un'eliminazione, vengono utilizzati GET, POST, PATCH, DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>L'endpoint e i flussi di lavoro dell'API per la privacy (Privacy/PrivacyTool) non gestiscono le risorse personalizzate non collegate all'entità profilo.
>Avrai la responsabilità di gestire e ripulire qualsiasi PII per queste risorse personalizzate. Per maggiori informazioni sullo strumento per la privacy, [fai clic qui](../../api/using/creating-a-privacy-request.md).

