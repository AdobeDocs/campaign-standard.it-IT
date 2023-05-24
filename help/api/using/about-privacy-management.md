---
title: Informazioni sulla gestione della privacy
description: Ulteriori informazioni sulla gestione della privacy con le API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: 210289d44f0ad0ebf0b2654f6e9795adad7dd458
workflow-type: tm+mt
source-wordcount: '107'
ht-degree: 0%

---


# Informazioni sulla gestione della privacy {#about-privacy-management}

Le API Campaign Standard forniscono funzioni che consentono il processo automatico delle richieste relative alle normative sulla privacy come RGPD e CCPA.

È possibile eseguire le seguenti azioni:

* Creare una nuova richiesta di accesso a dati personali
* Monitorare una richiesta di accesso a dati personali
* Recuperare un file di dati sulla privacy
* Gestire lo stato di rinuncia CCPA di un profilo.

L’endpoint API per la privacy è **/privacy/privacyTool**. La descrizione della risorsa PrivacyTool e i filtri associati sono disponibili nei metadati della risorsa. Consulta [Meccanismo metadati](../../api/using/metadata-mechanism.md).

L’opt-out CCPA viene gestito utilizzando **ccpaOptOut** attributo di profilo.

Per ulteriori informazioni su Adobe Campaign Standard e sulla conformità in materia di privacy, consulta [documentazione dedicata](../../start/using/privacy-requests.md).
