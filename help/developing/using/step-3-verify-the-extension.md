---
title: "Passaggio 3: verificare l’estensione"
description: Scopri come accedere al campo esteso con l’API Rest.
audience: developing
content-type: reference
topic-tags: use-case-extending-the-api
feature: Data Model
role: Developer
level: Experienced
exl-id: 34cb416c-ee3d-4b7c-a75b-640432db320d
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '61'
ht-degree: 8%

---

# Passaggio 3: verificare l’estensione{#step-verify-the-extension}

1. Esegui un’operazione di GET sui metadati dell’API di estensione Profiles &amp; Services per verificare se il campo aggiunto nella risorsa personalizzata Profiles è ora disponibile.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Restituisce:

   ![](assets/extendpandsapiview.png)

   Il settore è ora disponibile per ulteriori sviluppi e integrazioni.
