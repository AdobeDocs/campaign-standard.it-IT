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
TQID: https://experienceleague.adobe.com/LHlfIZ24iApQfr6dL-x-nQViltSetibBgt1slLDsRi4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2: id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 348
ht-degree: 22%

---

# Introduzione al modello dati di Campaign Standard {#get-started-data-model}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_datamodel.svg" width="60px"><p><a href="#data-model">Modello dati</a></p></td>
<td><img src="assets/do-not-localize/icon_custom.svg" width="60px"><p><a href="#custom-resources">Risorse personalizzate</a></p></td><td><img src="assets/do-not-localize/icon_api.svg" width="60px"><p><a href="#custom-resources">Utilizzare le API</a></p></td></tr>
</table>

Amplia il modello dati di Campaign Standard con campi e risorse personalizzate e monitora tutte le modifiche apportate al modello dati in un’unica schermata.

## Modello dati {#data-model}

<img src="assets/do-not-localize/icon_datamodel.svg" width="60px">

I dati utilizzati da Campaign sono definiti tramite risorse diverse definite in un **modello dati predefinito**. Il modello dati visualizza una struttura SQL predefinita per un set di risorse correlate al marketing: consegna, pubblico, pagine di destinazione, profilo e così via. A ogni risorsa sono associati dei filtri che ti consentono di navigare tra le diverse risorse.

Il menu **Diagnosi** ti consente di elencare gli oggetti tecnici generati da Campaign Standard: schemi di dati, pagine Web, filtri, ecc., consentendo di monitorare il modello di dati e qualsiasi modifica apportata allo stesso.

Ulteriori informazioni:

* [Concetti del modello dati](../../developing/using/data-model-concepts.md)
* [Best practice per i modelli di dati](../../developing/using/data-model-best-practices.md)
* [Descrizione del modello dati](../../developing/using/datamodel-introduction.md)
* [Monitoraggio delle modifiche al modello dati](../../developing/using/monitoring-data-model-changes.md)

## Risorse personalizzate {#custom-resources}

<img src="assets/do-not-localize/icon_custom.svg" width="60px">

Campaign Standard ti consente di **Arricchire il modello dati predefinito** per creare risorse personalizzate (ad esempio per aggiungere tabelle Acquisti o Prodotti) o per estendere le risorse esistenti con nuovi campi. Puoi anche configurare le schermate di Campaign per ottimizzare la navigazione attraverso le nuove risorse e i nuovi campi creati.

Inoltre, puoi **estendere le API REST di Campaign Standard** per esporre nei campi estesi delle API i profili delle risorse personalizzate. Ciò ti consente, ad esempio, di aggiornare il profilo di un cliente con un codice promozionale generato da un sistema di fatturazione.

Ulteriori informazioni:

* [Aggiunta o estensione di una risorsa](../../developing/using/key-steps-to-add-a-resource.md)
* [Estensione dell’API](../../developing/using/about-extending-the-api.md)
* [Caso d’uso: estensione della risorsa profilo con un nuovo campo](../../developing/using/extending-the-profile-resource-with-a-new-field.md)
* [Caso di utilizzo: estensione delle sottoscrizioni a una risorsa dell’applicazione](../../developing/using/extending-the-subscriptions-to-an-application-resource.md)

## Utilizzare le API {#apis}

<img src="assets/do-not-localize/icon_api.svg" width="60px">

Con le API di Campaign Standard, crea integrazioni per Adobe Campaign Standard e crea il tuo ecosistema interfacciando Campaign con il pannello di tecnologie che utilizzi. [Guida introduttiva alle API REST di Campaign Standard](../../api/using/get-started-apis.md)

## Risorse aggiuntive

* [Esportazione/importazione di risorse personalizzate](https://helpx.adobe.com/campaign/kb/acs-get-started-with-cusres.html)
* [Esportare dati da Campaign ad Adobe Experience Platform](../../integrating/using/export-campaign-data.md)
