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

Nell’interfaccia utente di Data Collection, crea elementi dati e regole per inviare dati PII e altri dati dalle app mobili a [!DNL Adobe Campaign Standard].

Per fare in modo che tutte le modifiche alla configurazione nell’interfaccia utente di Data Collection abbiano effetto, devi pubblicare tali modifiche. Per ulteriori informazioni, consulta [Pubblicazione](https://developer.adobe.com/client-sdks/documentation/getting-started/create-a-mobile-property/#publish-the-configuration).

Per creare regole nell’interfaccia utente di Data Collection, effettua le seguenti operazioni:

1. [Creazione di elementi dati](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Creazione di regole](../../administration/using/configuring-rules-launch.md#create-data-elements) per i casi d’uso che desideri supportare:
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

1. Nell’interfaccia utente di Data Collection, dal dashboard dell’app mobile, fai clic su **[!UICONTROL Data Elements]** scheda.

1. Per creare **[!UICONTROL Experience Cloud ID]** elemento dati, fai clic su **[!UICONTROL Create New Data Element]**.

1. In **[!UICONTROL Name]** campo, ad esempio digitare **mcid**.

1. Dalla sezione **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Then **[!UICONTROL Experience Cloud ID]** nel **[!UICONTROL Data element]** elenco a discesa tipo.

   ![](assets/do-not-localize/rules_1.png)

1. Per creare l’elemento dati Pkey, fai clic su **[!UICONTROL Add data element]**.

1. In **[!UICONTROL Name]** campo, ad esempio digitare **pkey**.

1. Dalla sezione **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Adobe Campaign Standard]**. Then **[!UICONTROL pkey]** nel **[!UICONTROL Data element]** elenco a discesa tipo.

1. Per creare l’elemento dati del server Campaign, fai clic su **[!UICONTROL Add data element]**.

1. In **[!UICONTROL Name]** digitare un nome, ad esempio **camp-server**.

1. Dalla sezione **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Adobe Campaign Standard]**. Allora, **[!UICONTROL Campaign Server]** nel **[!UICONTROL Data element]** elenco a discesa tipo.

## Creazione di regole {#creating-rules}

È necessario creare regole per i seguenti elementi:

