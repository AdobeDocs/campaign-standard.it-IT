---
solution: Campaign Standard
product: campaign
title: Risorse personalizzate
description: Ulteriori informazioni sulla gestione delle risorse personalizzate con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 3%

---


# Interazione con risorse personalizzate {#interacting-with-custom-resources}

L’endpoint **/customResources** ti consente di esporre le risorse personalizzate di Campaign in REST. In base a questa API, è disponibile un’integrazione tra entità personalizzate e endpoint esterni.

L&#39;endpoint /customResources ha esattamente lo stesso comportamento dell&#39;endpoint /profileAndServices .

Le risorse personalizzate esposte in questa API sono:

* tutte le entità collegate all’entità profilo
* tutte le entità collegate agli elementi figlio dell’entità profilo
* tutte le entità che non sono collegate al profilo e, per queste entità, i loro figli e nipoti.

>[!NOTE]
>Le risorse personalizzate disponibili in /profileAndServicesExt non sono esposte nell&#39;API /customResources.

Ecco un esempio per recuperare i metadati da una risorsa personalizzata:

```
GET /customResources/resourceType/<customResourceName>
```

Per eseguire una creazione, un aggiornamento o un’eliminazione, vengono utilizzati GET, POST, PATCH e DELETE.

```
POST /customResources/<customResourceName>
```

>[!NOTE]
>L’endpoint e i flussi di lavoro API per la privacy (/privacy/privacyTool) non gestiscono le risorse personalizzate non collegate all’entità profilo.
>Sarà tua responsabilità gestire e ripulire eventuali PII per queste risorse personalizzate. Per ulteriori informazioni sullo strumento per la privacy, [fai clic qui](../../api/using/creating-a-privacy-request.md).

