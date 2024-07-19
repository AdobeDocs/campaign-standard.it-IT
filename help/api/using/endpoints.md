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
source-wordcount: '225'
ht-degree: 11%

---

# Endpoint {#endpoints}

Gli endpoint disponibili per l’API REST di Adobe Campaign:

* **/profileAndServices**: interagire con campi predefiniti. I campi estesi non sono accessibili con questo endpoint.
* **/profileAndServicesExt**: interagire con i campi personalizzati aggiunti durante l&#39;estensione della risorsa personalizzata Profile o Services. Per ulteriori informazioni sulle risorse personalizzate, consulta [questa sezione](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI>**: interagire con l&#39;API dei messaggi transazionali (il nome dell&#39;endpoint dell&#39;API dei messaggi transazionali dipende dalla configurazione dell&#39;istanza). Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/managing-transactional-messages.md).
* **/workflow/execution**: interagire con i flussi di lavoro. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interagire con l&#39;API della privacy per consentire il processo automatico delle richieste di privacy. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/creating-a-privacy-request.md).
* **/history**: recupera la cronologia di marketing dei profili. Per ulteriori informazioni sui profili cliente integrati in Campaign, consulta la [documentazione di Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html).

Per impostazione predefinita, le risorse principali disponibili per le API **profileAndServices** e **profileAndServicesExt** sono:

* **/profile**: interagire con i profili dal database di Campaign. Per aggiungere profili a un servizio, utilizzare l&#39;endpoint **/servizio**. Per ulteriori informazioni sui profili in Campaign, consulta la [documentazione di Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html).
* **/servizio**: gestisci i servizi di abbonamento. Per ulteriori informazioni sui servizi in Campaign, consulta la [documentazione di Campaign](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html).

>[!NOTE]
>
>Tutte le altre risorse estese o create sono disponibili solo tramite API **ProfileAndServicesExt**. Per essere accessibili, devono essere collegati alla risorsa **Profilo**.
