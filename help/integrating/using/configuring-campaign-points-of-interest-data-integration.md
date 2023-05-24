---
title: Configurazione dell’integrazione di Campaign con i dati Punti di interesse
description: Scopri come configurare la funzione di dati Punti di interesse in Adobe Campaign per inviare messaggi personalizzati in base alla posizione degli abbonati.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: b097b3fa-f949-446e-ad44-cc6ca025ee55
source-git-commit: 884cd5e9c09aa85e744ca06b202eb46f73a33a76
workflow-type: tm+mt
source-wordcount: '1311'
ht-degree: 2%

---

# Configurazione dell’integrazione di Campaign con i dati Punti di interesse{#configuring-campaign-points-of-interest-data-integration}

## Configurazione dell’integrazione dei dati Campaign-Punti di interesse con gli SDK di Adobe Experience Platform {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>L&#39;app mobile deve essere già configurata in Adobe Campaign Standard mediante l&#39;SDK di Adobe Experience Platform. Per i passaggi dettagliati, fai riferimento a questo [pagina](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html?lang=it).

Le app mobili utilizzate per raccogliere i dati sulla posizione devono essere configurate da un **amministratore** nell’interfaccia di Adobe Campaign.

Per poter utilizzare Adobe Experience Platform Location Services con le app mobili configurate con Adobe Experience Platform SDK, è necessario:

