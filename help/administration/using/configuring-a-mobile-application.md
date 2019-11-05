---
title: Configurazione di un’applicazione mobile
description: Scopri come configurare Adobe Campaign per l'invio di notifiche push o messaggi in-app tramite SDK V4 o l'SDK della piattaforma Experience.
page-status-flag: mai attivato
uuid: 63e1476a-7875-4f48-ba9e-97f1a0007e42
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configurazione dei canali
discoiquuid: 2a14500f-5ede-4131-8b1a-b7fd65b7e3aa
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Configurazione di un’applicazione mobile{#configuring-a-mobile-application}

Le notifiche push o i messaggi in-app vengono ricevuti su applicazioni mobili che devono essere configurate in Adobe Mobile Services per la prima volta a seconda del canale che si desidera utilizzare.

* Per inviare messaggi in-app e notifiche push, le tue applicazioni mobili devono essere configurate in Adobe Campaign sfruttando gli SDK di Adobe Experience Platform. Consultate [Utilizzo di Adobe Experience Platform SDK](#using-adobe-experience-platform-sdk).

* Per inviare solo le notifiche push, puoi configurare l'integrazione tra Adobe Campaign e Adobe Mobile Service utilizzando SDK V4. Consultate [Utilizzo di SDK V4](#using-sdk-v4).

Dopo che le applicazioni mobili sono state configurate in Adobe Campaign sfruttando l’SDK di Experience Cloud Mobile V4 o Experience Platform, devono essere configurate da un amministratore nel [!UICONTROL Administration] &gt; [!UICONTROL Channels] &gt; [!UICONTROL Mobile app] menu.

>[!CAUTION]
>
>Le notifiche push e le implementazioni in-app devono essere eseguite da utenti esperti. Se avete bisogno di assistenza, contattate il vostro responsabile Adobe Account o il partner di servizi Professional.

Una volta impostata l’applicazione per dispositivi mobili, è possibile recuperare i dati PII raccolti per creare o aggiornare i profili dal database. Per ulteriori informazioni, consulta questa sezione: [Creazione e aggiornamento delle informazioni sul profilo in base ai dati](../../channels/using/updating-profile-with-mobile-app-data.md)delle applicazioni mobili.

## Utilizzo di Adobe Experience Platform SDK {#using-adobe-experience-platform-sdk}

>[!Note]
>
>Per ulteriori informazioni sui diversi casi di utilizzo per dispositivi mobili supportati in Adobe Campaign Standard utilizzando gli SDK di Adobe Experience Platform, consulta questa [pagina](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html).

Per inviare notifiche push e messaggi in-app con l’applicazione SDK Experience Platform, è necessario configurare un’applicazione mobile in Adobe Experience Platform Experience Platform Launch e configurarla in Adobe Campaign. Per i passaggi dettagliati per configurare l’applicazione mobile mediante l’SDK di Experience Platform, consulta questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Per avviare la configurazione, effettuate le operazioni seguenti:

1. Assicuratevi di poter accedere ai **[!UICONTROL Mobile]** canali: Notifica push e messaggio in-app in Adobe Campaign. In caso contrario, contattate il team di account.

   ![](assets/launch_1.png)

1. Crea l’applicazione mobile in Experience Platform Launch creando una proprietà di tipo Mobile. Per ulteriori informazioni, consulta la documentazione di [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-new-mobile-property) .
1. Installa l’ **[!UICONTROL Adobe Campaign Standard]** estensione per l’applicazione mobile in Experience Platform Launch:

   Per ulteriori informazioni sulle estensioni, consulta la documentazione [Experience Platform Launch](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard) .

1. Configurare le regole per l’applicazione in Adobe Launch, vedere [Configurazione dell’applicazione in Launch](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements)
1. Configura l’applicazione Adobe Launch in Adobe Campaign Standard, consulta [Configurazione dell’applicazione Adobe Launch in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeLaunchapplicationinAdobeCampaign).
1. Aggiungi una configurazione specifica per il canale alla configurazione dell'applicazione mobile. Vedi Configurazione dell'applicazione specifica per il [canale in Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#ChannelspecificapplicationconfigurationinAdobeCampaign).

   ![](assets/launch_2.png)

## Utilizzo di SDK V4 {#using-sdk-v4}

La notifica push è supportata dagli SDK SDK SDK V4 e Adobe Experience Platform a differenza di quelli in-app. Per i passaggi dettagliati per utilizzare le notifiche push con la tua app mobile, fai riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Le applicazioni mobili che ricevono notifiche push devono essere configurate da un amministratore nell'interfaccia di Adobe Campaign. Configurando Adobe Campaign e Adobe Mobile Services, potrai utilizzare i dati dell'applicazione mobile per le campagne.

Per poter inviare le notifiche push, devi:

1. Assicurati di poter accedere al **[!UICONTROL Mobile app]** canale in Adobe Campaign.
1. Configura l’applicazione mobile in:

   * [Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#SettingupamobileapplicationinAdobeCampaign).
   * [Adobe Mobile Services](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#ConfiguringamobileapplicationinAdobeMobileServices).

1. Esegui la configurazione specifica dell’applicazione mobile:

   * Crea un pacchetto del file di configurazione scaricato dall'interfaccia di Adobe Mobile Services con l'applicazione mobile.
   * Integra l’SDK di Experience Cloud Mobile nella tua applicazione mobile.

1. Definite i dati che desiderate raccogliere dagli utenti iscritti all'applicazione. Gli abbonati dell'applicazione mobile che dispongono di un profilo nel database Adobe Campaign vengono riconciliati in base ai criteri definiti.

   Per ulteriori informazioni, consultare questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html#Collectingsubscribersdatafromamobileapplication).

1. Accertatevi che la configurazione sia stata completata correttamente avviando l’applicazione mobile sul dispositivo e accedendo. Accertatevi di scegliere di ricevere le notifiche.
1. Quindi, nel menu avanzato di Adobe Campaign, seleziona **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Seleziona l’applicazione mobile dall’elenco per visualizzarne le proprietà. Le informazioni sull’iscrizione vengono visualizzate nell’elenco degli abbonati.

   ![](assets/push_notif_mobile_app.png)

1. Per controllare le applicazioni mobili a cui un profilo si è iscritto, nel **[!UICONTROL Profiles & Audiences > Profiles]** menu selezionare un profilo e fare clic sul **[!UICONTROL Edit profile properties]** pulsante a destra. Le applicazioni mobili sono elencate nella **[!UICONTROL Mobile App Subscriptions]** scheda.

   ![](assets/push_notif_subscriptions.png)