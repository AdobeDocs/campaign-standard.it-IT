---
title: Configurazione dell’integrazione di Campaign con i dati Punti di interesse
description: Scopri come configurare la funzione di dati Punti di interesse in Adobe Campaign per inviare messaggi personalizzati in base alla posizione degli abbonati.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: b097b3fa-f949-446e-ad44-cc6ca025ee55
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 1%

---

# Configurazione dell’integrazione di Campaign con i dati Punti di interesse{#configuring-campaign-points-of-interest-data-integration}

## Configurazione dell’integrazione dei dati Campaign-Punti di interesse con gli SDK di Adobe Experience Platform {#configuring-campaign-poi-aep-sdk}

>[!NOTE]
>
>L’app mobile deve essere già configurata in Adobe Campaign Standard utilizzando Adobe Experience Platform SDK. Per i passaggi dettagliati, fai riferimento a questa [pagina](https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html?lang=it).

Le app mobili utilizzate per raccogliere i dati sulla posizione devono essere configurate da un **amministratore** nell&#39;interfaccia di Adobe Campaign.

Per poter utilizzare Adobe Experience Platform Location Services con le applicazioni per dispositivi mobili configurate con Adobe Experience Platform SDK, è necessario:

1. Aggiungi l&#39;estensione **[!UICONTROL Places]** alla configurazione della tua app mobile nell&#39;interfaccia utente di Data Collection. Configura l’app mobile in Adobe Campaign. Consulta [Installare l&#39;estensione Luoghi](https://developer.adobe.com/client-sdks/solution/places).

1. Una volta configurate le estensioni, crea elementi dati nell’interfaccia utente di Data Collection per recuperare dati da queste estensioni. Consulta questa [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Step1Createdataelements) per creare gli elementi dati.

