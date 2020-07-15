---
title: Informazioni sulle notifiche push
description: Scopri le principali specificità del canale di notifica push in  Adobe Campaign.
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
source-git-commit: f9632e88b49c2280c76e709376cfb7a7a27abc1f
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 2%

---


# Informazioni sulle notifiche push{#about-push-notifications}

>[!CAUTION]
>
>L&#39;implementazione delle notifiche push deve essere eseguita da utenti esperti. Se avete bisogno di assistenza, contattate il vostro responsabile Adobe Account o il partner di servizi Professional. La notifica push è una funzione opzionale. Controllare il contratto di licenza e contattare il responsabile commerciale di riferimento per attivarlo.

 Adobe Campaign consente di inviare notifiche push personalizzate e segmentate ai dispositivi mobili iOS e Android.

Questi messaggi vengono ricevuti sulle applicazioni mobili configurate in  Adobe Campaign sfruttando l’SDK per Experience Platform . Per ulteriori informazioni, consulta [Configurazione di un’applicazione mobile tramite  SDK](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html)di Adobe Experience Platform.

In Adobe Campaign, mobile profile attributes data sent from mobile device are stored in **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** resource which allows you to define the data that you want to collect from your applications&#39; subscribers.

Questa risorsa deve essere estesa per raccogliere i dati che si intende inviare dal dispositivo mobile al Adobe Campaign . A tale scopo, fare riferimento a questa [pagina](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) per i passaggi dettagliati.

In  Adobe Campaign sono disponibili due tipi di notifica push:

* **[!UICONTROL Alert/Message/Badge]** le notifiche tipo consentono di inviare messaggi standard basati su testo con contenuto aggiuntivo (audio, simboli, collegamento profondo, ecc.) che è possibile definire nella **[!UICONTROL Advanced options]** sezione.

   Questi tipi di notifica consentono di aggiungere un titolo e un messaggio in cui è possibile utilizzare i campi di personalizzazione. Per personalizzare il messaggio, accertatevi di selezionare il **[!UICONTROL Send push on profiles]** modello.

* **[!UICONTROL Silent push]** le notifiche tipo vengono utilizzate per inviare all&#39;applicazione una notifica silenziosa senza alcun messaggio o contenuto per l&#39;utente finale. Un esempio tipico per questo tipo di messaggio è che l&#39;applicazione sia consapevole che sul server è disponibile del contenuto da scaricare.

È possibile configurare alcune configurazioni specifiche per definire il comportamento delle notifiche. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../channels/using/customizing-a-push-notification.md).

