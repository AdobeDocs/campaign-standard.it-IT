---
title: Configurazione delle regole di Adobe Experience Platform Launch per supportare i casi d’uso di Adobe Campaign Standard
description: Configurazione delle regole di Adobe Experience Platform Launch per supportare i casi d’uso di Adobe Campaign Standard
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: 8c4e38a3fc66e4d819575fcd64616a822e0e1f82
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 1%

---

# Configurazione delle regole di Launch per supportare casi d’uso di Adobe Campaign Standard {#configuring-rules-launch}

In [!DNL Adobe Experience Platform Launch] devi creare elementi dati e regole per inviare dati PII e altri dati dalle applicazioni mobili a [!DNL Adobe Campaign Standard].

Per fare in modo che tutte le modifiche di configurazione in [!DNL Adobe Experience Platform Launch] abbiano effetto, devi pubblicare queste modifiche. Per ulteriori informazioni, consulta [Pubblicazione](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration).

Per creare regole in [!DNL Experience Platform Launch], segui questi passaggi:

1. [Creazione di elementi dati](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Creazione di ](../../administration/using/configuring-rules-launch.md#create-data-elements) regole per i casi d’uso che desideri supportare:
   * [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback di tracciamento in-app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Postback di tracking delle notifiche push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Postback posizione](../../administration/using/configuring-rules-launch.md#location-postback)

## Creazione di elementi dati {#create-data-elements}

Di seguito sono riportati gli elementi dati che consigliamo di creare in [!DNL Experience Platform Launch].
Puoi creare elementi di dati aggiuntivi in base alle tue esigenze.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

Per creare questi elementi dati:

1. In [!DNL Experience Platform Launch], fai clic sulla scheda **[!UICONTROL Data Elements]** nel dashboard delle applicazioni mobili.

1. Per creare l&#39;elemento dati **[!UICONTROL Experience Cloud ID]**, fai clic su **[!UICONTROL Create New Data Element]**.

1. Nel campo **[!UICONTROL Name]**, ad esempio, digita **mcid**.

1. Dal menu a discesa **[!UICONTROL Extension]**, seleziona **[!UICONTROL Mobile Core]**. Quindi **[!UICONTROL Experience Cloud ID]** nel menu a discesa **[!UICONTROL Data element]** type .

   ![](assets/do-not-localize/rules_1.png)

1. Per creare l’elemento dati Pkey, fai clic su **[!UICONTROL Add data element]**.

1. Nel campo **[!UICONTROL Name]**, ad esempio, digitare **key**.

1. Dal menu a discesa **[!UICONTROL Extension]**, seleziona **[!UICONTROL Adobe Campaign Standard]**. Quindi **[!UICONTROL pkey]** nel menu a discesa **[!UICONTROL Data element]** type .

1. Per creare l’elemento dati del server Campaign, fai clic su **[!UICONTROL Add data element]**.

1. Nel campo **[!UICONTROL Name]**, digita un nome, ad esempio **camp-server**.

1. Dal menu a discesa **[!UICONTROL Extension]**, seleziona **[!UICONTROL Adobe Campaign Standard]**. Quindi, **[!UICONTROL Campaign Server]** nel menu a discesa del tipo **[!UICONTROL Data element]** .

## Creazione di regole {#creating-rules}

È necessario creare regole per i seguenti elementi:

* [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback di tracciamento in-app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Postback di tracking delle notifiche push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Postback posizione](../../administration/using/configuring-rules-launch.md#location-postback)

### Postback PII {#pii-postback}

>[!NOTE]
>
>Per inviare informazioni PII da un’app mobile ad Adobe Campaign, devi implementare un’API SDK. Per ulteriori informazioni, visita [CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii).

Per inviare dati PII a [!DNL Adobe Campaign Standard], crea una regola in [!DNL Experience Platform Launch]:

1. In [!DNL Experience Platform Launch], fai clic sulla scheda **[!UICONTROL Rules]** nel dashboard delle applicazioni mobili, quindi **[!UICONTROL Create New Rule]**.

1. Digita un nome, ad esempio **Mobile Core - Raccogli PII**.

1. Nella sezione **[!UICONTROL Events]**, fai clic su **[!UICONTROL Add]**.

1. Dal menu a discesa **[!UICONTROL Extension]**, seleziona **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Collect PII]** nel menu a discesa **[!UICONTROL Event type]** .

1. Fai clic su **[!UICONTROL Keep changes]**.

1. Nella sezione **[!UICONTROL Actions]**, fai clic su **[!UICONTROL Add]**.

1. Dal menu a discesa **[!UICONTROL Extension]**, seleziona **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Send PII]** nel menu a discesa **[!UICONTROL Action type]** .

1. In **[!UICONTROL URL]**, immetti il seguente URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Selezionare la casella di controllo **[!UICONTROL Add Post Body]**.

1. In **[!UICONTROL Post Body]**, digita quanto segue:

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

   MarketingCloudId consente di riconciliare gli abbonati all’app con i destinatari nel database ed è quindi necessario. Puoi specificare altre coppie chiave-valore in base alle tue esigenze aziendali. Nell’esempio precedente, e-mail, nome e cognome vengono trasmessi dall’app.

   Le chiavi (ad esempio cusEmail, cusFirstName e cusLastName) devono corrispondere agli ID campo definiti nella risorsa personalizzata nell’istanza di Adobe Campaign Standard. Le variabili di valore (ad esempio e-mail, firstName e LastName) devono corrispondere alle chiavi nei dati JSON inviati dall’app mobile durante la chiamata dell’API collectPII AMS dal codice dell’app.

   Puoi anche trasmettere i dati del ciclo di vita nel postback Raccogli PII o un postback diverso a seconda degli attivatori dell’evento. ecco un esempio dei dati del ciclo di vita JSON:

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "pushPlatform":"{%contextdata.pushPlatform%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   Gli elementi dati definiti in [!DNL Experience Platform Launch] devono essere racchiusi in due percentuali, ad esempio %%mcid%%%, e le variabili di contesto dell&#39;app devono essere racchiuse in singole percentuali, ad esempio %contextdata.email%.

1. In **[!UICONTROL Content Type]**, digita **application/json**.

1. In **[!UICONTROL Timeout]**, selezionare 0.

   ![](assets/do-not-localize/rules_2.png)

I dati utente sono ora configurati per l’invio a Campaign.

### Postback di tracciamento in-app {#inapp-tracking-postback}

>[!NOTE]
>
>Se utilizzi Android ACPCore v1.4.0 o versioni successive/ iOS ACPCore v2.3.0 o versioni successive, la configurazione dei postback di tracciamento non è necessaria.

Per inviare dati di tracciamento a [!DNL Adobe Campaign Standard] per ottenere rapporti su come gli utenti interagiscono con i messaggi in-app nella tua app mobile, crea la seguente regola in [!DNL Experience Platform Launch]:

1. In [!DNL Experience Platform Launch], seleziona la scheda **[!UICONTROL Rules]** dal dashboard delle applicazioni mobili e fai clic su **[!UICONTROL Add Rule]**.

1. Digita un nome, ad esempio **Adobe Campaign - Tracciamento dei clic in-app**.

1. Nella sezione **[!UICONTROL Events]**, fai clic su **[!UICONTROL Add]**.

1. Dal menu a discesa **[!UICONTROL Extension]**, seleziona **[!UICONTROL Adobe Campaign Standard]**. Quindi, **[!UICONTROL In-App click tracking]** nel menu a discesa **[!UICONTROL Event type]** .

1. Fai clic su **[!UICONTROL Keep changes]**.

1. Nella sezione **[!UICONTROL Actions]**, fai clic su **[!UICONTROL Add]**.

1. Dal menu a discesa **[!UICONTROL Extension]**, seleziona **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Send postback]** nel menu a discesa **[!UICONTROL Event type]** .

