---
title: '"Passaggio 3: verificare l’estensione"'
description: Scopri come accedere al campo esteso con l’API Rest.
page-status-flag: mai attivato
uuid: 35ba89a5-a354-466f-91a0-50de111a2e00
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: development
content-type: reference
topic-tags: use-case—extension-the-api
discoiquuid: 21bad242-5921-445c-8df9-3d57dbe35197
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Passaggio 3: verificare l’estensione{#step-verify-the-extension}

1. Effettuate un'operazione GET sui metadati dell'API Profili e servizi di estensione per verificare se il campo aggiunto nella risorsa personalizzata Profili è ora disponibile.

   ```
   GET profileAndServicesExt/resourceType/profile
   ```

1. Restituisce:

   ![](assets/extendpandsapiview.png)

   Il campo è ora disponibile per ulteriori sviluppi e integrazioni.

