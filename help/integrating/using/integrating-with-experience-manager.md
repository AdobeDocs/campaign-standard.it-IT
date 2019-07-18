---
title: Integrazione con Experience Manager
seo-title: Integrazione con Experience Manager
description: Integrazione con Experience Manager
seo-description: Con l'integrazione di Adobe Experience Manager, puoi creare contenuti direttamente in AEM e utilizzarli in Adobe Campaign.
page-status-flag: never-activated
uuid: ed 6 c 1 b 76-87 f 7-4 d 23-b 5 e 2-0765297 a 905 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6 c 0 c 3 c 5 b-b 596-459 e -87 dd-a 06 bb 7 d 633 d 2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Integrating with Experience Manager{#integrating-with-experience-manager}

Questa integrazione tra Adobe Campaign Standard e Adobe Experience Manager consente di utilizzare i contenuti creati in Adobe Experience Manager nelle e-mail di Adobe Campaign.

Puoi quindi sfruttare al massimo le funzionalità di modifica dei contenuti di Adobe Experience Manager e le funzionalità di consegna e gestione dati di Adobe Campaign.

>[!NOTE]
>
>Non è possibile eseguire test A/B per i contenuti importati da Adobe Experience Manager.

Adobe Campaign Standard è compatibile con Adobe Experience Manager 6.1, 6.2, 6.3 e 6.4. Le sezioni seguenti presentano una panoramica delle azioni che è possibile eseguire. For more information, refer to the sections dedicated to [configuration](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html) and the [use](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/campaign.html) of the integration.

## Prerequisites {#prerequisites}

Assicuratevi di disporre dei seguenti elementi in anticipo:

* An Adobe Experience Manager **authoring** instance
* An Adobe Experience Manager **publishing** instance
* Un'istanza di Adobe Campaign

## Use case {#use-case}

Per creare un contenuto e-mail in Adobe Experience Manager:

1. Crea un contenuto e-mail utilizzando un modello creato specificamente per Adobe Campaign.
1. In the content properties, select the **[!UICONTROL Cloud Service]** corresponding to your Adobe Campaign instance.
1. Modificate il contenuto inserendo testo, immagini, personalizzazioni ecc.
1. Convalidare il contenuto.

For more information, refer to the [detailed documentation](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/campaign.html).

![](assets/aem_content.png)

Per recuperare il contenuto in Adobe Campaign:

1. Crea un'e-mail basata su un modello di contenuto tipo di Adobe Experience Manager.
1. Collega un contenuto creato con Adobe Experience Manager mediante la schermata di definizione del contenuto e-mail di Adobe Campaign.

![](assets/aem_linked_content.png)

## Configuration {#configuration}

Per usare queste due soluzioni insieme, devi configurarle per connetterti tra loro.

1. Configura Adobe Campaign. A tal fine:

   * Configurate un account esterno di Adobe Experience Manager.
   * Configure the **AEMResourceTypeFilter** option, which recognizes the content types created in Adobe Experience Manager for Adobe Campaign.
   * Create un modello e-mail specificando come contenuto Adobe Experience Manager e collegate l'account esterno creato in precedenza a questo modello.

1. Configurare Adobe Experience Manager. A tal fine:

   * Configurate la replica tra le istanze di authoring e pubblicazione di Adobe Experience Manager.
   * Connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**.

