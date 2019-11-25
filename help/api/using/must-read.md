---
title: must-read
description: Deve essere letto prima di utilizzare le API.
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


# must-read {#must-read}

## Requisiti tecnici

* Le API di Adobe Campaign devono essere utilizzate solo da Server a Server.
* Controlla sempre con il tuo contatto tecnico Adobe se il caso di utilizzo che vuoi implementare è allineato con la scala consentita dalle API di Adobe Campaign.
* Per configurare un accesso AdobeIO è necessario disporre di autorizzazioni specifiche, contattate il supporto Adobe per qualsiasi problema.

## Rappresentazioni delle risorse

Tutte le risorse API sono disponibili in **JSON** con estensione URL o all’interno di un’intestazione HTTP Accept:

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>Senza estensione nell’URL, il formato **json è quello** predefinito per il tipo di contenuto.

<br/>

***esempio di richiesta***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## Chiave primaria e URL

* Non cercate di creare un URL da soli. Tutti gli URL vengono restituiti dall'API. Tuttavia, è possibile creare un URL basato sul nome della risorsa di livello principale.

* I valori della chiave primaria automatica (PKey) che illustrano gli esempi non sono destinati a funzionare in un'altra distribuzione specifica. Sono prodotti dall'API di Adobe Campaign.

* I valori di chiave primaria automatica generati da Adobe Campaign non devono mai essere memorizzati in un database o in un sito Web esterno. È necessario generare campi chiave specifici nella definizione del database e utilizzarli durante gli sviluppi.

## Tasti personalizzati {#custom-keys}

Se la risorsa del profilo è stata estesa con un campo chiave personalizzato, puoi utilizzare questo campo come chiave invece della chiave primaria automatica generata da Adobe Campaign:

`GET /.../profileAndServicesExt/profile/<customKey>`

Le chiavi personalizzate non possono essere modificate utilizzando un'operazione PATCH se il valore della chiave è diverso dalla chiave di origine o se si utilizza la propria chiave business come URI invece di quella fornita da Adobe.

Utilizzate una chiave personalizzata solo per le risorse **del profilo di livello** principale. Gli URL vengono restituiti dall'API e non devono mai essere generati dall'utente stesso.

<br/>

***Richiesta di esempio***

Per recuperare le iscrizioni per un profilo utilizzando una chiave personalizzata, eseguite un'operazione GET sulla chiave personalizzata.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Eseguite una richiesta GET sull'URL delle iscrizioni restituito.

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l'elenco delle sottoscrizioni per il profilo.

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
