---
solution: Campaign Standard
product: campaign
title: Configurazione per l’integrazione di Campaign-Experience Manager
description: Con l'integrazione Adobe Experience Manager, potete creare contenuti direttamente in AEM e usarli successivamente in  Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 3%

---


# Configurazione per l’integrazione di Campaign-Experience Manager {#configuration-aem}

Questa integrazione tra  Adobe Campaign Standard e Adobe Experience Manager consente di utilizzare il contenuto creato in Adobe Experience Manager nelle e-mail  Adobe Campaign.

In questo caso verrà illustrato come creare e gestire i contenuti delle e-mail in Adobe Experience Manager, quindi utilizzarli per le campagne di marketing importandoli nelle e-mail in  Adobe Campaign Standard.

## Prerequisiti {#prerequisites}

Prima di iniziare, accertatevi di disporre dei seguenti elementi:

* Un&#39;istanza Adobe Experience Manager **authoring**
* Un&#39;istanza di Adobe Experience Manager **publishing**
* Un&#39;istanza  Adobe Campaign

## Configurazione in  Adobe Campaign Standard {#config-acs}

Per utilizzare insieme queste due soluzioni, è necessario configurarle in modo che si connettano tra loro.
Per configurare  Adobe Campaign:

1. È innanzitutto necessario configurare l&#39;account esterno **[!UICONTROL Adobe Experience Manager instance]** in **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Configurate l&#39;account esterno di tipo Adobe Experience Manager con l&#39;URL **[!UICONTROL Server]**, **[!UICONTROL Account]** e **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Verificare che l&#39;opzione **[!UICONTROL AEMResourceTypeFilter]** sia stata configurata correttamente. Accedere al menu **[!UICONTROL Options]** in **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

1. Nel campo **[!UICONTROL Value (text)]**, verificare che la sintassi seguente sia corretta:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. Quindi, nel menu avanzato in **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**, duplicate uno dei modelli esistenti per creare un modello e-mail specifico per Adobe Experience Manager.

   ![](assets/aem_3.png)

1. Fate clic sull&#39;icona **[!UICONTROL Edit properties]**.

   ![](assets/aem_4.png)

1. Nell&#39;elenco a discesa **[!UICONTROL Content]**, selezionare **[!UICONTROL Adobe Experience Manager]** nel campo **[!UICONTROL Content source]**, quindi l&#39;account esterno creato in precedenza in **[!UICONTROL Adobe Experience Manager account]**.

È ora necessario configurare l&#39;integrazione in Adobe Experience Manager.

## Configurazione in Adobe Experience Manager {#config-aem}

Per configurare Adobe Experience Manager con  Adobe Campaign Standard, è necessario effettuare le seguenti operazioni:

1. È innanzitutto necessario configurare la replica tra le istanze di creazione e pubblicazione Adobe Experience Manager. Fare riferimento a questa sezione [](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. Connetti quindi Adobe Experience Manager a  Adobe Campaign configurando un **[!UICONTROL Cloud Service]** dedicato. Fare riferimento a questa sezione [](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. È ora necessario configurare l’esternalizzatore in Adobe Experience Manager nell’istanza di creazione. Fare riferimento a questa sezione [](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).