1. Quindi, nell’interfaccia utente di Data Collection, devi creare regole per supportare i casi d’uso per dispositivi mobili tra Point of Interests e Adobe Campaign.\
   Questa regola verrà attivata quando un utente immette un elemento **[!UICONTROL Point of Interest]** delimitato geograficamente. Fai riferimento a questa [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#Locationpostback) per creare la regola.

1. Definisci **[!UICONTROL Points of Interest]** in Places. Vedere [Creare un punto di interesse](https://experienceleague.adobe.com/docs/places/using/poi-mgmt-ui/create-a-poi-ui.html).

1. Assicurati di accedere all’app mobile e ai dati sulla posizione raccolti in Adobe Campaign. Consulta [Accesso alle app mobili utilizzate per raccogliere i dati sulla posizione](#accessing-mobile-apps-used-to-collect-location-data) e [Accesso ai dati sulla posizione raccolti](#accessing-collected-location-data).

## Configurazione dell’integrazione dei dati Campaign-Punti di interesse tramite SDK V4 {#configuring-campaign-poi-sdkv4}

Le app mobili utilizzate per raccogliere i dati sulla posizione devono essere configurate da un **amministratore** nell&#39;interfaccia di Adobe Campaign.

Per utilizzare la funzione di dati dei punti di interesse con le app mobili configurate con SDK V4, è necessario:

1. Accedere ad Adobe Analytics per dispositivi mobili. Controlla il contratto di licenza o contatta il responsabile dell’account Adobe per ulteriori informazioni.
1. Configura l’app mobile in Adobe Campaign. Consulta [Configurazione di un&#39;app mobile in Campaign](#setting-up-a-mobile-app-in-campaign).
1. Configura l’app mobile nell’interfaccia di Adobe Mobile Services. Questo consente di assicurarsi che i dati raccolti da Adobe Mobile Services vengano inviati ad Adobe Campaign. Vedi [Configurazione di un&#39;app mobile in Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).
1. Esegui la configurazione specifica dell’app mobile:

   * Crea un pacchetto del file di configurazione scaricato dall&#39;interfaccia di Adobe Mobile Services con l&#39;app mobile.
   * Integra Experience Cloud Mobile SDK nella tua app mobile. Vedi [Integrazione di SDK in un&#39;app mobile](#integrating-the-sdk-into-a-mobile-application).

1. Definisci i punti di interesse nell’interfaccia di Adobe Mobile Services. Vedi [Definizione dei punti di interesse in Adobe Mobile Services](#defining-points-of-interest-in-adobe-mobile-services).
1. Definisci i dati da raccogliere dagli abbonati all’app mobile. Vedi [Raccolta dei dati dei punti di interesse degli abbonati](#collecting-subscribers--points-of-interest-data).
1. Assicurati di accedere all’app mobile e ai dati sulla posizione raccolti in Adobe Campaign. Consulta [Accesso alle app mobili utilizzate per raccogliere i dati sulla posizione](#accessing-mobile-apps-used-to-collect-location-data) e [Accesso ai dati sulla posizione raccolti](#accessing-collected-location-data).

### Configurazione di un’app mobile in Adobe Campaign tramite SDK V4 {#setting-up-a-mobile-app-in-campaign}

Per poter raccogliere i dati dei punti di interesse con Adobe Campaign, devi configurare l’app mobile da cui Adobe Campaign riceverà i dati.

1. Fai clic sul logo **Adobe** nell&#39;angolo in alto a sinistra, quindi seleziona **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app]**.
1. Fare clic su **[!UICONTROL Create]** per configurare un&#39;applicazione.
1. Immettere un nome nel campo **[!UICONTROL Application name]** e fare clic su **[!UICONTROL Create]**.

   Non compilare la sezione **[!UICONTROL Device-specific settings]**. Questo si applica solo alla configurazione di applicazioni che ricevono notifiche push.

Nella sezione **[!UICONTROL Mobile application properties]** sono elencati due URL: **[!UICONTROL Collect PII endpoint]** e **[!UICONTROL Location Services endpoint]**. Verranno utilizzati nell’interfaccia di Adobe Mobile Services. Vedi [Configurazione di un&#39;app mobile in Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).

* L&#39;URL **[!UICONTROL Collect PII endpoint]** viene utilizzato per raccogliere gli ID Experience Cloud e i token di registrazione degli utenti dall&#39;app mobile all&#39;avvio. Quando un utente accede all’applicazione utilizzando credenziali quali e-mail, nome, cognome e così via, questi dati vengono raccolti e utilizzati anche per riconciliare il token di registrazione dell’utente con un profilo Adobe Campaign.
* L&#39;URL **[!UICONTROL Location Services endpoint]** viene utilizzato per raccogliere dati sulla posizione come latitudine, longitudine e raggio di un utente da un punto di interesse.

È ora possibile utilizzare questi valori in Adobe Mobile Services per completare la configurazione, come spiegato nella sezione [Configurazione di un&#39;app mobile in Adobe Mobile Services](#configuring-a-mobile-app-in-adobe-mobile-services).

![](assets/poi_mobile_app_properties.png)

### Configurazione di un’app mobile V4 in Adobe Mobile Services {#configuring-a-mobile-app-in-adobe-mobile-services}

Per inviare i dati raccolti da Adobe Mobile Services ad Adobe Campaign, devi configurare i postback nell’interfaccia di Mobile Services.

Saranno necessarie informazioni specifiche che è possibile trovare nei parametri delle app mobili impostati in Adobe Campaign (vedere [Configurazione di un&#39;app mobile in Campaign](#setting-up-a-mobile-app-in-campaign)):

* **[!UICONTROL IMS Organization ID]**
* **[!UICONTROL Collect PII Endpoint]**
* **[!UICONTROL Location Services endpoint]**

Devi avere accesso ad Adobe Analytics per effettuare la seguente configurazione. Se non sei un utente di Adobe Analytics, contatta il tuo amministratore Adobe Campaign.

1. Accedi a [mobilemarketing.adobe.com](https://mobilemarketing.adobe.com/).
1. Crea l’applicazione o selezionane una esistente.
1. Passare alla pagina **[!UICONTROL Manage App Settings]**.
1. Nella sezione **Servizio ID visitatori**, seleziona **Abilita** e seleziona la tua organizzazione dall&#39;elenco a discesa. Fai clic su **Salva**.

   >[!CAUTION]
   >
   >Questa organizzazione deve essere la stessa utilizzata nell’istanza di Adobe Campaign.

1. Fai clic su **[!UICONTROL Manage Postbacks]**.
1. Crea un postback.

   * Seleziona **[!UICONTROL PII]** come **[!UICONTROL Postback Type]**.
   * Nel campo **[!UICONTROL URL]**, copia l&#39;URL **[!UICONTROL Collect PII Endpoint]** dall&#39;app mobile configurata nell&#39;interfaccia di Adobe Campaign, preceduto dal nome del server. Consulta [Configurazione di un&#39;app mobile in Campaign](#setting-up-a-mobile-app-in-campaign).
   * Compila il campo **[!UICONTROL Post Body]** come segue:

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

   * Imposta **Tipo di contenuto** come **[!UICONTROL application/json]**.
   * In **Quali tag di dati attivano il postback?**, selezionare qualsiasi evento, in genere **[!UICONTROL Launched]** e **[!UICONTROL exists]**.
   * Fai clic su **[!UICONTROL Save & Activate]**.

1. Crea un secondo postback.

   * Seleziona **[!UICONTROL Postback]** come **[!UICONTROL Postback Type]**.
   * Nel campo **[!UICONTROL URL]**, copia l&#39;URL **[!UICONTROL Location Services Endpoint]** dall&#39;app mobile configurata nell&#39;interfaccia di Adobe Campaign, preceduto dal nome del server. Consulta [Configurazione di un&#39;app mobile in Campaign](#setting-up-a-mobile-app-in-campaign).
   * Compila il campo **[!UICONTROL Post Body]** come segue:

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

   * Imposta **Tipo di contenuto** come **[!UICONTROL application/json]**.
   * In **Quali tag di dati attivano il postback?**, selezionare **[!UICONTROL campaign.test]** e **[!UICONTROL exists]**.
   * Fai clic su **[!UICONTROL Save & Activate]**.

>[!NOTE]
>
>Per informazioni dettagliate sulla configurazione dei postback, consulta la [documentazione di Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/manage-app-settings-ug/configuring-app/signals.html).

### Integrazione di SDK in un’app mobile {#integrating-the-sdk-into-a-mobile-application}

Il kit di sviluppo software (SDK) del servizio core Mobile facilita l’integrazione di un’app mobile in Adobe Campaign.

Questo passaggio è descritto in questa [pagina](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html).

### Definizione dei punti di interesse in Adobe Mobile Services {#defining-points-of-interest-in-adobe-mobile-services}

Per definire i punti di interesse utilizzati per raccogliere i dati sulla posizione:

1. Passa all’interfaccia di Adobe Mobile Services.
1. Aggiungi l’applicazione.

   Per ulteriori informazioni sulla gestione delle applicazioni in Mobile Services, consulta la [documentazione di Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/manage-apps-ug/t-new-app.html).

1. Definisci i punti di interesse.

   Per ulteriori informazioni sulla gestione dei punti di interesse, consulta la [documentazione di Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/location-ug/t-manage-points.html).

### Raccolta dei dati dei punti di interesse degli abbonati {#collecting-subscribers--points-of-interest-data}

Una risorsa personalizzata specifica ti consente di definire i dati da raccogliere dagli abbonati alle tue applicazioni.

Questo passaggio è descritto nella pagina [Configurazione di un&#39;app mobile tramite SDK V4](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html).

## Accesso alle app mobili utilizzate per raccogliere i dati sulla posizione {#accessing-mobile-apps-used-to-collect-location-data}

Per accedere alle applicazioni create correttamente in Adobe Campaign:

1. Fai clic sul logo **Adobe** nell&#39;angolo in alto a sinistra.
1. Selezionare **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK v4)]** o **[!UICONTROL Mobile app (AEP SDK)]** a seconda di SDK.
1. Seleziona un’app mobile dall’elenco per visualizzarne le proprietà.

   ![](assets/poi_mobile_app_subscribers.png)

Nella scheda **[!UICONTROL Mobile application subscribers]** viene inoltre visualizzato un elenco degli abbonati all&#39;applicazione. Gli abbonati sono tutti gli utenti che hanno installato l&#39;applicazione sul loro dispositivo mobile. I profili del database di Adobe Campaign sono identificati con un token di registrazione.

## Accesso ai dati sulla posizione raccolti {#accessing-collected-location-data}

Al termine della configurazione, i dati dei punti di interesse raccolti vengono elencati nella scheda **[!UICONTROL Places]** di ciascun profilo. Per accedere all&#39;elenco:

1. Seleziona un profilo.
1. Fare clic sul pulsante **[!UICONTROL Edit profile properties]** a destra.
1. Seleziona la scheda **[!UICONTROL Places]**.

   ![](assets/poi_profile_places.png)

Vengono elencati i dati dei punti di interesse raccolti per il profilo corrente. I dati sulla posizione vengono memorizzati nel database di Adobe Campaign per sei mesi.

Per ulteriori informazioni sull&#39;accesso e la modifica dei profili, vedere [Profili](../../audiences/using/about-profiles.md).
