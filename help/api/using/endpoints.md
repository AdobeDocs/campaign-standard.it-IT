---
title: Endpoint
description: Ulteriori informazioni sugli endpoint API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9f6d3da6-374d-47f5-bc8f-b31b19cbb5ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 10%

---

# Endpoint {#endpoints}

Gli endpoint disponibili per l’API REST di Adobe Campaign:

* **/profileAndServices**: interagisci con i campi predefiniti. I campi estesi non sono accessibili con questo endpoint.
* **/profileAndServicesExt**: interagisci con i campi personalizzati aggiunti durante l’estensione della risorsa personalizzata Profilo o Servizi . Per ulteriori informazioni sulle risorse personalizzate, consulta [questa sezione](../../api/using/custom-resources.md).
* **/&lt;transactionalapi>**: interagisci con l’API dei messaggi transazionali (il nome dell’endpoint API dei messaggi transazionali dipende dalla configurazione dell’istanza). Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/managing-transactional-messages.md).
* **/workflow/execute**: interagisci con i flussi di lavoro. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interagisci con l’API per la privacy per consentire il processo automatico delle richieste di privacy. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/creating-a-privacy-request.md).
* **/history**: recupera la cronologia di marketing dei profili. Per ulteriori informazioni sui profili cliente integrati in Campaign, consulta [Documentazione di Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

Per impostazione predefinita, le risorse principali disponibili per **profileAndServices** e **profileAndServicesExt** Le API sono:

* **/profile**: interagisci con i profili dal database Campaign. Per aggiungere profili a un servizio, utilizza la funzione **/service** punto finale. Per ulteriori informazioni sui profili in Campaign, consulta la [Documentazione di Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**: gestire i servizi di abbonamento. Per ulteriori informazioni sui servizi in Campaign, consulta la [Documentazione di Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Tutte le altre risorse che sono state estese o create sono disponibili tramite **ProfileAndServicesExt** Solo API. Devono essere collegati al **Profilo** per essere accessibile.
