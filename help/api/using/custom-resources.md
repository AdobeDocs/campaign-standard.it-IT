---
title: Risorse personalizzate
description: Ulteriori informazioni sulla gestione delle risorse personalizzate con API/
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
source-git-commit: b06edadfa963881403328c4ab37d25d701bc8237

---


# Risorse personalizzate {#custom-resources}

Adobe Campaign viene fornito con un modello dati predefinito, in cui i dati vengono definiti tramite risorse diverse. È possibile arricchire il modello dati fornito estendendo le risorse per aggiungere campi personalizzati, ad esempio le tabelle di acquisto o di prodotto.

Le risorse personalizzate sono accessibili tramite API che utilizzano l'endpoint **/profileAndServicesExt** e il nome della risorsa personalizzata.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Per le risorse che non sono pronte all’uso, utilizzate sempre il prefisso <b>"cus"</b> prima del nome della risorsa.

Puoi eseguire qualsiasi operazione con risorse personalizzate, purché collegate alla tabella Profilo. Ad esempio, consideriamo la struttura delle tabelle di seguito:

![testo alt](assets/cusresources.png)

In tal caso, tutte le risorse dalle tabelle **Transazione**, **TransactionDetails** e **Product** sono disponibili purché collegate alla tabella **Profilo** .

<br/>

***Richiesta di esempio***

Esempio di richiesta GET per accedere alla risorsa profileAndServicesExt estesa.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Restituisce l'elenco di tutte le risorse personalizzate collegate. Potete quindi utilizzare gli URL delle risorse per eseguire qualsiasi attività API descritta in questa documentazione.

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

Per ulteriori informazioni sull'estensione del modello dati, consulta la documentazione Campaign:

* [Concetti del modello dati](../../developing/using/data-model-concepts.md)
* [Estensione dell'API](../../developing/using/about-extending-the-api.md)
* [Definizione di collegamenti con altre risorse](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
