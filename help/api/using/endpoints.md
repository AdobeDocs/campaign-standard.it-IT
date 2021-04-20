---
solution: Campaign Standard
product: campaign
title: Endpoint
description: Ulteriori informazioni sugli endpoint API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '247'
ht-degree: 10%

---


# Endpoint {#endpoints}

Gli endpoint disponibili per l’API REST di Adobe Campaign:

* **/profileAndServices**: interagisci con i campi predefiniti. I campi estesi non sono accessibili con questo endpoint.
* **/profileAndServicesExt**: interagisci con i campi personalizzati aggiunti durante l’estensione della risorsa personalizzata Profilo o Servizi . Per ulteriori informazioni sulle risorse personalizzate, consulta [questa sezione](../../api/using/custom-resources.md).
* **/&lt;transactionalapi>**: interagisci con l’API dei messaggi transazionali (il nome dell’endpoint API dei messaggi transazionali dipende dalla configurazione dell’istanza). Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/managing-transactional-messages.md).
* **/workflow/esecuzione**: interagisci con i flussi di lavoro. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interagisci con l’API per la privacy per consentire il processo automatico delle richieste di privacy. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/creating-a-privacy-request.md).
* **/cronologia**: recupera la cronologia di marketing dei profili. Per ulteriori informazioni sui profili cliente integrati in Campaign, consulta la [documentazione di Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

Per impostazione predefinita, le risorse principali disponibili per le API **profileAndServices** e **profileAndServicesExt** sono:

* **/profile**: interagisci con i profili dal database Campaign. Per aggiungere profili a un servizio, utilizza l&#39;endpoint **/service** . Per ulteriori informazioni sui profili in Campaign, consulta la [documentazione della campagna](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/service**: gestire i servizi di abbonamento. Per ulteriori informazioni sui servizi in Campaign, consulta la [documentazione della campagna](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Tutte le altre risorse che sono state estese o create sono disponibili solo tramite l&#39;API **ProfileAndServicesExt** . Per essere accessibili, devono essere collegati alla risorsa **Profilo** .
