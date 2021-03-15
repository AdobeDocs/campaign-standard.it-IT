---
solution: Campaign Standard
product: campaign
title: Interazione con lo storico dei dati marketing
description: Scopri come interagire con la cronologia di marketing dei profili.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 10%

---


# Interazione con lo storico dei dati marketing {#interacting-with-marketing-history}

L’endpoint **history** consente di interagire con la cronologia di marketing di un profilo.
In questo modo, ad esempio, puoi recuperare facilmente la pagina speculare per una consegna inviata a un profilo. Per farlo, segui la procedura indicata di seguito:

1. Esegui una GET con l&#39;endpoint **history** e la chiave primaria del profilo.
1. Esegui una richiesta di GET sul **eventi** href restituito.
1. Restituisce l&#39;elenco degli eventi per il profilo con collegamenti alle pagine mirror nel nodo **mirrorPage** .

<br/>

***Richiesta di esempio***

Recupera la cronologia di marketing del profilo con una richiesta GET.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/"<PKEY>" \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Il nodo &quot;eventi&quot; restituisce l’URL che ti dà accesso agli eventi sul profilo.

```
{
  "PKey": "<PKEY>",
  "firstName": "John",
  "lastName":"Doe",
  "birthDate": "1980-10-24",
  "events": {
    "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/",
    "metadata": "subHisto"
    },
}
```

Esegui una richiesta GET sul href degli eventi restituiti.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Restituisce l&#39;elenco degli eventi per il profilo con i collegamenti alle pagine mirror nel nodo &quot;mirrorPage&quot;.

```
    {
      "PKey": "<PKEY>",
      "category": "email",
      "date": "2018-05-17 08:44:49.366Z",
      "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>",
      "label": "Send via email",
      "mirrorPage": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/history/<PKEY>/events/<PKEY>/mirrorPage/"
      },
      "type": "outbound"
    }
```
