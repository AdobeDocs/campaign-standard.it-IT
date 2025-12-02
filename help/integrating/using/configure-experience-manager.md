---
title: Configurazione dell’integrazione di Campaign ed Experience Manager
description: Con l’integrazione di Adobe Experience Manager, puoi creare contenuti direttamente in AEM e utilizzarli successivamente in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: f56f5a19-6283-4eef-8127-c69a16a42a37
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 7%

---

# Configurazione dell’integrazione di Campaign ed Experience Manager {#configuration-aem}

Questa integrazione tra Adobe Campaign Standard e Adobe Experience Manager consente di utilizzare i contenuti creati in Adobe Experience Manager nelle e-mail di Adobe Campaign.

Con questo caso d’uso imparerai a creare e gestire i contenuti delle e-mail in Adobe Experience Manager, per poi utilizzarli per le campagne di marketing importandoli nelle e-mail in Adobe Campaign Standard.

## Prerequisiti {#prerequisites}

Prima di procedere, accertati di disporre dei seguenti elementi:

* Un&#39;istanza di **authoring** di Adobe Experience Manager
* Un&#39;istanza **publishing** di Adobe Experience Manager
* Un’istanza di Adobe Campaign

## Configurazione in Adobe Campaign Standard {#config-acs}

Per utilizzare insieme queste due soluzioni, è necessario configurarle per connettersi tra loro.
Per configurare Adobe Campaign:

1. Devi innanzitutto configurare l&#39;account esterno **[!UICONTROL Adobe Experience Manager instance]** in **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Configurare l&#39;account esterno del tipo Adobe Experience Manager con l&#39;URL **[!UICONTROL Server]**, **[!UICONTROL Account]** e **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Verificare che l&#39;opzione **[!UICONTROL AEMResourceTypeFilter]** sia stata configurata correttamente. Accedere al menu **[!UICONTROL Options]** nel menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

1. Nel campo **[!UICONTROL Value (text)]**, verificare che la sintassi seguente sia corretta:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. Quindi, nel menu avanzato in **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**, duplica uno dei modelli esistenti per creare un modello e-mail specifico per Adobe Experience Manager.

   ![](assets/aem_3.png)

1. Fare clic sull&#39;icona **[!UICONTROL Edit properties]**.

   ![](assets/aem_4.png)

1. Nel menu a discesa **[!UICONTROL Content]**, seleziona **[!UICONTROL Adobe Experience Manager]** nel campo **[!UICONTROL Content source]**, quindi l&#39;account esterno creato in precedenza in **[!UICONTROL Adobe Experience Manager account]**.

Ora devi configurare l’integrazione in Adobe Experience Manager.

## Configurazione in Adobe Experience Manager {#config-aem}

Per configurare Adobe Experience Manager con Adobe Campaign Standard, devi seguire questi passaggi:

1. Devi innanzitutto configurare la replica tra le istanze di authoring e pubblicazione di Adobe Experience Manager. Consulta questa [sezione](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. Quindi, connetti Adobe Experience Manager ad Adobe Campaign configurando un **[!UICONTROL Cloud Service]** dedicato. Consulta questa [sezione](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. Ora devi configurare Externalizer in Adobe Experience Manager nell’istanza Autore. Consulta questa [sezione](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).
