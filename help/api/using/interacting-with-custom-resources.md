---
solution: Campaign Standard
product: campaign
title: Risorse personalizzate
description: Ulteriori informazioni sulla gestione delle risorse personalizzate con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---


# Interazione con risorse personalizzate {#interacting-with-custom-resources}

L&#39;endpoint **/customResources** consente di esporre le risorse personalizzate ACS in REST. In base a questa API, è disponibile un&#39;integrazione tra entità personalizzate e endpoint esterni.

L&#39;endpoint /customResources ha esattamente lo stesso comportamento dell&#39;endpoint /profileAndServices.

Le risorse personalizzate esposte in questa API sono:

* tutte le entità collegate all&#39;entità profilo
* tutte le entità collegate agli elementi secondari dell&#39;entità profilo
* tutte le entità che non sono collegate al profilo e, per queste entità, ai loro figli e nipoti.

>[!NOTE]
>Le risorse personalizzate disponibili in /profileAndServicesExt non sono esposte nell&#39;API /customResources.

Di seguito è riportato un esempio per recuperare i metadati da una risorsa personalizzata:

```
GET /customResources/resourceType/<customResourceName>
```

Per eseguire una creazione, un aggiornamento o un&#39;eliminazione, vengono utilizzati GET, POST, PATCH, DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>L&#39;endpoint e i flussi di lavoro dell&#39;API per la privacy (/privacy/privacyTool) non gestiscono le risorse personalizzate non collegate all&#39;entità profilo.
>Avrai la responsabilità di gestire e ripulire qualsiasi PII per queste risorse personalizzate. Per maggiori informazioni sullo strumento per la privacy, [fai clic qui](../../api/using/creating-a-privacy-request.md).

