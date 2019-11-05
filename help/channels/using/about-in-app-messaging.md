---
title: Informazioni sulla messaggistica in-app
description: Visualizza messaggi o avvisi all'interno dell'applicazione mobile con messaggi in-app.
page-status-flag: mai attivato
uuid: 6784cdfc-6db9-41dd-9fbb-2e756a5bcb5f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canali
content-type: reference
topic-tags: messaggi in-app
discoiquuid: a4168cfb-22bf-4ab3-b9d8-6e76e1bdc055
context-tags: consegna,trigger,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Informazioni sulla messaggistica in-app{#about-in-app-messaging}

Messaggistica in-app è un canale di messaggistica che consente di visualizzare un messaggio quando l'utente è attivo all'interno dell'applicazione mobile. Questo tipo di messaggio è complementare alle notifiche push inviate al centro di notifica del telefono degli utenti. Per ulteriori informazioni sul canale di notifica push, consulta questa [sezione](../../channels/using/about-push-notifications.md).

Questo canale richiede l’integrazione delle applicazioni mobili con l’SDK di Adobe Experience Platform. Queste app devono essere attivate in Adobe Experience Platform Launch prima di essere disponibili in Adobe Campaign per le consegne in-app.

![](assets/launch_campaign.png)

Per iniziare a inviare messaggi in-app sulle applicazioni mobili che utilizzano l’SDK della piattaforma Experience, devi soddisfare i seguenti prerequisiti:

1. In Adobe Campaign, assicurati di poter accedere al **[!UICONTROL In-App]** canale. Se non riuscite ad accedere a questi canali, contattate il team di account.

1. Per sfruttare i casi di utilizzo per dispositivi mobili in Adobe Campaign Standard con un'applicazione Experience Cloud SDK, è necessario creare un'app mobile in Adobe Experience Platform Launch e configurarla in Adobe Campaign Standard. Per la guida passo-passo, fai riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

1. Una volta configurato, ora puoi preparare il messaggio in-app. Per ulteriori informazioni, consultare questa [pagina](../../channels/using/preparing-and-sending-an-in-app-message.md#preparing-your-in-app-message).

1. Potete quindi decidere di inviare un messaggio [](../../channels/using/customizing-an-in-app-message.md) In-App o [Personalizzare un tipo](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)di messaggio di notifica locale.

1. La consegna è ora pronta per essere inviata. Per ulteriori informazioni, consultare questa [pagina](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message).

**Contenuto correlato:**

* [Report in-app](../../reporting/using/in-app-report.md)
* [Domande frequenti su push e in-app](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)
* [Casi di utilizzo per dispositivi mobili supportati in Adobe Campaign Standard](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)