1. Aggiungi il **[!UICONTROL Places]** estensione alla configurazione dell’app mobile nell’interfaccia utente di Data Collection. Configura l’app mobile in Adobe Campaign. Consulta [Installare l’estensione Places](https://experienceleague.adobe.com/docs/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch).

1. Una volta configurate le estensioni, crea elementi dati nell’interfaccia utente di Data Collection per recuperare dati da queste estensioni. Fai riferimento a questo [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) per creare gli elementi dati.

1. Quindi, nell’interfaccia utente di Data Collection, devi creare regole per supportare i casi d’uso per dispositivi mobili tra Point of Interests e Adobe Campaign.\
   Questa regola verrà attivata quando un utente immette una regola geofisica **[!UICONTROL Point of Interest]**. Fai riferimento a questo [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) per creare la regola.

1. Definisci le **[!UICONTROL Points of Interest]** in Places. Consulta [Creare un punto di interesse](https://experienceleague.adobe.com/docs/places/using/poi-mgmt-ui/create-a-poi-ui.html).

1. Assicurati di accedere all’app mobile e ai dati sulla posizione raccolti in Adobe Campaign. Consulta [Accesso alle app mobili utilizzate per raccogliere i dati sulla posizione](#accessing-mobile-apps-used-to-collect-location-data) e [Accesso ai dati sulla posizione raccolti](#accessing-collected-location-data).

## Configurazione dell’integrazione dei dati Campaign-Punti di interesse tramite SDK V4 {#configuring-campaign-poi-sdkv4}

Le app mobili utilizzate per raccogliere i dati sulla posizione devono essere configurate da un **amministratore** nell’interfaccia di Adobe Campaign.

Per utilizzare la funzione dati Punto di interesse con le applicazioni mobili configurate con SDK V4, è necessario:

1. Accedere ad Adobe Analytics per dispositivi mobili. Controlla il contratto di licenza o contatta il responsabile dell’account Adobe per ulteriori informazioni.
1. Configura l’app mobile in Adobe Campaign. Consulta [Configurazione di un’app mobile in Campaign](#setting-up-a-mobile-app-in-campaign).
1. Configura la tua app mobile nell’interfaccia di Adobe Mobile Services. Questo consente di assicurarsi che i dati raccolti da Adobe Mobile Services vengano inviati ad Adobe Campaign. Consulta [Configurazione di un’app mobile in Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).
1. Esegui la configurazione specifica dell’app mobile:

   * Crea un pacchetto del file di configurazione scaricato dall’interfaccia di Adobe Mobile Services con l’app mobile.
   * Integra l’SDK di Experience Cloud Mobile nell’app mobile. Consulta [Integrazione dell’SDK in un’app mobile](#integrating-the-sdk-into-a-mobile-application).

1. Definisci i punti di interesse nell’interfaccia di Adobe Mobile Services. Consulta [Definizione dei punti di interesse in Adobe Mobile Services](#defining-points-of-interest-in-adobe-mobile-services).
1. Definisci i dati da raccogliere dagli abbonati all’app mobile. Consulta [Raccolta dei dati dei punti di interesse degli abbonati](#collecting-subscribers--points-of-interest-data).
1. Assicurati di accedere all’app mobile e ai dati sulla posizione raccolti in Adobe Campaign. Consulta [Accesso alle app mobili utilizzate per raccogliere i dati sulla posizione](#accessing-mobile-apps-used-to-collect-location-data) e [Accesso ai dati sulla posizione raccolti](#accessing-collected-location-data).

### Configurazione di un’app mobile in Adobe Campaign tramite SDK V4 {#setting-up-a-mobile-app-in-campaign}

Per poter raccogliere i dati dei punti di interesse con Adobe Campaign, devi configurare l’app mobile da cui Adobe Campaign riceverà i dati.

1. Fai clic su **Adobe** nell&#39;angolo in alto a sinistra, quindi seleziona **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**.
1. Clic **[!UICONTROL Create]** per impostare un&#39;applicazione.
1. Immetti un nome in **[!UICONTROL Application name]** e fai clic su **[!UICONTROL Create]**.

   Non compilare il campo **[!UICONTROL Device-specific settings]** sezione. Questo si applica solo alla configurazione di applicazioni che ricevono notifiche push.

In **[!UICONTROL Mobile application properties]** , vengono elencati due URL: **[!UICONTROL Collect PII endpoint]** e **[!UICONTROL Location Services endpoint]**. Verranno utilizzati nell’interfaccia di Adobe Mobile Services. Consulta [Configurazione di un’app mobile in Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).

* Il **[!UICONTROL Collect PII endpoint]** L’URL viene utilizzato per raccogliere gli ID Experienci Cloud e i token di registrazione degli utenti dall’app mobile all’avvio. Quando un utente accede all’applicazione utilizzando credenziali quali e-mail, nome, cognome e così via, questi dati vengono raccolti e utilizzati anche per riconciliare il token di registrazione dell’utente con un profilo Adobe Campaign.
* Il **[!UICONTROL Location Services endpoint]** L’URL viene utilizzato per raccogliere dati sulla posizione, ad esempio la latitudine, la longitudine e il raggio di un utente, da un punto di interesse.

È ora possibile utilizzare questi valori in Adobe Mobile Services per completare la configurazione, come spiegato in [Configurazione di un’app mobile in Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services) sezione.

![](assets/poi_mobile_app_properties.png)

### Configurazione di un’app mobile V4 in Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Per inviare i dati raccolti da Adobe Mobile Services ad Adobe Campaign, devi configurare i postback nell’interfaccia di Mobile Services.

Saranno necessarie informazioni specifiche reperibili nei parametri delle app mobili impostati in Adobe Campaign (consulta [Configurazione di un’app mobile in Campaign](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

Devi avere accesso ad Adobe Analytics per effettuare la seguente configurazione. Se non sei un utente di Adobe Analytics, contatta il tuo amministratore Adobe Campaign.

1. Accedi a [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/).
1. Crea l’applicazione o selezionane una esistente.
1. Vai a **[!UICONTROL Manage App Settings]** pagina.
1. In **Servizio ID visitatore** sezione, spunta **Abilita** e seleziona la tua organizzazione dall’elenco a discesa. Fai clic su **Salva**.

   >[!CAUTION]
   >
   >Questa organizzazione deve essere la stessa utilizzata nell’istanza di Adobe Campaign.

1. Fai clic su **[!UICONTROL Manage Postbacks]**.
1. Crea un postback.

   * Seleziona **[!UICONTROL PII]** come **[!UICONTROL Postback Type]**.
   * In **[!UICONTROL URL]** , copia il **[!UICONTROL Collect PII Endpoint]** URL dall’app mobile configurata nell’interfaccia di Adobe Campaign, preceduto dal nome del server. Consulta [Configurazione di un’app mobile in Campaign](#setting-up-a-mobile-app-in-campaign).
   * Compila il **[!UICONTROL Post Body]** come segue:

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

   * Imposta **Tipo di contenuto** as **[!UICONTROL application/json]**.
   * In **Quali tag di dati attivano il postback?**, seleziona qualsiasi evento, in genere **[!UICONTROL Launched]** e **[!UICONTROL exists]**.
   * Fai clic su **[!UICONTROL Save & Activate]**.

1. Crea un secondo postback.

   * Seleziona **[!UICONTROL Postback]** come **[!UICONTROL Postback Type]**.
   * In **[!UICONTROL URL]** , copia il **[!UICONTROL Location Services Endpoint]** URL dall’app mobile configurata nell’interfaccia di Adobe Campaign, preceduto dal nome del server. Consulta [Configurazione di un’app mobile in Campaign](#setting-up-a-mobile-app-in-campaign).
   * Compila il **[!UICONTROL Post Body]** come segue:

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

   * Imposta **Tipo di contenuto** as **[!UICONTROL application/json]**.
   * In **Quali tag di dati attivano il postback?**, seleziona **[!UICONTROL campaign.test]** e **[!UICONTROL exists]**.
   * Fai clic su **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>Per informazioni dettagliate sulla configurazione dei postback, consulta [Documentazione di Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html).

### Integrazione dell’SDK in un’app mobile {#integrating-the-sdk-into-a-mobile-application}

Il kit di sviluppo software (SDK) del servizio core Mobile facilita l’integrazione di un’app mobile in Adobe Campaign.

Questo passaggio è descritto in [pagina](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html).

### Definizione dei punti di interesse in Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Per definire i punti di interesse utilizzati per raccogliere i dati sulla posizione:

1. Passa all’interfaccia di Adobe Mobile Services.
1. Aggiungi l’applicazione.

   Per ulteriori informazioni sulla gestione delle applicazioni in Mobile Services, consulta [Documentazione di Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/t-new-app.html).

1. Definisci i punti di interesse.

   Per ulteriori informazioni sulla gestione dei punti di interesse, consulta [Documentazione di Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/location-ug/t-manage-points.html).

### Raccolta dei dati dei punti di interesse degli abbonati {#collecting-subscribers--points-of-interest-data}

Una risorsa personalizzata specifica ti consente di definire i dati da raccogliere dagli abbonati alle tue applicazioni.

Questo passaggio è descritto nella sezione [Configurazione di un’app mobile tramite SDK V4](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html) pagina.

## Accesso alle app mobili utilizzate per raccogliere i dati sulla posizione {#accessing-mobile-apps-used-to-collect-location-data}

Per accedere alle applicazioni create correttamente in Adobe Campaign:

1. Fai clic su **Adobe** in alto a sinistra.
1. Seleziona **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** o **[!UICONTROL Mobile app (AEP SDK)]** a seconda dell’SDK.
1. Seleziona un’app mobile dall’elenco per visualizzarne le proprietà.

   ![](assets/poi_mobile_app_subscribers.png)

Un elenco degli abbonati all’applicazione viene visualizzato anche nel **[!UICONTROL Mobile application subscribers]** scheda. Gli abbonati sono tutti gli utenti che hanno installato l&#39;applicazione sul loro dispositivo mobile. I profili del database di Adobe Campaign sono identificati con un token di registrazione.

## Accesso ai dati sulla posizione raccolti {#accessing-collected-location-data}

Al termine della configurazione, i dati dei punti di interesse raccolti vengono elencati in **[!UICONTROL Places]** di ciascun profilo. Per accedere all&#39;elenco:

1. Seleziona un profilo.
1. Fai clic su **[!UICONTROL Edit profile properties]** a destra.
1. Seleziona la scheda **[!UICONTROL Places]**.

   ![](assets/poi_profile_places.png)

Vengono elencati i dati dei punti di interesse raccolti per il profilo corrente. I dati sulla posizione vengono memorizzati nel database di Adobe Campaign per sei mesi.

Per ulteriori informazioni sull’accesso e la modifica dei profili, consulta [Profili](../../audiences/using/about-profiles.md).
