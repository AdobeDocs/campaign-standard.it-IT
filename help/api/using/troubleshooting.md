---
title: Risoluzione dei problemi
description: Ulteriori informazioni sui problemi comuni relativi alle API Campaign Standard.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Risoluzione dei problemi {#troubleshooting}

* **Quando vai alla console Adobe.io ricevi il seguente errore: "La console Adobe I/O è disponibile solo per selezionare i membri degli account enterprise. Se ritenete di dover disporre dell'accesso, contattate l'amministratore di sistema."**

Potete creare chiavi API solo per le organizzazioni IMS di cui siete amministratore. Se questo messaggio viene visualizzato e desiderate creare chiavi API e chiedere a un amministratore dell'organizzazione IMS.

* **Quando fai una richiesta ad Adobe.io ricevi {"error_code":"403023","message":"Profilo non valido"}**

Ciò significa che si è verificato un problema con il provisioning IMS del prodotto Campaign specifico: il team IMS deve correggerlo.

Per maggiori dettagli, puoi chiamare l'API IMS con il tuo token per vedere come sarà il tuo profilo IMS: Per poter inoltrare la richiesta, è necessario disporre di un prodCtx in cui l'ID_organizzazione corrisponde a quello immesso nell'URL.
Se manca il provisioning IMS, è necessario risolvere il problema.

```
-X GET https://mc.adobe.io/{ORGANIZATION}/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

e restituisce il seguente errore.

```
{"error_code":"403023","message":"Profile is not valid"}
```

Controlla il profilo IMS con questa richiesta.

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Nella risposta, il valore ORGANIZATION_ID deve essere lo stesso nella prima richiesta GET.

```
{
  "countryCode": "FR",
  "mrktPermEmail": null,
  "projectedProductContext": [
    {
    "prodCtx": {
      "statusCode": "ACTIVE",
      "ident": "ZQ9FRQK7BF09YXAESFY9DDQP1G",
      "modDts": 1448307260000,
      "organization_id": "actest",
      "owningEntity": "6096892F54B5819E0A4C98A2@AdobeOrg",
      "serviceCode": "dma_tartan",
      "label": "Adobe Marketing Cloud",
      "serviceLevel": "standard",
      "createDts": 1421181343000,
      "deal_id": " "
      }
    }
  ]
}
```

* **Quando fai una richiesta ad Adobe.io ottieni {"code":500, "message":"Oops. È andato male qualcosa. Controllare l'URI e riprovare."}**

Adobe.io dichiara l'URI non valido: probabilmente l'URI richiesto non è valido. In Adobe.io, quando selezionate il servizio Campaign, viene visualizzato un selettore con un elenco di possibili ID_organizzazione. È necessario verificare che quello scelto sia quello inserito nell'URL.

* **Quando fai una richiesta ad Adobe.io ricevi {"error_code":"401013","message":"Oauth token is not valid"}**

Il token non è valido (chiamata IMS impropria utilizzata per generare un token) oppure il token è scaduto.

* **Non vedo il mio profilo dopo la creazione**

A seconda della configurazione dell’istanza, il profilo creato deve essere associato a un’ **organizzazioneUnit**. Per informazioni su come aggiungere questo campo nella creazione, consulta [questa sezione](../../api/using/creating-profiles.md).

<!-- * (error duplicate key : quand tu crées un profile qui existe déjà , il faut faire un patch pour updater le profile plutôt qu’un POST)

With Curl
List all profiles

Create a profile

Update the mobilePhone attribute of a profile

API Calls on Service

GET the list of services

-->

<!--

How to find and use a filter?
Error codes:

* PAtch sur Age = message d'erreur :
500
Cannot update the 'age' property that is read-only
'age' property is not valid for the 'profile' resource.
-->

<!--
How to filter a list of subscribed profiles with available profile filters ? by date (by les filtres dispo sur la ressource) ?

Pattern classique :

recupérer la liste des subscriptions filtrées d'un profile
1) get sur profile
2) recup PKey
3) get sur PKey
4) get sur href des subscriptions

Comment savoir quel filtre appliquer ?

1) get sur metadata de profile
2) retourne description de la collection subscription
3) get sur la valeur du champ resTarget
4) get sur le href dans filters
5) retourne les filtres applicables sur l'url des data.

-->
