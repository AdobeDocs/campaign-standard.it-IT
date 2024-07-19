---
title: Configurazione delle regole di tag per supportare casi d’uso di Adobe Campaign Standard
description: Scopri come configurare le regole di tag per supportare casi d’uso di Adobe Campaign Standard
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: 597ece8d833a216f0540f801461b08fdc9865024
workflow-type: tm+mt
source-wordcount: '983'
ht-degree: 2%

---

# Configurazione delle regole di tag per supportare casi d’uso di Adobe Campaign Standard {#configuring-rules-launch}

Nell&#39;interfaccia utente di Data Collection, crea elementi dati e regole per inviare dati PII e altri dati dalle app mobili a [!DNL Adobe Campaign Standard].

Per fare in modo che tutte le modifiche alla configurazione nell’interfaccia utente di Data Collection abbiano effetto, devi pubblicare tali modifiche. Per ulteriori informazioni, vedere [Pubblicazione](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration).

Per creare regole nell’interfaccia utente di Data Collection, effettua le seguenti operazioni:

1. [Creazione di elementi dati](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Creazione di regole](../../administration/using/configuring-rules-launch.md#create-data-elements) per i casi d&#39;uso che si desidera supportare:
   * [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback del tracciamento in-app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Postback tracciamento notifiche push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Postback posizione](../../administration/using/configuring-rules-launch.md#location-postback)

## Creazione di elementi dati {#create-data-elements}

Di seguito sono riportati gli elementi dati che consigliamo di creare nell’interfaccia utente di Data Collection.
Puoi creare elementi di dati aggiuntivi in base alle tue esigenze.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

Per creare questi elementi dati:

1. Nell&#39;interfaccia utente di Data Collection, dal dashboard dell&#39;applicazione mobile, fare clic sulla scheda **[!UICONTROL Data Elements]**.

1. Per creare l&#39;elemento dati **[!UICONTROL Experience Cloud ID]**, fare clic su **[!UICONTROL Create New Data Element]**.

1. Nel campo **[!UICONTROL Name]**, ad esempio, digita in **mcid**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi **[!UICONTROL Experience Cloud ID]** nel menu a discesa del tipo **[!UICONTROL Data element]**.

   ![](assets/do-not-localize/rules_1.png)

1. Per creare l&#39;elemento dati Pkey, fare clic su **[!UICONTROL Add data element]**.

1. Nel campo **[!UICONTROL Name]**, ad esempio, digitare **pkey**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Adobe Campaign Standard]**. Quindi **[!UICONTROL pkey]** nel menu a discesa del tipo **[!UICONTROL Data element]**.

1. Per creare l&#39;elemento dati del server Campaign, fare clic su **[!UICONTROL Add data element]**.

1. Nel campo **[!UICONTROL Name]** digitare un nome, ad esempio **camp-server**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Adobe Campaign Standard]**. Quindi, **[!UICONTROL Campaign Server]** nel menu a discesa del tipo **[!UICONTROL Data element]**.

## Creazione di regole {#creating-rules}

È necessario creare regole per i seguenti elementi:

* [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback del tracciamento in-app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Postback tracciamento notifiche push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Postback posizione](../../administration/using/configuring-rules-launch.md#location-postback)

### Postback PII {#pii-postback}

>[!NOTE]
>
>Per inviare informazioni PII da un’app mobile ad Adobe Campaign, devi implementare un’API SDK. Per ulteriori informazioni, vai a [CollectPII](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#collectpii).

Per inviare dati PII a [!DNL Adobe Campaign Standard], crea una regola nell&#39;interfaccia utente di Data Collection:

1. Nell&#39;interfaccia utente di Data Collection, dal dashboard dell&#39;applicazione mobile, fare clic sulla scheda **[!UICONTROL Rules]** e quindi su **[!UICONTROL Create New Rule]**.

1. Digitare un nome, ad esempio **Mobile Core - Raccogli PII**.

1. Nella sezione **[!UICONTROL Events]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Collect PII]** nel menu a discesa **[!UICONTROL Event type]**.

1. Fai clic su **[!UICONTROL Keep changes]**.

1. Nella sezione **[!UICONTROL Actions]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Send PII]** nel menu a discesa **[!UICONTROL Action type]**.

