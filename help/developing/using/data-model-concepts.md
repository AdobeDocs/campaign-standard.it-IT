---
title: Concetti del modello dati
description: Scopri il modello dati di Adobe Campaign e come modificarlo.
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 71ee939b6ef256be8c693ec6e15d9609c7e80677

---


# Concetti del modello dati{#data-model-concepts}

Adobe Campaign viene fornito con un modello dati predefinito. Questo modello di dati può essere modificato dagli [amministratori](../../administration/using/users-management.md#functional-administrators) che possono aggiungere nuove risorse o estensioni alle risorse esistenti.

>[!CAUTION]
>
>La creazione e la modifica di risorse sono operazioni sensibili che devono essere eseguite solo da utenti esperti.

Il menu **[!UICONTROL Administration]** &gt;, accessibile tramite il logo Adobe Campaign, consente di gestire le risorse **[!UICONTROL Development]** **personalizzate,** pubblicarle **e** accedere agli strumenti **** diagnostici.

I dati utilizzati da Adobe Campaign sono definiti tramite risorse diverse. È possibile **arricchire il modello** di dati fornito creando risorse personalizzate, ad esempio tabelle di acquisto o di prodotti.

Le risorse pronte all'uso (come campagne, e-mail o audience) non possono essere modificate. Tuttavia, è possibile estendere le risorse personalizzate per aggiungere nuovi campi.

I campi di estensione vengono generati con un prefisso in modo che non entrino mai in conflitto con i campi forniti.

>[!NOTE]
>
>Puoi trovare una rappresentazione del modello di dati per le risorse pronte all’uso [qui](https://docs.campaign.adobe.com/doc/standard/en/datamodel/datamodel.html).

Potete anche **configurare la navigazione** nelle schermate corrispondenti alla risorsa creata.

È possibile **esportare e importare** risorse personalizzate, ad esempio da uno sviluppo a un ambiente di produzione. Per ulteriori informazioni, consulta questo caso [di utilizzo](../../automating/using/exporting-importing-custom-resources.md)passo.
