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
source-git-commit: 3b7da7df5092476be4c6acc21b2ad2472a80da83

---


# Configurazione di un'applicazione mobile{#configuring-a-mobile-application}

Le notifiche push o i messaggi in-app vengono ricevuti nelle applicazioni mobili che devono prima essere configurate in Adobe Mobile Services a seconda del canale che desideri utilizzare.

* Per inviare messaggi in-app e notifiche push, le applicazioni mobili devono essere configurate in Adobe Campaign sfruttando gli SDK della piattaforma Adobe Experience Platform. Consultate [Utilizzo dell'SDK Adobe Experience Platform](#using-adobe-experience-platform-sdk).

* Per inviare solo notifiche push, puoi configurare l'integrazione tra Adobe Campaign e Adobe Mobile Services tramite SDK V 4. Consultate [Utilizzo dell'SDK V 4](#using-sdk-v4).

Dopo che le applicazioni mobili sono state configurate in Adobe Campaign sfruttando l'SDK di Experience Cloud Mobile SDK V 4 o Experience Platform, devono essere configurate da un amministratore nel menu [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] .

>[!CAUTION]
>
>Le notifiche push e le implementazioni in-app devono essere eseguite da utenti esperti. Se devi essere assistito, contatta il tuo partner di servizi di Adobe o Executive Services.

Una volta configurato un'applicazione mobile, potete recuperare i dati PII raccolti per creare o aggiornare profili dal database. Per ulteriori informazioni, consulta questa sezione: [Creazione e aggiornamento di informazioni sul profilo basate sui dati dell'applicazione mobile](../../channels/using/updating-profile-with-mobile-app-data.md).

## Utilizzo dell'SDK Adobe Experience Platform {#using-adobe-experience-platform-sdk}

>[!Note]
>
>Per ulteriori informazioni sui diversi casi di utilizzo per dispositivi mobili supportati in Adobe Campaign Standard mediante gli SDK di Adobe Experience Platform, fai riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

Per inviare notifiche push e messaggi in-app con l'applicazione Experience Platform SDK, un'applicazione mobile deve essere configurata in Adobe Experience Platform Experience Platform Experience Platform Launch e configurata in Adobe Campaign. Per i passaggi dettagliati per configurare l'applicazione mobile utilizzando l'SDK della piattaforma Experience Platform, fai riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Segui i passaggi seguenti per avviare la configurazione:

1. Assicuratevi di poter accedere ai **[!UICONTROL Mobile]** canali: Notifica push e messaggio in-app in Adobe Campaign. In caso contrario, contattate il team di account.

   ![](assets/launch_1.png)

1. Crea l'applicazione mobile in Experience Platform Launch creando una proprietà di tipo Mobile. Per ulteriori informazioni, consulta la documentazione della piattaforma [Experience Platform.](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property)
1. Installa l **[!UICONTROL Adobe Campaign Standard]** 'estensione per l'applicazione mobile in Experience Platform Launch:

   Per ulteriori informazioni sulle estensioni, consulta la documentazione sulla piattaforma [Experience Platform.](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard)

1. Configurazione delle regole per l'applicazione in Adobe Launch, consultate [Configurazione dell'applicazione in Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. Configura l'applicazione Adobe Launch in Adobe Campaign Standard, consultate [Configurazione dell'applicazione Adobe Launch in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Aggiungi configurazione specifica del canale al set di applicazioni per dispositivi mobili, consulta [Configurazione dell'applicazione specifica per il canale in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)

## Utilizzo dell'SDK V 4 {#using-sdk-v4}

La notifica push è supportata da SDK V 4 e SDK Adobe Experience Platform a differenza dell'app in-app. Per i passaggi dettagliati per utilizzare le notifiche push con la tua app mobile, fai riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Le applicazioni mobili che ricevono le notifiche push devono essere configurate da un amministratore nell'interfaccia di Adobe Campaign. Configurando sia Adobe Campaign che Adobe Mobile Services, potrai utilizzare i dati dell'applicazione mobile per le tue campagne.

Per poter inviare notifiche push, è necessario:

1. Assicurati di poter accedere al **[!UICONTROL Mobile app]** canale in Adobe Campaign.
1. Configura l'applicazione mobile in:

   * [Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign).
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices).

1. Eseguite la configurazione specifica dell'applicazione mobile:

   * Crea un pacchetto con il file di configurazione scaricato dall'interfaccia di Adobe Mobile Services con l'applicazione mobile.
   * Integra l'SDK di Experience Cloud Mobile nell'applicazione mobile.

1. Definite i dati che desiderate raccogliere dagli abbonati dell'applicazione. Gli abbonati dell'applicazione mobile che hanno un profilo nel database Adobe Campaign vengono riconciliati in base ai criteri definiti.

   Per ulteriori informazioni, consultate questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication).

1. Accertatevi che la configurazione sia stata completata correttamente avviando l'applicazione mobile sul dispositivo e effettuando l'accesso. Assicurati di ricevere le notifiche.
1. Quindi, nel menu avanzato di Adobe Campaign, seleziona **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Seleziona l'applicazione mobile dall'elenco per visualizzarne le proprietà. Le informazioni di iscrizione vengono visualizzate sotto l'elenco degli abbonati.

   ![](assets/push_notif_mobile_app.png)

1. Per controllare a quante applicazioni mobili si è iscritto un profilo, nel **[!UICONTROL Profiles & Audiences > Profiles]** menu selezionate un profilo e fate clic sul **[!UICONTROL Edit profile properties]** pulsante a destra. Le applicazioni mobili sono elencate nella **[!UICONTROL Mobile App Subscriptions]** scheda.

   ![](assets/push_notif_subscriptions.png)