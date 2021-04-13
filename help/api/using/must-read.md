---
solution: Campaign Standard
product: campaign
title: Must-read
description: Must-read prima di utilizzare le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 9e2d1b59-55a5-4715-adfb-35191a9df536
translation-type: tm+mt
source-git-commit: 01e4eb027b55815c3680b26691e61cbe5b63ee8c
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 0%

---

# Must-Read {#must-read}

## Requisiti tecnici

* Le API di Adobe Campaign devono essere utilizzate solo da Server a Server.
* Controlla sempre con il tuo contatto tecnico Adobe se il caso d’uso che desideri implementare è allineato con la scala consentita dalle API Adobe Campaign.
* L&#39;impostazione di un accesso AdobeIO richiede autorizzazioni specifiche. Per qualsiasi problema, contatta il supporto Adobe.

## Diritti e accesso

* Per impostazione predefinita, le API di Adobe Campaign utilizzano il contesto amministratore, pertanto le unità e i ruoli dell’organizzazione non sono applicabili.
* Le API di Adobe Campaign sono escluse dal contesto del ruolo.
* Se desideri configurare le API con un’unità o ruoli dell’organizzazione, contatta prima il contatto tecnico per Adobe.

## Rappresentanza delle risorse

Tutte le risorse API sono disponibili in **JSON** con estensione URL o all&#39;interno di un&#39;intestazione HTTP Accept:

`GET /profileAndServices/<resourceName>.json`

>[!NOTE]
>
>Senza estensione nell&#39;URL, il formato **json è quello predefinito** per il tipo di contenuto.

<br/>

***esempio di richiesta***

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile.json \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

## Chiave principale e URL

* Non cercare di generare un URL da solo. Tutti gli URL vengono restituiti dall’API. Tuttavia, è possibile creare un URL basato sul nome della risorsa di livello principale.

* I valori della chiave primaria automatica (PKey) che illustrano gli esempi non sono destinati a funzionare in un&#39;altra implementazione specifica. Sono prodotti dall’API Adobe Campaign.

* I valori della chiave primaria automatica generati da Adobe Campaign non devono mai essere memorizzati in un database o un sito Web esterno. È necessario generare campi chiave specifici nella definizione del database e utilizzarli durante gli sviluppi.

## Tasti personalizzati {#custom-keys}

Se la risorsa profilo è stata estesa con un campo chiave personalizzato, puoi utilizzare questo campo come chiave invece della chiave primaria automatica generata da Adobe Campaign:

`GET /.../profileAndServicesExt/profile/<customKey>`

Non è possibile modificare le chiavi personalizzate utilizzando un’operazione PATCH se il valore della chiave è diverso dalla chiave di origine o se si utilizza la chiave business personalizzata come URI invece di quella fornita dall’Adobe.

Utilizza una chiave personalizzata solo per **risorse di profilo di primo livello** . Gli URL vengono restituiti dall’API e non devono mai essere generati da te stesso.

<br/>

***Richiesta di esempio***

Per recuperare le sottoscrizioni per un profilo utilizzando una chiave personalizzata, esegui un’operazione di GET sulla chiave personalizzata.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/<customKey> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Esegui una richiesta di GET sull&#39;URL degli abbonamenti restituito.

```
-X GET <SUBSCRIPTION_URL> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l’elenco delle sottoscrizioni per il profilo.

```
"service": {
"PKey": "<PKEY>",
"href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/service/<PKEY>",
"label": "Sport Newsletter",
"name": "SVC1",
"title": "Sport Newsletter (SVC1)"
}
```
