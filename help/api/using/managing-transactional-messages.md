---
title: Gestione dei messaggi transazionali
description: Scopri come gestire i messaggi transazionali con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 00d39438-a232-49f1-ae5e-1e98c73397e3
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 3%

---

# Gestione dei messaggi transazionali {#managing-transactional-messages}

## Informazioni sulla messaggistica transazionale

Dopo aver creato e pubblicato un evento transazionale, devi integrare l’attivazione di questo evento nel sito web.

>[!NOTE]
>
>La configurazione di un evento è presentata in [questa sezione](../../channels/using/configuring-transactional-event.md).

Ad esempio, desideri attivare un evento &quot;Abbandono carrello&quot; ogni volta che uno dei tuoi clienti lascia il tuo sito web prima di acquistare i prodotti nel carrello. A questo scopo, lo sviluppatore web deve utilizzare l’API dei messaggi transazionali REST.

1. Lo sviluppatore invia una richiesta in base al metodo POST, che attiva l’ [invio dell’evento sulle transazioni](#sending-a-transactional-event).
1. La risposta alla richiesta POST contiene una chiave primaria, che consente allo sviluppatore di inviare una o più richieste tramite una richiesta GET. In questo modo è in grado di ottenere lo stato [evento](#transactional-event-status).

## Invio di un evento sulle transazioni {#sending-a-transactional-event}

L’evento transazionale viene inviato tramite una richiesta POST con la seguente struttura URL:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;organization>**: il tuo ID ORGANIZZAZIONE personale. Fai riferimento a [questa sezione](../../api/using/must-read.md).

* **&lt;transactionalapi>**: endPoints dell’API per messaggi transazionali.

   Il nome dell’endpoint API per i messaggi transazionali dipende dalla configurazione dell’istanza. Corrisponde al valore &quot;mc&quot; seguito dall’ID organizzazione personale. Prendiamo l’esempio della società Geometrixx, con &quot;geometrixx&quot; come ID organizzazione. In tal caso, la richiesta POST sarebbe la seguente:

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (L’endpoint API per i messaggi transazionali è visibile anche durante l’anteprima API)

* **&lt;eventid>**: il tipo di evento che si desidera inviare. Questo ID viene generato durante la creazione della configurazione dell&#39;evento (consulta [questa sezione](../../channels/using/configuring-transactional-event.md#creating-an-event)).

### intestazione di richiesta POST

La richiesta deve contenere un &quot;Content-Type: intestazione application/json&quot;.

È necessario aggiungere un set di caratteri, ad esempio **utf-8**. Questo valore dipende dall’applicazione REST in uso.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### corpo della richiesta POST

I dati dell’evento sono contenuti nel corpo di JSON POST. La struttura dell’evento dipende dalla sua definizione. Il pulsante di anteprima API nella schermata di definizione delle risorse fornisce un esempio di richiesta. Fai riferimento a [questa sezione](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

I seguenti parametri facoltativi possono essere aggiunti al contenuto dell’evento per gestire l’invio di messaggi transazionali collegati all’evento:

* **scadenza**  (facoltativo): dopo tale data, l’invio dell’evento sulle transazioni verrà annullato.
* **programmato**  (facoltativo): a partire da questa data, l’evento sulle transazioni verrà elaborato e il messaggio sulle transazioni verrà inviato.

>[!NOTE]
>
>I valori dei parametri &quot;expiration&quot; e &quot;Scheduled&quot; seguono il formato ISO 8601. La norma ISO 8601 specifica l&#39;uso della lettera maiuscola &quot;T&quot; per separare la data e l&#39;ora. Tuttavia, può essere rimosso dall&#39;ingresso o dall&#39;uscita per una migliore leggibilità.

### Risposta alla richiesta POST

La risposta di POST restituisce lo stato dell’evento sulle transazioni al momento della creazione. Per recuperare il proprio stato corrente (dati evento, stato evento..), utilizza la chiave primaria restituita dalla risposta di POST in una richiesta GET:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Richiesta di esempio***

Richiesta di POST per l’invio dell’evento.

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

### Stato dell’evento sulle transazioni {#transactional-event-status}

Nella risposta, il campo &quot;status&quot; ti consente di sapere se l’evento è stato elaborato o meno:

* **in sospeso**: l&#39;evento è in sospeso - l&#39;evento assume questo stato quando è appena stato attivato.
* **elaborazione**: l’evento è in attesa di consegna: viene trasformato in un messaggio e il messaggio viene inviato.
* **in pausa**: il processo dell’evento è in pausa. Non viene più elaborato, ma viene mantenuto in coda nel database di Adobe Campaign. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../channels/using/publishing-transactional-message.md#suspending-a-transactional-message-publication).
* **trasformati**: l&#39;evento è stato elaborato e il messaggio è stato inviato correttamente.
* **ignorato**: l’evento è stato ignorato dalla consegna, in genere quando un indirizzo è in quarantena.
* **deliveryFailed**: si è verificato un errore di consegna durante l’elaborazione dell’evento.
* **routingFailed**: la fase di routing non è riuscita - questo può verificarsi, ad esempio, quando il tipo di evento specificato non può essere trovato.
* **tooOld**: l’evento è scaduto prima che fosse in grado di essere elaborato. ciò può accadere per vari motivi, ad esempio, quando un’invio non riesce più a volte (questo fa sì che l’evento non sia più aggiornato) o quando il server non può più elaborare gli eventi dopo essere stato sovraccaricato.
* **targetingFailed**: Campaign Standard non è riuscito ad arricchire un collegamento utilizzato per il targeting dei messaggi.
