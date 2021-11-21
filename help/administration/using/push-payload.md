---
title: Struttura del payload per le notifiche push di Campaign Standard
description: Questo documento ha lo scopo di descrivere la struttura del payload ricevuto nelle applicazioni mobili.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: a6515795-1006-4f27-bc44-5ae8b8edc018
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 3%

---

# Comprensione della struttura del payload per le notifiche push {#push-payload}

Adobe Campaign consente di inviare notifiche push personalizzate e segmentate su dispositivi mobili iOS e Android alle app mobili (app mobile).

Ogni notifica push ricevuta su un’app mobile contiene alcune informazioni utilizzate dall’app per visualizzare la notifica push se viene inviata una notifica push di avviso e molto probabilmente eseguirà anche altri calcoli, soprattutto se viene inviata una notifica push automatica.

Queste informazioni vengono ricevute dal codice dell’app mobile in un gestore di eventi che indica che è stata ricevuta una notifica push. Quando si inviano notifiche push da Adobe Campaign Standard, le informazioni ricevute nell’app mobile possono anche contenere informazioni specifiche di Campaign Standard che possono essere utilizzate per sfruttare alcune funzionalità fornite da Campaign Standard. Inoltre, il payload può contenere dati personalizzati che possono essere utilizzati dall’app mobile.

Questo documento descrive la struttura del payload ricevuto in un’app mobile quando una notifica push viene inviata correttamente a un’app da Adobe Campaign Standard.

>[!NOTE]
>
>La struttura del payload varia a seconda del tipo di app mobile (ad esempio, app iOS, app Android con abilitazione FCM).

## Struttura del payload push {#push-payload-structure}

Questa sezione descrive la struttura di un payload di esempio per varie piattaforme mobili e descrive gli attributi principali al suo interno. Questa è la struttura del payload ricevuto nel codice dell’app mobile nel gestore di eventi che indica che è stata ricevuta una notifica push.

Gli attributi del payload e i relativi valori variano in base alle configurazioni fornite nelle opzioni avanzate di notifica push. Questa sezione fornisce anche una mappatura tra queste configurazioni nell’interfaccia utente di Campaign Standard e gli attributi nel payload per chiarire in che modo il payload cambierà durante la configurazione di un’opzione in Campaign Standard.

### Per l’app mobile iOS {#payload-structure-ios}

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

La sezione più importante del payload è il dizionario aps, che contiene le chiavi definite da Apple e viene utilizzato per determinare in che modo il sistema che riceve la notifica deve avvisare l’utente, se del caso. Questa sezione contiene chiavi predefinite utilizzate dall’app mobile per formulare il comportamento della notifica push.

I dettagli approfonditi sugli attributi all’interno di app sono disponibili nei documenti per sviluppatori di Apple: [Creazione del payload di notifica remota](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH10-SW1).

### Per app Android {#payload-structure-android}

**Esempio di invio di payload dall’app Adobe Campaign all’app Android**

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

