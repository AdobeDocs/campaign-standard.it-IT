---
title: Informazioni sulle notifiche push
description: Scopri le principali specificità del canale di notifica push in Adobe Campaign.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 501ba6f97a86076116d4d84f43df674536e12f6a

---


# Informazioni sulle notifiche push{#about-push-notifications}

>[!CAUTION]
>
>L&#39;implementazione delle notifiche push deve essere eseguita da utenti esperti. Se avete bisogno di assistenza, contattate il vostro responsabile Adobe Account o il partner di servizi Professional. La notifica push è una funzione opzionale. Controllare il contratto di licenza e contattare il responsabile commerciale di riferimento per attivarlo.

Adobe Campaign consente di inviare notifiche push personalizzate e segmentate ai dispositivi mobili iOS e Android.

Questi messaggi vengono ricevuti sulle applicazioni mobili configurate in Adobe Campaign sfruttando l’SDK V4 per Experience Cloud Mobile o l’SDK per la piattaforma Experience Cloud. Per ulteriori informazioni, consulta [Configurazione di un’applicazione mobile tramite SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) e [Configurazione di un’applicazione mobile tramite gli SDK](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)Adobe Experience Platform.

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**resource which allows you to define the data that you want to collect from your applications&#39; subscribers.

Questa risorsa deve essere estesa per raccogliere i dati che si intende inviare dal dispositivo mobile ad Adobe Campaign. A tale scopo, fare riferimento a questa [pagina](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) per i passaggi dettagliati.

In Adobe Campaign sono disponibili due tipi di notifica push:

* **[!UICONTROL Alert/Message/Badge]**le notifiche tipo consentono di inviare messaggi standard basati su testo con contenuto aggiuntivo (audio, simboli, collegamento profondo, ecc.) che è possibile definire nella**[!UICONTROL Advanced options]** sezione.

   Questi tipi di notifica consentono di aggiungere un titolo e un messaggio in cui è possibile utilizzare i campi di personalizzazione. Per personalizzare il messaggio, accertatevi di selezionare il **[!UICONTROL Send push on profiles]**modello.

* **[!UICONTROL Silent push]**le notifiche tipo vengono utilizzate per inviare all&#39;applicazione una notifica silenziosa senza alcun messaggio o contenuto per l&#39;utente finale. Un esempio tipico per questo tipo di messaggio sarebbe fare in modo che l&#39;applicazione sia consapevole che sul server è disponibile del contenuto da scaricare.

È possibile configurare alcune configurazioni specifiche per definire il comportamento delle notifiche. For more on this, refer to [this section](../../channels/using/customizing-a-push-notification.md).

In qualità di utente esperto, per definire queste configurazioni specifiche, consulta le [note tecniche](https://helpx.adobe.com/campaign/kb/acs-article-list.html)sulle app mobili.

>[!NOTE]
>
>Le leggi sulla privacy differiscono per paese. In alcuni paesi è necessario informare gli utenti dei tipi di dati raccolti dalle applicazioni mobili. Controlla le leggi relative alle applicazioni mobili nel tuo paese. Assicuratevi che le notifiche push inviate alle applicazioni mobili siano conformi ai prerequisiti e alle condizioni specificati da Apple (Apple Push Notification Service) e Google (Google Cloud Messaging o Firebase Cloud Messaging).

**Contenuto correlato:**

* [Preparazione e invio di una notifica push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Creazione di una notifica push multilingue](../../channels/using/creating-a-multilingual-push-notification.md)
* [Report notifiche push](../../reporting/using/push-notification-report.md)
* [Guida per dispositivi mobili Campaign Standard](https://helpx.adobe.com/campaign/kb/acs-mobile.html)

## Prerequisiti {#prerequisites}

>[!NOTE]
>Per sfruttare la funzione di notifica push di Campaign, devi fornire un certificato push valido in formato .pem senza password.
Se disponete di un certificato p12 valido, potete facilmente convertirlo in un file .pem utilizzando le risorse online.

Innanzitutto, per poter inviare le notifiche push, devi configurare l’applicazione mobile utilizzando SDK V4. Puoi anche configurare l’applicazione mobile mediante gli SDK di Experience Platform. Per ulteriori informazioni, consultare questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Prima di inviare le notifiche push, devi:

1. Assicurati di poter accedere al **[!UICONTROL Mobile app]**canale in Adobe Campaign.
1. Configura l’applicazione mobile in:

   * Adobe Campaign
   * Interfaccia di Adobe Mobile Services

1. Esegui la configurazione specifica dell’applicazione mobile:

   * Crea un pacchetto del file di configurazione scaricato dall&#39;interfaccia di Adobe Mobile Services con l&#39;applicazione mobile.
   * Integra l’SDK di Experience Cloud Mobile nella tua applicazione mobile.

1. Definite i dati che desiderate raccogliere dagli utenti iscritti all&#39;applicazione. Gli abbonati dell&#39;applicazione mobile che dispongono di un profilo nel database Adobe Campaign vengono riconciliati in base ai criteri definiti.

Dopo aver configurato l&#39;applicazione mobile, ora puoi iniziare a preparare e inviare i messaggi in-app. Per ulteriori informazioni, consultate [Preparazione e invio di una notifica](../../channels/using/preparing-and-sending-a-push-notification.md)push.
