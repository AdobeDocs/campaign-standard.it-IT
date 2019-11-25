---
title: Gestione dei messaggi transazionali
description: Scopri come gestire i messaggi transazionali con le API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Gestione dei messaggi transazionali {#managing-transactional-messages}

## Informazioni sui messaggi transazionali

Dopo aver creato un evento, dovrete integrare l’attivazione di questo evento nel sito Web.

>[!NOTE]
>
>La creazione e la pubblicazione di un evento sono descritte nella documentazione relativa <a href="https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html">alla</a>campagna.

Ad esempio, si desidera che venga attivato un evento "abbandono carrello" ogni volta che un cliente abbandona il sito Web prima di acquistare i prodotti nel carrello. A tal fine, lo sviluppatore Web deve utilizzare REST Transactional Messages API.

1. Lo sviluppatore invia una richiesta in base al metodo POST, che attiva l' [invio dell'evento](#sending-a-transactional-event)transazionale.
1. La risposta alla richiesta POST contiene una chiave primaria, che consente allo sviluppatore di inviare una o più richieste tramite una richiesta GET. In questo modo è in grado di ottenere lo stato [dell’](#transactional-event-status)evento.

## Invio di un evento transazionale {#sending-a-transactional-event}

L’evento transazionale viene inviato tramite una richiesta POST con la seguente struttura URL:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;ORGANIZZAZIONE&gt;**: l’ID organizzazione personale. Fare riferimento a [questa sezione](../../api/using/must-read.md).

* **&lt;transactionalAPI&gt;**: endPoints dell'API dei messaggi transazionali.

   Il nome dell'endpoint API dei messaggi transazionali dipende dalla configurazione dell'istanza. Corrisponde al valore "mc" seguito dall’ID organizzazione personale. Prendiamo l’esempio della società Geometrixx, con "geometrixx" come ID organizzazione. In tal caso, la richiesta POST sarebbe la seguente:

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (L'endpoint API dei messaggi transazionali è visibile anche durante l'anteprima API)

* **&lt;eventID&gt;**: il tipo di evento da inviare. Questo ID viene generato al momento della creazione della definizione dell’evento. Consulta la documentazione relativa alla [campagna](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

### Intestazione richiesta POST

La richiesta deve contenere un "Content-Type: application/json" header.

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

I dati dell’evento sono contenuti nel corpo JSON POST. La struttura dell'evento dipende dalla sua definizione. Il pulsante Anteprima API nella schermata di definizione delle risorse fornisce un esempio di richiesta. Consulta la documentazione relativa alla [campagna](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

Al contenuto dell'evento possono essere aggiunti i seguenti parametri facoltativi per gestire l'invio di messaggi transazionali collegati all'evento:

* **scadenza** (facoltativo): dopo tale data, l'invio dell'evento transazionale verrà annullato.
* **pianificato** (facoltativo): a partire da tale data, l'evento transazionale verrà elaborato e il messaggio transazionale verrà inviato.

>[!NOTE]
>
>I valori dei parametri "scadenza" e "programmata" seguono il formato ISO 8601. La norma ISO 8601 specifica l’uso della lettera maiuscola "T" per separare la data e l’ora. Tuttavia, può essere rimosso dall'ingresso o dall'uscita per una migliore leggibilità.

### Risposta alla richiesta POST

La risposta POST restituisce lo stato dell’evento transazionale al momento della creazione. Per recuperare il proprio stato corrente (dati evento, stato evento...), utilizzate la Chiave primaria restituita dalla risposta POST in una richiesta GET:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Richiesta di esempio***

Richiesta POST per inviare l’evento.

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

Nella risposta, il campo "status" consente di sapere se l’evento è stato elaborato o meno:

* **in sospeso**: l'evento è in sospeso. L'evento assume questo stato quando è appena stato attivato.
* **elaborazione**: l'evento è in attesa di consegna; viene trasformato in un messaggio e il messaggio viene inviato.
* **messi in pausa**: il processo evento è in pausa. Non viene più elaborata, ma tenuta in coda nel database di Adobe Campaign. Per ulteriori informazioni, consulta la documentazione relativa alla [campagna](https://helpx.adobe.com/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message).
* **elaborati**: l'evento è stato elaborato e il messaggio è stato inviato correttamente.
* **ignorato**: l'evento è stato ignorato dalla consegna, in genere quando un indirizzo è in quarantena.
* **deliveryFailed**: si è verificato un errore di consegna durante l'elaborazione dell'evento.
* **routingFailed**: la fase di routing non è riuscita. Ciò potrebbe verificarsi, ad esempio, quando il tipo di evento specificato non è possibile trovare.
* **tooOld**: l'evento è scaduto prima che fosse possibile elaborarlo. Ciò può accadere per vari motivi, ad esempio, quando un'invio ha esito negativo diverse volte (questo determina l'assenza di un evento) o quando il server non è più in grado di elaborare gli eventi dopo essere stato sovraccaricato.
* **targetingFailed**: Campaign Standard non è riuscito ad arricchire un collegamento utilizzato per il targeting dei messaggi.
