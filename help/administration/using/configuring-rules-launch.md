---
solution: Campaign Standard
product: campaign
title: Configurazione  regole Adobe Experience Platform Launch per supportare  casi di utilizzo Adobe Campaign Standard
description: Configurazione  regole Adobe Experience Platform Launch per supportare  casi di utilizzo Adobe Campaign Standard
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 1%

---


# Configurazione delle regole di Launch per supportare casi d’uso di Adobe Campaign Standard {#configuring-rules-launch}

In [!DNL Adobe Experience Platform Launch], è necessario creare elementi di dati e regole per inviare dati PII e altri dati dalle applicazioni mobili a [!DNL Adobe Campaign Standard].

Per assicurarsi che tutte le modifiche alla configurazione in [!DNL Adobe Experience Platform Launch] abbiano effetto, è necessario pubblicare tali modifiche. Per ulteriori informazioni, vedere [Pubblicazione](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration).

Per creare le regole in [!DNL Experience Platform Launch], procedere come segue:

1. [Creazione di elementi di dati](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Creazione di ](../../administration/using/configuring-rules-launch.md#create-data-elements) regole per i casi di utilizzo da supportare:
   * [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback per tracciamento in-app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Post-back di tracciamento delle notifiche push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Postback posizione](../../administration/using/configuring-rules-launch.md#location-postback)

## Creazione di elementi di dati {#create-data-elements}

Di seguito sono riportati gli elementi di dati che consigliamo di creare in [!DNL Experience Platform Launch].
Puoi creare elementi di dati aggiuntivi in base alle tue esigenze.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

Per creare i seguenti elementi di dati:

1. In [!DNL Experience Platform Launch], nel dashboard delle applicazioni mobili fare clic sulla scheda **[!UICONTROL Data Elements]**.

1. Per creare l&#39;elemento di dati **[!UICONTROL Experience Cloud ID]**, fare clic su **[!UICONTROL Create New Data Element]**.

1. Nel campo **[!UICONTROL Name]**, ad esempio, digitare **mcid**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi **[!UICONTROL Experience Cloud ID]** nel menu a discesa **[!UICONTROL Data element]** tipo.

   ![](assets/do-not-localize/rules_1.png)

1. Per creare l&#39;elemento dati Pkey, fare clic su **[!UICONTROL Add data element]**.

1. Nel campo **[!UICONTROL Name]**, ad esempio, digitare **key**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Adobe Campaign Standard]**. Quindi **[!UICONTROL pkey]** nel menu a discesa **[!UICONTROL Data element]** tipo.

1. Per creare l&#39;elemento dati del server Campaign, fai clic su **[!UICONTROL Add data element]**.

1. Nel campo **[!UICONTROL Name]** digitare un nome, ad esempio **server-campeggio**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Adobe Campaign Standard]**. Quindi, **[!UICONTROL Campaign Server]** nel menu a discesa **[!UICONTROL Data element]** tipo.

## Creazione di regole {#creating-rules}

È necessario creare regole per i seguenti elementi:

* [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback per tracciamento in-app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Post-back di tracciamento delle notifiche push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Postback posizione](../../administration/using/configuring-rules-launch.md#location-postback)

### Postback PII {#pii-postback}

>[!NOTE]
>
>Per inviare informazioni PII da un&#39;app mobile a  Adobe Campaign, devi implementare un&#39;API SDK. Per ulteriori informazioni, vedere [CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii).

Per inviare dati PII a [!DNL Adobe Campaign Standard], create una regola in [!DNL Experience Platform Launch]:

1. In [!DNL Experience Platform Launch], nel dashboard dell&#39;applicazione mobile fare clic sulla scheda **[!UICONTROL Rules]**, quindi su **[!UICONTROL Create New Rule]**.

1. Digitate un nome, ad esempio **Mobile Core - Raccogli PII**.

1. Nella sezione **[!UICONTROL Events]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Collect PII]** nel menu a discesa **[!UICONTROL Event type]**.

