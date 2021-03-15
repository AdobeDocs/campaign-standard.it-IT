---
solution: Campaign Standard
product: campaign
title: Risorse personalizzate
description: Ulteriori informazioni sulla gestione delle risorse personalizzate con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingegnere dati
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 6%

---


# Risorse personalizzate {#custom-resources}

Adobe Campaign viene fornito con un modello dati predefinito, in cui i dati vengono definiti tramite risorse diverse. È possibile arricchire il modello dati fornito estendendo le risorse per aggiungere campi personalizzati o tabelle personalizzate, ad esempio tabelle di acquisto o di prodotti.

Le risorse personalizzate sono accessibili tramite API che utilizzano l&#39;endpoint **/profileAndServicesExt** e il nome della risorsa personalizzata.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Per le risorse non pronte all’uso, utilizza sempre il prefisso <b>&quot;cus&quot;</b> prima del nome della risorsa.

Puoi eseguire qualsiasi operazione con risorse personalizzate, purché collegate alla tabella Profilo . Ad esempio, consideriamo la struttura delle tabelle seguente:

![testo alt](assets/cusresources.png)

In tal caso, tutte le risorse delle tabelle **Transaction**, **TransactionDetails** e **Product** sono disponibili purché siano collegate alla tabella **Profile**.

<br/>

***Richiesta di esempio***

Richiesta di GET di esempio per accedere alla risorsa profileAndServicesExt estesa.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Restituisce l’elenco di tutte le risorse personalizzate collegate. Puoi quindi utilizzare gli URL delle risorse per eseguire qualsiasi attività API descritta in questa documentazione.

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```

Per ulteriori informazioni sull’estensione del modello dati, consulta la documentazione Campaign:

* [Concetti del modello dati](../../developing/using/data-model-concepts.md)
* [Estensione dell’API](../../developing/using/about-extending-the-api.md)
* [Definizione di collegamenti con altre risorse](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
