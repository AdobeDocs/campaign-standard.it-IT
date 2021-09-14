---
title: Informazioni sulle unità geografiche
description: Ulteriori informazioni sulle unità geografiche e sulle API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 5%

---


# Informazioni sulle unità geografiche {#about-geographical-units}

>[!CAUTION]
>
>La funzione Unità geografica è stata rimossa da Campaign Standard 18.7.
>
>Di conseguenza, non è possibile implementare questa funzionalità a partire dalla versione 18.7 per le nuove istanze di Campaign Standard e per quelle esistenti prive di unità geografiche.
>
>Per ulteriori informazioni, consulta la pagina <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=it#">Funzioni obsolete</a> .

L&#39;endpoint **geoUnitBase** consente di interagire con le unità geografiche, consentendoti, ad esempio, di aggiornare gli attributi o l&#39;unità di un profilo.

Il campo **Unità geografica** viene aggiunto a un profilo durante l’estensione della risorsa profilo. Di conseguenza, ricorda di utilizzare sempre l&#39;endpoint **profileAndServicesExt** per interagire con le unità geografiche. Per ulteriori informazioni sull’estensione della risorsa del profilo, consulta la [documentazione della campagna](https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).
