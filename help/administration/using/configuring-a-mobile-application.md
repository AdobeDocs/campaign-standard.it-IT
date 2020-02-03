---
title: Configurazione di un’applicazione mobile
description: Scopri come configurare Adobe Campaign per l'invio di notifiche push o messaggi in-app tramite SDK V4 o l'SDK della piattaforma Experience.
page-status-flag: never-activated
uuid: 63e1476a-7875-4f48-ba9e-97f1a0007e42
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 2a14500f-5ede-4131-8b1a-b7fd65b7e3aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aa1539a1fc5fd08e7cf4e081ae2517e39ddde121

---


# Configurazione di un’applicazione mobile{#configuring-a-mobile-application}

Le notifiche push o i messaggi in-app vengono ricevuti su applicazioni mobili che devono essere configurate in Adobe Campaign Standard per la prima volta a seconda del canale che si desidera utilizzare.

Per inviare messaggi in-app e notifiche push, le tue applicazioni mobili devono essere configurate in Adobe Campaign sfruttando gli SDK di Adobe Experience Platform. Consultate [Utilizzo di Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk).

Dopo che le applicazioni mobili sono state configurate in Adobe Campaign sfruttando l’SDK di Experience Cloud Mobile V4 o Experience Platform, devono essere configurate da un amministratore nel [!UICONTROL Administration] > [!UICONTROL Channels] > [!UICONTROL Mobile app] menu.

>[!CAUTION]
>
>Le notifiche push e le implementazioni in-app devono essere eseguite da utenti esperti. Se avete bisogno di assistenza, contattate il vostro responsabile Adobe Account o il partner di servizi Professional.

Una volta impostata l’applicazione per dispositivi mobili, è possibile recuperare i dati PII raccolti per creare o aggiornare i profili dal database. Per ulteriori informazioni, consulta questa sezione: [Creazione e aggiornamento delle informazioni sul profilo in base ai dati](../../channels/using/updating-profile-with-mobile-app-data.md)delle applicazioni mobili.

Per le linee guida generali per le consegne di Mobile in Adobe Campaign Standard, fai riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Utilizzo di Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

>[!Note]
>
>Per ulteriori informazioni sui diversi casi di utilizzo per dispositivi mobili supportati in Adobe Campaign Standard utilizzando gli SDK di Adobe Experience Platform, consulta questa [pagina](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

Per inviare notifiche push e messaggi in-app con l’applicazione SDK Experience Platform, è necessario configurare un’applicazione mobile in Adobe Experience Platform Experience Platform Launch e configurarla in Adobe Campaign. Per i passaggi dettagliati per configurare l’applicazione mobile mediante l’SDK di Experience Platform, consulta questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Per avviare la configurazione, effettuate le operazioni seguenti:

1. Assicuratevi di poter accedere ai **[!UICONTROL Mobile]**canali: Notifica push e messaggio in-app in Adobe Campaign. In caso contrario, contattate il team di account.

   ![](assets/launch_1.png)

1. Crea l’applicazione mobile in Experience Platform Launch creando una proprietà di tipo Mobile. Per ulteriori informazioni, consulta la documentazione di [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) .
1. Installa l’ **[!UICONTROL Adobe Campaign Standard]**estensione per l’applicazione mobile in Experience Platform Launch:

   Per ulteriori informazioni sulle estensioni, consulta la documentazione [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) .

1. Configurare le regole per l’applicazione in Adobe Launch, vedere [Configurazione dell’applicazione in Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. Configura l’applicazione Adobe Launch in Adobe Campaign Standard, consulta [Configurazione dell’applicazione Adobe Launch in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Aggiungi una configurazione specifica per il canale alla configurazione dell&#39;applicazione mobile. Vedi Configurazione dell&#39;applicazione specifica per il [canale in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)
