---
title: Must-read
description: Deve essere letto prima di utilizzare le API.
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
source-wordcount: '320'
ht-degree: 0%

---


# Must-Read {#must-read}

## Requisiti tecnici

*  le API Adobe Campaign devono essere utilizzate solo da Server a Server.
* Controllate sempre con il vostro contatto tecnico  Adobe se il caso di utilizzo che desiderate implementare è allineato con la scala consentita dalle API Adobe Campaign .
* La configurazione di un accesso AdobeIO richiede autorizzazioni specifiche. Per qualsiasi problema, contattate il supporto del Adobe .

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

* Non cercate di creare un URL da soli. Tutti gli URL vengono restituiti dall&#39;API. Tuttavia, è possibile creare un URL basato sul nome della risorsa di livello principale.

* I valori della chiave primaria automatica (PKey) che illustrano gli esempi non sono destinati a funzionare in un&#39;altra distribuzione specifica. Vengono prodotti dall&#39;API Adobe Campaign .

* I valori di chiave primaria automatica generati da  Adobe Campaign non devono mai essere memorizzati in un database o in un sito Web esterno. È necessario generare campi chiave specifici nella definizione del database e utilizzarli durante gli sviluppi.

## Tasti personalizzati {#custom-keys}

Se la risorsa del profilo è stata estesa con un campo chiave personalizzato, è possibile utilizzare questo campo come chiave invece della chiave primaria automatica generata da  Adobe Campaign:

`GET /.../profileAndServicesExt/profile/<customKey>`

Le chiavi personalizzate non possono essere modificate utilizzando un&#39;operazione PATCH se il valore della chiave è diverso dalla chiave di origine o se si utilizza la propria chiave business come URI invece di quella fornita dal Adobe .

Utilizzate una chiave personalizzata solo per le risorse **del profilo di livello** principale. Gli URL vengono restituiti dall&#39;API e non devono mai essere generati dall&#39;utente stesso.

<br/>

***Richiesta di esempio***

Per recuperare le sottoscrizioni per un profilo utilizzando una chiave personalizzata, eseguite un&#39;operazione sulla chiave personalizzata.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Eseguite una richiesta di GET sull&#39;URL delle sottoscrizioni restituito.

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l&#39;elenco delle sottoscrizioni per il profilo.

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
