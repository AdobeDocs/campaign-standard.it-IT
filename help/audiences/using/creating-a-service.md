---
title: Creazione di un servizio
description: Scoprite come creare il vostro primo servizio e configurarlo per inviare le conferme e-mail ai vostri abbonati.
page-status-flag: never-activated
uuid: 0d95d852-0f22-4b7b-b301-8fb4844c3ca2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
discoiquuid: 6b7788fe-fa6c-472a-97db-765595ce1589
context-tags: service,wizard;service,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: de16bef6cfd0afa3f664c98fe77484044aac6610

---


# Creazione di un servizio{#creating-a-service}

Per poter gestire le iscrizioni, è innanzitutto necessario creare un servizio e configurarlo. La configurazione di un nuovo servizio consente di specificare le conferme e-mail che i profili riceveranno al momento dell’iscrizione o dell’annullamento dell’iscrizione al servizio. Verranno inoltre definite le pagine di destinazione di iscrizione e annullamento dell&#39;iscrizione collegate al servizio. Ad esempio, un collegamento di iscrizione a un servizio inserito in un messaggio e-mail indirizza automaticamente il profilo alla pagina di destinazione dell&#39;iscrizione specificata nel servizio.

Per configurare un servizio:

1. Dal menu avanzato **[!UICONTROL Profiles & audiences]**>**[!UICONTROL Services]** tramite il logo Adobe Campaign, aggiungi un nuovo servizio o seleziona un servizio esistente. Se create un nuovo servizio, seguite semplicemente i passaggi indicati sullo schermo.

   È disponibile un modello di servizio predefinito. Questo modello è preconfigurato con pagine di destinazione predefinite ed e-mail di conferma. Potete creare altri modelli per definire configurazioni specifiche. Per ulteriori informazioni, consulta la sezione [Gestione dei modelli](../../start/using/marketing-activity-templates.md) .

1. Nella **[!UICONTROL Service properties]**sezione, a cui si accede tramite il![](assets/edit_darkgrey-24px.png)pulsante nel dashboard del servizio, configurate i messaggi di conferma per le sottoscrizioni e le sottoscrizioni.

   ![](assets/lp_service_parameters.png)

1. Selezionate l’ **[!UICONTROL Subscriptions with an expiration date]**opzione per impostare una durata di validità per l’iscrizione.

   ![](assets/lp_service_expiration.png)

Puoi utilizzare la data di scadenza in un&#39;attività di segmentazione per eseguire il targeting dei profili sottoscritti per un servizio non scaduto.

1. Compila il **[!UICONTROL Service label]**campo. L&#39;etichetta del servizio è obbligatoria quando si utilizza un messaggio di conferma personalizzato.

1. Selezionate un modello di messaggio di conferma per iscrizioni e annullamento delle iscrizioni. Sono disponibili tre modalità:

   * **[!UICONTROL No message]**: questa modalità consente di creare un servizio senza un messaggio di conferma.
   * **[!UICONTROL Default message]**: in questa modalità verrà utilizzato il messaggio transazionale di conferma dell&#39;iscrizione o dell&#39;annullamento dell&#39;iscrizione. I messaggi di conferma predefiniti sono generici e saranno identici per tutti i servizi che utilizzano la modalità predefinita.

      >[!NOTE]
      >
      >Puoi modificare un messaggio predefinito facendo clic sulla relativa etichetta nella **[!UICONTROL Service properties]**sezione o selezionandolo dall&#39;elenco dei messaggi transazionali di Adobe Campaign, dopo aver selezionato la**[!UICONTROL Show internal transactional messages]** casella.

   * **[!UICONTROL Custom message]**: questa modalità consente di gestire messaggi di conferma personalizzati, specifici per ogni servizio. Quindi seleziona il**[!UICONTROL Custom subscription event configuration]** quale è associato a un modello di messaggio [](../../channels/using/about-transactional-messaging.md) transazionale specifico. Per ulteriori informazioni, consultate [Conferma dell’iscrizione a un servizio](../../audiences/using/confirming-subscription-to-a-service.md).

1. Salvate il servizio. È ora pronto per essere utilizzato.

Una volta creato il servizio, potete iniziare a promuoverlo.

**Argomenti correlati:**

* [Gestione di un servizio e delle iscrizioni](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/services-and-subscriptions.html) video
* [Promozione di un servizio](../../audiences/using/promoting-a-service.md)
* [Creazione di un&#39;audience composta da abbonati](../../audiences/using/creating-audiences.md#creating-list-audiences)
* [Collegamento di una pagina di destinazione a un servizio](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)