In qualità di utente esperto, per definire queste configurazioni specifiche, consulta le [note tecniche](https://helpx.adobe.com/it/campaign/kb/acs-article-list.html)sulle app mobili.

>[!NOTE]
>
>Le leggi sulla privacy differiscono per paese. In alcuni paesi è necessario informare gli utenti dei tipi di dati raccolti dalle applicazioni mobili. Controlla le leggi relative alle applicazioni mobili nel tuo paese. Assicuratevi che le notifiche push inviate alle applicazioni mobili siano conformi ai prerequisiti e alle condizioni specificati da Apple (Apple Push Notification Service) e Google (Google Cloud Messaging o Firebase Cloud Messaging).

**Contenuto correlato:**

* [Preparazione e invio di una notifica push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Creazione di una notifica push multilingue](../../channels/using/creating-a-multilingual-push-notification.md)
* [Report notifiche push](../../reporting/using/push-notification-report.md)
* [Guida di Campaign Standard Mobile](https://helpx.adobe.com/it/campaign/kb/acs-mobile.html)

## Prerequisiti {#prerequisites}

>[!NOTE]
>Per sfruttare la funzione di notifica push di Campaign, devi fornire un certificato push valido in formato .pem senza password.
Se disponete di un certificato p12 valido, potete facilmente convertirlo in un file .pem utilizzando le risorse online.

Prima di inviare le notifiche push, devi:

1. In  Adobe Campaign, accertatevi di poter accedere al **[!UICONTROL Push notification]** canale. Se non riuscite ad accedere a questi canali, contattate il team di account.

1. Verificate che l&#39;utente disponga delle autorizzazioni necessarie in  Adobe Campaign Standard e Experience Platform Launch.

1. Ad Experience Platform Launch, create una proprietà mobile. Per ulteriori informazioni, consultate [Configurare una proprietà](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)mobile.

1. In Experience Platform Launch, installate l’ **[!UICONTROL Adobe Campaign Standard]** estensione.

1. In  Adobe Campaign Standard, configurate la proprietà mobile creata nel Experience Platform Launch. Per ulteriori informazioni, consultate [Impostazione dell&#39;applicazione di Experience Platform Launch in  Adobe Campaign](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html#SettingupyourAdobeExperiencePlatformLaunchapplicationinAdobeCampaign).

1. Aggiungi la configurazione specifica per il canale alla configurazione dell’applicazione mobile. Per ulteriori informazioni, consulta Configurazione dell’applicazione specifica per il [canale in  Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Per supportare le implementazioni di casi di utilizzo per dispositivi mobili, consulta le istruzioni dettagliate sulle estensioni, le regole di Experience Platform Launch e l’implementazione dell’SDK nei casi di utilizzo [Mobile supportati in  Adobe Campaign Standard utilizzando gli SDK](https://helpx.adobe.com/campaign/kb/configure-launch-rules-acs-use-cases.html)di  Adobe Experience Platform.

## Domande frequenti sulle notifiche push {#push-faq}

### Quali sarebbero alcune utili raccomandazioni sulle risorse per ulteriori informazioni sui canali push? {#resource-push}

Consulta le risorse seguenti:

* [Esercitazioni video](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [Documentazione del prodotto](../../channels/using/about-push-notifications.md)
* Configurazione mediante la [documentazione AEP SDK](../../administration/using/configuring-a-mobile-application.md)
* [Pagina community](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### Cosa devo fare per acquisire un token push in Campaign? {#push-token-acquisition}

Verificate che il team di provisioning abbia completato il provisioning del canale push in  Adobe Campaign Standard. Implementa l’API setPushIdentifier dall’SDK. For more on this, refer to this [page](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/adobe-campaign-standard#set-up-push-messaging).

### Una volta che ho il token push e l&#39;ECID in Campaign, cos&#39;altro devo inviare una notifica push? {#sending-push}

Per inviare una notifica push, i clienti devono fornire un certificato push valido in formato .pem. Non è necessaria una password per questo certificato.

### E se avessi un certificato .p12 invece del certificato .pem? {#certificates}

Potete convertire un certificato .p12 in un certificato .pem eseguendo il comando seguente nel terminale. Sono inoltre disponibili diverse risorse online per le istruzioni di conversione.

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### Come posso sapere se il caricamento del certificato ha esito positivo? {#certificate-upload}

Vedrai il seguente messaggio.

![](assets/faq_2.png)

### Posso caricare sia i certificati di produzione che i certificati sandbox allo stesso tempo per l&#39;app iOS (N/D per Android)? {#prod-sandbox-certificate}

No, le app funzioneranno in modalità sandbox o di produzione e non potranno essere modificate nell&#39;altra (ad es. sandbox all&#39;app di produzione) dopo la configurazione. È consigliabile testare prima l&#39;app in modalità sandbox e quindi passare alla modalità di produzione.

Per passare alla modalità di produzione, dovrete creare un&#39;altra app. Inoltre, accertatevi di non selezionare la casella di controllo sandbox e di caricare un certificato di produzione.

### Posso caricare contemporaneamente sia le credenziali iOS che quelle Android? {#ios-android-credentials}

Sì, Campaign supporta entrambe le piattaforme contemporaneamente e consente di caricare le credenziali per entrambe le piattaforme.

### Ho caricato correttamente i certificati push, ma non viene inviato alcun messaggio push. {#push-certificates-upload}

Verificate che i certificati push siano validi verificandone la validità [qui](https://pushtry.com/).

### Posso inviare le notifiche push da push.com ma non tramite Campaign. {#push-not-sending}

Accertatevi di seguire le istruzioni di payload push fornite [qui](../../administration/using/push-payload.md).

Nota: per Android, Campaign supporta solo il payload di dati e non il payload di notifica

### Ho configurato un&#39;app nella sezione Amministrazione del  Adobe Campaign Standard, ma l&#39;app mobile non è disponibile nelle proprietà di consegna. {#mobile-app-unavailable}

Un&#39;app deve avere anche un certificato push valido caricato prima di poter essere reso disponibile nelle proprietà di consegna.

### Ho provato tutte le istruzioni presenti in questa pagina, ma non sono in grado di inviare push da Campaign. {#push-troubleshoot}

Per favore, apri un ticket di assistenza clienti.

### Le notifiche push vengono recapitate da Campaign, ma il file multimediale non viene visualizzato.{#media-file-unavailable}

Gli sviluppatori di app mobili devono gestire il supporto per i file multimediali nell&#39;app. A volte la larghezza di banda di rete potrebbe anche impedire il rendering di un file multimediale. Fare riferimento a questa [pagina](../../administration/using/image-push-notification.md) per ulteriori puntatori.

### Cosa devo fare per abilitare il reporting push in Campaign? {#push-reporting-enable}

Effettuate le seguenti operazioni:

* Configura un postback di tracciamento push. Le istruzioni sono disponibili [qui](../../administration/using/configuring-a-mobile-application.md).
* Implementa l’API trackAction da Mobile Core. Per ulteriori informazioni, consultare questa [pagina](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference) .

Istruzioni più dettagliate sono disponibili in questa [pagina](../../administration/using/push-tracking.md).

### Quali report sono disponibili per il canale push? {#push-report-available}

Un rapporto out-of-the-box è disponibile in  Adobe Campaign per il canale push. Fare riferimento a questa [documentazione](../../reporting/using/push-notification-report.md).

Consultate questa [pagina](../../reporting/using/indicator-calculation.md#push-notification-delivery) per comprendere come vengono calcolate le singole metriche push.

### I collegamenti profondi sono supportati nei messaggi push e in-app? {#deeplink-push}

Sì, i collegamenti dei dettagli sono supportati nei messaggi push. I collegamenti di dettaglio devono includere:

* la lingua in cui si afferma che il tracciamento della consegna deve essere disabilitato per consentire il funzionamento dei collegamenti dettagliati.
* Applicate un&#39;applicazione con il ramo come partner in grado di eseguire il tracciamento del collegamento profondo. Per ulteriori informazioni sull&#39;integrazione di ramo e  Adobe Campaign Standard, fare riferimento a questa [pagina](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).