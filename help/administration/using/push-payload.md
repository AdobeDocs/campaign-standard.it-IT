---
title: Informazioni sulla struttura payload delle notifiche push di Campaign Standard
description: Questo documento descrive la struttura del payload ricevuto nelle applicazioni mobili.
page-status-flag: never-activated
uuid: 961aaeb5-6948-4fd2-b8d7-de4510c10566
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: 23b4212e-e878-4922-be20-50fb7fa88ae8
context-tags: mobileApp,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 02fa55789449efe03af75779892303941b8a2871
workflow-type: tm+mt
source-wordcount: '1150'
ht-degree: 0%

---


# Understanding Campaign Standard Push Notifications Payload Structure {#push-payload}

 Adobe Campaign consente di inviare notifiche push personalizzate e segmentate su dispositivi mobili iOS e Android alle applicazioni mobili (app mobile).

Ogni notifica push ricevuta su un&#39;app mobile contiene alcune informazioni che vengono utilizzate dall&#39;app per visualizzare la notifica push se viene inviata una notifica push di avviso e molto probabilmente eseguirà anche qualche ulteriore calcolo, soprattutto se viene inviata una notifica push invisibile.

Queste informazioni vengono ricevute dal codice dell&#39;app mobile in un gestore eventi che indica che è stata ricevuta una notifica push. Quando si inviano notifiche push da  Adobe Campaign Standard, le informazioni ricevute nell&#39;app mobile possono anche contenere informazioni specifiche per Campaign Standard che possono essere utilizzate per sfruttare alcune funzionalità fornite da Campaign Standard. Inoltre, il payload può contenere dati personalizzati che possono essere utilizzati dall&#39;app mobile.

Questo documento descrive la struttura del payload ricevuto in un&#39;app mobile quando una notifica push viene inviata correttamente a un&#39;app da  Adobe Campaign Standard.

>[!NOTE]
>
>La struttura del payload varia a seconda del tipo di app mobile (ad es. app iOS, app Android abilitate per FCM).

## Struttura payload push {#push-payload-structure}

Questa sezione descrive la struttura di un payload di esempio per diverse piattaforme mobili e descrive gli attributi principali al suo interno. Si tratta della struttura del payload ricevuto nel codice dell&#39;app mobile nel gestore eventi che indica che è stata ricevuta una notifica push.

Gli attributi di payload e i relativi valori variano in base alle configurazioni fornite nelle opzioni avanzate di notifica push. Questa sezione fornisce anche una mappatura tra queste configurazioni nell’interfaccia utente di Campaign Standard e gli attributi nel payload, per chiarire in che modo il payload cambierà durante la configurazione di un’opzione in Campaign Standard.

### Per l&#39;app mobile iOS {#payload-structure-ios}

**Payload di esempio inviato da  Adobe Campaign all&#39;app iOS:**

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

