---
title: Creazione di un servizio
seo-title: Creazione di un servizio
description: Creazione di un servizio
seo-description: Scoprite come creare il vostro primo servizio e configurarlo per inviare le conferme e-mail ai vostri abbonati.
page-status-flag: mai attivato
uuid: 0d95d852-0f22-4b7b-b301-8fb4844c3ca2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: gestione delle sottoscrizioni
discoiquuid: 6b7788fe-fa6c-472a-97db-765595ce1589
context-tags: servizio,procedura guidata;servizio,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: da59fad19bcf35b63afdfc6389be527c27f21fc3

---


# Creazione di un servizio{#creating-a-service}

Per poter gestire le iscrizioni, è innanzitutto necessario creare un servizio e configurarlo. La configurazione di un nuovo servizio consente di specificare le conferme e-mail che i profili riceveranno al momento dell’iscrizione o dell’annullamento dell’iscrizione al servizio. Verranno inoltre definite le pagine di destinazione di iscrizione e annullamento dell'iscrizione collegate al servizio. Ad esempio, un collegamento di iscrizione a un servizio inserito in un messaggio e-mail indirizza automaticamente il profilo alla pagina di destinazione dell'iscrizione specificata nel servizio.

Per configurare un servizio:

1. Dal menu avanzato **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Services]** tramite il logo Adobe Campaign, aggiungi un nuovo servizio o seleziona un servizio esistente. Se create un nuovo servizio, seguite semplicemente i passaggi indicati sullo schermo.

   È disponibile un modello di servizio predefinito. Questo modello è preconfigurato con pagine di destinazione predefinite ed e-mail di conferma. Potete creare altri modelli per definire configurazioni specifiche. Per ulteriori informazioni, consulta la sezione [Gestione dei modelli](../../start/using/about-templates.md) .

1. Nella **[!UICONTROL Service properties]** sezione, a cui si accede tramite il ![](assets/edit_darkgrey-24px.png) pulsante nel dashboard del servizio, configurate i messaggi di conferma per le sottoscrizioni e le sottoscrizioni.

   ![](assets/lp_service_parameters.png)

1. Fill in the  field. **[!UICONTROL Service label]** L'etichetta del servizio è obbligatoria quando si utilizza un messaggio di conferma personalizzato.

1. Selezionate un modello di messaggio di conferma per iscrizioni e annullamento delle iscrizioni. Sono disponibili tre modalità:

   * **[!UICONTROL No message]**: this mode allows you to create a service without a confirmation message.
   * **[!UICONTROL Default message]**: this mode will use the default subscription or unsubscription confirmation transactional message. The default confirmation messages are generic and will be the same for all services that use the default mode.

      >[NOTE]
      >
      >You can modify a default message by clicking its label in the  section or by selecting it from the Adobe Campaign transactional message list, after checking the  box.**[!UICONTROL Service properties]****[!UICONTROL Show internal transactional messages]**

   * **[!UICONTROL Custom message]**: questa modalità consente di gestire messaggi di conferma personalizzati, specifici per ogni servizio. You then select the  which is associated with a specific transactional message template. **[!UICONTROL Custom subscription event configuration]**[](../../channels/using/about-transactional-messaging.md) For more on this, see [Confirming subscription to a service](../../audiences/using/confirming-subscription-to-a-service.md).

1. Salvate il servizio. È ora pronto per essere utilizzato.

Once a service has been created, you can start promoting it.

**Related topics:**

* [Managing a service and subscriptions video](https://helpx.adobe.com/campaign/kt/acs/using/acs-services-and-subscriptions-feature-video-use.html)
* [Promoting a service](../../audiences/using/promoting-a-service.md)
* [Creating an audience made of subscribers](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [Collegamento di un modulo a un servizio in una pagina di destinazione](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service)