1. In **[!UICONTROL URL]**, digita il seguente URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Selezionare la casella di controllo **[!UICONTROL Add post body]**.

1. In **[!UICONTROL Post Body]**, digita **{}**.

1. In **[!UICONTROL Content Type]**, digita **application/json**.

1. In **[!UICONTROL Timeout]**, selezionare 0.

   ![](assets/do-not-localize/rules_3.png)

### Postback di tracking delle notifiche push {#push-tracking-postback}

>[!NOTE]
>
>Se utilizzi Android ACPCore v1.4.0 o versioni successive/ iOS ACPCore v2.3.0 o versioni successive, la configurazione dei postback di tracciamento non è necessaria.

Per inviare i dati di tracciamento a [!DNL Adobe Campaign Standard], che consente di monitorare le consegne di notifiche push e l’interazione degli utenti con la tua app mobile, devi creare una regola in [!DNL Experience Platform Launch].

Per ulteriori informazioni sul tracciamento push, consulta [Tracciamento push](../../administration/using/push-tracking.md).

Per tenere traccia delle azioni eseguite nell’app, utilizza l’API trackAction. Per ulteriori informazioni, consulta [Tracciare le azioni eseguite nell’app](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. In [!DNL Experience Platform Launch], fai clic sulla scheda **[!UICONTROL Rules]** nel dashboard delle applicazioni mobili e fai clic su **[!UICONTROL Add Rule]**.

1. Digita un nome, ad esempio **Adobe Campaign - tracciamento dei clic push**.

1. Nella sezione **[!UICONTROL Events]**, fai clic su **[!UICONTROL Add]**.

1. Dal menu a discesa **[!UICONTROL Extension]**, seleziona **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Track Action]** nel menu a discesa **[!UICONTROL Event type]** .

