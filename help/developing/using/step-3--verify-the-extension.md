---
solution: Campaign Standard
product: campaign
title: '"Passaggio 3: verificare l’estensione"'
description: Scopri come accedere al campo esteso con l’API Rest.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
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

