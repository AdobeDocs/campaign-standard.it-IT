---
title: Informazioni sulla gestione della privacy
description: Ulteriori informazioni sulla gestione della privacy con le API
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '112'
ht-degree: 4%

---


# Informazioni sulla gestione della privacy {#about-privacy-management}

Le API di Campaign Standard forniscono funzionalità che consentono il processo automatico delle richieste relative alle normative sulla privacy come RGPD e CCPA.

Le azioni che puoi eseguire sono le seguenti:

* Creare una nuova richiesta di accesso a dati personali,
* Monitorare una richiesta di accesso a dati personali,
* Recuperare un file di dati sulla privacy,
* Gestisci lo stato di rinuncia CCPA di un profilo.

L&#39;endpoint API per la privacy è **/privacy/privacyTool**. La descrizione della risorsa PrivacyTool e i filtri associati sono disponibili nei metadati della risorsa. Vedere [Meccanismo metadati](../../api/using/metadata-mechanism.md).

La rinuncia al CCPA viene gestita utilizzando l&#39;attributo di profilo **ccpaOptOut** .

Per ulteriori informazioni su Adobe Campaign Standard e sulla conformità in materia di privacy, consulta la [documentazione dedicata](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html).