**Payload di esempio JSON da utilizzare [Google FCM tester](https://pushtry.com/)**

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

Il payload contiene un messaggio di dati che include tutto il contenuto della consegna delle notifiche push, incluse le coppie chiave/valore personalizzate, e l’app client deve gestire il messaggio per generare e mostrare le notifiche push, se necessario, altrimenti aggiungere qualsiasi altra logica di business.

Per comprendere gli aspetti di un payload android, fai riferimento a [Concetti e opzioni di messaggistica (fcm)](https://firebase.google.com/docs/cloud-messaging/concept-options).

>[!NOTE]
>
>Il supporto per i messaggi di notifica nel payload Android è stato rimosso a partire da gennaio 2018 per abilitare il risveglio dell’app e il passaggio del controllo all’app mobile senza che l’utente debba interagire con l’app.

### Mappatura tra le configurazioni di Campaign Standard e gli attributi del payload {#mapping-payload}

| Configurazione della campagna | Attributo interessato in iOS | Attributo interessato in Android | Descrizione |
|:-:|:-:|:-:|:-:|
| Titolo del messaggio <br>Corpo del messaggio | alert → titolo <br> allerta → corpo | title <br>corpo | Questi dati contengono specifiche del messaggio di avviso.<br>Il titolo e le chiavi corpo forniscono il contenuto dell’avviso. |
| Riprodurre un suono | suono | suono | Un suono personalizzato da riprodurre con l&#39;avviso. |
| Valore del badge | badge | badge | Un valore intero da utilizzare per applicare un badge all’icona dell’app. |
| Aggiungere un deep link | uri | NA | Un deep link ti consente di portare gli utenti direttamente al contenuto presente all’interno dell’applicazione (anziché aprire una pagina del browser web). |
| Categoria | categoria | categoria | Per visualizzare azioni personalizzate con una notifica remota. <br>La chiave di categoria consente al sistema di visualizzare le azioni per tale categoria come pulsanti nell’interfaccia di avviso. |
| Campi personalizzati | custom_field1, custom_field2 ... | custom_field1, custom_field2 ... | Qualsiasi dato personalizzato che desideri inviare alla tua app. |
| URL di contenuti rich media (file immagine, gif, audio e video)<br>(Applicabile solo per iOS 10 o versione successiva) | media-attachment-url | NA | URL dei file multimediali per aggiungere contenuti avanzati alla notifica. <br>Quando si fornisce un valore per questo URL, il flag di contenuto variabile viene inviato automaticamente nel payload. <br> (Applicabile solo per iOS 10 o versione successiva) |
| Contenuto variabile <br> (Applicabile solo per iOS 10 o versione successiva) | contenuto variabile | NA | L’estensione del servizio di notifica nell’app &quot;intercetta&quot; tutte le notifiche remote con la chiave a contenuto variabile e ti consentirà di gestire/manipolare il contenuto del payload della richiesta, che può quindi essere utilizzato per personalizzare la notifica. I casi d’uso di questa funzione includono il download e la visualizzazione di più file multimediali, la decrittografia di tutti i dati crittografati presenti nel payload push. Ulteriori informazioni sono disponibili in [Modificare il payload di una notifica remota](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html). <br>(Applicabile solo per iOS 10 o versione successiva) |
| Contenuto disponibile | disponibile | NA | Quando si seleziona questa opzione, si attiva la risveglia di un’app iOS in background/in sospensione. La riattivazione implica che l’app viene eseguita in background e che il gestore di eventi appropriato responsabile della ricezione del payload di dati di notifica push ottiene un controllo e può utilizzare i dati per eseguire qualsiasi calcolo, inclusi, tra l’altro, la creazione di notifiche push personalizzate e la visualizzazione dello stesso. Ulteriori informazioni sono disponibili in [Svegliare l’app con la consegna delle notifiche](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html). |
| URL contenuti rich media (file immagine)<br>(applicabile solo per Android) | NA | media-attachment-url | URL dei file di immagine per aggiungere contenuti avanzati alla notifica. |
| NA | _mId<br>_dId | _mId <br>_dId | Valori di broadlogId e deliveryId.<br>Questi attributi sono necessari se l’app desidera richiamare un postback di tracciamento per tracciare quando hai fatto clic/aperto sulla notifica push. Queste informazioni vengono calcolate e inviate internamente dal server app senza l’intervento dell’utente.<br>Le informazioni sui postback si trovano in questo [page](../../administration/using/configuring-rules-launch.md#inapp-tracking-postback). |

### Come recuperare le informazioni sul payload nel codice dell’app mobile {#payload-information}

Le informazioni sul payload inviate dal server app vengono ricevute dal codice dell’app mobile in un gestore di eventi che indica che è stata ricevuta una notifica push. Questo evento varia a seconda della piattaforma mobile su cui viene lavorato e anche a seconda che l’app sia in esecuzione in primo piano o in background. La seguente documentazione ti aiuta a identificare il gestore di eventi che desideri gestire in base al tuo caso d’uso.

* Applicazioni iOS: **Gestione delle notifiche remote** sezione [Notifiche remote](https://developer.apple.com/library/archive/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/HandlingRemoteNotifications.html).
* Applicazioni Android: [Ricezione dei messaggi su un’app client Android](https://firebase.google.com/docs/cloud-messaging/android/receive)

**Esempio per l’app mobile iOS**

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

**Esempio per l’app FCM mobile Android**

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