1. Fai clic su **[!UICONTROL Keep changes]**.

1. Nella sezione **[!UICONTROL Actions]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Send PII]** nel menu a discesa **[!UICONTROL Action type]**.

1. In **[!UICONTROL URL]**, immettete il seguente URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Selezionare la casella di controllo **[!UICONTROL Add Post Body]**.

1. In **[!UICONTROL Post Body]** digitare quanto segue:

   ```
   {
   "marketingCloudId":
   "{%%mcid%%}",
   "cusEmail":
   "{%contextdata.email%}",
   "cusFirstName":
   "{%contextdata.firstName%}",
   "cusLastName":
   "{%contextdata.lastName%}" }
   ```

   MarketingCloudId consente di riconciliare gli abbonati all&#39;app con i destinatari nel database e, di conseguenza, è necessario. Puoi specificare altre coppie chiave-valore in base alle tue esigenze aziendali. Nell&#39;esempio precedente, dall&#39;app vengono passati e-mail, nome e cognome.

   Le chiavi (ad esempio cusEmail, cusFirstName e cusLastName) devono corrispondere agli ID campo definiti nella risorsa personalizzata nell&#39;istanza di Adobe Campaign Standard . Le variabili del valore (ad esempio email, firstName e LastName) devono corrispondere alle chiavi nei dati JSON inviati dall’app mobile mentre richiamano l’API AMS collectPII dal codice dell’app.

   Potete anche trasmettere i dati del ciclo di vita nel postback Collect PII o in un postback diverso a seconda delle attivazioni dell’evento. di seguito è riportato un esempio del JSON dei dati del ciclo di vita:

   ```
   {
   "marketingCloudId":"{%%mcid%%}",
   "cusDayslastlaunch": "{%%DaysSinceLastUse%%}", 
   "cusDaysfirstlaunch": "{%%DaysSinceFirstUse%%}", 
   "cusLaunches": "{%%Launches%%}"
   }
   ```

   Gli elementi di dati definiti in [!DNL Experience Platform Launch] devono essere racchiusi in due percentuali, ad esempio %%mcid%%, e le variabili di contesto dall&#39;app devono essere racchiuse in singole percentuali, ad esempio %contextdata.email%.

1. In **[!UICONTROL Content Type]** digitare **application/json**.

1. In **[!UICONTROL Timeout]**, selezionare 0.

   ![](assets/do-not-localize/rules_2.png)

I dati utente sono ora configurati per essere inviati a Campaign.

### Postback di tracciamento in-app {#inapp-tracking-postback}

Per inviare i dati di tracciamento a [!DNL Adobe Campaign Standard] per segnalare come gli utenti interagiscono con i messaggi in-app nell&#39;applicazione mobile, crea la regola seguente in [!DNL Experience Platform Launch]:

1. In [!DNL Experience Platform Launch], nel dashboard dell&#39;applicazione mobile selezionare la scheda **[!UICONTROL Rules]** e fare clic su **[!UICONTROL Add Rule]**.

1. Digitare un nome, ad esempio **Adobe Campaign - Tracciamento clic in-app**.

1. Nella sezione **[!UICONTROL Events]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Adobe Campaign Standard]**. Quindi, **[!UICONTROL In-App click tracking]** nel menu a discesa **[!UICONTROL Event type]**.

1. Fai clic su **[!UICONTROL Keep changes]**.

1. Nella sezione **[!UICONTROL Actions]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Send postback]** nel menu a discesa **[!UICONTROL Event type]**.

1. In **[!UICONTROL URL]**, digitate il seguente URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Selezionare la casella di controllo **[!UICONTROL Add post body]**.

1. In **[!UICONTROL Post Body]**, digitare **{}**.

1. In **[!UICONTROL Content Type]** digitare **application/json**.

1. In **[!UICONTROL Timeout]**, selezionare 0.

   ![](assets/do-not-localize/rules_3.png)

