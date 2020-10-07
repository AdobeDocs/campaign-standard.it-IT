---
title: '"Passaggio 3: verificare l’estensione"'
description: Scopri come accedere al campo esteso con l’API Rest.
page-status-flag: never-activated
uuid: 35ba89a5-a354-466f-91a0-50de111a2e00
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 13%

---


# Passaggio 3: verificare l’estensione{#step-verify-the-extension}

1. Effettuate un&#39;operazione sui metadati dell&#39;API Profili e servizi di estensione per verificare se il campo aggiunto nella risorsa personalizzata Profili è ora disponibile.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Restituisce:

   ![](assets/extendpandsapiview.png)

   Il campo è ora disponibile per ulteriori sviluppi e integrazioni.