1. In **[!UICONTROL URL]**, immettere il seguente URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Selezionare la casella di controllo **[!UICONTROL Add Post Body]**.

1. In **[!UICONTROL Post Body]**, digitare quanto segue:

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "pushPlatform":
   "{%contextdata.pushPlatform%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   MarketingCloudId consente di riconciliare gli abbonati all’app con i destinatari nel database ed è, di conseguenza, obbligatorio. Puoi specificare altre coppie chiave-valore in base alle tue esigenze aziendali. Nell’esempio precedente, e-mail, nome e cognome vengono trasmessi dall’app.

   Le chiavi (ad esempio cusEmail, cusFirstName e cusLastName) devono corrispondere agli ID campo definiti nella risorsa personalizzata nell’istanza di Adobe Campaign Standard. Le variabili di valore (ad esempio e-mail, firstName e LastName) devono corrispondere alle chiavi nei dati JSON inviati dall’app mobile durante la chiamata dell’API collectPII di AMS dal codice dell’app.

   Puoi anche trasmettere i dati del ciclo di vita nel postback Raccogli PII o in un postback diverso a seconda dei trigger dell’evento. di seguito è riportato un esempio di JSON per i dati del ciclo di vita:

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "pushPlatform":"{%contextdata.pushPlatform%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   Gli elementi dati definiti nell’interfaccia utente di Data Collection devono essere racchiusi tra percentuali doppie, ad esempio `%%mcid%%`, mentre le variabili di contesto dell’app devono essere racchiuse tra percentuali singole, ad esempio %contextdata.email%.

1. In **[!UICONTROL Content Type]**, digitare **application/json**.

1. In **[!UICONTROL Timeout]**, selezionare 0.

   ![](assets/do-not-localize/rules_2.png)

I dati utente sono ora configurati per l’invio a Campaign.

### Postback del tracciamento in-app {#inapp-tracking-postback}

>[!NOTE]
>
>Se utilizzi Android ACPCore v1.4.0 o versione successiva/ iOS ACPCore v2.3.0 o versione successiva, non è necessario configurare i postback di tracciamento.

Per inviare i dati di tracciamento a [!DNL Adobe Campaign Standard] per generare rapporti sull&#39;interazione degli utenti con i messaggi in-app nell&#39;app mobile, crea la regola seguente nell&#39;interfaccia utente di Data Collection:

1. Nell&#39;interfaccia utente di Data Collection, dal dashboard dell&#39;applicazione mobile, selezionare la scheda **[!UICONTROL Rules]** e fare clic su **[!UICONTROL Add Rule]**.

1. Digita un nome, ad esempio **Adobe Campaign - Tracciamento dei clic in-app**.

1. Nella sezione **[!UICONTROL Events]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Adobe Campaign Standard]**. Quindi, **[!UICONTROL In-App click tracking]** nel menu a discesa **[!UICONTROL Event type]**.

1. Fai clic su **[!UICONTROL Keep changes]**.

1. Nella sezione **[!UICONTROL Actions]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Send postback]** nel menu a discesa **[!UICONTROL Event type]**.

1. In **[!UICONTROL URL]**, digitare il seguente URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Selezionare la casella di controllo **[!UICONTROL Add post body]**.

1. In **[!UICONTROL Post Body]**, digitare **{}**.

1. In **[!UICONTROL Content Type]**, digitare **application/json**.

1. In **[!UICONTROL Timeout]**, selezionare 0.

   ![](assets/do-not-localize/rules_3.png)

### Postback tracciamento notifiche push {#push-tracking-postback}

>[!NOTE]
>
>Se utilizzi Android ACPCore v1.4.0 o versione successiva/ iOS ACPCore v2.3.0 o versione successiva, non è necessario configurare i postback di tracciamento.

