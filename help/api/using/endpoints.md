---
title: Endpoint
description: Ulteriori informazioni sugli endpoint API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 554bf4a441a0fb4daea3c5eddd95b0197ca12ae6

---


# Endpoint {#endpoints}

Gli endpoint disponibili per l'API REST di Adobe Campaign:

* **/profileAndServices**: interagisci con i campi out of the box. I campi estesi non sono accessibili con questo endpoint.
* **/profileAndServicesExt**: interagisci con i campi personalizzati aggiunti durante l'estensione di risorse personalizzata Profilo o Servizi. For more on custom resources, refer to [this section](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI&gt;**: interagisci con l'API dei messaggi transazionali (il nome dell'endpoint API dei messaggi transazionali dipende dalla configurazione dell'istanza). For more on this, refer to [this section](../../api/using/managing-transactional-messages.md).
* **/workflow/esecuzione**: interagisci con i flussi di lavoro. For more on this, refer to [this section](../../api/using/managing-workflows.md).
* **/privacy/privacyTool**: interagisci con l’API per la privacy per consentire il processo automatico delle richieste di privacy. For more on this, refer to [this section](../../api/using/privacy-management.md).
* **/history**: recuperare la cronologia di marketing dei profili. Per ulteriori informazioni sui profili cliente integrati in Campaign, consulta la documentazione [di](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)Campaign.

Per impostazione predefinita, le risorse principali disponibili per le API **profileAndServices** e **profileAndServicesExt** sono:

* **/profile**: interagisci con i profili provenienti dal database Campaign. Per aggiungere profili a un servizio, utilizzate l'endpoint **/servizio** . Per ulteriori informazioni sui profili in Campaign, consulta la documentazione [relativa alla](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)campagna.
* **/service**: gestire i servizi di iscrizione. Per ulteriori informazioni sui servizi in Campaign, consulta la documentazione [relativa alla](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)campagna.

>[!NOTE]
>
>Tutte le altre risorse che sono state estese o create sono disponibili solo tramite l'API **ProfileAndServicesExt** . Per essere accessibili, devono essere collegati alla risorsa **Profilo** .