**Payload di esempio JSON da usare con[iOS APNS Tester](https://pushtry.com/)**

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

La sezione più importante del payload è il dizionario aps, che contiene le chiavi definite da Apple e viene utilizzato per determinare in che modo il sistema che riceve la notifica deve avvisare l&#39;utente, se del caso. Questa sezione contiene chiavi predefinite utilizzate dall&#39;app mobile per formulare il comportamento della notifica push.

Informazioni dettagliate sugli attributi all&#39;interno di app sono disponibili nei documenti per sviluppatori Apple: [Creazione del payload](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1)di notifica remota.

### Per app Android {#payload-structure-android}

**Esempio di invio del payload da  Adobe Campaign all&#39;app Android**

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

**Payload di esempio JSON per utilizzare[Google FCM tester](https://pushtry.com/)**

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

Il payload contiene un messaggio di dati che include tutto il contenuto per la consegna delle notifiche push, incluse le coppie chiave/valore personalizzate, e l&#39;app client deve gestire il messaggio per creare e mostrare la notifica push, se necessario o per aggiungere qualsiasi altra logica di business.

Per comprendere gli aspetti di un payload android, fare riferimento a [Messaging Concepts and Options (fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>Il supporto per i messaggi di notifica nel payload Android è stato rimosso a partire da gennaio 2018 per abilitare il risveglio dell&#39;app e passare il controllo all&#39;app mobile senza che l&#39;utente debba interagire con l&#39;app.

### Mapping tra configurazioni Campaign Standard e attributi di payload {#mapping-payload}

| Configurazione campagna | Attributo interessato in iOS | Attributo interessato in Android | Descrizione |
|:-:|:-:|:-:|:-:|
| Titolo del messaggio <br>Corpo del messaggio | alert → title <br> alert → corpo | title <br>body | Questi dati contengono specifiche del messaggio di avviso.<br>Le chiavi del titolo e del corpo forniscono il contenuto dell’avviso. |
| Riproduzione di un suono | sound | sound | Un suono personalizzato da riprodurre con l&#39;avviso. |
| Valore del contrassegno | badge | badge | Un valore intero da utilizzare per applicare un contrassegno all&#39;icona dell&#39;app. |
| Aggiungere un collegamento profondo | uri | NA | Un collegamento profondo consente di portare gli utenti direttamente al contenuto presente all’interno dell’applicazione (anziché aprire una pagina del browser Web). |
| Categoria | category | category | Per visualizzare azioni personalizzate con una notifica remota. <br>La chiave di categoria consente al sistema di visualizzare le azioni per quella categoria come pulsanti nell&#39;interfaccia dell&#39;avviso. |
| Campi personalizzati | custom_field1, custom_field2 ... | custom_field1, custom_field2 ... | Qualsiasi dato personalizzato che desideri inviare alla tua app. |
| URL contenuto multimediale (file immagine, gif, audio e video)<br>(applicabile solo per iOS 10 o versione successiva) | media-attachment-url | NA | URL dei file multimediali per aggiungere contenuto dettagliato alla notifica. <br>Quando si fornisce un valore per questo URL, il flag di contenuto variabile viene inviato automaticamente nel payload. <br> (applicabile solo per iOS 10 o versione successiva) |
| Contenuto variabile <br> (applicabile solo per iOS 10 o versione successiva) | contenuto variabile | NA | L&#39;estensione del servizio di notifica nell&#39;app &quot;intercetta&quot; tutte le notifiche remote con la chiave a contenuto variabile e ti consentirà di gestire/manipolare il contenuto del payload della richiesta, che può quindi essere utilizzato per personalizzare la notifica. I casi d’uso di questa funzione includono il download e la visualizzazione di più supporti, la decrittografia di tutti i dati crittografati presenti nel payload push. Ulteriori informazioni sono disponibili in [Modifica del payload di una notifica](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html)remota. <br>(applicabile solo per iOS 10 o versione successiva) |
| Contenuto disponibile | content-available | NA | Selezionando questa opzione si attiva il risveglio di un&#39;app iOS in stato di background/sospensione. La veglia implica che l&#39;app viene eseguita in background e che il gestore eventi appropriato responsabile della ricezione del payload di dati di notifica push ottiene un controllo e può utilizzare i dati per eseguire qualsiasi calcolo, incluso, a titolo esemplificativo, la creazione di notifiche push personalizzate e la visualizzazione dello stesso. Ulteriori informazioni sono disponibili in [sveglia app con consegna](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html)delle notifiche. |
| URL contenuto multimediale (file immagine)<br>(applicabile solo per Android) | NA | media-attachment-url | URL dei file immagine per aggiungere contenuto dettagliato alla notifica. |
| NA | _mId<br>_dId | _mId <br>_dId | Valori di broadcastId e deliveryId.<br>Questi attributi sono richiesti se l&#39;app desidera richiamare un postback di tracciamento per tenere traccia di quando si fa clic/si apre la notifica push. Queste informazioni vengono calcolate e inviate internamente dal server app senza l&#39;intervento dell&#39;utente.<br>Informazioni sui postback sono disponibili in questa [pagina](https://helpx.adobe.com/campaign/kb/config-app-in-launch.html#PIIpostback). |

### Come recuperare le informazioni di payload nel codice dell&#39;app mobile {#payload-information}

Le informazioni di payload inviate dal server app vengono ricevute dal codice dell&#39;app mobile in un gestore eventi che indica che è stata ricevuta una notifica push. Questo evento può variare in base alla piattaforma mobile su cui viene lavorato e anche in base al fatto che l&#39;app sia in esecuzione in primo piano o in background. La seguente documentazione consente di identificare il gestore di eventi che si desidera gestire in base al caso di utilizzo.

* Applicazioni iOS: **Gestione delle notifiche** remote in Notifiche [](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html)remote.
* Applicazioni Android: [Ricezione di messaggi su un&#39;app client Android](https://firebase.google.com/docs/cloud-messaging/android/receive)

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

**Esempio per app FCM Android Mobile**

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
