---
title: Paginazione
description: Scoprite come eseguire le operazioni di impaginazione.
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


# Paginazione

Per impostazione predefinita, in un elenco vengono caricate 25 risorse.

Il parametro **_lineCount** consente di limitare il numero di risorse elencate nella risposta.  È quindi possibile utilizzare il nodo **successivo** per visualizzare i risultati successivi.

>[!NOTE]&gt;
>
>Utilizzare sempre il valore URL restituito nel nodo **successivo** per eseguire una richiesta di impaginazione.
>
>La richiesta **_lineStart** viene calcolata e deve essere sempre utilizzata all’interno dell’URL restituito nel nodo **successivo** .

<!-- serverside pagination. quand table très longue (au delà de 100.000), on peut plus faire de next. doit utiliser à la place les trucs type lineStart etc. si false: voudra dirre que ça a atteint la limite-->

<br/>

***Richiesta di esempio***

Esempio di richiesta GET per visualizzare 1 record della risorsa profilo.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile?_lineCount=1 \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

<!-- dans l'exemple, avoir le node "next"-->

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
        }
    ],
    ...
}
```
