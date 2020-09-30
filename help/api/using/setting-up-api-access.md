---
title: Configurazione dell'accesso API
description: Scoprite come configurare l'accesso alle API Campaign Standard.
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
source-git-commit: b0e69280912ee70e6f53efd24782474395c57f74
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 1%

---


# Impostazione dell’accesso API {#setting-up-api-access}

 l&#39;accesso alle API Adobe Campaign Standard è configurato attraverso i passaggi descritti di seguito. Ciascuno di questi passaggi è descritto nel [della documentazione](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)IO del Adobe.

>[!IMPORTANT]
>
>Per gestire i certificati in  I/O Adobe, accertatevi di disporre dei diritti di amministratore <b>di</b> sistema sull&#39;organizzazione o su un account [](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> sviluppatore nell&#39;Admin Console.

1. **Verificate di disporre di un certificato** digitale oppure createne uno, se necessario. Le chiavi pubblica e privata fornite con il certificato sono necessarie nei seguenti passaggi.
1. **Crea una nuova integrazione per  Adobe Campaign Service** in  I/O Adobe e configurala. Le credenziali verranno quindi generate (Chiave API, Segreto cliente...).
1. **Create un token Web JSON (JWT)** dalle credenziali generate in precedenza e firmatelo con la vostra chiave privata. Il JWT codifica tutte le informazioni di identità e sicurezza necessarie per  Adobe per verificare la propria identità e concedere l&#39;accesso all&#39;API.
1. **Scambiate il JWT per ottenere un token** di accesso tramite una richiesta di POST. Questo token di accesso dovrà essere utilizzato in ogni intestazione delle richieste API.

Per stabilire una sessione dell&#39;API I/O di Adobe  servizio sicuro, ogni richiesta a un servizio di Adobe  deve includere nell&#39;intestazione Autorizzazione le informazioni riportate di seguito.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZZAZIONE>**: Si tratta dell’ID organizzazione personale, un ID organizzazione viene fornito dal Adobe  per ogni istanza:

   * &lt;ORGANIZZAZIONE> : l’istanza di produzione,
   * &lt;ORGANIZATION-mkt-stage>: l’istanza dell’area di visualizzazione.

   Per ottenere il valore ID ORGANIZZAZIONE, rivolgiti all’amministratore o al contatto tecnico  Adobe. È inoltre possibile recuperarlo  Adobe I/O quando si crea una nuova integrazione, nell&#39;elenco delle licenze (vedere la documentazione <a href="https://www.adobe.io/authentication.html">IO</a>Adobe).

* **&lt;ACCESS_TOKEN>**: Token di accesso personale, recuperato durante lo scambio del token Web JSON tramite una richiesta di POST.

* **&lt;API_KEY>**: la chiave API personale. Viene fornito in  I/O Adobe dopo la creazione di una nuova integrazione  Adobe Campaign Service.

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