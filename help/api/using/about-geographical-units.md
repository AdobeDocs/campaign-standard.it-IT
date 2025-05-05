---
title: Informazioni sulle unità geografiche
description: Ulteriori informazioni sulle unità geografiche e sulle API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---


# Informazioni sulle unità geografiche {#about-geographical-units}

>[!CAUTION]
>
>La funzione Unità geografica è stata rimossa con la versione 18.7 di Campaign Standard.
>
>Di conseguenza, a partire dalla versione 18.7 di non sarà possibile implementare questa funzionalità né per le nuove istanze di Campaign Standard né per quelle esistenti senza unità geografiche create.
>
>Per ulteriori informazioni, consulta la pagina <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=it#">Funzioni obsolete</a>.

L&#39;endpoint **geoUnitBase** consente di interagire con le unità geografiche, ad esempio per aggiornare gli attributi o l&#39;unità di un profilo.

Il campo **Unità geografica** viene aggiunto a un profilo durante l&#39;estensione della risorsa profilo. Di conseguenza, ricorda di utilizzare sempre l&#39;endpoint **profileAndServicesExt** per interagire con le unità geografiche. Per ulteriori informazioni sull&#39;estensione della risorsa del profilo, consulta la [documentazione di Campaign](https://helpx.adobe.com/it/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).
