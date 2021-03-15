---
solution: Campaign Standard
product: campaign
title: Risoluzione dei problemi
description: Ulteriori informazioni sui problemi comuni relativi alle API di Campaign Standard.
audience: developing
content-type: reference
topic-tags: use-case--extending-the-api
feature: API
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---


# Risoluzione dei problemi {#troubleshooting}

* **Quando si accede alla console Adobe.io si verifica il seguente errore: &quot;La console Adobe I/O è disponibile solo per selezionare i membri degli account aziendali. Se ritieni di avere accesso, contatta l&#39;amministratore di sistema.&quot;**

Puoi creare chiavi API solo per le organizzazioni IMS di cui sei amministratore. Se viene visualizzato questo messaggio e desideri creare le chiavi API, rivolgiti a un amministratore dell’organizzazione IMS.

* **Quando effettui una richiesta ad Adobe.io ottieni {&quot;error_code&quot;:&quot;403023&quot;,&quot;message&quot;:&quot;Profile is not valid&quot;}**

Ciò significa che si è verificato un problema con il provisioning IMS del prodotto Campaign specifico: il team IMS deve correggerlo.

Per ottenere ulteriori dettagli puoi chiamare l’API IMS con il token per vedere come si presenta il tuo profilo IMS: Devi avere un prodCtx in cui l&#39;id_organizzazione è lo stesso di quello inserito nell&#39;URL per Adobe.io per poter instradare la tua richiesta.
Se manca, è necessario correggere il provisioning IMS.

```
-X GET https://mc.adobe.io/{ORGANIZATION}/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce il seguente errore.

```
{"error_code":"403023","message":"Profile is not valid"}
```

Controlla il tuo profilo IMS con questa richiesta.

```
-X GET https://ims-na1.adobelogin.com/ims/profile/v1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Nella risposta, il valore ORGANIZATION_ID deve essere lo stesso nella prima richiesta di GET.

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

* **Quando fai una richiesta ad Adobe.io ottieni {&quot;code&quot;:500, &quot;message&quot;:&quot;Oops. Qualcosa è andato storto. Controlla l&#39;URI e riprova.&quot;}**

Adobe.io dichiara l&#39;URI non valido: probabilmente l’URI richiesto non è valido. Su Adobe.io quando selezioni il servizio Campaign ottieni un selettore con un elenco di possibili id_organizzazione . Devi verificare che quello scelto sia quello inserito nell&#39;URL.

* **Quando effettui una richiesta ad Adobe.io ottieni {&quot;error_code&quot;:&quot;401013&quot;,&quot;message&quot;:&quot;Oauth token is not valid&quot;}**

Il token non è valido (chiamata IMS impropria utilizzata per generare un token) o il token è scaduto.

* **Non vedo il mio profilo dopo la creazione**

A seconda della configurazione dell&#39;istanza, il profilo creato deve essere associato a un **orgUnit**. Per informazioni su come aggiungere questo campo nella creazione, consulta [questa sezione](../../api/using/creating-profiles.md).

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
