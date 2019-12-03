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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Informazioni sulle unità geografiche {#about-geographical-units}

>[!CAUTION]
>
>La funzione Unità geografica è stata rimossa con la release Campaign Standard 18.7.
Di conseguenza, le nuove istanze di Campaign Standard, così come quelle esistenti senza unità geografiche create, non possono implementare questa funzionalità a partire dalla versione 18.7.
Per ulteriori informazioni, consultare la pagina Funzioni <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html"></a> obsolete.

L'endpoint **geoUnitBase** consente di interagire con le unità geografiche, consentendo, ad esempio, di aggiornare gli attributi o aggiornare l'unità di un profilo.

Il campo Unità **** geografica viene aggiunto a un profilo quando si estende la risorsa del profilo. Come risultato, ricordati di utilizzare sempre l'endpoint **profileAndServicesExt** per interagire con le unità geografiche. Per ulteriori informazioni sull'estensione delle risorse del profilo, consulta la documentazione relativa alla [campagna](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).
