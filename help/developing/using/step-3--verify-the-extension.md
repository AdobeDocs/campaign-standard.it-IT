---
solution: Campaign Standard
product: campaign
title: '"Passaggio 3: verificare l’estensione"'
description: Scopri come accedere al campo esteso con l’API Rest.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 12%

---


# Passaggio 3: verificare l’estensione{#step-verify-the-extension}

1. Esegui un’operazione di GET sui metadati dell’API di estensione Profiles &amp; Services per verificare se il campo aggiunto nella risorsa personalizzata Profiles è ora disponibile.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Restituisce:

   ![](assets/extendpandsapiview.png)

   Il campo è ora disponibile per ulteriori sviluppi e integrazioni.

