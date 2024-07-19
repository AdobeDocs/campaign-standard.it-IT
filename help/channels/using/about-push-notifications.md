---
title: Informazioni sulle notifiche push
description: Scopri le principali specificità del canale di notifica push in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Push
role: User
level: Intermediate
exl-id: e61daed6-a0ec-49d8-b1ad-77590fafb496
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '1206'
ht-degree: 39%

---

# Informazioni sulle notifiche push{#about-push-notifications}

>[!CAUTION]
>
>L’implementazione delle notifiche push deve essere eseguita da utenti esperti. Se hai bisogno di assistenza, contatta il responsabile dell’account di Adobe o un partner di servizi professionali. La notifica push è una funzione opzionale. Controlla il contratto di licenza e contatta il responsabile dell’account per attivarla.

Adobe Campaign ti consente di inviare notifiche push personalizzate e segmentate ai dispositivi mobili iOS e Android.

Questi messaggi vengono ricevuti sulle app mobili che configuri in Adobe Campaign sfruttando l’SDK di Experience Platform. Per ulteriori informazioni, consulta [Configurazione di un’app mobile tramite gli SDK di Adobe Experience Platform](../../administration/using/configuring-a-mobile-application.md).

In Adobe Campaign, i dati degli attributi del profilo mobile inviati da dispositivi mobili sono memorizzati nella risorsa **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** che ti consente di definire i dati da raccogliere dagli abbonati alle tue applicazioni.

Questa risorsa deve essere estesa per raccogliere i dati che intendi inviare dal dispositivo mobile ad Adobe Campaign. A tale scopo, consulta questa [pagina](../../developing/using/extending-the-subscriptions-to-an-application-resource.md) per i passaggi dettagliati.

In Adobe Campaign sono disponibili due tipi di notifica push:

* Le notifiche di tipo **[!UICONTROL Alert/Message/Badge]** ti consentono di inviare messaggi standard basati su testo con contenuto aggiuntivo (audio, simboli, deep link, ecc.) che puoi definire nella sezione **[!UICONTROL Advanced options]**.

  Questi tipi di notifica ti consentono di aggiungere un titolo e un messaggio in cui puoi utilizzare campi di personalizzazione. Per personalizzare il messaggio, accertati di selezionare il modello **[!UICONTROL Send push on profiles]**.

* Le notifiche di tipo **[!UICONTROL Silent push]** vengono utilizzate per inviare all’applicazione una notifica silenziosa senza alcun messaggio o contenuto per l’utente finale. Un caso di utilizzo tipico per questo tipo di messaggio consiste nel comunicare all’applicazione che sul server è disponibile del contenuto da scaricare.

Puoi configurare alcune configurazioni specifiche per definire il comportamento delle notifiche. Per ulteriori informazioni, consulta [questa sezione](../../channels/using/customizing-a-push-notification.md).

>[!NOTE]
>
>Le leggi sulla privacy differiscono a seconda del paese. In alcuni paesi è necessario che informi gli utenti sui tipi di dati raccolti dalle app mobili. Controlla le leggi relative alle app mobili vigenti nel tuo paese. Assicurati che le notifiche push inviate alle app mobili siano conformi ai prerequisiti e alle condizioni specificati da Apple (Apple Push Notification Service) e Google (Google Cloud Messaging o Firebase Cloud Messaging).

**Contenuto correlato:**

* [Preparazione e invio di una notifica push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Creazione di una notifica push multilingue](../../channels/using/creating-a-multilingual-push-notification.md)
* [Rapporto notifiche push](../../reporting/using/push-notification-report.md)
* [Guida di Campaign Standard Mobile](../../channels/using/get-started-communication-channels.md)

## Prerequisiti {#prerequisites}

>[!NOTE]
>Per sfruttare la funzione di notifica push di Campaign, devi fornire un certificato push valido in formato .pem senza password.
>
>Se disponi di un certificato p12 valido, puoi facilmente convertirlo in un file .pem utilizzando risorse online.

Prima di inviare le notifiche push, devi:

1. In Adobe Campaign, assicurati di poter accedere al canale **[!UICONTROL Push notification]**. Se non riesci ad accedere a questi canali, contatta il team dell’account.

1. Verifica che l’utente disponga delle autorizzazioni necessarie in Adobe Campaign Standard e nei tag in Adobe Experience Platform.

1. Nell’interfaccia utente di Data Collection , crea una proprietà mobile. Per ulteriori informazioni, consulta [Configurare una proprietà mobile](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/).

1. Nell&#39;interfaccia utente di Data Collection , installare l&#39;estensione **[!UICONTROL Adobe Campaign Standard]**.