### Post-back delle notifiche push {#push-tracking-postback}

Per inviare i dati di tracciamento a [!DNL Adobe Campaign Standard], in modo da tenere traccia delle consegne di notifiche push e dell&#39;interazione degli utenti con l&#39;applicazione mobile, è necessario creare una regola in [!DNL Experience Platform Launch].

Per ulteriori informazioni sul tracciamento push, consultate [Tracciamento push](../../administration/using/push-tracking.md).

Per tracciare le azioni dell&#39;app, usa l&#39;API trackAction. Per ulteriori informazioni, vedi [Tracciare le azioni dell&#39;app](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. In [!DNL Experience Platform Launch], nel dashboard dell&#39;applicazione mobile fare clic sulla scheda **[!UICONTROL Rules]** e quindi su **[!UICONTROL Add Rule]**.

1. Digitare un nome, ad esempio **Adobe Campaign - tracciamento dei clic push**.

1. Nella sezione **[!UICONTROL Events]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Track Action]** nel menu a discesa **[!UICONTROL Event type]**.

1. Dal menu a discesa **[!UICONTROL Action]**, selezionare **[!UICONTROL Action]**, selezionare **[!UICONTROL equals]**, quindi digitare **tracking**.

1. Fai clic su **[!UICONTROL Keep changes]**. Quindi, nella sezione **[!UICONTROL Actions]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Send postback]** nel menu a discesa **[!UICONTROL Action type]**.

1. In **[!UICONTROL URL]**, immettete il seguente URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Selezionare la casella di controllo **[!UICONTROL Add post body]**.

1. Aggiungi il corpo del post, ad esempio { }.

1. In **[!UICONTROL Content Type]** digitare **application/json**.

1. In **[!UICONTROL Timeout]**, selezionare 0.

### Postback posizione {#location-postback}

1. In [!DNL Experience Platform Launch], nel dashboard dell&#39;applicazione mobile fare clic sulla scheda **[!UICONTROL Rules]** e quindi su **[!UICONTROL Add Rule]**.

1. Digitare un nome, ad esempio **Posizione postback**.

1. Nella sezione **[!UICONTROL Events]**, fare clic su **[!UICONTROL Add]**.

1. Create un evento, ad esempio, Enter POI o Exit POI. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **Luoghi - Beta**. Quindi, **Inserire POI** o **Esci da POI** nel menu a discesa **[!UICONTROL Event type]**.

1. Immettete un nome, ad esempio **Luoghi - Beta - Immettete POI** o **Esci da POI**.

1. Nella sezione **[!UICONTROL Actions]**, fare clic su **[!UICONTROL Add]**.

1. Dall&#39;elenco a discesa **[!UICONTROL Extension]**, selezionare **[!UICONTROL Mobile Core]**. Quindi, **[!UICONTROL Send postback]** dal menu a discesa **[!UICONTROL Action type]**.

1. Inserite un nome, ad esempio **Mobile Core - Send Location Postback**.

1. In **[!UICONTROL URL]**, immettete il seguente URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Selezionate la casella di controllo **[!UICONTROL Add post body]** e aggiungete il corpo del post, ad esempio:

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
   >Nell&#39;esempio precedente, gli elementi di dati sul lato destro devono essere configurati in [!DNL Experience Platform Launch] sfruttando i passaggi descritti in [Creazione di elementi di dati](../../administration/using/configuring-rules-launch.md#create-data-elements). Gli elementi di dati sul lato sinistro sono supportati in [!DNL Adobe Campaign Standard] e non richiedono alcuna configurazione. Se sono necessari dati aggiuntivi, è necessario eseguire estensioni di risorse personalizzate in [!DNL Adobe Campaign Standard].

1. In **[!UICONTROL Content Type]** digitare **application/json**.

1. In **[!UICONTROL Timeout]**, selezionare 5.

   ![](assets/do-not-localize/rules_4.png)
