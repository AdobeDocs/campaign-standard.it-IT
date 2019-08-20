---
title: Configurazione dell'integrazione dei dati relativi ai punti di interesse
seo-title: Configurazione dell'integrazione dei dati relativi ai punti di interesse
description: Configurazione dell'integrazione dei dati relativi ai punti di interesse
seo-description: Scopri come configurare la funzionalità dei dati Points of Interest in Adobe Campaign per inviare messaggi personalizzati basati sulla posizione degli abbonati.
page-status-flag: never-activated
uuid: 0689 a 06 c-cc 1 a -442 f -95 b 8-a 07 fcec 85 d 79
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: a 967 c 6 cc-c 53 b -41 b 4-866 b -90860 d 78 f 463
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d857bee3e7cb54ec179a73d9c256a14771cbd474

---


# Configurazione dell'integrazione dei dati relativi ai punti di interesse{#configuring-campaign-points-of-interest-data-integration}

## Configurazione dell'integrazione dei dati relativi ai punti di interesse delle campagne con gli SDK di Adobe Experience Platform {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>L'applicazione mobile deve essere già configurata in Adobe Campaign Standard tramite Adobe Experience Platform SDK. Per i passaggi dettagliati, fate riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Le applicazioni mobili utilizzate per raccogliere i dati sulla posizione devono essere configurate da un **amministratore** nell'interfaccia di Adobe Campaign.

Per poter utilizzare i servizi di localizzazione Adobe Experience Platform con applicazioni mobili configurate con Adobe Experience Platform SDK, devi:

1. Aggiungi le **[!UICONTROL Places]****[!UICONTROL Places Monitor]** estensioni alla configurazione dell'app mobile in Adobe Experience Platform Launch. Imposta la tua applicazione mobile in Adobe Campaign. Consulta [Installare l'estensione Places in Adobe Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-extension#install-the-places-extension-in-adobe-experience-platform-launch) e [Installare l'estensione Places Monitor in Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-monitor-extension/using-the-places-monitor-extension).

1. Una volta configurate le estensioni, create elementi di dati all'interno **[!UICONTROL Adobe Experience Platform Launch]** per recuperare dati da queste estensioni. Fate riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) per creare gli elementi dei dati.

1. Quindi, in **[!UICONTROL Adobe Experience Platform Launch]**, devi creare regole per supportare i casi di utilizzo per dispositivi mobili tra i vari punti di interesse e Adobe Campaign.\
   Questa regola verrà attivata quando un utente immette un geotargeting **[!UICONTROL Point of Interest]**. Fate riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) per creare la vostra regola.

