---
title: Gestione dei messaggi delle transazioni
description: Scopri come gestire i messaggi transazionali con le API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 1%

---


# Gestione dei messaggi delle transazioni {#managing-transactional-messages}

## Informazioni sulla messaggistica transazionale

Dopo aver creato un evento, dovrete integrare l’attivazione di questo evento nel sito Web.

>[!NOTE]
>
>La creazione e la pubblicazione di un evento sono descritte nella documentazione relativa [alla](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)campagna.

Ad esempio, si desidera che venga attivato un evento &quot;abbandono carrello&quot; ogni volta che un cliente abbandona il sito Web prima di acquistare i prodotti nel carrello. A tal fine, lo sviluppatore Web deve utilizzare REST Transactional Messages API.

1. Lo sviluppatore invia una richiesta in base al metodo POST, che attiva l&#39; [invio dell&#39;evento](#sending-a-transactional-event)transazionale.
1. La risposta alla richiesta di POST contiene una chiave primaria, che consente allo sviluppatore di inviare una o più richieste tramite una richiesta di GET. In questo modo è in grado di ottenere lo stato [dell’](#transactional-event-status)evento.

## Invio di un evento transazionale {#sending-a-transactional-event}

L’evento transazionale viene inviato tramite una richiesta POST con la seguente struttura URL:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;ORGANIZZAZIONE>**: l’ID organizzazione personale. Fai riferimento a [questa sezione](../../api/using/must-read.md).

* **&lt;transactionalAPI>**: endPoints dell&#39;API dei messaggi transazionali.

   Il nome dell&#39;endpoint API dei messaggi transazionali dipende dalla configurazione dell&#39;istanza. Corrisponde al valore &quot;mc&quot; seguito dall’ID organizzazione personale. Prendiamo l&#39;esempio della società Geometrixx, con &quot;geometrixx&quot; come ID organizzazione. In tal caso, la richiesta POST sarebbe la seguente:

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (L&#39;endpoint API dei messaggi transazionali è visibile anche durante l&#39;anteprima API)

* **&lt;eventID>**: il tipo di evento che si desidera inviare. Questo ID viene generato al momento della creazione della definizione dell’evento. Consulta la documentazione relativa alla [campagna](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

### Intestazione richiesta POST

La richiesta deve contenere un &quot;Content-Type: application/json&quot; header.

È necessario aggiungere un charset, ad esempio **utf-8**. Questo valore dipende dall’applicazione REST in uso.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### corpo della richiesta POST

I dati dell&#39;evento sono contenuti nel corpo del POST JSON. La struttura dell&#39;evento dipende dalla sua definizione. Il pulsante Anteprima API nella schermata di definizione delle risorse fornisce un esempio di richiesta. Consulta la documentazione relativa alla [campagna](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

Al contenuto dell&#39;evento possono essere aggiunti i seguenti parametri facoltativi per gestire l&#39;invio di messaggi transazionali collegati all&#39;evento:

* **scadenza** (facoltativo): dopo tale data, l&#39;invio dell&#39;evento transazionale verrà annullato.
* **pianificato** (facoltativo): a partire da tale data, l&#39;evento transazionale verrà elaborato e il messaggio transazionale verrà inviato.

>[!NOTE]
>
>I valori dei parametri &quot;scadenza&quot; e &quot;programmata&quot; seguono il formato ISO 8601. La norma ISO 8601 specifica l’uso della lettera maiuscola &quot;T&quot; per separare la data e l’ora. Tuttavia, può essere rimosso dall&#39;ingresso o dall&#39;uscita per una migliore leggibilità.

### Risposta alla richiesta POST

La risposta POST restituisce lo stato dell&#39;evento transazionale al momento della creazione. Per recuperare il suo stato corrente (dati evento, stato evento...), utilizzate la chiave primaria restituita dalla risposta POST in una richiesta di GET:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Richiesta di esempio***

POST richiesta di invio dell’evento.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/mcAdobe/EVTcartAbandonment \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79'

{
  "email":"test@example.com",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "ctx":
  {
    "cartAmount": "$ 125",
    "lastProduct": "Leather motorbike jacket",
    "firstName": "Jack"
  }
}
```

Risposta alla richiesta POST.

```
{
  "PKey":"<PKEY>",
  "ctx":
  {
    "cartAmount": "",
    "lastProduct": "",
    "firstName": ""
  }
  "email":"",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "href": "mcAdobe/EVTcartAbandonment/<PKEY>",
  "serverUrl":" https://myserver.com ",
  "status":"pending",
  "type":""
}
```

### Stato evento transazionale {#transactional-event-status}

Nella risposta, il campo &quot;status&quot; consente di sapere se l’evento è stato elaborato o meno:

* **in sospeso**: l&#39;evento è in sospeso. L&#39;evento assume questo stato quando è appena stato attivato.
* **elaborazione**: l&#39;evento è in attesa di consegna; viene trasformato in un messaggio e il messaggio viene inviato.
* **messi in pausa**: il processo evento è in pausa. Non viene più elaborata, ma tenuta in coda nel database Adobe Campaign . For more on this, refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message).
* **elaborati**: l&#39;evento è stato elaborato e il messaggio è stato inviato correttamente.
* **ignorato**: l&#39;evento è stato ignorato dalla consegna, in genere quando un indirizzo è in quarantena.
* **deliveryFailed**: si è verificato un errore di consegna durante l&#39;elaborazione dell&#39;evento.
* **routingFailed**: la fase di routing non è riuscita. Ciò potrebbe verificarsi, ad esempio, quando il tipo di evento specificato non è possibile trovare.
* **tooOld**: l&#39;evento è scaduto prima che fosse possibile elaborarlo. Ciò può accadere per vari motivi, ad esempio, quando un&#39;invio ha esito negativo diverse volte (questo determina l&#39;assenza di un evento) o quando il server non è più in grado di elaborare gli eventi dopo essere stato sovraccaricato.
* **targetingFailed**: Campaign Standard non è riuscito ad arricchire un collegamento utilizzato per il targeting dei messaggi.
