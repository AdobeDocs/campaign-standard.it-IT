---
title: Configurazione dell’integrazione dei dati Campaign-Punti di interesse
description: Scopri come configurare la funzione Dati punti di interesse in  Adobe Campaign per l'invio di messaggi personalizzati in base alla posizione degli abbonati.
page-status-flag: never-activated
uuid: 0689a06c-cc1a-442f-95b8-a07fcec85d79
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: a967c6cc-c53b-41b4-866b-90860d78f463
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 3%

---


# Configurazione dell’integrazione dei dati Campaign-Punti di interesse{#configuring-campaign-points-of-interest-data-integration}

## Configurazione dell’integrazione dei dati Campaign-Points of Interest con gli SDK Adobe Experience Platform {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>L’applicazione mobile deve essere già configurata in  Adobe Campaign Standard tramite Adobe Experience Platform SDK. For the detailed steps, refer to this [page](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html).

Le applicazioni mobili utilizzate per raccogliere i dati sulla posizione devono essere configurate da un **amministratore** nell&#39;interfaccia Adobe Campaign .

Per poter utilizzare Adobe Experience Platform Location Services con applicazioni mobili configurate con Adobe Experience Platform SDK, devi:

1. Aggiungi le estensioni **[!UICONTROL Places]** **[!UICONTROL Places Monitor]** e le estensioni alla configurazione dell&#39;app mobile in  Adobe Experience Platform Launch. Configurate l’applicazione mobile in  Adobe Campaign. Consultate [Installare l’estensione Luoghi in  Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-extension/places-extension.html#install-the-places-extension-in-adobe-experience-platform-launch) e [Installare l’estensione Monitor Luoghi in Experience Platform Launch](https://docs.adobe.com/content/help/en/places/using/places-ext-aep-sdks/places-monitor-extension/using-places-monitor-extension.html#install-the-places-monitor-extension-in-experience-platform-launch).

1. Una volta configurate le estensioni, create elementi di dati all&#39;interno **[!UICONTROL Adobe Experience Platform Launch]** per recuperare i dati da queste estensioni. Fare riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) per creare gli elementi dati.

1. Quindi, in **[!UICONTROL Adobe Experience Platform Launch]**, devi creare delle regole per supportare i casi di utilizzo di dispositivi mobili tra i punti di interesse e  Adobe Campaign.\
   Questa regola viene attivata quando un utente entra in un campo con geofrequenza **[!UICONTROL Point of Interest]**. Fate riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) per creare la regola.