1. Dal menu a discesa **[!UICONTROL Action]**, seleziona **[!UICONTROL Action]**, seleziona **[!UICONTROL equals]** e digita **tracking**.

1. Fai clic su **[!UICONTROL Keep changes]**. Quindi, nella sezione **[!UICONTROL Actions]**, fai clic su **[!UICONTROL Add]**.

1. Dal menu a discesa **[!UICONTROL Extension]**, seleziona **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Send postback]** nel menu a discesa **[!UICONTROL Action type]** .

1. In **[!UICONTROL URL]**, immetti il seguente URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Selezionare la casella di controllo **[!UICONTROL Add post body]**.

1. Aggiungi il corpo del post, ad esempio { }.

1. In **[!UICONTROL Content Type]**, digita **application/json**.

1. In **[!UICONTROL Timeout]**, selezionare 0.

### Postback posizione {#location-postback}

1. In [!DNL Experience Platform Launch], fai clic sulla scheda **[!UICONTROL Rules]** nel dashboard delle applicazioni mobili e fai clic su **[!UICONTROL Add Rule]**.

1. Digita un nome, ad esempio **Posizione postback**.

1. Nella sezione **[!UICONTROL Events]**, fai clic su **[!UICONTROL Add]**.

1. Crea un evento, ad esempio Enter POI (Inserisci POI) o Exit POI (Esci POI). Dal menu a discesa **[!UICONTROL Extension]**, seleziona **Luoghi - Beta**. Quindi, **Inserisci POI** o **Esci da POI** nel menu a discesa **[!UICONTROL Event type]**.

1. Inserisci un nome, ad esempio **Luoghi - Beta - Inserisci POI** o **Esci da POI**.

1. Nella sezione **[!UICONTROL Actions]**, fai clic su **[!UICONTROL Add]**.

1. Dal menu a discesa **[!UICONTROL Extension]**, seleziona **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Send postback]** dal menu a discesa **[!UICONTROL Action type]**.

1. Immetti un nome, ad esempio **Mobile Core - Send Location Postback**.

1. In **[!UICONTROL URL]**, immetti il seguente URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Seleziona la casella di controllo **[!UICONTROL Add post body]** e aggiungi il corpo del post, ad esempio:

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
   >Nell&#39;esempio precedente, gli elementi dati sul lato destro devono essere configurati in [!DNL Experience Platform Launch] sfruttando i passaggi descritti in [Creazione di elementi dati](../../administration/using/configuring-rules-launch.md#create-data-elements). Gli elementi dati sul lato sinistro sono supportati in [!DNL Adobe Campaign Standard] e non richiedono alcuna configurazione. Se hai bisogno di dati aggiuntivi, devi eseguire estensioni di risorse personalizzate in [!DNL Adobe Campaign Standard].

1. In **[!UICONTROL Content Type]**, digita **application/json**.

1. In **[!UICONTROL Timeout]**, selezionare 5.

   ![](assets/do-not-localize/rules_4.png)
