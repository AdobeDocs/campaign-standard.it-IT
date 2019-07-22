---
title: Configurazione di un'applicazione mobile
seo-title: Configurazione di un'applicazione mobile
description: Configurazione di un'applicazione mobile
seo-description: Scopri come configurare Adobe Campaign per l'invio di notifiche push o messaggi in-app tramite SDK V 4 o Experience Platform SDK.
page-status-flag: never-activated
uuid: 63 e 1476 a -7875-4 f 48-ba 9 e -97 f 1 a 0007 e 42
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: riferimento
topic-tags: configuring-channels
discoiquuid: 2 a 14500 f -5 ede -4131-8 b 1 a-b 7 fd 65 b 7 e 3 aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b9799c40bd7b6422409456db2c4f694f486b42f8

---


# Configuring a mobile application{#configuring-a-mobile-application}

Le notifiche push o i messaggi in-app vengono ricevuti nelle applicazioni mobili che devono prima essere configurate in Adobe Mobile Services a seconda del canale che desideri utilizzare.

* Per inviare messaggi in-app e notifiche push, le applicazioni mobili devono essere configurate in Adobe Campaign sfruttando gli SDK della piattaforma Adobe Experience Platform. See [Using Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk).

* Per inviare solo notifiche push, puoi configurare l'integrazione tra Adobe Campaign e Adobe Mobile Services tramite SDK V 4. See [Using SDK V4](#using-sdk-v4).

After your mobile applications are set up in Adobe Campaign by leveraging the Experience Cloud Mobile SDK V4 or Experience Platform SDK, they need to be configured by an administrator under the [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] menu.

>[!CAUTION]
>
>Le notifiche push e le implementazioni in-app devono essere eseguite da utenti esperti. Se devi essere assistito, contatta il tuo partner di servizi di Adobe o Executive Services.

## Using Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

Per inviare notifiche push e messaggi in-app con l'applicazione Experience Platform SDK, un'applicazione mobile deve essere configurata in Adobe Experience Platform Experience Platform Experience Platform Launch e configurata in Adobe Campaign. For the detailed steps to configure your mobile application using Experience Platform SDK, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Segui i passaggi seguenti per avviare la configurazione:

1. Make sure you can access the **[!UICONTROL Mobile]** channels: Push notification and In-App message in Adobe Campaign. In caso contrario, contattate il team di account.

   ![](assets/launch_1.png)

1. Crea l'applicazione mobile in Experience Platform Launch creando una proprietà di tipo Mobile. For more info, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) documentation.
1. Install the **[!UICONTROL Adobe Campaign (Beta)]** extension for your mobile application in Experience Platform Launch:

   For more information on extensions, refer to the [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard-beta) documentation.

1. Configure rules for your application in Adobe Launch, see [Configuring your application in Launch](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ConfiguringyourapplicationinLaunch)
1. Configure your Adobe Launch application in Adobe Campaign Standard, see [Setting up your Adobe Launch application in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Add channel specific configuration to your Mobile Application set-up, see [Channel-specific application configuration in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)

## Using SDK V4 {#using-sdk-v4}

La notifica push è supportata da SDK V 4 e SDK Adobe Experience Platform a differenza dell'app in-app. For the detailed steps to use push notifications with your mobile app, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Le applicazioni mobili che ricevono le notifiche push devono essere configurate da un amministratore nell'interfaccia di Adobe Campaign. Configurando sia Adobe Campaign che Adobe Mobile Services, potrai utilizzare i dati dell'applicazione mobile per le tue campagne.

Per poter inviare notifiche push, è necessario:

1. Make sure you can access the **[!UICONTROL Mobile app]** channel in Adobe Campaign.
1. Configura l'applicazione mobile in:

   * [Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign).
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices).

1. Eseguite la configurazione specifica dell'applicazione mobile:

   * Crea un pacchetto con il file di configurazione scaricato dall'interfaccia di Adobe Mobile Services con l'applicazione mobile.
   * Integra l'SDK di Experience Cloud Mobile nell'applicazione mobile.

1. Definite i dati che desiderate raccogliere dagli abbonati dell'applicazione. Gli abbonati dell'applicazione mobile che hanno un profilo nel database Adobe Campaign vengono riconciliati in base ai criteri definiti.

   For more on this, refer to this [page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication).

1. Accertatevi che la configurazione sia stata completata correttamente avviando l'applicazione mobile sul dispositivo e effettuando l'accesso. Assicurati di ricevere le notifiche.
1. Then, in Adobe Campaign's advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Seleziona l'applicazione mobile dall'elenco per visualizzarne le proprietà. Le informazioni di iscrizione vengono visualizzate sotto l'elenco degli abbonati.

   ![](assets/push_notif_mobile_app.png)

1. To check the mobile applications a profile has subscribed to, in the **[!UICONTROL Profiles & Audiences > Profiles]** menu, select a profile and click the **[!UICONTROL Edit profile properties]** button on the right. The mobile applications are listed in the **[!UICONTROL Mobile App Subscriptions]** tab.

   ![](assets/push_notif_subscriptions.png)