1. Definire i punti **[!UICONTROL Points of Interest]** in Luoghi. Consultate [Creare un punto di interesse](https://placesdocs.com/places-services-by-adobe-documentation/places-database-management-1/managing-pois-in-the-places-ui#create-a-poi).

1. Assicurati di accedere all'applicazione mobile e ai dati sulla posizione raccolti in Adobe Campaign. Consultate [Accesso alle app mobili utilizzate per raccogliere i dati](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) sulla posizione e [Accesso ai dati sulla posizione raccolti](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

## Configurazione dell'integrazione dei dati relativi ai punti di interesse con l'SDK V 4 {#configuring-campaign-poi-sdkv4}

Le applicazioni mobili utilizzate per raccogliere i dati sulla posizione devono essere configurate da un **amministratore** nell'interfaccia di Adobe Campaign.

Per utilizzare la funzionalità dati Punto di interesse con applicazioni mobili configurate con SDK V 4, devi:

1. Accedere ad Adobe Analytics per dispositivi mobili. Controllate il contratto di licenza o contattate il vostro account esecutivo Adobe per ulteriori informazioni.
1. Imposta la tua applicazione mobile in Adobe Campaign. Consultate [Configurazione di un'app mobile in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
1. Configura la tua applicazione mobile nell'interfaccia di Adobe Mobile Services. Questo consente di garantire che i dati raccolti da Adobe Mobile Services vengano inviati ad Adobe Campaign. Consultate [Configurazione di un'app mobile in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).
1. Eseguite la configurazione specifica dell'applicazione mobile:

   * Crea un pacchetto con il file di configurazione scaricato dall'interfaccia di Adobe Mobile Services con l'applicazione mobile.
   * Integra l'SDK di Experience Cloud Mobile nell'applicazione mobile. Consultate [Integrazione dell'SDK in un'applicazione mobile](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#integrating-the-sdk-into-a-mobile-application).

1. Definisci punti di interesse nell'interfaccia di Adobe Mobile Services. Consulta [Definizione dei punti di interesse in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#defining-points-of-interest-in-adobe-mobile-services).
1. Definite i dati che desiderate raccogliere dagli abbonati dell'applicazione mobile. Consultate [Raccolta dei dati dei punti di interesse per gli abbonati](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#collecting-subscribers--points-of-interest-data).
1. Assicurati di accedere all'applicazione mobile e ai dati sulla posizione raccolti in Adobe Campaign. Consultate [Accesso alle app mobili utilizzate per raccogliere i dati](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-mobile-apps-used-to-collect-location-data) sulla posizione e [Accesso ai dati sulla posizione raccolti](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#accessing-collected-location-data).

### Configurazione di un'app mobile in Adobe Campaign tramite SDK V 4 {#setting-up-a-mobile-app-in-campaign}

Per poter raccogliere i dati dei punti di interesse con Adobe Campaign, devi configurare l'applicazione mobile dalla quale Adobe Campaign riceverà i dati.

1. Fate clic sul **[!UICONTROL Adobe Campaign]** logo, nell'angolo in alto a sinistra, quindi selezionate **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Fate clic per **[!UICONTROL Create]** configurare un'applicazione.
1. Immettete un nome nel **[!UICONTROL Application name]** campo e fate clic **[!UICONTROL Create]** su.

   Non compilare la **[!UICONTROL Device-specific settings]** sezione. Ciò vale solo per la configurazione delle applicazioni che ricevono le notifiche push.

Nella **[!UICONTROL Mobile application properties]** sezione vengono elencati due URL: **[!UICONTROL Collect PII endpoint]** e **[!UICONTROL Location Services endpoint]**. Saranno utilizzati nell'interfaccia di Adobe Mobile Services. Consultate [Configurazione di un'app mobile in Adobe Mobile Services](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services).

* L' **[!UICONTROL Collect PII endpoint]** URL viene utilizzato per raccogliere gli ID Experience Cloud degli utenti e i token di registrazione dall'applicazione mobile al momento dell'avvio. Quando un utente accede all'applicazione utilizzando credenziali quali e-mail, nome, cognome ecc., questi dati vengono raccolti e utilizzati per riconciliare il token di registrazione dell'utente con un profilo Adobe Campaign.
* L' **[!UICONTROL Location Services endpoint]** URL viene utilizzato per raccogliere dati sulla posizione quali latitudine, longitudine e raggio dell'utente da un punto di interesse.

Ora puoi utilizzare questi valori in Adobe Mobile Services per completare la configurazione, come spiegato nella [sezione Configurazione di un'app mobile nella](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#configuring-a-mobile-app-in-adobe-mobile-services) sezione Adobe Mobile Services.

![](assets/poi_mobile_app_properties.png)

### Configurazione di un'app mobile V 4 in Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Per inviare i dati raccolti da Adobe Mobile Services ad Adobe Campaign, devi configurare i postback nell'interfaccia di Mobile Services.

Hai bisogno di informazioni specifiche nei parametri delle applicazioni mobili impostate in Adobe Campaign (vedi [Configurazione di un'app mobile in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

Per effettuare la configurazione seguente, devi avere accesso ad Adobe Analytics. Se non sei un utente di Adobe Analytics, contatta l'amministratore di Adobe Campaign.

1. Accedete a [mobilemarketing.adobe.com](http://mobilemarketing.adobe.com/).
1. Create l'applicazione o selezionatene una esistente.
1. Passate alla **[!UICONTROL Manage App Settings]** pagina.
1. Nella **sezione Servizio** ID visitatore, seleziona **Abilita** e seleziona la tua organizzazione dall'elenco a discesa. Fate clic **su Salva**.

   >[!CAUTION]
   >
   >Questa organizzazione deve essere uguale a quella utilizzata nell'istanza di Adobe Campaign.

1. Click **[!UICONTROL Manage Postbacks]**.
1. Crea un postback.

   * Selezionare **[!UICONTROL PII]** come **[!UICONTROL Postback Type]**.
   * Nel **[!UICONTROL URL]** campo, copiate l' **[!UICONTROL Collect PII Endpoint]** URL dall'applicazione mobile configurata nell'interfaccia di Adobe Campaign, preceduto dal nome del server. Consultate [Configurazione di un'app mobile in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Compila il **[!UICONTROL Post Body]** campo come segue:

      Per iOS:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"apns",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

      Per Android:

      ```
      {
      "userKey": "{userKey}",
      "pushPlatform":"gcm",
      "marketingCloudId":"{%mcid%}",
      "cusEmail":"{email}",
      "cusFirstName":"{firstName}",
      "cusLastName":"{lastName}"
      }
      ```

   * Imposta **tipo di contenuto** come **[!UICONTROL application/json]**.
   * In **Quali tag dati attivare il postback?**, selezionate qualsiasi evento, in genere **[!UICONTROL Launched]** e **[!UICONTROL exists]**.
   * Click **[!UICONTROL Save & Activate]**.

1. Crea un secondo postback.

   * Selezionare **[!UICONTROL Postback]** come **[!UICONTROL Postback Type]**.
   * Nel **[!UICONTROL URL]** campo, copiate l' **[!UICONTROL Location Services Endpoint]** URL dall'applicazione mobile configurata nell'interfaccia di Adobe Campaign, preceduto dal nome del server. Consultate [Configurazione di un'app mobile in Campaign](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md#setting-up-a-mobile-app-in-campaign).
   * Compila il **[!UICONTROL Post Body]** campo come segue:

      ```
      {
      "locationData":{
      "distances":"{a.loc.dist}",
      "poiLabel":"{a.loc.poi}",
      "latitude.a":"{a.loc.lat.a}",
      "latitude.b":"{a.loc.lat.b}",
      "latitude.c":"{a.loc.lat.c}",
      "longitude.a":"{a.loc.lon.a}",
      "longitude.b":"{a.loc.lon.b}",
      "longitude.c":"{a.loc.lon.c}",
      "appId":"{a.appid}",
      "marketingCloudId":"{mid}"
      }
      }
      ```

   * Imposta **tipo di contenuto** come **[!UICONTROL application/json]**.
   * In **Quali tag dati attivare il postback?**, selezionate **[!UICONTROL campaign.test]** e **[!UICONTROL exists]**.
   * Click **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>Per informazioni dettagliate sulla configurazione dei postback, consulta la documentazione [di Adobe Mobile Services](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html).

### Integrazione dell'SDK in un'applicazione mobile {#integrating-the-sdk-into-a-mobile-application}

Il kit di sviluppo software (SDK) del servizio di base Mobile facilita l'integrazione di un'applicazione mobile in Adobe Campaign.

Questo passaggio è descritto in questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

### Definizione dei punti di interesse in Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Per definire i punti di interesse utilizzati per raccogliere i dati sulla posizione:

1. Vai all'interfaccia di Adobe Mobile Services.
1. Aggiungete l'applicazione.

   Per ulteriori informazioni sulla gestione delle applicazioni in Mobile Services, consulta la documentazione [di Adobe Mobile Services](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html).

1. Definire i punti di interesse.

   Per ulteriori informazioni sulla gestione dei punti di interesse, consulta la documentazione [di Adobe Mobile Services](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html).

### Raccolta dei dati dei punti di interesse per gli abbonati {#collecting-subscribers--points-of-interest-data}

Una specifica risorsa personalizzata consente di definire i dati da raccogliere dagli abbonati delle applicazioni.

Questo passaggio è descritto nella [sezione Configurazione di un'applicazione mobile utilizzando](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) la pagina SDK V 4.


## Accesso alle app mobili utilizzate per raccogliere i dati sulla posizione {#accessing-mobile-apps-used-to-collect-location-data}

Per accedere alle applicazioni create con successo in Adobe Campaign:

1. Fate clic sul **[!UICONTROL Adobe Campaign]** logo, nell'angolo in alto a sinistra.
1. Seleziona **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app (SDK v4)]** o **[!UICONTROL Mobile app (AEP SDK)]** a seconda dell'SDK.
1. Selezionate un'applicazione mobile dall'elenco per visualizzarne le proprietà.

   ![](assets/poi_mobile_app_subscribers.png)

Nella **[!UICONTROL Mobile application subscribers]** scheda viene visualizzato anche un elenco degli abbonati dell'applicazione. Gli utenti iscritti sono tutti gli utenti che hanno installato l'applicazione sul dispositivo mobile. I profili del database di Adobe Campaign sono identificati da un token di registrazione.

## Accesso ai dati di posizione raccolti {#accessing-collected-location-data}

Una volta effettuata la configurazione, i dati dei punti di interesse raccolti vengono elencati nella **[!UICONTROL Places]** scheda di ciascun profilo. Per accedere all'elenco:

1. Selezionate un profilo.
1. Fate clic sul **[!UICONTROL Edit profile properties]** pulsante a destra.
1. Selezionare la **[!UICONTROL Places]** scheda.

   ![](assets/poi_profile_places.png)

Vengono elencati i dati dei punti di interesse raccolti per il profilo corrente. I dati sulla posizione sono memorizzati nel database Adobe Campaign per sei mesi.

Per ulteriori informazioni sull'accesso e la modifica dei profili, consulta [Profili](../../audiences/using/about-profiles.md).
