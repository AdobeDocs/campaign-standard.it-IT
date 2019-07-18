---
title: Informazioni sulle notifiche push
seo-title: Informazioni sulle notifiche push
description: Informazioni sulle notifiche push
seo-description: Scopri le specificità principali del canale di notifica push in Adobe Campaign.
page-status-flag: never-activated
uuid: 961 aaeb 5-6948-4 fd 2-b 8 d 7-de 4510 c 10566
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: notifiche push
discoiquuid: 23 b 4212 e-e 878-4922-be 20-50 fb 7 fa 88 ae 8
context-tags: Mobileapp, panoramica
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 80e65c3fedc5452105c296144a683948daa69150

---


# About push notifications{#about-push-notifications}

>[!CAUTION]
>
>L'implementazione delle notifiche push deve essere eseguita da utenti esperti. Se devi essere assistito, contatta il tuo partner di servizi di Adobe o Executive Services. La notifica push è una funzione opzionale. Controllate il contratto di licenza e contattate il vostro account executive per attivarlo.

Adobe Campaign consente di inviare notifiche push personalizzate e segmentate ai dispositivi mobili iOS e Android.

Questi messaggi vengono ricevuti sulle applicazioni mobili configurate in Adobe Campaign sfruttando l'SDK di Experience Cloud Mobile SDK V 4 o Experience Platform. For more information on this, refer to [Configuring a mobile application using SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) and [Configuring a mobile application using Adobe Experience Platform SDKs](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications' subscribers.

Questa risorsa deve essere estesa per raccogliere i dati che intendi inviare dal dispositivo mobile ad Adobe Campaign. To do so, refer to this [page](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) for the detailed steps.

In Adobe Campaign sono disponibili due tipi di notifica push:

* **[!UICONTROL Alert/Message/Badge]** Le notifiche di tipo consentono di inviare messaggi standard basati su testo con contenuto aggiuntivo (audio, badge, collegamento profondo ecc.) that you can define in the **[!UICONTROL Advanced options]** section.

   Questo tipo di notifica consente di aggiungere un titolo e un messaggio in cui potete utilizzare i campi di personalizzazione. To be able to personalize your message, make sure you select the **[!UICONTROL Send push on profiles]** template.

* **[!UICONTROL Silent push]** Le notifiche di tipo vengono utilizzate per inviare in modo invisibile all'applicazione senza messaggio o contenuto per l'utente finale. Un caso d'uso tipico per questo tipo di messaggio è fare in modo che l'applicazione sappia che è disponibile contenuto disponibile sul server.

Alcune configurazioni specifiche possono essere configurate per definire il comportamento delle notifiche. For more on this, refer to [this section](../../channels/using/customizing-a-push-notification.md).

As an expert user, to define these specific configurations, refer to the mobile app [technotes](https://helpx.adobe.com/campaign/kb/acs-article-list.html).

>[!NOTE]
>
>Le leggi sulla privacy differiscono per paese. Alcuni paesi richiedono di informare gli utenti dei tipi di dati raccolti dalle applicazioni mobili. Controllate le leggi pertinenti alle applicazioni mobili nel vostro paese. Assicurati che le notifiche push inviate alle applicazioni mobili siano conformi ai prerequisiti e alle condizioni specificate da Apple (Apple Push Notification Service) e Google (Google Cloud Messaging o Firebase Cloud Messaging).

**Contenuto correlato:**

* [Preparazione e invio di una notifica push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Creazione di una notifica push multilingue](../../channels/using/creating-a-multilingual-push-notification.md)
* [Invio di una notifica push all'interno di un flusso di lavoro](../../automating/using/push-notification-delivery.md)
* [Domande frequenti su push e in-app](https://helpx.adobe.com/campaign/kb/push_inapp_faq.html)

## Prerequisites {#prerequisites}

>[!NOTE]
>Per sfruttare la funzione di notifica push da Campaign, è necessario fornire un certificato push valido nel formato. pem senza password.
Se disponete di un certificato p 12 valido, potete convertirlo facilmente in un file. pem utilizzando le risorse online.

Innanzitutto, per iniziare a inviare le notifiche push, devi configurare l'applicazione mobile tramite SDK V 4. Puoi anche configurare la tua applicazione mobile utilizzando gli SDK della piattaforma Experience Platform. For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Prima di inviare le notifiche push, è necessario:

1. Make sure you can access the **[!UICONTROL Mobile app]** channel in Adobe Campaign.
1. Configura l'applicazione mobile in:

   * Adobe Campaign
   * Interfaccia di Adobe Mobile Services

1. Eseguite la configurazione specifica dell'applicazione mobile:

   * Crea un pacchetto con il file di configurazione scaricato dall'interfaccia di Adobe Mobile Services con l'applicazione mobile.
   * Integra l'SDK di Experience Cloud Mobile nell'applicazione mobile.

1. Definite i dati che desiderate raccogliere dagli abbonati dell'applicazione. Gli abbonati dell'applicazione mobile che hanno un profilo nel database Adobe Campaign vengono riconciliati in base ai criteri definiti.

Dopo aver configurato l'applicazione mobile, ora puoi iniziare a preparare e inviare i messaggi in-app. For more on this, refer to [Preparing and sending a push notification](../../channels/using/preparing-and-sending-a-push-notification.md).
