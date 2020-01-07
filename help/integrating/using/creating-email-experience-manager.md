---
title: Creazione di un contenuto e-mail in Adobe Experience Manager.
description: Con l'integrazione di Adobe Experience Manager, puoi creare contenuti direttamente in AEM e usarli successivamente in Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1d89c8afad835810292689f4b77b0c4d6ba6a86c

---


# Creazione di un contenuto e-mail in Adobe Experience Manager {#creating-email-aem}

Questa integrazione tra Adobe Campaign Standard e Adobe Experience Manager consente di utilizzare il contenuto creato in Adobe Experience Manager nelle e-mail di Adobe Campaign.

Questo caso d’uso illustra come creare un contenuto e-mail in Adobe Experience Manager.

## Prerequisiti {#prerequisites}

Prima di iniziare, accertatevi di disporre dei seguenti elementi:

* Un’istanza di **authoring** Adobe Experience Manager
* Un’istanza di **pubblicazione** Adobe Experience Manager
* Un&#39;istanza di Adobe Campaign

## Configurazione {#configuration}

Per utilizzare insieme queste due soluzioni, è necessario configurarle in modo che si connettano tra loro.

1. Configura Adobe Campaign. Per eseguire questa operazione:

   * Configurare un account esterno di tipo Adobe Experience Manager.
   * Configura l&#39; **[!UICONTROL AEMResourceTypeFilter]**opzione, che riconosce i tipi di contenuto creati in Adobe Experience Manager per Adobe Campaign.
   * Create un modello e-mail specificando che si tratta del contenuto Adobe Experience Manager e collegate a questo modello l&#39;account esterno creato in precedenza.

1. Configurare Adobe Experience Manager. Per eseguire questa operazione:

   * Configurare la replica tra le istanze di creazione e pubblicazione di Adobe Experience Manager.
   * Connetti Adobe Experience Manager ad Adobe Campaign configurando un componente dedicato **[!UICONTROL Cloud Service]**.

## Creazione di un contenuto e-mail in Adobe Experience Manager {#use-case}

Per creare un contenuto e-mail in Adobe Experience Manager:

1. Crea un contenuto e-mail utilizzando un modello creato appositamente per Adobe Campaign.
1. Nelle proprietà del contenuto, selezionate il **[!UICONTROL Cloud Service]**corrispondente all&#39;istanza di Adobe Campaign.
1. Modificate il contenuto inserendo testo, immagini, personalizzazione ecc.
1. Convalida del contenuto.

Per ulteriori informazioni, consulta la documentazione [](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/campaign.html)dettagliata.

![](assets/aem_content.png)

Per recuperare il contenuto in Adobe Campaign:

1. Crea un messaggio e-mail basato su un modello di contenuto di tipo Adobe Experience Manager.
1. Collega un contenuto creato con Adobe Experience Manager utilizzando la schermata di definizione del contenuto dell&#39;e-mail di Adobe Campaign.

![](assets/aem_linked_content.png)

