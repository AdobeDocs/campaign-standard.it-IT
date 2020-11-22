---
solution: Campaign Standard
product: campaign
title: Endpoint
description: Ulteriori informazioni sugli endpoint API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 10%

---


# Endpoint {#endpoints}

Gli endpoint disponibili per  API REST di Adobe Campaign:

* **/profileAndServices**: interagisci con i campi out-of-box. I campi estesi non sono accessibili con questo endpoint.
* **/profileAndServicesExt**: interagisci con i campi personalizzati aggiunti durante l&#39;estensione di risorse personalizzata Profilo o Servizi. For more on custom resources, refer to [this section](../../api/using/custom-resources.md).
* **/&lt;transactionalAPI>**: interagisci con l&#39;API dei messaggi transazionali (il nome dell&#39;endpoint API dei messaggi transazionali dipende dalla configurazione dell&#39;istanza). Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/managing-transactional-messages.md).
* **/workflow/esecuzione**: interagisci con i flussi di lavoro. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/controlling-a-workflow.md).
* **/privacy/privacyTool**: interagisci con l’API per la privacy per consentire il processo automatico delle richieste di privacy. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../api/using/creating-a-privacy-request.md).
* **/history**: recupera la cronologia di marketing dei profili. Per ulteriori informazioni sui profili cliente integrati in Campaign, consulta la documentazione [di](https://helpx.adobe.com/campaign/standard/audiences/using/integrated-customer-profile.html)Campaign.

Per impostazione predefinita, le risorse principali disponibili per le API **profileAndServices** e **profileAndServicesExt** sono:

* **/profile**: interagisci con i profili provenienti dal database Campaign. Per aggiungere profili a un servizio, utilizzate l&#39;endpoint **/servizio** . Per ulteriori informazioni sui profili in Campaign, consulta la documentazione [relativa alla](https://helpx.adobe.com/campaign/standard/audiences/using/about-profiles.html)campagna.
* **/service**: gestire i servizi di iscrizione. Per ulteriori informazioni sui servizi in Campaign, consulta la documentazione [relativa alla](https://helpx.adobe.com/campaign/standard/audiences/using/creating-a-service.html)campagna.

>[!NOTE]
>
>Tutte le altre risorse che sono state estese o create sono disponibili solo tramite l&#39;API **ProfileAndServicesExt** . Per essere accessibili, devono essere collegati alla risorsa **Profilo** .
