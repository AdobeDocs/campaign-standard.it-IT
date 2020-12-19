---
solution: Campaign Standard
product: campaign
title: Informazioni sulle unità geografiche
description: Ulteriori informazioni sulle unità geografiche e sulle API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: ad7322905c69f9575e11efc9d8f68cf909dc425f
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 5%

---


# Informazioni sulle unità geografiche {#about-geographical-units}

>[!CAUTION]
>
>La funzione Unità geografica è stata rimossa con la release Campaign Standard 18.7.
>
>Di conseguenza, non è possibile implementare questa funzionalità a partire dalla versione 18.7 per le nuove istanze Campaign Standard, così come per le istanze esistenti prive di unità geografiche.
>
>Per ulteriori informazioni, consultare la pagina <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=it#">Funzioni obsolete</a>.

L&#39;endpoint **geoUnitBase** consente di interagire con le unità geografiche, consentendo, ad esempio, di aggiornare gli attributi o aggiornare l&#39;unità di un profilo.

Il campo **Unità geografica** viene aggiunto a un profilo quando si estende la risorsa del profilo. Di conseguenza, ricordare di utilizzare sempre l&#39;endpoint **profileAndServicesExt** per interagire con le unità geografiche. Per ulteriori informazioni sull&#39;estensione delle risorse del profilo, fare riferimento alla [Documentazione campagna](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).
