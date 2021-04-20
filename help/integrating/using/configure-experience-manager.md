---
solution: Campaign Standard
product: campaign
title: Configurazione per l’integrazione di Campaign-Experience Manager
description: Con l’integrazione di Adobe Experience Manager, puoi creare contenuti direttamente in AEM e utilizzarli successivamente in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 3%

---


# Configurazione per l’integrazione di Campaign-Experience Manager {#configuration-aem}

Questa integrazione tra Adobe Campaign Standard e Adobe Experience Manager consente di utilizzare il contenuto creato in Adobe Experience Manager nelle e-mail Adobe Campaign.

Con questo caso d’uso imparerai a creare e gestire i contenuti delle e-mail in Adobe Experience Manager, quindi utilizzali per le campagne di marketing importandoli nelle e-mail in Adobe Campaign Standard.

## Prerequisiti {#prerequisites}

Assicurati di disporre in precedenza dei seguenti elementi:

* Un&#39;istanza Adobe Experience Manager **authoring**
* Un&#39;istanza Adobe Experience Manager **publishing**
* Un’istanza di Adobe Campaign

## Configurazione in Adobe Campaign Standard {#config-acs}

Per utilizzare insieme queste due soluzioni, è necessario configurarle in modo che si connettano tra loro.
Per configurare Adobe Campaign:

1. Devi innanzitutto configurare l’account esterno **[!UICONTROL Adobe Experience Manager instance]** in **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Configura l&#39;account esterno di tipo Adobe Experience Manager con l&#39;URL **[!UICONTROL Server]**, **[!UICONTROL Account]** e **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Verifica che l&#39;opzione **[!UICONTROL AEMResourceTypeFilter]** sia stata configurata correttamente. Accedi al menu **[!UICONTROL Options]** nel menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** .

1. Nel campo **[!UICONTROL Value (text)]** , verifica che la sintassi seguente sia corretta:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. Quindi, nel menu avanzato in **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**, duplica uno dei modelli esistenti per creare un modello e-mail specifico per Adobe Experience Manager.

   ![](assets/aem_3.png)

1. Fai clic sull&#39;icona **[!UICONTROL Edit properties]** .

   ![](assets/aem_4.png)

1. Nel menu a discesa **[!UICONTROL Content]** , seleziona **[!UICONTROL Adobe Experience Manager]** nel campo **[!UICONTROL Content source]** , quindi fai clic sull’account esterno creato in precedenza in **[!UICONTROL Adobe Experience Manager account]**.

Ora devi configurare l’integrazione in Adobe Experience Manager.

## Configurazione in Adobe Experience Manager {#config-aem}

Per configurare Adobe Experience Manager con Adobe Campaign Standard, segui questi passaggi:

1. È innanzitutto necessario configurare la replica tra le istanze di authoring e pubblicazione di Adobe Experience Manager. Fare riferimento a questa sezione [sezione](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. Quindi, connetti Adobe Experience Manager ad Adobe Campaign configurando un **[!UICONTROL Cloud Service]** dedicato. Fare riferimento a questa sezione [sezione](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. Ora devi configurare l’esternalizzatore in Adobe Experience Manager sull’istanza di authoring. Fare riferimento a questa sezione [sezione](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).

