---
solution: Campaign Standard
product: campaign
title: Configurazione dell'accesso API
description: Scoprite come configurare l'accesso alle API Campaign Standard.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 1%

---


# Impostazione dell’accesso API {#setting-up-api-access}

 l&#39;accesso alle API Adobe Campaign Standard è configurato attraverso i passaggi descritti di seguito. Ciascuno di questi passaggi è descritto nella [ documentazione IO del Adobe](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Per gestire i certificati in  I/O Adobe, accertatevi di disporre dei diritti di <b>amministratore di sistema</b> nell&#39;organizzazione o di un account [sviluppatore](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> nell&#39;Admin Console.

1. **Verificate di disporre di un certificato** digitale oppure createne uno, se necessario. Le chiavi pubblica e privata fornite con il certificato sono necessarie nei seguenti passaggi.
1. **Crea una nuova integrazione per  Adobe Campaign** Servicein  I/O Adobe e configurala. Le credenziali verranno quindi generate (Chiave API, Segreto cliente...).
1. **Create un token Web JSON (JWT)** dalle credenziali generate in precedenza e firmatelo con la vostra chiave privata. Il JWT codifica tutte le informazioni di identità e sicurezza necessarie per  Adobe per verificare la propria identità e concedere l&#39;accesso all&#39;API.
1. **Scambiare il JWT per un** Token di accesso tramite una richiesta di POST. Questo token di accesso dovrà essere utilizzato in ogni intestazione delle richieste API.

Per stabilire una sessione di servizio sicura  Adobe I/O API, ogni richiesta a un servizio  Adobe deve includere nell’intestazione Autorizzazione le informazioni riportate di seguito.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**: Si tratta dell’ID organizzazione personale, un ID organizzazione viene fornito dal Adobe  per ogni istanza:

   * &lt;organization> : l’istanza di produzione,
   * &lt;organization-mkt-stage>: l’istanza dell’area di visualizzazione.

   Per ottenere il valore ID ORGANIZZAZIONE, rivolgiti all’amministratore o al contatto tecnico  Adobe. È inoltre possibile recuperarlo in  Adobe I/O quando si crea una nuova integrazione, nell&#39;elenco delle licenze (vedere la <a href="https://www.adobe.io/authentication.html"> documentazione IO Adobe</a>).

* **&lt;access_token>**: Token di accesso personale, recuperato durante lo scambio del token Web JSON tramite una richiesta di POST.

* **&lt;api_key>**: la chiave API personale. Viene fornito in  Adobe I/O dopo la creazione di una nuova integrazione  Adobe Campaign Service.

   ![testo alt](assets/tenant.png)

## Risoluzione dei problemi

Durante l&#39;integrazione AdobeIO, se viene visualizzato il seguente errore:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Per verificare se il parametro CNAME è stato creato correttamente, rivolgetevi al vostro amministratore o al vostro  Adobe di contatto tecnico.