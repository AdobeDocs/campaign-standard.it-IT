---
title: Configurazione delle regole di tag per supportare casi d’uso di Adobe Campaign Standard
description: Scopri come configurare le regole dei tag per supportare i casi d’uso di Adobe Campaign Standard
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: b5f4f612-ea23-4007-b427-069777ecdd58
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '998'
ht-degree: 2%

---

# Configurazione delle regole di tag per supportare casi d’uso di Adobe Campaign Standard {#configuring-rules-launch}

Nell’interfaccia utente di raccolta dati, crea elementi dati e regole per inviare dati PII e altri dati dalle applicazioni mobili a [!DNL Adobe Campaign Standard].

Per fare in modo che tutte le modifiche di configurazione nell’interfaccia utente della raccolta dati abbiano effetto, devi pubblicare tali modifiche. Per ulteriori informazioni, consulta [Pubblicazione](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#publish-the-configuration).

Per creare regole nell’interfaccia utente di raccolta dati, effettua le seguenti operazioni:

1. [Creazione di elementi dati](../../administration/using/configuring-rules-launch.md#create-data-elements)
2. [Creazione di regole](../../administration/using/configuring-rules-launch.md#create-data-elements) per i casi d’uso che desideri supportare:
   * [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
   * [Postback di tracciamento in-app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
   * [Postback di tracking delle notifiche push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
   * [Postback posizione](../../administration/using/configuring-rules-launch.md#location-postback)

## Creazione di elementi dati {#create-data-elements}

Di seguito sono riportati gli elementi dati che consigliamo di creare nell’interfaccia utente di raccolta dati.
Puoi creare elementi di dati aggiuntivi in base alle tue esigenze.

* **[!UICONTROL Experience Cloud ID]**
* **[!UICONTROL Pkey]**
* **[!UICONTROL Campaign server]**

Per creare questi elementi dati:

1. Nell’interfaccia utente Raccolta dati, dal dashboard dell’app mobile, fai clic su **[!UICONTROL Data Elements]** scheda .

1. Per creare **[!UICONTROL Experience Cloud ID]** elemento dati, fai clic su **[!UICONTROL Create New Data Element]**.

1. In **[!UICONTROL Name]** ad esempio, digitare **mcid**.

1. Da **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Then **[!UICONTROL Experience Cloud ID]** in **[!UICONTROL Data element]** elenco a discesa digitare .

   ![](assets/do-not-localize/rules_1.png)

1. Per creare l’elemento dati Pkey, fai clic su **[!UICONTROL Add data element]**.

1. In **[!UICONTROL Name]** ad esempio, digitare **chiave**.

1. Da **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Adobe Campaign Standard]**. Then **[!UICONTROL pkey]** in **[!UICONTROL Data element]** elenco a discesa digitare .

1. Per creare l’elemento dati del server Campaign, fai clic su **[!UICONTROL Add data element]**.

1. In **[!UICONTROL Name]** campo, digitare un nome, ad esempio **cameriere**.

1. Da **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Adobe Campaign Standard]**. Allora, **[!UICONTROL Campaign Server]** in **[!UICONTROL Data element]** elenco a discesa digitare .

## Creazione di regole {#creating-rules}

È necessario creare regole per i seguenti elementi:

* [Postback PII](../../administration/using/configuring-rules-launch.md#pii-postback)
* [Postback di tracciamento in-app](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback)
* [Postback di tracking delle notifiche push](../../administration/using/configuring-rules-launch.md#push-tracking-postback)
* [Postback posizione](../../administration/using/configuring-rules-launch.md#location-postback)

### Postback PII {#pii-postback}

>[!NOTE]
>
>Per inviare informazioni PII da un’app mobile ad Adobe Campaign, devi implementare un’API SDK. Per ulteriori informazioni, consulta [CollectPII](https://aep-sdks.gitbook.io/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#collect-pii).

Per inviare dati PII a [!DNL Adobe Campaign Standard], crea una regola nell’interfaccia utente Raccolta dati:

1. Nell’interfaccia utente Raccolta dati, dal dashboard dell’app mobile, fai clic su **[!UICONTROL Rules]** scheda then **[!UICONTROL Create New Rule]**.

1. Digita un nome, ad esempio **Mobile Core - Raccogli PII**.

1. In **[!UICONTROL Events]** sezione, fai clic su **[!UICONTROL Add]**.

1. Da **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Allora, **[!UICONTROL Collect PII]** in **[!UICONTROL Event type]** a discesa.

1. Fai clic su **[!UICONTROL Keep changes]**.

1. In **[!UICONTROL Actions]** sezione, fai clic su **[!UICONTROL Add]**.

1. Da **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Allora, **[!UICONTROL Send PII]** in **[!UICONTROL Action type]** a discesa.

1. In **[!UICONTROL URL]**, immetti il seguente URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/subscriptions/{%%mcid%%}
   ```

1. Seleziona la **[!UICONTROL Add Post Body]** casella di controllo.

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

   Gli elementi dati definiti nell’interfaccia utente di Raccolta dati devono essere racchiusi in due percentuali, ad esempio `%%mcid%%`, e le variabili di contesto dell&#39;app devono essere racchiuse in singole percentuali, ad esempio %contextdata.email%.

1. In **[!UICONTROL Content Type]**, tipo **application/json**.

1. In **[!UICONTROL Timeout]**, seleziona 0.

   ![](assets/do-not-localize/rules_2.png)

I dati utente sono ora configurati per l’invio a Campaign.

### Postback di tracciamento in-app {#inapp-tracking-postback}

>[!NOTE]
>
>Se utilizzi Android ACPCore v1.4.0 o successivo/iOS ACPCore v2.3.0 o successivo, non è necessario configurare i postback di tracciamento.

Per inviare dati di tracciamento a [!DNL Adobe Campaign Standard] per rapporti sulle modalità di interazione degli utenti con i messaggi in-app nell’app mobile, crea la seguente regola nell’interfaccia utente di raccolta dati:

1. Nell’interfaccia utente di raccolta dati, seleziona il **[!UICONTROL Rules]** e fai clic su **[!UICONTROL Add Rule]**.

1. Digita un nome, ad esempio **Adobe Campaign - Tracciamento dei clic in-app**.

1. In **[!UICONTROL Events]** sezione, fai clic su **[!UICONTROL Add]**.

1. Da **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Adobe Campaign Standard]**. Allora, **[!UICONTROL In-App click tracking]** in **[!UICONTROL Event type]** a discesa.

1. Fai clic su **[!UICONTROL Keep changes]**.

1. In **[!UICONTROL Actions]** sezione, fai clic su **[!UICONTROL Add]**.

1. Da **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Allora, **[!UICONTROL Send postback]** in **[!UICONTROL Event type]** a discesa.

1. In **[!UICONTROL URL]**, digita il seguente URL:

   ```
   https://{%%camp-server%%}/r/?id={%id%}&mcid={%%mcid%%}
   ```

1. Seleziona la **[!UICONTROL Add post body]** casella di controllo.

1. In **[!UICONTROL Post Body]**, tipo **{}**.

1. In **[!UICONTROL Content Type]**, tipo **application/json**.

1. In **[!UICONTROL Timeout]**, seleziona 0.

   ![](assets/do-not-localize/rules_3.png)

### Postback di tracking delle notifiche push {#push-tracking-postback}

>[!NOTE]
>
>Se utilizzi Android ACPCore v1.4.0 o successivo/iOS ACPCore v2.3.0 o successivo, non è necessario configurare i postback di tracciamento.

Per inviare dati di tracciamento a [!DNL Adobe Campaign Standard], per tenere traccia delle consegne di notifiche push e dell’interazione degli utenti con l’app mobile, devi creare una regola nell’interfaccia utente di raccolta dati.

Per ulteriori informazioni sul tracciamento push, vedi [Tracciamento push](../../administration/using/push-tracking.md).

Per tenere traccia delle azioni eseguite nell’app, utilizza l’API trackAction. Per ulteriori informazioni, consulta [Tracciare le azioni eseguite nell’app](https://app.gitbook.com/@aep-sdks/s/docs/using-mobile-extensions/mobile-core/mobile-core-api-reference#track-app-actions).

1. Nell’interfaccia utente Raccolta dati, dal dashboard dell’app mobile, fai clic su **[!UICONTROL Rules]** e fai clic su **[!UICONTROL Add Rule]**.

1. Digita un nome, ad esempio **Adobe Campaign - Tracciamento dei clic push**.

1. In **[!UICONTROL Events]** sezione, fai clic su **[!UICONTROL Add]**.

1. Da **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Allora, **[!UICONTROL Track Action]** in **[!UICONTROL Event type]** a discesa.

1. Da **[!UICONTROL Action]** a discesa, seleziona **[!UICONTROL Action]**, seleziona **[!UICONTROL equals]** e tipo **tracking**.

1. Fai clic su **[!UICONTROL Keep changes]**. Quindi, nella **[!UICONTROL Actions]** sezione, fai clic su **[!UICONTROL Add]**.

1. Da **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Allora, **[!UICONTROL Send postback]** in **[!UICONTROL Action type]** a discesa.

1. In **[!UICONTROL URL]**, immetti il seguente URL:

   ```
   https://{%%camp-server%%}/r/?id={%contextdata.broadlogId%},{%contextdata.deliveryId%},{%contextdata.action%}&mcId={%%mcid%%}
   ```

1. Seleziona la **[!UICONTROL Add post body]** casella di controllo.

1. Aggiungi il corpo del post, ad esempio { }.

1. In **[!UICONTROL Content Type]**, tipo **application/json**.

1. In **[!UICONTROL Timeout]**, seleziona 0.

### Postback posizione {#location-postback}

1. Nell’interfaccia utente Raccolta dati, dal dashboard dell’app mobile, fai clic su **[!UICONTROL Rules]** e fai clic su **[!UICONTROL Add Rule]**.

1. Digita un nome, ad esempio **Postback posizione**.

1. In **[!UICONTROL Events]** sezione, fai clic su **[!UICONTROL Add]**.

1. Crea un evento, ad esempio Enter POI (Inserisci POI) o Exit POI (Esci POI). Da **[!UICONTROL Extension]** a discesa, seleziona **Luoghi - Beta**. Allora, **Inserisci POI** o **Esci dal POI** in **[!UICONTROL Event type]** a discesa.

1. Immettere un nome, ad esempio **Luoghi - Beta - Inserisci POI** o **Esci dal POI**.

1. In **[!UICONTROL Actions]** sezione, fai clic su **[!UICONTROL Add]**.

1. Da **[!UICONTROL Extension]** a discesa, seleziona **[!UICONTROL Mobile Core]**. Allora, **[!UICONTROL Send postback]** dal **[!UICONTROL Action type]** a discesa.

1. Immettere un nome, ad esempio **Mobile Core - Invia postback posizione**.

1. In **[!UICONTROL URL]**, immetti il seguente URL:

   ```
   https://{%%camp-server%%}/rest/head/mobileAppV5/{%%pkey%%}/locations/
   ```

1. Seleziona la **[!UICONTROL Add post body]** e aggiungi il corpo del post, ad esempio:

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
   >Nell’esempio precedente, gli elementi dati sul lato destro devono essere configurati nell’interfaccia utente Raccolta dati sfruttando i passaggi descritti in [Creazione di elementi dati](../../administration/using/configuring-rules-launch.md#create-data-elements). Gli elementi dati sul lato sinistro sono supportati in [!DNL Adobe Campaign Standard] e non è necessaria alcuna configurazione. Se hai bisogno di dati aggiuntivi, devi eseguire estensioni di risorse personalizzate in [!DNL Adobe Campaign Standard].

1. In **[!UICONTROL Content Type]**, tipo **application/json**.

1. In **[!UICONTROL Timeout]**, selezionare 5.

   ![](assets/do-not-localize/rules_4.png)
