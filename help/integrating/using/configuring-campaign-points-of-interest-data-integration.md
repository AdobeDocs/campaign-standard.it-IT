---
title: Configurazione dell’integrazione dei dati Campaign-Punti di interesse
description: Scopri come configurare la funzione Dati punti di interesse in Adobe Campaign per l'invio di messaggi personalizzati in base alla posizione degli abbonati.
page-status-flag: mai attivato
uuid: 0689a06c-cc1a-442f-95b8-a07fEC85d79
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integration
content-type: reference
topic-tags: utilizzo di campagne e analisi per dispositivi mobili
discoiquuid: a967c6cc-c53b-41b4-866b-90860d78f463
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Configurazione dell’integrazione dei dati Campaign-Punti di interesse{#configuring-campaign-points-of-interest-data-integration}

## Configurazione dell’integrazione dei dati Campaign-Points of Interest con gli SDK della piattaforma Adobe Experience {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>L'applicazione mobile deve già essere configurata in Adobe Campaign Standard tramite Adobe Experience Platform SDK. Per i passaggi dettagliati, consultate questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

Le applicazioni mobili utilizzate per raccogliere i dati sulla posizione devono essere configurate da un **amministratore** nell'interfaccia di Adobe Campaign.

Per poter utilizzare Adobe Experience Platform Location Services con applicazioni mobili configurate con l’SDK di Adobe Experience Platform, devi:

1. Aggiungi le estensioni **[!UICONTROL Places]** **[!UICONTROL Places Monitor]** e le estensioni alla configurazione dell'app mobile in Adobe Experience Platform Launch. Configurate l'applicazione mobile in Adobe Campaign. Consultate [Installare l’estensione Luoghi in Adobe Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-extension#install-the-places-extension-in-adobe-experience-platform-launch) e [Installare l’estensione Monitor Luoghi in Experience Platform Launch](https://placesdocs.com/places-services-by-adobe-documentation/configure-places-in-the-sdk/places-monitor-extension/using-the-places-monitor-extension).

1. Una volta configurate le estensioni, create elementi di dati all'interno **[!UICONTROL Adobe Experience Platform Launch]** per recuperare i dati da queste estensioni. Fare riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) per creare gli elementi dati.

1. Quindi, in **[!UICONTROL Adobe Experience Platform Launch]**, devi creare delle regole per supportare i casi di utilizzo di dispositivi mobili tra i punti di interesse e Adobe Campaign.\
   Questa regola verrà attivata quando un utente immette un geofencing **[!UICONTROL Point of Interest]**. Fate riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) per creare la regola.

1. Definite il vostro **[!UICONTROL Points of Interest]** in Luoghi. Consulta [Creare un punto di interesse](https://placesdocs.com/places-services-by-adobe-documentation/places-database-management-1/managing-pois-in-the-places-ui#create-a-poi).

1. Assicurati di accedere all'applicazione mobile e ai dati sulla posizione raccolti in Adobe Campaign. Consultate [Accesso alle app mobili utilizzate per raccogliere i dati](#accessing-mobile-apps-used-to-collect-location-data) sulla posizione e [Accesso ai dati](#accessing-collected-location-data)sulla posizione raccolti.

## Configurazione dell’integrazione dei dati Campaign-Points of Interest con SDK V4 {#configuring-campaign-poi-sdkv4}

Le applicazioni mobili utilizzate per raccogliere i dati sulla posizione devono essere configurate da un **amministratore** nell'interfaccia di Adobe Campaign.

Per utilizzare la funzione dati punto di interesse con applicazioni mobili configurate con SDK V4, è necessario:

1. Accesso ad Adobe Analytics per dispositivi mobili. Per ulteriori informazioni, contattate il vostro responsabile commerciale di Adobe.
1. Configurate l'applicazione mobile in Adobe Campaign. Consultate [Configurazione di un'app mobile in Campaign](#setting-up-a-mobile-app-in-campaign).
1. Configura l’applicazione mobile nell’interfaccia di Adobe Mobile Services. Questo consente di garantire che i dati raccolti da Adobe Mobile Services vengano inviati ad Adobe Campaign. Consultate [Configurazione di un’app mobile in Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).
1. Esegui la configurazione specifica dell’applicazione mobile:

   * Crea un pacchetto del file di configurazione scaricato dall'interfaccia di Adobe Mobile Services con l'applicazione mobile.
   * Integra l’SDK di Experience Cloud Mobile nella tua applicazione mobile. Consultate [Integrazione dell’SDK in un’applicazione](#integrating-the-sdk-into-a-mobile-application)mobile.

1. Definisci punti di interesse nell'interfaccia di Adobe Mobile Services. Consulta [Definizione dei punti di interesse in Adobe Mobile Services](#defining-points-of-interest-in-adobe-mobile-services).
1. Definite i dati che desiderate raccogliere dagli utenti iscritti all'applicazione mobile. Consulta [Raccolta dei dati sui punti di interesse](#collecting-subscribers--points-of-interest-data)degli abbonati.
1. Assicurati di accedere all'applicazione mobile e ai dati sulla posizione raccolti in Adobe Campaign. Consultate [Accesso alle app mobili utilizzate per raccogliere i dati](#accessing-mobile-apps-used-to-collect-location-data) sulla posizione e [Accesso ai dati](#accessing-collected-location-data)sulla posizione raccolti.

### Impostazione di un'app mobile in Adobe Campaign tramite SDK V4 {#setting-up-a-mobile-app-in-campaign}

Per poter raccogliere i dati dei punti di interesse con Adobe Campaign, devi configurare l'applicazione mobile da cui Adobe Campaign riceverà i dati.

1. Fate clic sul **[!UICONTROL Adobe Campaign]** logo, nell’angolo in alto a sinistra, quindi selezionate **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app]**.
1. Fate clic **[!UICONTROL Create]** per configurare un'applicazione.
1. Immettete un nome nel **[!UICONTROL Application name]** campo e fate clic su **[!UICONTROL Create]**.

   Non compilare la **[!UICONTROL Device-specific settings]** sezione. Ciò vale solo per la configurazione di applicazioni che ricevono notifiche push.

Nella **[!UICONTROL Mobile application properties]** sezione sono elencati due URL: **[!UICONTROL Collect PII endpoint]** e **[!UICONTROL Location Services endpoint]**. Saranno utilizzati nell'interfaccia di Adobe Mobile Services. Consultate [Configurazione di un’app mobile in Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).

* L' **[!UICONTROL Collect PII endpoint]** URL viene utilizzato per raccogliere gli Experience Cloud ID degli utenti e i token di registrazione dall'applicazione mobile quando viene avviata. Quando un utente accede all'applicazione utilizzando credenziali come e-mail, nome, cognome e così via, questi dati vengono anche raccolti e utilizzati per riconciliare il token di registrazione dell'utente con un profilo Adobe Campaign.
* L' **[!UICONTROL Location Services endpoint]** URL viene utilizzato per raccogliere dati sulla posizione, ad esempio latitudine, longitudine e raggio di un utente da un punto di interesse.

Ora puoi utilizzare questi valori in Adobe Mobile Services per completare la configurazione, come spiegato nella sezione [Configurazione di un'app mobile in Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services) .

![](assets/poi_mobile_app_properties.png)

### Configurazione di un'app mobile V4 in Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Per inviare i dati raccolti da Adobe Mobile Services ad Adobe Campaign, devi configurare i postback nell'interfaccia di Mobile Services.

Avrai bisogno di informazioni specifiche reperibili nei parametri dell'applicazione mobile impostati in Adobe Campaign (vedi [Impostazione di un'app mobile in Campaign](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

Devi avere accesso ad Adobe Analytics per eseguire la configurazione seguente. Se non sei un utente Adobe Analytics, contatta il tuo amministratore Adobe Campaign.

1. Accedete a [mobilemarketing.adobe.com](http://mobilemarketing.adobe.com/).
1. Create l'applicazione o selezionatene una esistente.
1. Vai alla **[!UICONTROL Manage App Settings]** pagina.
1. Nella sezione Servizio **ID** visitatori, seleziona **Abilita** e seleziona la tua organizzazione dall’elenco a discesa. Fate clic su **Salva**.

   >[!CAUTION]
   >
   >Questa organizzazione deve corrispondere a quella utilizzata nell'istanza di Adobe Campaign.

1. Click **[!UICONTROL Manage Postbacks]**.
1. Creare un postback.

   * Selezionare **[!UICONTROL PII]** come **[!UICONTROL Postback Type]**.
   * Nel **[!UICONTROL URL]** campo, copiate l’ **[!UICONTROL Collect PII Endpoint]** URL dall’applicazione mobile configurata nell’interfaccia di Adobe Campaign, preceduto dal nome del server. Consultate [Configurazione di un'app mobile in Campaign](#setting-up-a-mobile-app-in-campaign).
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

   * Impostate Tipo **di** contenuto come **[!UICONTROL application/json]**.
   * In **quali tag di dati viene attivato il postback?**, selezionate un evento, in genere **[!UICONTROL Launched]** e **[!UICONTROL exists]**.
   * Click **[!UICONTROL Save & Activate]**.

1. Crea un secondo postback.

   * Selezionare **[!UICONTROL Postback]** come **[!UICONTROL Postback Type]**.
   * Nel **[!UICONTROL URL]** campo, copiate l’ **[!UICONTROL Location Services Endpoint]** URL dall’applicazione mobile configurata nell’interfaccia di Adobe Campaign, preceduto dal nome del server. Consultate [Configurazione di un'app mobile in Campaign](#setting-up-a-mobile-app-in-campaign).
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

   * Impostate Tipo **di** contenuto come **[!UICONTROL application/json]**.
   * In **quali tag di dati viene attivato il postback?**, selezionare **[!UICONTROL campaign.test]** e **[!UICONTROL exists]**.
   * Click **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>Per informazioni dettagliate sulla configurazione dei postback, consulta la documentazione [di](https://marketing.adobe.com/resources/help/en_US/mobile/signals_.html)Adobe Mobile Services.

### Integrazione dell’SDK in un’applicazione mobile {#integrating-the-sdk-into-a-mobile-application}

Il kit di sviluppo software (SDK) del servizio core Mobile facilita l'integrazione di un'applicazione mobile in Adobe Campaign.

Questo passaggio è descritto in questa [pagina](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

### Definizione dei punti di interesse in Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Per definire i punti di interesse utilizzati per raccogliere i dati sulla posizione:

1. Vai all'interfaccia di Adobe Mobile Services.
1. Aggiungete l'applicazione.

   Per ulteriori informazioni sulla gestione delle applicazioni in Mobile Services, consulta la documentazione [di](https://marketing.adobe.com/resources/help/en_US/mobile/t_new_app.html)Adobe Mobile Services.

1. Definire i punti di interesse.

   Per ulteriori informazioni sulla gestione dei punti di interesse, consulta la documentazione [di](https://marketing.adobe.com/resources/help/en_US/mobile/t_manage_points.html)Adobe Mobile Services.

### Raccolta dei dati dei punti di interesse degli abbonati {#collecting-subscribers--points-of-interest-data}

Una risorsa personalizzata specifica consente di definire i dati che si desidera raccogliere dagli abbonati delle applicazioni.

Questo passaggio è descritto nella pagina [Configurazione di un’applicazione mobile tramite SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) .


## Accesso alle app mobili utilizzate per raccogliere i dati sulla posizione {#accessing-mobile-apps-used-to-collect-location-data}

Per accedere alle applicazioni create correttamente in Adobe Campaign:

1. Fate clic sul **[!UICONTROL Adobe Campaign]** logo, nell’angolo in alto a sinistra.
1. Seleziona **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Mobile app (SDK v4)]** o **[!UICONTROL Mobile app (AEP SDK)]** a seconda dell’SDK.
1. Selezionate un’applicazione mobile dall’elenco per visualizzarne le proprietà.

   ![](assets/poi_mobile_app_subscribers.png)

Nella **[!UICONTROL Mobile application subscribers]** scheda viene visualizzato anche un elenco degli utenti iscritti all'applicazione. Gli abbonati sono tutti gli utenti che hanno installato l’applicazione sul proprio dispositivo mobile. I profili del database di Adobe Campaign sono identificati con un token di registrazione.

## Accesso ai dati di posizione raccolti {#accessing-collected-location-data}

Al termine dell'impostazione, i dati raccolti sui punti di interesse sono elencati nella **[!UICONTROL Places]** scheda di ciascun profilo. Per accedere all'elenco:

1. Selezionare un profilo.
1. Fate clic sul **[!UICONTROL Edit profile properties]** pulsante a destra.
1. Selezionate la **[!UICONTROL Places]** scheda.

   ![](assets/poi_profile_places.png)

Vengono elencati i dati raccolti sui punti di interesse per il profilo corrente. I dati sulla posizione vengono memorizzati nel database di Adobe Campaign per sei mesi.

Per ulteriori informazioni sull'accesso e la modifica dei profili, vedere [Profili](../../audiences/using/about-profiles.md).