1. In Adobe Campaign Standard, configura la proprietà mobile creata nell’interfaccia utente di Data Collection. Per ulteriori informazioni, vedere [Configurazione dell&#39;applicazione tag in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#set-up-campaign).

1. Aggiungi la configurazione specifica per il canale alla configurazione dell’app mobile. Per ulteriori informazioni, consulta [Configurazione dell’applicazione specifica per il canale in Adobe Campaign](../../administration/using/configuring-a-mobile-application.md#channel-specific-config).

1. Per supportare le implementazioni dei casi d&#39;uso per dispositivi mobili, consulta le istruzioni dettagliate su estensioni, regole di tag e implementazione SDK in [casi d&#39;uso per dispositivi mobili supportati in Adobe Campaign Standard utilizzando gli SDK di Adobe Experience Platform](../../administration/using/configuring-rules-launch.md).

## Domande frequenti sulle notifiche push {#push-faq}

### Quali sono alcuni consigli utili sulle risorse per ulteriori informazioni sul canale push? {#resource-push}

Consulta le risorse seguenti:

* [Tutorials video](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/mobile/push/creating-a-push-notification.html)
* [Documentazione del prodotto](../../channels/using/about-push-notifications.md)
* Configurare utilizzando la [documentazione](../../administration/using/configuring-a-mobile-application.md) dell&#39;SDK AEP
* [Pagina community](https://experienceleaguecommunities.adobe.com/t5/adobe-campaign-standard/ct-p/adobe-campaign-standard-community)

### Cosa devo fare per acquisire un token push in Campaign? {#push-token-acquisition}

Assicurati che il team di provisioning abbia completato il provisioning del canale push in Adobe Campaign Standard. Implementa l’API setPushIdentifier dall’SDK. Per ulteriori informazioni, consulta questa [pagina](https://developer.adobe.com/client-sdks/documentation/adobe-campaign-standard/#set-up-push-messaging).

### Una volta che dispongo di token push ed ECID in Campaign, cos’altro è necessario per inviare una notifica push? {#sending-push}

Per inviare una notifica push, i clienti devono fornire un certificato push valido in formato .pem. Non è necessaria una password per questo certificato.

### Cosa succede se dispongo di un certificato .p12 invece di un certificato .pem? {#certificates}

Per convertire un certificato .p12 in un certificato .pem, esegui il comando seguente nel terminale. Sono disponibili diverse risorse online per le istruzioni di conversione.

```
openssl pkcs12 -in pushcert.p12 -out pushcert.pem -nodes -clcerts
```

### Come posso sapere se il caricamento del certificato è riuscito? {#certificate-upload}

Verrà visualizzato il seguente messaggio.

![](assets/faq_2.png)

### Posso caricare contemporaneamente i certificati di produzione e sandbox per l’app iOS (N/D per Android)? {#prod-sandbox-certificate}

No, le app funzioneranno sia in modalità sandbox che in modalità di produzione e non possono essere modificate una volta configurate. È consigliabile testare l’app prima in modalità sandbox e quindi passare alla modalità di produzione.

Per passare alla modalità di produzione, dovrai creare un’altra app. Inoltre, assicurati di non selezionare la casella di controllo sandbox e di caricare un certificato di produzione.

### Posso caricare contemporaneamente le credenziali sia di iOS che di Android? {#ios-android-credentials}

Sì, Campaign supporta entrambe le piattaforme contemporaneamente e consente di caricare le credenziali per entrambe.

### I certificati push sono stati caricati correttamente, ma non vengono inviati messaggi push. {#push-certificates-upload}

Assicurati che i certificati push siano validi sottoponendoli a test [qui](https://pushtry.com/).

### Sono in grado di inviare notifiche push correttamente da pushtry.com ma non tramite Campaign. {#push-not-sending}

Verifica di seguire le istruzioni di payload push fornite [qui](../../administration/using/push-payload.md).

Tieni presente che per Android, Campaign supporta solo il payload dei dati e non il payload di notifica

### Ho configurato un’app nella sezione Amministrazione di Adobe Campaign Standard, ma l’app mobile non è disponibile nelle proprietà Consegna. {#mobile-app-unavailable}

Un’app deve avere anche un certificato push valido caricato prima che possa essere reso disponibile nelle proprietà di consegna.

### Ho provato tutte le istruzioni su questa pagina, ma non sono in grado di inviare messaggi push da Campaign. {#push-troubleshoot}

Per favore, apri un ticket di assistenza clienti.

### Le notifiche push vengono inviate da Campaign, ma il file multimediale non viene visualizzato.{#media-file-unavailable}

Gli sviluppatori di app mobili devono gestire il supporto per i file multimediali nell’app. A volte la larghezza di banda di rete può anche impedire il rendering di un file multimediale. Fai riferimento a questa [pagina](../../administration/using/image-push-notification.md) per ulteriori puntatori.

### Cosa devo fare per abilitare i rapporti push in Campaign? {#push-reporting-enable}

Segui i passaggi seguenti:

* Configura un postback di tracciamento push. Le istruzioni sono disponibili [qui](../../administration/using/configuring-a-mobile-application.md).
* Implementa l’API trackAction da Mobile Core. Per ulteriori informazioni, consulta questa [pagina](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/).

Istruzioni più dettagliate sono disponibili in questa [pagina](../../administration/using/push-tracking.md).

### Quali rapporti sono disponibili per il canale push? {#push-report-available}

In Adobe Campaign per il canale push è disponibile un rapporto pronto all’uso. Consulta questa [documentazione](../../reporting/using/push-notification-report.md).

Consulta questa [pagina](../../reporting/using/indicator-calculation.md#push-notification-delivery) per informazioni sul calcolo di ciascuna metrica push.

### I deep link sono supportati nei messaggi push e in-app? {#deeplink-push}

Sì, i deep link sono supportati nei messaggi push. I collegamenti diretti devono includere:

* Lingua che indica che il tracciamento della consegna deve essere disabilitato affinché i collegamenti diretti funzionino.
* Appsflyer con Branch come partner in grado di eseguire il tracciamento del deep link. Per ulteriori informazioni sull&#39;integrazione di Branch e Adobe Campaign Standard, consulta questa [pagina](https://help.branch.io/using-branch/docs/adobe-campaign-standard-1).
