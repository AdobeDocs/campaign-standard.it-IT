---
title: Struttura del payload per le notifiche push di Campaign Standard
description: Scopri la struttura del payload ricevuto nelle applicazioni mobili
audience: channels
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '1088'
ht-degree: 3%

---

# Comprensione della struttura del payload per le notifiche push {#push-payload}

Adobe Campaign ti consente di inviare notifiche push personalizzate e segmentate su dispositivi mobili iOS e Android alle app mobili (app mobile).

Ogni notifica push ricevuta su un’app mobile contiene alcune informazioni utilizzate dall’app per visualizzare la notifica push in caso di invio di una notifica push di avviso ed è molto probabile che venga eseguito un ulteriore calcolo, soprattutto se viene inviata una notifica push invisibile all’utente.

Queste informazioni vengono ricevute dal codice dell&#39;app mobile in un gestore eventi che indica che è stata ricevuta una notifica push. Quando si inviano notifiche push da Adobe Campaign Standard, le informazioni ricevute nell’app mobile possono contenere anche informazioni specifiche per Campaign Standard che possono essere utilizzate per sfruttare alcune funzioni fornite da Campaign Standard. Inoltre, il payload può contenere dati personalizzati che possono essere utilizzati dall’app mobile.

Questo documento descrive la struttura del payload ricevuto in un’app mobile quando una notifica push viene inviata correttamente a un’app da Adobe Campaign Standard.

>[!NOTE]
>
>La struttura del payload varia a seconda del tipo di app mobile (ad esempio app iOS, app Android abilitata per FCM).

## Struttura del payload push {#push-payload-structure}

Questa sezione descrive la struttura di un payload di esempio per varie piattaforme mobili e descrive i principali attributi in essa contenuti. Struttura del payload ricevuto nel codice dell’app mobile nel gestore eventi che indica la ricezione di una notifica push.

Gli attributi del payload e i relativi valori variano in base alle configurazioni fornite nelle opzioni avanzate per le notifiche push. Questa sezione fornisce anche una mappatura tra queste configurazioni nell’interfaccia utente di Campaign Standard e gli attributi nel payload, al fine di chiarire come cambierà il payload al momento della configurazione di un’opzione in Campaign Standard.

### Per l’app mobile di iOS {#payload-structure-ios}

**Payload di esempio inviato da Adobe Campaign all’app iOS:**

```
{

    "aps":{

            "alert":{

                    "body":"This is the content of my push notification",

                    "title":"Push Notification Title"

            },

            "content-available":1,

            "category":"NEW_MESSAGE_CATEGORY",

            "badge":2,

            "mutable-content":1,

            "sound":"default"

        },

    "custom_field1":"custom_value1",

    "custom_field2":"custom_value2",

    "media-attachment-url":"https://2.img-dpreview.com/files/p/articles/9440145363/Creative_Cloud.jpeg",

    "uri":"https://mydeeplinkurl.com",

    "_dId":"56c4",

    "_mId":"h138a"} 
```

