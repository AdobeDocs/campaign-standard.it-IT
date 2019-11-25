---
title: Configurazione dell'accesso API
description: Scopri come configurare l'accesso alle API Campaign Standard.
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


# Impostazione dell'accesso API {#setting-up-api-access}

L'accesso alle API Adobe Campaign Standard è configurato attraverso i passaggi descritti di seguito. Ciascuno di questi passaggi è descritto dettagliatamente nella documentazione [di](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe IO.

>[!CAUTION]
>
>Per gestire i certificati in Adobe IO, accertatevi di disporre dei diritti di amministratore <b>di</b> sistema sull'organizzazione o su un account <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html"></a> sviluppatore nell'Admin Console.

1. **Verificate di disporre di un certificato** digitale oppure createne uno, se necessario. Le chiavi pubblica e privata fornite con il certificato sono necessarie nei seguenti passaggi.
1. **Crea una nuova integrazione con Adobe Campaign Service** in Adobe IO e configurala. Le credenziali verranno quindi generate (Chiave API, Segreto cliente...).
1. **Create un token Web JSON (JWT)** dalle credenziali generate in precedenza e firmatelo con la vostra chiave privata. Il JWT codifica tutte le informazioni di identità e sicurezza necessarie ad Adobe per verificare la tua identità e concederti l'accesso all'API.
1. **Scambiate il JWT per ottenere un token** di accesso tramite una richiesta POST. Questo token di accesso dovrà essere utilizzato in ogni intestazione delle richieste API.

Per stabilire una sessione dell'API Adobe I/O sicura per il servizio, ogni richiesta a un servizio Adobe deve includere nell'intestazione Autorizzazione le informazioni riportate di seguito.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZZAZIONE&gt;**: Questo è l’ID organizzazione personale, un ID organizzazione viene fornito da Adobe per ogni istanza:

   * &lt;ORGANIZZAZIONE&gt; : l’istanza di produzione,
   * &lt;ORGANIZATION-mkt-stage&gt;: l’istanza dell’area di visualizzazione.
   Per ottenere il valore ID ORGANIZZAZIONE, rivolgiti all’amministratore o al contatto tecnico Adobe. È inoltre possibile recuperarlo in Adobe I/O al momento della creazione di una nuova integrazione, nell'elenco delle licenze (consultare la documentazione <a href="https://www.adobe.io/authentication.html">di</a>Adobe IO).

* **&lt;ACCESS_TOKEN&gt;**: Token di accesso personale, che è stato recuperato durante lo scambio del token Web JSON tramite una richiesta POST.

* **&lt;API_KEY&gt;**: la chiave API personale. Viene fornito in Adobe I/O dopo la creazione di una nuova integrazione con Adobe Campaign Service.

   ![testo alt](assets/tenant.png)