Per inviare i dati di tracciamento a [!DNL Adobe Campaign Standard], in modo da tenere traccia delle consegne delle notifiche push e dell&#39;interazione degli utenti con l&#39;app mobile, è necessario creare una regola nell&#39;interfaccia utente di Data Collection.

Per ulteriori informazioni sul tracciamento push, vedere [Tracciamento push](../../administration/using/push-tracking.md).

Per tenere traccia delle azioni eseguite nell’app, utilizza l’API trackAction. Per ulteriori informazioni, consulta [Tracciare le azioni eseguite nell&#39;app](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. Nell&#39;interfaccia utente di Data Collection, dal dashboard dell&#39;applicazione mobile, fare clic sulla scheda **[!UICONTROL Rules]** e quindi su **[!UICONTROL Add Rule]**.

1. Digita un nome, ad esempio **Adobe Campaign - monitoraggio dei clic push**.

1. Nella sezione **[!UICONTROL Events]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Track Action]** nel menu a discesa **[!UICONTROL Event type]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Action]**, selezionare **[!UICONTROL Action]**, selezionare **[!UICONTROL equals]** e digitare **tracking**.

1. Fai clic su **[!UICONTROL Keep changes]**. Nella sezione **[!UICONTROL Actions]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Send postback]** nel menu a discesa **[!UICONTROL Action type]**.

1. In **[!UICONTROL URL]**, immettere il seguente URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Selezionare la casella di controllo **[!UICONTROL Add post body]**.

1. Aggiungi il corpo del post, ad esempio { }.

1. In **[!UICONTROL Content Type]**, digitare **application/json**.

1. In **[!UICONTROL Timeout]**, selezionare 0.

### Postback posizione {#location-postback}

1. Nell&#39;interfaccia utente di Data Collection, dal dashboard dell&#39;applicazione mobile, fare clic sulla scheda **[!UICONTROL Rules]** e quindi su **[!UICONTROL Add Rule]**.

1. Digita un nome, ad esempio **Postback località**.

1. Nella sezione **[!UICONTROL Events]**, fare clic su **[!UICONTROL Add]**.

1. Crea un evento, ad esempio Enter POI (Inserisci POI) o Exit POI (Esci POI). Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **Places - Beta**. Quindi, **Inserisci POI** o **Esci POI** nel menu a discesa **[!UICONTROL Event type]**.

1. Immetti un nome, ad esempio **Places - Beta - Enter POI** or **Exit POI**.

1. Nella sezione **[!UICONTROL Actions]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Send postback]** dal menu a discesa **[!UICONTROL Action type]**.

1. Immetti un nome, ad esempio **Mobile Core - Send Location Postback**.

1. In **[!UICONTROL URL]**, immettere il seguente URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Selezionare la casella di controllo **[!UICONTROL Add post body]** e aggiungere il corpo del post, ad esempio:

   ```
   {
   "locationData": {
       "distances": "{%%Distance%%}",
       "poiLabel": "{%%POILabel%%}",
       "latitude": "{%%Latitude%%}",
       "longitude": "{%%Longitude%%}",
       "appId": "{%%AppId%%}",
       "marketingCloudId": "{%%ECID%%}"
   }
   }
   ```

   >[!NOTE]
   >
   >Nell&#39;esempio precedente, gli elementi dati sul lato destro devono essere configurati nell&#39;interfaccia utente di Data Collection sfruttando i passaggi descritti in [Creazione di elementi dati](../../administration/using/configuring-rules-launch.md#create-data-elements). Gli elementi dati sul lato sinistro sono supportati in [!DNL Adobe Campaign Standard] e non richiedono alcuna configurazione. Se sono necessari dati aggiuntivi, è necessario eseguire estensioni di risorse personalizzate in [!DNL Adobe Campaign Standard].

1. In **[!UICONTROL Content Type]**, digitare **application/json**.

1. In **[!UICONTROL Timeout]**, selezionare 5.

   ![](assets/do-not-localize/rules_4.png)
