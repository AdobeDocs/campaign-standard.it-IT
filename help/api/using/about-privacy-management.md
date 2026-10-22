---
title: Informazioni sulla gestione della privacy
description: Ulteriori informazioni sulla gestione della privacy con le API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 0%
---

# Informazioni sulla gestione della privacy {#about-privacy-management}

Le API di Campaign Standard forniscono funzioni che consentono il processo automatico delle richieste relative alle normative sulla privacy come RGPD e CCPA.

È possibile eseguire le seguenti azioni:

* Creare una nuova richiesta di accesso a dati personali
* Monitorare una richiesta di accesso a dati personali
* Recuperare un file di dati sulla privacy
* Gestire lo stato di rinuncia CCPA di un profilo.

L&#39;endpoint API per la privacy è **/privacy/privacyTool**. La descrizione della risorsa PrivacyTool e i filtri associati sono disponibili nei metadati della risorsa. Consulta [Meccanismo metadati](../../api/using/metadata-mechanism.md).

La rinuncia CCPA viene gestita utilizzando l&#39;attributo di profilo **ccpaOptOut**.

Per ulteriori informazioni su Adobe Campaign Standard e sulla conformità in materia di privacy, consulta la [documentazione dedicata](../../start/using/privacy-requests.md).
