---
title: Configurazione dell'integrazione Campaign-Experience Manager
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
source-git-commit: 37b1c17234a300b092db3c810a32de3600bb8f2f

---


# Configurazione dell&#39;integrazione Campaign-Experience Manager {#configuration-aem}

Questa integrazione tra Adobe Campaign Standard e Adobe Experience Manager consente di utilizzare il contenuto creato in Adobe Experience Manager nelle e-mail di Adobe Campaign.

In questo caso verrà illustrato come creare e gestire il contenuto delle e-mail in Adobe Experience Manager, quindi utilizzarlo per le campagne di marketing importandolo nelle e-mail in Adobe Campaign Standard.

## Prerequisiti {#prerequisites}

Prima di iniziare, accertatevi di disporre dei seguenti elementi:

* Un’istanza di **authoring** Adobe Experience Manager
* Un’istanza di **pubblicazione** Adobe Experience Manager
* Un&#39;istanza di Adobe Campaign

## Configurazione in Adobe Campaign Standard {#config-acs}

Per utilizzare insieme queste due soluzioni, è necessario configurarle in modo che si connettano tra loro.
Per configurare Adobe Campaign:

1. È innanzitutto necessario configurare l&#39;account **[!UICONTROL Adobe Experience Manager instance]** esterno in **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts menu]**.

1. Configura l’account esterno di tipo Adobe Experience Manager con il tuo **[!UICONTROL Server]** URL **[!UICONTROL Account]** e **[!UICONTROL Password]**.

   ![](assets/aem_1.png)

1. Verificate che l&#39; **[!UICONTROL AEMResourceTypeFilter]** opzione sia stata configurata correttamente. Accedete al **[!UICONTROL Options]** menu in **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** menu.

1. Nel **[!UICONTROL Value (text)]** campo, verificare che la sintassi seguente sia corretta:

   ```
   mcm/campaign/components/newsletter,mcm/campaign/components/campaign_newsletterpage,mcm/neolane/components/newsletter
   ```

   ![](assets/aem_2.png)

1. Quindi, nel menu avanzato in **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**, duplicate uno dei modelli esistenti per creare un modello e-mail specifico per Adobe Experience Manager.

   ![](assets/aem_3.png)

1. Fate clic sull&#39; **[!UICONTROL Edit properties]** icona.

   ![](assets/aem_4.png)

1. Nell&#39; **[!UICONTROL Content]** elenco a discesa, seleziona **[!UICONTROL Adobe Experience Manager]** nel **[!UICONTROL Content source]** campo l&#39;account esterno creato in precedenza nell&#39; **[!UICONTROL Adobe Experience Manager account]**.

È ora necessario configurare l&#39;integrazione in Adobe Experience Manager.

## Configurazione in Adobe Experience Manager {#config-aem}

Per configurare Adobe Experience Manager con Adobe Campaign Standard, devi effettuare le seguenti operazioni:

1. È innanzitutto necessario configurare la replica tra le istanze di creazione e pubblicazione di Adobe Experience Manager. Fare riferimento a questa [sezione](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-adobe-experience-manager).

1. Connetti quindi Adobe Experience Manager ad Adobe Campaign configurando un&#39;app dedicata **[!UICONTROL Cloud Service]**. Fare riferimento a questa [sezione](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#connecting-aem-to-adobe-campaign).

1. È ora necessario configurare l’esternalizzatore in Adobe Experience Manager nell’istanza di creazione. Fare riferimento a questa [sezione](https://docs.adobe.com/content/help/en/experience-manager-65/administering/integration/campaignstandard.html#configuring-the-externalizer).

