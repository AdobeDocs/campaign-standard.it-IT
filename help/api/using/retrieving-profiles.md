---
solution: Campaign Standard
product: campaign
title: Recupero profili
description: Ulteriori informazioni su come recuperare i profili con le API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: da0aa6c111f3e44bb502c1e5c4ad7feff9108d81
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 5%

---


# Recupero profili {#retrieving-profiles}

Il recupero dei profili viene eseguito con una richiesta **GET**.

Potete quindi perfezionare la ricerca utilizzando filtri, ordine e impaginazione. Per ulteriori informazioni, consultare la sezione [Operazioni aggiuntive](../../api/using/sorting.md).

Inoltre, le API Campaign Standard consentono di ricercare profili basati su uno dei seguenti campi: email, nome, cognome o qualsiasi campo personalizzato. Per ulteriori informazioni al riguardo, consulta [questa sezione](#searching-field).

<br/>

***Richieste di esempio***

* Esempio di richiesta di GET per recuperare tutti i profili.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Risposta alla richiesta.

   ```
   {
       "content": [
           {
               "PKey": "<PKEY>",
               "firstName": "John",
               "lastName":"Doe",
               "birthDate": "1980-10-24",
               ...
           },
           ...
   }
   ```

* Esempio di richiesta di GET per recuperare i primi 10 valori e-mail.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Risposta alla richiesta. Il nodo &quot;successivo&quot; restituisce l’URL che consente di accedere ai 10 valori e-mail successivi.

   ```
   {
   "content": [
       "amy.dakota@mail.com",
       "kristen.smith@mail.com",
       "omalley@mail.com",
       "xander.harrys@mail.com",
       "jane.summer@mail.com",
       "gloria.boston@mail.com",
       "edward.snow@mail.com",
       "dorian.simons@mail.com",
       "peter.paolini@mail.com",
       "mingam+test08@adobe.com"
   ],
   "next": {
       "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10&_
       lineStart=@Qy2MRJCS67PFf8soTf4BzF7BXsq1Gbkp_e5lLj1TbE7HJKqc"
   }
   }
   ```

## Ricerca di profili in base a un campo {#searching-field}

Il parametro **[!UICONTROL filterType]** consente di recuperare i profili in base a uno di questi campi: e-mail, nome, cognome o qualsiasi campo personalizzato aggiunto nel filtro avanzato durante l’estensione della risorsa del profilo.

>[!NOTE]
>
>Le ricerche sono con distinzione tra maiuscole e minuscole ed eseguite solo sui prefissi. Ad esempio, non sarà possibile cercare un profilo utilizzando le ultime lettere del suo cognome.

***Richieste di esempio***

* Richiesta di esempio per filtrare i profili in base al nome.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John&filterType=firstName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Richiesta di esempio per filtrare i profili in base al cognome.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=Miller&filterType=lastName \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Esempio di richiesta per filtrare i profili in base all’e-mail.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Richiesta di esempio per filtrare i profili in base al campo personalizzato &quot;Hobby&quot;.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```
