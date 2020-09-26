---
title: Guida introduttiva al modello dati di Campaign Standard
description: Arricchite il modello di dati Campaign Standard con campi e risorse personalizzati ed estendete le API REST per esporre i campi estesi.
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4ae70ca95cb282a694c41361d859b19385db5673
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 16%

---


# Guida introduttiva al modello dati di Campaign Standard {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Modello dati</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Risorse personalizzate</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Utilizzo delle API</a></p></td></tr>
</table>

Amplia il modello di dati Campaign Standard con campi e risorse personalizzate e monitora tutte le modifiche apportate al modello di dati in un&#39;unica visualizzazione.

## Modello dati {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

I dati utilizzati da Campaign sono definiti tramite risorse diverse definite in un modello **dati** predefinito. Il modello dati visualizza una struttura SQL out-of-the-box per un insieme di risorse correlate al marketing: distribuzione, pubblico, pagine di destinazione, profilo, ecc. A ogni risorsa sono associati dei filtri, che consentono di navigare tra le risorse.

Il menu **Diagnosi** consente di elencare gli oggetti tecnici generati dai Campaign Standard: schemi di dati, pagine Web, filtri, ecc., che consentono di monitorare il modello dati e qualsiasi modifica apportata.

Leggi tutto:

* [Concetti del modello dati](../../developing/using/data-model-concepts.md)
* [Best practice per i modelli di dati](../../developing/using/data-model-best-practices.md)
* [Descrizione del modello dati](../../developing/using/datamodel-introduction.md)
* [Monitoraggio delle modifiche al modello dati](../../developing/using/monitoring-data-model-changes.md)

## Risorse personalizzate {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard consente di **arricchire il modello** dati predefinito per creare risorse personalizzate (ad esempio per aggiungere tabelle Acquisto o Prodotto) o per estendere le risorse esistenti con nuovi campi. Puoi anche configurare le schermate Campagna per ottimizzare la navigazione attraverso le nuove risorse e campi che sono stati creati.

Inoltre, potete **estendere le API** REST Campaign Standard per esporre nei campi estesi delle API i profili delle risorse personalizzate. Questo consente, ad esempio, di aggiornare il profilo di un cliente con un codice promozionale generato da un sistema di fatturazione.

Leggi tutto:

* [Aggiunta o estensione di una risorsa](../../developing/using/key-steps-to-add-a-resource.md)
* [Estensione dell&#39;API](../../developing/using/about-extending-the-api.md)
* [Caso di utilizzo: Estensione della risorsa profilo con un nuovo campo](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Caso di utilizzo: Estensione delle sottoscrizioni a una risorsa applicazione](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Utilizzo delle API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Con le API Campaign Standard, crea integrazioni per  Adobe Campaign Standard e crea il tuo ecosistema personale interfacciando Campaign con il pannello di tecnologie che utilizzi. [Introduzione alle API REST Campaign Standard](../../api/using/get-started-apis.md)

## Risorse aggiuntive

* [Informazioni sul Connettore dati di Adobe Experience Platform](../../developing/using/aep-about-data-connector.md)
* [Creazione di risorse personalizzate (video)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/developing/custom-resources-develop/creating-custom-resources.html)
* [Esportazione/importazione di risorse personalizzate](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
