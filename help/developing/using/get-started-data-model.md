---
title: Introduzione al modello dati di Campaign Standard
description: Arricchisci il modello di dati di Campaign Standard con campi e risorse personalizzati ed estendi le API REST per esporre i campi estesi.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Data Model
role: Developer
level: Intermediate
exl-id: a8d15053-c20f-4334-a732-3b36cb00794d
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 31%

---

# Introduzione al modello dati di Campaign Standard {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Modello dati</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Risorse personalizzate</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Utilizzare le API</a></p></td></tr>
</table>

Amplia il modello dati Campaign Standard con campi e risorse personalizzate e monitora tutte le modifiche apportate al modello dati in un’unica schermata.

## Modello dati {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

I dati utilizzati da Campaign sono definiti tramite risorse diverse definite in un **modello dati predefinito**. Il modello dati visualizza una struttura SQL preconfigurata per un set di risorse correlate al marketing: consegna, pubblico, pagine di destinazione, profilo, ecc. A ciascuna risorsa sono associati dei filtri che consentono di navigare tra le varie risorse.

Il menu **Diagnosi** consente di elencare gli oggetti tecnici generati da Campaign Standard: schemi di dati, pagine web, filtri, ecc., che consentono di monitorare il modello dati ed eventuali modifiche apportate al modello.

Leggi tutto:

* [Concetti del modello dati](../../developing/using/data-model-concepts.md)
* [Best practice per i modelli di dati](../../developing/using/data-model-best-practices.md)
* [Descrizione del modello dati](../../developing/using/datamodel-introduction.md)
* [Monitoraggio delle modifiche al modello dati](../../developing/using/monitoring-data-model-changes.md)

## Risorse personalizzate {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard consente di **arricchire il modello dati predefinito** per creare risorse personalizzate (ad esempio per aggiungere tabelle Acquisto o Prodotto) o per estendere le risorse esistenti con nuovi campi. Puoi anche configurare le schermate di Campaign per ottimizzare la navigazione tramite le nuove risorse e i nuovi campi creati.

Inoltre, puoi **estendere le API REST di Campaign Standard** per esporre nei campi estesi delle API le risorse personalizzate Profili. Questo ti consente, ad esempio, di aggiornare il profilo di un cliente con un codice promozionale generato da un sistema di fatturazione.

Leggi tutto:

* [Aggiunta o estensione di una risorsa](../../developing/using/key-steps-to-add-a-resource.md)
* [Estensione dell’API](../../developing/using/about-extending-the-api.md)
* [Caso di utilizzo: Estensione della risorsa profilo con un nuovo campo](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Caso di utilizzo: Estensione degli abbonamenti a una risorsa dell’applicazione](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Utilizzare le API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Con le API di Campaign Standard, crea integrazioni per Adobe Campaign Standard e crea il tuo ecosistema interfacciando Campaign con il pannello di tecnologie che utilizzi. [Guida introduttiva alle API REST di Campaign Standard](../../api/using/get-started-apis.md)

## Risorse aggiuntive

* [Esportazione/importazione di risorse personalizzate](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
* [Esportare dati da Campaign ad Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
