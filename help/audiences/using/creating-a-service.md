---
title: Creazione di un servizio
seo-title: Creazione di un servizio
description: Creazione di un servizio
seo-description: Scopri come creare il primo servizio e configurarlo per inviare conferme e-mail agli abbonati.
page-status-flag: never-activated
uuid: 0 d 95 d 852-0 f 22-4 b 7 b-b 301-8 fb 4844 c 3 ca 2
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: audience
content-type: riferimento
topic-tags: gestione iscrizioni
discoiquuid: 6 b 7788 fe-fa 6 c -472 a -97 db -765595 ce 1589
context-tags: service, wizard; service, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Creating a service{#creating-a-service}

Per poter gestire le iscrizioni, occorre innanzitutto creare un servizio e configurarlo. La configurazione di un nuovo servizio consente di specificare le conferme e-mail ricevute dai profili per l'iscrizione o la cancellazione dal servizio. Verranno inoltre definite le pagine di iscrizione e annullamento dell'iscrizione collegate al servizio. Ad esempio, un collegamento di iscrizione del servizio inserito in un'e-mail indirizzerà automaticamente il profilo alla pagina di destinazione di iscrizione specificata nel servizio.

Per configurare un servizio:

1. From the advanced menu **Profiles &amp; audiences** &gt; **Services** via the Adobe Campaign logo, add a new service or select an existing service. Se create un nuovo servizio, seguite semplicemente i passaggi indicati sullo schermo.

   È disponibile un modello di servizio predefinito. Questo modello è preconfigurato con pagine di destinazione predefinite e e-mail di conferma. Potete creare altri modelli per definire configurazioni specifiche. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. In the **Service properties** section, accessed via the ![](assets/edit_darkgrey-24px.png) button in the service dashboard, configure the confirmation messages for subscriptions and unsubscriptions.

   ![](assets/lp_service_parameters.png)

1. Selezionate un modello di messaggio di conferma per iscrizioni e annullamento delle sottoscrizioni. Sono disponibili tre modalità:

   * **[!UICONTROL No message]**: Questa modalità consente di creare un servizio senza un messaggio di conferma.
   * **[!UICONTROL Default message]**: Questa modalità utilizza il messaggio predefinito di conferma o annullamento dell'iscrizione. I messaggi di conferma predefiniti sono generici e saranno identici per tutti i servizi che utilizzano la modalità predefinita.
   * **[!UICONTROL Custom message]**: Questa modalità consente di gestire i messaggi di conferma personalizzati, specifici per ogni servizio. You then select the **[!UICONTROL Custom subscription event configuration]** which is associated with a specific transactional message template. Refer to [Transactional messages](../../channels/using/about-transactional-messaging.md) for more information on transactional event and message configuration.

1. Salvate il servizio. Ora è pronto per essere utilizzato.

Una volta creato un servizio, potete iniziare a promuoverlo.

**Argomenti correlati:**

* [Gestione di un video di servizi e iscrizioni](https://helpx.adobe.com/campaign/kt/acs/using/acs-services-and-subscriptions-feature-video-use.html)
* [Promozione di un servizio](../../audiences/using/promoting-a-service.md)
* [Creazione di un pubblico composto da utenti iscritti](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [Collegamento di un modulo a un servizio in una pagina di destinazione](../../channels/using/designing-a-landing-page.md#linking-a-form-to-a-service)

