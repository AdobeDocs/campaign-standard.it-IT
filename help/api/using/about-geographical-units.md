---
title: Informazioni sulle unità geografiche
description: Ulteriori informazioni sulle unità geografiche e sulle API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 3%

---


# Informazioni sulle unità geografiche {#about-geographical-units}

>[!CAUTION]
>
>La funzione Unità geografica è stata rimossa con la release Campaign Standard 18.7.
>
>Di conseguenza, non è possibile implementare questa funzionalità a partire dalla versione 18.7 per le nuove istanze Campaign Standard, così come per le istanze esistenti prive di unità geografiche.
>
>Per ulteriori informazioni, consulta la pagina Funzioni <a href="https://helpx.adobe.com/it/campaign/kb/acs-deprecated-and-removed-features.html"></a> obsolete.

L&#39;endpoint **geoUnitBase** consente di interagire con le unità geografiche, consentendo, ad esempio, di aggiornare gli attributi o aggiornare l&#39;unità di un profilo.

Il campo Unità **** geografica viene aggiunto a un profilo quando si estende la risorsa del profilo. Come risultato, ricordati di utilizzare sempre l&#39;endpoint **profileAndServicesExt** per interagire con le unità geografiche. Per ulteriori informazioni sull&#39;estensione delle risorse del profilo, consulta la documentazione relativa alla [campagna](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).
