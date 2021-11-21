---
title: Risorse personalizzate
description: Ulteriori informazioni sulla gestione delle risorse personalizzate con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d7b2231d-46ff-4966-9ea7-27a775e5236b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 5%

---

# Risorse personalizzate {#custom-resources}

Adobe Campaign viene fornito con un modello dati predefinito, in cui i dati vengono definiti tramite risorse diverse. È possibile arricchire il modello dati fornito estendendo le risorse per aggiungere campi personalizzati o tabelle personalizzate, ad esempio tabelle di acquisto o di prodotti.

Le risorse personalizzate sono accessibili tramite API che utilizzano **/profileAndServicesExt** e il nome della risorsa personalizzata.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Per le risorse non pronte all’uso, utilizza sempre la funzione <b>&quot;cus&quot;</b> prima del nome della risorsa.

Puoi eseguire qualsiasi operazione con risorse personalizzate, purché collegate alla tabella Profilo . Ad esempio, consideriamo la struttura delle tabelle seguente:

![testo alt](assets/cusresources.png)

In tal caso, tutte le risorse del **Transazione**, **DettagliTransazione** e **Prodotto** le tabelle sono disponibili a condizione che siano collegate **Profilo** tabella.

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