* [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback del tracciamento in-app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Postback tracciamento notifiche push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Postback posizione](../../administration/using/configuring-rules-launch.md#location-postback)

### Postback PII {#pii-postback}

>[!NOTE]
>
>Per inviare informazioni PII da un’app mobile ad Adobe Campaign, devi implementare un’API SDK. Per ulteriori informazioni, consulta [CollectPII](https://developer.adobe.com/client-sdks/documentation/mobile-core/api-reference/#collectpii).

Per inviare dati PII a [!DNL Adobe Campaign Standard], crea una regola nell’interfaccia utente di Data Collection:

1. Nell’interfaccia utente di Data Collection, dal dashboard dell’app mobile, fai clic su **[!UICONTROL Rules]** quindi tab **[!UICONTROL Create New Rule]**.

1. Digita un nome, ad esempio: **Core mobile - Raccolta PII**.

1. In **[!UICONTROL Events]** , fare clic su **[!UICONTROL Add]**.

1. Dalla sezione **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Allora, **[!UICONTROL Collect PII]** nel **[!UICONTROL Event type]** a discesa.

1. Fai clic su **[!UICONTROL Keep changes]**.

1. In **[!UICONTROL Actions]** , fare clic su **[!UICONTROL Add]**.

1. Dalla sezione **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Allora, **[!UICONTROL Send PII]** nel **[!UICONTROL Action type]** a discesa.

1. In entrata **[!UICONTROL URL]**, immetti il seguente URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Seleziona la **[!UICONTROL Add Post Body]** casella di controllo.

1. In entrata **[!UICONTROL Post Body]**, digitare quanto segue:

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

   Gli elementi dati definiti nell’interfaccia utente di Data Collection devono essere inclusi in percentuali doppie, ad esempio `%%mcid%%`Le variabili di contesto e dell&#39;app devono essere racchiuse in percentuali singole, ad esempio %contextdata.email%.

1. In entrata **[!UICONTROL Content Type]**, tipo **application/json**.

1. In entrata **[!UICONTROL Timeout]**, selezionare 0.

   ![](assets/do-not-localize/rules_2.png)

I dati utente sono ora configurati per l’invio a Campaign.

### Postback del tracciamento in-app {#inapp-tracking-postback}

>[!NOTE]
>
>Se utilizzi Android ACPCore v1.4.0 o versione successiva/ iOS ACPCore v2.3.0 o versione successiva, non è necessario configurare i postback di tracciamento.

Per inviare i dati di tracciamento a [!DNL Adobe Campaign Standard] per generare rapporti sull’interazione degli utenti con i messaggi in-app nell’app mobile, crea la seguente regola nell’interfaccia utente di Data Collection:

1. Nell’interfaccia utente di Data Collection, dal dashboard dell’app mobile, seleziona la **[!UICONTROL Rules]** e fai clic su **[!UICONTROL Add Rule]**.

1. Digita un nome, ad esempio: **Adobe Campaign - Tracciamento dei clic in-app**.

1. In **[!UICONTROL Events]** , fare clic su **[!UICONTROL Add]**.

1. Dalla sezione **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Adobe Campaign Standard]**. Allora, **[!UICONTROL In-App click tracking]** nel **[!UICONTROL Event type]** a discesa.

1. Fai clic su **[!UICONTROL Keep changes]**.

1. In **[!UICONTROL Actions]** , fare clic su **[!UICONTROL Add]**.

1. Dalla sezione **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Allora, **[!UICONTROL Send postback]** nel **[!UICONTROL Event type]** a discesa.

1. In entrata **[!UICONTROL URL]**, digita il seguente URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Seleziona la **[!UICONTROL Add post body]** casella di controllo.

1. In entrata **[!UICONTROL Post Body]**, tipo **{}**.

1. In entrata **[!UICONTROL Content Type]**, tipo **application/json**.

1. In entrata **[!UICONTROL Timeout]**, selezionare 0.

   ![](assets/do-not-localize/rules_3.png)

### Postback tracciamento notifiche push {#push-tracking-postback}

>[!NOTE]
>
>Se utilizzi Android ACPCore v1.4.0 o versione successiva/ iOS ACPCore v2.3.0 o versione successiva, non è necessario configurare i postback di tracciamento.

Per inviare i dati di tracciamento a [!DNL Adobe Campaign Standard], che consente di tenere traccia delle consegne delle notifiche push e dell’interazione degli utenti con l’app mobile, è necessario creare una regola nell’interfaccia utente di Data Collection.

Per ulteriori informazioni sul tracciamento push, consulta [Tracciamento push](../../administration/using/push-tracking.md).

Per tenere traccia delle azioni eseguite nell’app, utilizza l’API trackAction. Per ulteriori informazioni, consulta [Tracciare le azioni eseguite nell’app](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. Nell’interfaccia utente di Data Collection, dal dashboard dell’app mobile, fai clic su **[!UICONTROL Rules]** e fai clic su **[!UICONTROL Add Rule]**.

1. Digita un nome, ad esempio: **Adobe Campaign - tracciamento dei clic push**.

1. In **[!UICONTROL Events]** , fare clic su **[!UICONTROL Add]**.

1. Dalla sezione **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Allora, **[!UICONTROL Track Action]** nel **[!UICONTROL Event type]** a discesa.

1. Dalla sezione **[!UICONTROL Action]** a discesa, seleziona **[!UICONTROL Action]**, seleziona **[!UICONTROL equals]**, e tipo **tracciamento**.

1. Fai clic su **[!UICONTROL Keep changes]**. Quindi, nella **[!UICONTROL Actions]** , fare clic su **[!UICONTROL Add]**.

1. Dalla sezione **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Allora, **[!UICONTROL Send postback]** nel **[!UICONTROL Action type]** a discesa.

1. In entrata **[!UICONTROL URL]**, immetti il seguente URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Seleziona la **[!UICONTROL Add post body]** casella di controllo.

1. Aggiungi il corpo del post, ad esempio { }.

1. In entrata **[!UICONTROL Content Type]**, tipo **application/json**.

1. In entrata **[!UICONTROL Timeout]**, selezionare 0.

### Postback posizione {#location-postback}

1. Nell’interfaccia utente di Data Collection, dal dashboard dell’app mobile, fai clic su **[!UICONTROL Rules]** e fai clic su **[!UICONTROL Add Rule]**.

1. Digita un nome, ad esempio: **Postback posizione**.

1. In **[!UICONTROL Events]** , fare clic su **[!UICONTROL Add]**.

1. Crea un evento, ad esempio Enter POI (Inserisci POI) o Exit POI (Esci POI). Dalla sezione **[!UICONTROL Extension]** a discesa, seleziona **Places - Beta**. Allora, **Inserisci POI** o **Esci da POI** nel **[!UICONTROL Event type]** a discesa.

1. Immetti un nome, ad esempio: **Places - Beta - Inserisci POI** o **Esci da POI**.

1. In **[!UICONTROL Actions]** , fare clic su **[!UICONTROL Add]**.

1. Dalla sezione **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Allora, **[!UICONTROL Send postback]** dal **[!UICONTROL Action type]** a discesa.

1. Immetti un nome, ad esempio: **Core mobile - Postback della posizione di invio**.

1. In entrata **[!UICONTROL URL]**, immetti il seguente URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Seleziona la **[!UICONTROL Add post body]** e aggiungere il corpo del post, ad esempio:

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
   >Nell’esempio precedente, gli elementi dati sul lato destro devono essere configurati nell’interfaccia utente di Data Collection sfruttando i passaggi descritti in [Creazione di elementi dati](../../administration/using/configuring-rules-launch.md#create-data-elements). Gli elementi dati a sinistra sono supportati in [!DNL Adobe Campaign Standard] e non richiedono alcuna configurazione. Se hai bisogno di dati aggiuntivi, devi eseguire estensioni di risorse personalizzate in [!DNL Adobe Campaign Standard].

1. In entrata **[!UICONTROL Content Type]**, tipo **application/json**.

1. In entrata **[!UICONTROL Timeout]**, selezionare 5.

   ![](assets/do-not-localize/rules_4.png)
