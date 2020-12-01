---
solution: Campaign Standard
product: campaign
title: Guida introduttiva al modello dati di Campaign Standard
description: Arricchisci il modello di dati di Campaign Standard con campi e risorse personalizzati ed estendi le API REST per esporre i campi estesi.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 30%

---


# Guida introduttiva al modello dati di Campaign Standard {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Modello dati</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Risorse personalizzate</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Utilizzo delle API</a></p></td></tr>
</table>

Amplia il modello dati Campaign Standard con campi e risorse personalizzate e monitora tutte le modifiche apportate al modello dati in un’unica schermata.

## Modello dati {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

I dati utilizzati da Campaign sono definiti tramite risorse diverse definite in un **modello dati predefinito**. Il modello dati visualizza una struttura SQL out-of-the-box per un insieme di risorse correlate al marketing: distribuzione, pubblico, pagine di destinazione, profilo, ecc. A ogni risorsa sono associati dei filtri, che consentono di navigare tra le risorse.

Il menu **Diagnosi** consente di elencare gli oggetti tecnici generati dal Campaign Standard: schemi di dati, pagine Web, filtri, ecc., che consentono di monitorare il modello dati e qualsiasi modifica apportata.

Leggi tutto:

* [Concetti del modello dati](../../developing/using/data-model-concepts.md)
* [Best practice per i modelli di dati](../../developing/using/data-model-best-practices.md)
* [Descrizione del modello dati](../../developing/using/datamodel-introduction.md)
* [Monitoraggio delle modifiche al modello dati](../../developing/using/monitoring-data-model-changes.md)

## Risorse personalizzate {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard consente di **arricchire il modello dati predefinito** per creare risorse personalizzate (ad esempio per aggiungere tabelle Acquisto o Prodotto) o per estendere le risorse esistenti con nuovi campi. Puoi anche configurare le schermate Campagna per ottimizzare la navigazione attraverso le nuove risorse e campi che sono stati creati.

Inoltre, potete **estendere le API REST Campaign Standard** per esporre nei campi estesi delle API i profili delle risorse personalizzate. Questo consente, ad esempio, di aggiornare il profilo di un cliente con un codice promozionale generato da un sistema di fatturazione.

Leggi tutto:

* [Aggiunta o estensione di una risorsa](../../developing/using/key-steps-to-add-a-resource.md)
* [Estensione dell&#39;API](../../developing/using/about-extending-the-api.md)
* [Caso di utilizzo: Estensione della risorsa profilo con un nuovo campo](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Caso di utilizzo: Estensione delle sottoscrizioni a una risorsa applicazione](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Operazioni con le API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Con le API Campaign Standard, crea integrazioni per  Adobe Campaign Standard e crea il tuo ecosistema personale interfacciando Campaign con il pannello di tecnologie che utilizzi. [Guida introduttiva alle API REST di Campaign Standard](../../api/using/get-started-apis.md)

## Risorse aggiuntive

* [Informazioni sul Connettore dati di Adobe Experience Platform](../../developing/using/aep-about-data-connector.md)
* [Esportazione/importazione di risorse personalizzate](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