**Payload di esempio JSON da utilizzare con [Tester APNS di iOS](https://pushtry.com/)**

```
{

  "aps": {

    "alert": {

      "title": "Push Notification Title",

      "body": "body of push"

    },

    "badge": 33,

    "sound": "default"

  },

  "custom_field1": "custom_value1",

  "uri": "https://mydeeplinkurl.com"

}
```

La sezione più importante del payload è il dizionario aps, che contiene le chiavi definite da Apple e viene utilizzato per determinare in che modo il sistema che riceve la notifica dovrebbe avvisare l’utente, se presente. Questa sezione contiene chiavi predefinite utilizzate dall’app mobile per formulare il comportamento della notifica push.

Per informazioni approfondite sugli attributi all’interno di aps, consulta i documenti per gli sviluppatori di Apple: [Creazione del payload di notifica remota](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1).

### Per app Android {#payload-structure-android}

**Payload di esempio inviato da Adobe Campaign all&#39;app Android**

```
{

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "title": "adobe title 123",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

**Payload di esempio JSON da utilizzare [Tester Google FCM](https://pushtry.com/)**

```
{

  "to": "<==========ENTER your device token==============>",

  "collapseKey": "1476005",

  "priority": "high",

  "data": {

    "_dId": "d57fd6",

    "_mId": "h1685a5",

    "title": "adobe title 123",

    "body": "adobe body 123",

    "category": "adobe category 123",

    "custom key 1": "value 1",

    "custom key 2": "test value 2",

    "custom key 3": "foo bar android",

    "media-attachment-url": "http://adobegiphy.com?test=123",

    "sound": "http://testcampaign.instance.com/r/?id=s1685a5,d57fd6,d57ff5",

    "uri": "http://testcampaign.instance.com/r/?id=d1685a5,d57fd6,d57ff6",

    "badge": 1817

  }

}
```

Il payload contiene un messaggio dati che include tutti i contenuti di consegna delle notifiche push, incluse le coppie chiave/valore personalizzate. L’app client deve gestire il messaggio per generare e visualizzare le notifiche push, se necessario, oppure per aggiungere qualsiasi altra logica di business.

Per comprendere gli aspetti di un payload android, consulta [Concetti e opzioni di messaggistica (fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>Il supporto per i messaggi di notifica nel payload Android è stato rimosso a gennaio 2018 per consentire la riattivazione dell’app e il passaggio del controllo all’app mobile senza che l’utente debba interagire con l’app.

### Mappatura tra configurazioni Campaign Standard e attributi del payload {#mapping-payload}

| Configurazione della campagna | Attributo interessato in iOS | Attributo interessato in Android | Descrizione |
|:-:|:-:|:-:|:-:|
| Titolo messaggio <br>Corpo del messaggio | titolo → avviso <br> corpo del → di avviso | titolo <br>corpo | Questi dati contengono le specifiche del messaggio di avviso.<br>Le chiavi del titolo e del corpo forniscono il contenuto dell’avviso. |
| Riproduci un suono | suono | suono | Suono personalizzato da riprodurre con l&#39;avviso. |
| Valore del badge | badge | badge | Valore intero da utilizzare per il badge dell’icona dell’app. |
| Aggiungere un deep link | uri | NA | Un deep link ti consente di portare gli utenti direttamente al contenuto presente all’interno dell’applicazione (anziché aprire una pagina del browser web). |
| Categoria | categoria | categoria | Per visualizzare azioni personalizzate con una notifica remota. <br>Il tasto di categoria consente al sistema di visualizzare le azioni per tale categoria come pulsanti nell&#39;interfaccia di avviso. |
| Campi personalizzati | custom_field1, custom_field2 ... | custom_field1, custom_field2 ... | Eventuali dati personalizzati che desideri inviare all’app. |
| URL di contenuti rich media (file immagine, gif, audio e video)<br>(Applicabile solo per iOS 10 o versione successiva) | media-attachment-url | NA | URL dei file multimediali per aggiungere contenuti avanzati alla notifica. <br>Quando fornisci un valore per questo URL, il flag di contenuto mutabile viene inviato automaticamente nel payload. <br> (Applicabile solo per iOS 10 o versione successiva) |
| Contenuto variabile <br> (Applicabile solo per iOS 10 o versione successiva) | contenuto mutabile | NA | L’estensione del servizio di notifica nell’app &quot;intercetta&quot; tutte le notifiche remote con la chiave di contenuto mutabile e ti consente di gestire/manipolare il contenuto del payload della richiesta, che può quindi essere utilizzato per personalizzare la notifica. I casi di utilizzo di questa funzione includono il download e la visualizzazione di più file multimediali e la decrittografia di eventuali dati crittografati presenti nel payload push. Ulteriori informazioni sono disponibili in [Modificare il payload di una notifica remota](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html). <br>(Applicabile solo per iOS 10 o versione successiva) |
| Contenuto disponibile | disponibile per il contenuto | NA | Selezionando questa opzione si abilita la riattivazione di un’app iOS mentre si trova in stato di background/sospensione. La riattivazione implica che l’app viene eseguita in background e che il gestore eventi appropriato responsabile della ricezione del payload dei dati della notifica push ottiene un controllo e può utilizzare i dati per eseguire qualsiasi calcolo, incluso ma non limitato alla creazione di notifiche push personalizzate e alla visualizzazione delle stesse. Ulteriori informazioni sono disponibili in [App di riattivazione con consegna notifiche](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| URL contenuti rich media (file di immagine)<br>(Applicabile solo per Android) | NA | media-attachment-url | URL dei file immagine per aggiungere contenuto avanzato alla notifica. |
| NA | _mId<br>_dId | _mId <br>_dId | Valori di broadlogId e deliveryId.<br>Questi attributi sono necessari se l’app desidera chiamare un postback di tracciamento per tenere traccia di quando si è fatto clic o si è aperta la notifica push. Queste informazioni vengono calcolate e inviate internamente dall’app server senza l’intervento dell’utente.<br>Le informazioni sui postback sono disponibili in questo [pagina](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback). |

### Come recuperare le informazioni sul payload nel codice dell’app mobile {#payload-information}

Le informazioni sul payload inviate dal server dell’app vengono ricevute dal codice dell’app mobile in un gestore eventi che indica la ricezione di una notifica push. Questo evento varia in base alla piattaforma mobile su cui si lavora e anche in base al fatto che l’app sia in esecuzione in primo piano o in background. La seguente documentazione consente di identificare il gestore eventi che desideri gestire in base al caso d’uso.

* Applicazioni iOS: **Gestione delle notifiche remote** sezione in [Notifiche remote](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html).
* Applicazioni Android: [Ricezione di messaggi su un’app client Android](https://firebase.google.com/docs/cloud-messaging/android/receive)

**Esempio per l&#39;app mobile iOS**

```
 - (void)application:(UIApplication *)application

didReceiveRemoteNotification:(NSDictionary *)userInfo {

    

    NSDictionary *apsDict = [userInfo objectForKey:@"aps"];

    NSDictionary *alertDict = [apsDict objectForKey:@"alert"];

    NSString *title = [alertDict objectForKey:@"title"];

    NSString *body = [alertDict objectForKey:@"body"];

    NSString *category = [apsDict objectForKey:@"category"];

    NSString *deliveryId = userInfo[@"_dId"];

    NSString *broadlogId = userInfo[@"_mId"];

    NSString *mediaAttachmentURL = userInfo[@"media-attachment-url"];

    NSString *deeplinkURL = userInfo[@"uri"];

    NSString *customValue1 = userInfo[@"custom_field1"];   

}
```

**Esempio per app FCM per dispositivi mobili Android**

```
public void onMessageReceived(RemoteMessage message) {

    Map<String, String> dataMap = message.getData();

     

    String title = dataMap.get("title");

    String body = dataMap.get("body");

    String category = dataMap.get("category");

    String deliveryId = dataMap.get("_dId");

    String broadlogId = dataMap.get("_mId");

    String mediaAttachmentURL = dataMap.get("media-attachment-url");

    String deeplinkURL = dataMap.get("uri");

    String customValue1 = dataMap.get("custom_field1");

}
```
