---
title: Informazioni sui messaggi in-app
seo-title: Informazioni sui messaggi in-app
description: Informazioni sui messaggi in-app
seo-description: Visualizza un messaggio o un avviso nell'applicazione mobile con i messaggi in-app.
page-status-flag: never-activated
uuid: 6784 cdfc -6 db 9-41 dd -9 fbb -2 e 756 a 5 bcb 5 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: messaggistica in-app
discoiquuid: a 4168 cfb -22 bf -4 ab 3-b 9 d 8-6 e 76 e 1 bdc 055
context-tags: distribuzione, trigger, indietro
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 74f037ba618639ab61edfb8311adeb44a7a99ebd

---


# About In-App messaging{#about-in-app-messaging}

Messaggistica in-app è un canale di messaggistica che consente di visualizzare un messaggio quando l'utente è attivo nell'applicazione mobile. Questo tipo di messaggio è gratuito per le notifiche push inviate al centro notifiche del telefono degli utenti. For more information on the push notification channel, refer to this [section](../../channels/using/about-push-notifications.md).

Questo canale richiede che le applicazioni mobili siano integrate con Adobe Experience Platform SDK. Queste app devono essere attivate in Adobe Experience Platform Launch prima di essere disponibili in Adobe Campaign per le consegne in-app.

![](assets/launch_campaign.png)

Per iniziare a inviare messaggi in-app sulle applicazioni mobili che sfruttano l'SDK della piattaforma Experience Platform, devi soddisfare i prerequisiti seguenti:

1. In Adobe Campaign, make sure you can access the **[!UICONTROL In-App]** channel. Se non riuscite ad accedere a questi canali, contattate il team di account.
1. In Experience Platform Launch, create l'applicazione mobile creando una proprietà mobile e impostando la vostra app mobile con l'SDK della piattaforma Experience Platform.

   For more information, refer to the [Set up a mobile property](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property) section in Adobe Launch documentation.

1. In Experience Platform Launch, install the **[!UICONTROL Adobe Campaign Standard]** extension for your mobile application in Experience Platform Launch:

   For more on extensions, refer to the [Configure Campaign Standard Extension in Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) in Experience Platform Launch documentation.

1. In Experience Platform Launch, configure rules and data elements for your application, see [Configuring your application in Experience Platform Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)

1. Configure your Experience Platform Launch application in Adobe Campaign Standard, see [Setting up your Experience Platform Launch application in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign) .

To learn how to configure Experience Platform SDKs, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

**Contenuto correlato:**

* [Preparazione e invio di un messaggio in-app](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [Personalizzazione di un messaggio in-app](../../channels/using/customizing-an-in-app-message.md)
* [Personalizzazione di un tipo di messaggio di notifica locale](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)
* [Invio di un messaggio in-app all'interno di un flusso di lavoro](../../automating/using/in-app-delivery.md)
* [Domande frequenti su push e in-app](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)