1. Definite il vostro **[!UICONTROL Points of Interest]** in Luoghi. Consulta [Creare un punto di interesse](https://docs.adobe.com/content/help/en/places/using/poi-mgmt-ui/create-a-poi-ui.html).

1. Accertatevi di accedere all’applicazione mobile e ai dati sulla posizione raccolti in  Adobe Campaign. Consultate [Accesso alle app mobili utilizzate per raccogliere i dati](#accessing-mobile-apps-used-to-collect-location-data) sulla posizione e [Accesso ai dati](#accessing-collected-location-data)sulla posizione raccolti.

## Configurazione dell’integrazione dei dati Campaign-Points of Interest con SDK V4 {#configuring-campaign-poi-sdkv4}

Le applicazioni mobili utilizzate per raccogliere i dati sulla posizione devono essere configurate da un **amministratore** nell&#39;interfaccia Adobe Campaign .

Per utilizzare la funzione dati punto di interesse con applicazioni mobili configurate con SDK V4, è necessario:

1. Accesso a  Adobe Analytics per dispositivi mobili. Per maggiori informazioni, consulta il contratto di licenza o contatta l&#39;amministratore dell&#39;account  Adobe.
1. Configurate l’applicazione mobile in  Adobe Campaign. Consultate [Configurazione di un&#39;app mobile in Campaign](#setting-up-a-mobile-app-in-campaign).
1. Configurate l&#39;applicazione mobile nell&#39;interfaccia di  Adobe Mobile Services. Questo consente di garantire che i dati raccolti da  Adobe Mobile Services vengano inviati a  Adobe Campaign. Consulta [Configurazione di un&#39;app mobile in  Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).
1. Esegui la configurazione specifica dell’applicazione mobile:

   * Creare un pacchetto del file di configurazione scaricato dall&#39;interfaccia di  Adobe Mobile Services con l&#39;applicazione mobile.
   * Integra l’SDK per dispositivi mobili  Experience Cloud nell’applicazione mobile. Consultate [Integrazione dell’SDK in un’applicazione](#integrating-the-sdk-into-a-mobile-application)mobile.

1. Definisci punti di interesse nell&#39;interfaccia  Adobe Mobile Services. Consulta [Definizione dei punti di interesse in  Adobe Mobile Services](#defining-points-of-interest-in-adobe-mobile-services).
1. Definite i dati che desiderate raccogliere dagli utenti iscritti all&#39;applicazione mobile. Consulta [Raccolta dei dati sui punti di interesse](#collecting-subscribers--points-of-interest-data)degli abbonati.
1. Accertatevi di accedere all’applicazione mobile e ai dati sulla posizione raccolti in  Adobe Campaign. Consultate [Accesso alle app mobili utilizzate per raccogliere i dati](#accessing-mobile-apps-used-to-collect-location-data) sulla posizione e [Accesso ai dati](#accessing-collected-location-data)sulla posizione raccolti.

### Configurazione di un&#39;app mobile in  Adobe Campaign con SDK V4 {#setting-up-a-mobile-app-in-campaign}

Per poter raccogliere i dati dei punti di interesse con  Adobe Campaign, devi configurare l&#39;applicazione mobile da cui  Adobe Campaign riceverà i dati.

1. Fai clic sul logo **[!UICONTROL Adobe Campaign]** nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**.
1. Fate clic **[!UICONTROL Create]** per configurare un&#39;applicazione.
1. Immettete un nome nel **[!UICONTROL Application name]** campo e fate clic su **[!UICONTROL Create]**.

   Non compilare la **[!UICONTROL Device-specific settings]** sezione. Ciò vale solo per la configurazione di applicazioni che ricevono notifiche push.

Nella **[!UICONTROL Mobile application properties]** sezione sono elencati due URL: **[!UICONTROL Collect PII endpoint]** e **[!UICONTROL Location Services endpoint]**. Saranno utilizzati nell&#39;interfaccia di  Adobe Mobile Services. Consulta [Configurazione di un&#39;app mobile in  Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).

* L&#39; **[!UICONTROL Collect PII endpoint]** URL viene utilizzato per raccogliere gli ID Experience Cloud  utenti e i token di registrazione dall&#39;applicazione mobile quando viene avviata. Quando un utente accede all&#39;applicazione utilizzando le credenziali come e-mail, nome, cognome e così via, questi dati vengono anche raccolti e utilizzati per riconciliare il token di registrazione dell&#39;utente con un profilo Adobe Campaign .
* L&#39; **[!UICONTROL Location Services endpoint]** URL viene utilizzato per raccogliere dati sulla posizione, ad esempio latitudine, longitudine e raggio di un utente da un punto di interesse.

Ora puoi utilizzare questi valori in  Adobe Mobile Services per completare la configurazione, come spiegato nella sezione [Configurazione di un&#39;app mobile  Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services) .

![](assets/poi_mobile_app_properties.png)

### Configurazione di un&#39;app mobile V4 in  Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Per inviare i dati raccolti da  Adobe Mobile Services a  Adobe Campaign, devi configurare i postback nell&#39;interfaccia di Mobile Services.

Avrai bisogno di informazioni specifiche reperibili nei parametri dell&#39;applicazione mobile impostati in  Adobe Campaign (vedi [Impostazione di un&#39;app mobile in Campaign](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

È necessario avere accesso a  Adobe Analytics per eseguire la configurazione seguente. Se non siete utenti Adobe Analytics , contattate il vostro amministratore Adobe Campaign .

1. Accedete a [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/).
1. Create l&#39;applicazione o selezionatene una esistente.
1. Go to the **[!UICONTROL Manage App Settings]** page.
1. Nella sezione Servizio **ID** visitatori, seleziona **Abilita** e seleziona la tua organizzazione dall’elenco a discesa. Fai clic su **Salva**.

   >[!CAUTION]
   >
   >Questa organizzazione deve corrispondere a quella utilizzata nell&#39;istanza di Adobe Campaign .

1. Fai clic su **[!UICONTROL Manage Postbacks]**.
1. Creare un postback.

   * Selezionare **[!UICONTROL PII]** come **[!UICONTROL Postback Type]**.
   * Nel **[!UICONTROL URL]** campo, copiate l’ **[!UICONTROL Collect PII Endpoint]** URL dall’applicazione mobile configurata nell’interfaccia Adobe Campaign , preceduta dal nome del server. Consultate [Configurazione di un&#39;app mobile in Campaign](#setting-up-a-mobile-app-in-campaign).
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
   * Fai clic su **[!UICONTROL Save & Activate]**.

1. Crea un secondo postback.

   * Selezionare **[!UICONTROL Postback]** come **[!UICONTROL Postback Type]**.
   * Nel **[!UICONTROL URL]** campo, copiate l’ **[!UICONTROL Location Services Endpoint]** URL dall’applicazione mobile configurata nell’interfaccia Adobe Campaign , preceduta dal nome del server. Consultate [Configurazione di un&#39;app mobile in Campaign](#setting-up-a-mobile-app-in-campaign).
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
   * In **quali tag di dati viene attivato il postback?**, selezionate **[!UICONTROL campaign.test]** e **[!UICONTROL exists]**.
   * Fai clic su **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>Per informazioni dettagliate sulla configurazione dei postback, consulta la documentazione [](https://docs.adobe.com/content/help/en/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html)Mobile Services.

### Integrazione dell’SDK in un’applicazione mobile {#integrating-the-sdk-into-a-mobile-application}

Il kit di sviluppo software (SDK) del servizio core Mobile facilita l&#39;integrazione di un&#39;applicazione mobile in  Adobe Campaign.

Questo passaggio è descritto in questa [pagina](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html).

### Definizione dei punti di interesse in  Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Per definire i punti di interesse utilizzati per raccogliere i dati sulla posizione:

1. Vai all&#39;interfaccia di  Adobe Mobile Services.
1. Aggiungete l&#39;applicazione.

   Per ulteriori informazioni sulla gestione delle applicazioni in Mobile Services, consulta la documentazione [](https://docs.adobe.com/content/help/en/mobile-services/using/manage-apps-ug/t-new-app.html)Mobile Services.

1. Definire i punti di interesse.

   Per ulteriori informazioni sulla gestione dei punti di interesse, consulta la documentazione [](https://docs.adobe.com/content/help/en/mobile-services/using/location-ug/t-manage-points.html)Mobile Services.

### Raccolta dei dati dei punti di interesse degli abbonati {#collecting-subscribers--points-of-interest-data}

Una risorsa personalizzata specifica consente di definire i dati che si desidera raccogliere dagli abbonati delle applicazioni.

Questo passaggio è descritto nella pagina [Configurazione di un’applicazione mobile tramite SDK V4](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html) .


## Accesso alle app mobili utilizzate per raccogliere i dati sulla posizione {#accessing-mobile-apps-used-to-collect-location-data}

Per accedere alle applicazioni create correttamente in  Adobe Campaign:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner.
1. Seleziona **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** o **[!UICONTROL Mobile app (AEP SDK)]** a seconda dell’SDK.
1. Selezionate un’applicazione mobile dall’elenco per visualizzarne le proprietà.

   ![](assets/poi_mobile_app_subscribers.png)

Nella **[!UICONTROL Mobile application subscribers]** scheda viene visualizzato anche un elenco degli utenti iscritti all&#39;applicazione. Gli abbonati sono tutti gli utenti che hanno installato l’applicazione sul proprio dispositivo mobile. I profili  database Adobe Campaign sono identificati con un token di registrazione.

## Accesso ai dati di posizione raccolti {#accessing-collected-location-data}

Al termine dell&#39;impostazione, i dati raccolti sui punti di interesse sono elencati nella **[!UICONTROL Places]** scheda di ciascun profilo. Per accedere all&#39;elenco:

1. Selezionare un profilo.
1. Fate clic sul **[!UICONTROL Edit profile properties]** pulsante a destra.
1. Seleziona la scheda **[!UICONTROL Places]**.

   ![](assets/poi_profile_places.png)

Vengono elencati i dati raccolti sui punti di interesse per il profilo corrente. I dati sulla posizione vengono memorizzati nel database Adobe Campaign  per sei mesi.

Per ulteriori informazioni sull&#39;accesso e la modifica dei profili, vedere [Profili](../../audiences/using/about-profiles.md).
