---
title: Recupero dei profili
description: Ulteriori informazioni su come recuperare profili con API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 19679804-f728-49fa-b26e-8f31b67c29bf
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 5%

---

# Recupero dei profili {#retrieving-profiles}

Il recupero dei profili viene eseguito con una richiesta **GET**.

Puoi quindi perfezionare la ricerca utilizzando filtri, ordini e impaginazione. Per ulteriori informazioni, consulta la sezione [Operazioni aggiuntive](../../api/using/sorting.md) .

Inoltre, le API di Campaign Standard ti consentono di cercare profili in base a uno di questi campi: e-mail, nome, cognome o qualsiasi campo personalizzato. Per ulteriori informazioni al riguardo, consulta [questa sezione](#searching-field).

<br/>

***Richieste di esempio***

* Richiesta di GET di esempio per recuperare tutti i profili.

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

* Richiesta di GET di esempio per recuperare i primi 10 valori e-mail.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/email?_lineCount=10 \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

   Risposta alla richiesta. Il nodo &quot;successivo&quot; restituisce l’URL che ti dà accesso ai 10 valori e-mail successivi.

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

Il parametro **[!UICONTROL filterType]** ti consente di recuperare profili in base a uno di questi campi: e-mail, nome, cognome o qualsiasi campo personalizzato aggiunto nel filtro avanzato durante l’estensione della risorsa profilo.

>[!NOTE]
>
>Le ricerche sono sensibili all’uso di maiuscole e minuscole ed eseguite solo sui prefissi. Ad esempio, non potrai cercare un profilo utilizzando le ultime lettere del suo cognome.

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

* Richiesta di esempio per filtrare i profili in base all’e-mail.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile/byText?text=John%40gmail.com&filterType=email \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```

* Richiesta di esempio per filtrare profili in base al campo personalizzato &quot;Hobby&quot;.

   ```
   -X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byText?cusHobby=Dancing&filterType=Hobby \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>'
   ```
