---
title: Concetti del modello dati
seo-title: Concetti del modello dati
description: Concetti del modello dati
seo-description: Scopri il modello dati Adobe Campaign e come modificarlo.
page-status-flag: never-activated
uuid: cacd 563 f -6936-4 b 3 e -83 e 3-5 d 4 ae 31 d 44 e 8
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: sviluppo
content-type: riferimento
topic-tags: about-custom-resources
discoiquuid: 4 e 0468 da -3052-4 ce 5-8174-45 aba 1 f 5 c 4 ed
context-tags: Cusresource, overview; Eventcusresource, overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c880b265cf83cb76b2cdbe3cbdd77182adb71bb1

---


# Data model concepts{#data-model-concepts}

Adobe Campaign viene fornito con un modello dati predefinito. This data model can be modified by [administrators](../../administration/using/types-of-users.md#functional-administrators) who are able to add new resources or extensions to existing resources.

>[!CAUTION]
>
>La creazione e la modifica delle risorse sono operazioni sensibili che devono essere eseguite solo dagli utenti esperti.

The **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** menu, accessed via the Adobe Campaign logo, allows you to manage your **custom resources**, **publish** them, and **access the diagnostic tools**.

I dati utilizzati da Adobe Campaign sono definiti tramite risorse diverse.

You can **enrich the data template** that is provided by creating your own custom resources, such as purchase or product tables.

Le risorse integrate (come campagne, e-mail o audience) non possono essere modificate. Tuttavia, le risorse personalizzate possono essere estese per aggiungere nuovi campi.

>[!NOTE]
>
>You can find a datamodel representation for the out-of-the-box resources [here](https://docs.campaign.adobe.com/doc/standard/en/datamodel/datamodel.html).

You can also **configure the navigation** in the screens corresponding to the resource created.

I campi dell'estensione vengono generati con un prefisso in modo che non siano mai in conflitto con i campi inclusi.
