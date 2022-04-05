---
title: Configurazione dell’accesso API
description: Scopri come impostare l’accesso alle API di Campaign Standard.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '364'
ht-degree: 1%

---

# Impostazione dell’accesso alle API {#setting-up-api-access}

L’accesso alle API di Adobe Campaign Standard è configurato attraverso i passaggi seguenti. Ciascuno di questi passaggi è descritto nella sezione [Adobe documentazione IO](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Per gestire i certificati in Adobe IO, assicurati di disporre di <b>Amministratore di sistema</b> diritti dell&#39;organizzazione o [account sviluppatore](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> nell&#39;Admin Console.

1. **Verifica di disporre di un certificato digitale** oppure creane uno, se necessario. Le chiavi pubbliche e private fornite con il certificato sono necessarie nei passaggi seguenti.
1. **Creare una nuova integrazione con Adobe Campaign Service** in Adobe IO e configuralo. Le credenziali verranno quindi generate (chiave API, segreto client...).
1. **Creare un token web JSON (JWT)** dalle credenziali generate in precedenza e firmalo con la tua chiave privata. JWT codifica tutte le informazioni di identità e sicurezza necessarie per Adobe per verificare la tua identità e concedere l’accesso all’API.
1. **Sostituire il JWT con un token di accesso** tramite una richiesta POST. Questo token di accesso dovrà essere utilizzato in ogni intestazione delle richieste API.

Per stabilire una sessione API di Adobe I/O servizio-servizio sicura, ogni richiesta a un servizio Adobe deve includere nell’intestazione Autorizzazione le informazioni riportate di seguito.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**: Si tratta dell’ID organizzazione personale, un ID organizzazione viene fornito per Adobe per ciascuna istanza :

   * &lt;organization> : la tua istanza di produzione,
   * &lt;organization-mkt-stage>: la tua istanza del palco.

   Per ottenere il valore dell’ID ORGANIZZAZIONE, rivolgiti all’amministratore o al contatto tecnico Adobe. È inoltre possibile recuperarlo in Adobe I/O durante la creazione di una nuova integrazione, nell&#39;elenco delle licenze (consulta <a href="https://developer.adobe.com/developer-console/docs/guides/authentication/">Adobe documentazione IO</a>).

* **&lt;access_token>**: Token di accesso personale, recuperato durante lo scambio del token web JSON tramite una richiesta POST.

* **&lt;api_key>**: la tua chiave API personale. Viene fornito in Adobe I/O dopo la creazione di una nuova integrazione con Adobe Campaign Service.

   ![testo alt](assets/tenant.png)

## Risoluzione dei problemi

Durante l&#39;integrazione di AdobeIO, se viene visualizzato il seguente errore:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Per verificare se il parametro CNAME è stato creato correttamente, rivolgiti all’amministratore o al contatto tecnico Adobe.
