---
title: Provisioning e configurazione dell'integrazione con Audience Manager o con il servizio di base Persone
seo-title: Provisioning e configurazione dell'integrazione con Audience Manager o con il servizio di base Persone
description: Provisioning e configurazione dell'integrazione con Audience Manager o con il servizio di base Persone
seo-description: 'Scopri come configurare l''integrazione del servizio di base Audience Manager/Persone per iniziare a condividere audience o segmenti con le diverse soluzioni Adobe Experience Cloud. '
page-status-flag: never-activated
uuid: e 7329644-0033-4729-b 4 a 7-61 bef 137 f 4 b 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: eb 24 f 4 ea -325 f -433 a -91 a 0-c 45906320 bcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Provisioning and configuring integration with Audience Manager or People core service{#provisioning-and-configuring-integration-with-audience-manager-or-people-core-service}

The provisioning and configuring of Audience Manager and People core in Adobe Campaign take two steps: [Submitting request to Adobe](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#submitting-request-to-adobe) then [Configuring the integration in Adobe Campaign](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#configuring-the-integration-in-adobe-campaign).

## Submitting request to Adobe {#submitting-request-to-adobe}

L'integrazione di Audience Manager (AAM) o di servizi di base Persone consente di importare ed esportare audience o segmenti in Adobe Campaign.

Questa integrazione deve essere configurata prima. To request provisioning of this integration, write an email to [Digital-Request@adobe.com](mailto:Digital-Request@adobe.com) with the following information:

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Tipo di richiesta:</strong><br /> </td> 
   <td> Configurare l'integrazione con il servizio core AAM/Persone </td> 
  </tr> 
  <tr> 
   <td> <strong>Nome organizzazione:</strong><br /> </td> 
   <td> Nome organizzazione </td> 
  </tr> 
  <tr> 
   <td> <strong>ID organizzazione IMS</strong><br /> </td> 
   <td> ID organizzazione IMS * </td> 
  </tr> 
  <tr> 
   <td> <strong>Ambiente:</strong><br /> </td> 
   <td> Esempio: Produzione </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM o Servizio Persone</strong><br /> </td> 
   <td> Esempio: Adobe Audience Manager </td> 
  </tr> 
  <tr> 
   <td> <strong>ID dichiarato o ID visitatore</strong><br /> </td> 
   <td> Esempio: ID dichiarato </td> 
  </tr> 
  <tr> 
   <td> <strong>Informazioni aggiuntive</strong><br /> </td> 
   <td> Eventuali informazioni o commenti utili </td> 
  </tr> 
 </tbody> 
</table>

* You can find your IMS Org ID on the Experience Cloud, in the **Administration** menu. Viene fornito anche quando si stabilisce la prima connessione ad Adobe Experience Cloud.

## Configuring the integration in Adobe Campaign {#configuring-the-integration-in-adobe-campaign}

Dopo aver inviato questa richiesta, Adobe passa al provisioning dell'integrazione e ti contatterà per fornire dettagli e informazioni su come finalizzare la configurazione:

* [Passaggio 1: Configurare o controllare gli account esterni in Adobe Campaign](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Passaggio 2: Configurare le origini dati](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources)
* [Passaggio 3: Configurare il server di tracciamento campagna](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-3--configure-campaign-tracking-server)
* [Passaggio 4: Configurare il servizio ID visitatori](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md#step-4--configure-the-visitor-id-service)

### Step 1: Configure or check the external accounts in Adobe Campaign {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Per prima cosa è necessario configurare o controllare gli account esterni in Adobe Campaign. Questi account dovrebbero essere stati configurati da Adobe e dovrebbero essere state comunicate le informazioni necessarie.

A tal fine:

1. From the advanced menu, select **Administration &gt; Application settings &gt; External accounts**.

   Selezionate uno dei seguenti account esterni disponibili per questa integrazione:

   ![](assets/integration_aam_1.png)

1. Enter **[!UICONTROL Receiver server]** in following format
1. Enter the **[!UICONTROL AWS Access Key ID]**, **[!UICONTROL Secret Access Key]** and **[!UICONTROL AWS Region]**.

Gli account esterni sono ora configurati per questa integrazione.

### Step 2: Configure the Data Sources {#step-2--configure-the-data-sources}

Le due seguenti origini dati vengono create all'interno di Audience Manager: Adobe Campaign (MID) e Adobe Campaign (declaredid). Allo stesso tempo, queste due origini dati sono disponibili in Adobe Campaign:

* **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**: Si tratta di un'origine dati out-of-the-box configurata per impostazione predefinita per l'ID visitatore. I segmenti creati da Campaign saranno parte di questa origine dati.
* **Origine dati ID** dichiarata: Questa origine dati deve essere creata e mappata con la **[!UICONTROL DeclaredId]** definizione dell'origine dati da Audience Manager.

Nel caso di più siti Web con domini diversi, Adobe Campaign non supporta la riconciliazione basata su ECID.

To configure the **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]** data source:

1. In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, select **[!UICONTROL Recipient - Visitor ID (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Choose **[!UICONTROL Adobe Campaign]** in the **[!UICONTROL Data Source/ Alias]** drop-down.
1. Enter the **[!UICONTROL AAM Destination ID]** provided by Adobe.

   ![](assets/integration_aam_3.png)

1. In the **[!UICONTROL Reconciliation process]** category, we advise you not to change the reconciliation criteria and always use the **[!UICONTROL Visitor ID]**.
1. Click **[!UICONTROL Save]**.

To create the **[!UICONTROL Declared ID]** data source:

1. In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, click the **[!UICONTROL Create]** button.
1. Edit the **[!UICONTROL Label]** of your data source.
1. In the **[!UICONTROL Data Source/ Alias]** drop-down, choose the Data Source corresponding to the **[!UICONTROL DeclaredID]** data source from Audience Manager.
1. Configure your data source by entering the **[!UICONTROL Data Source / Alias]** and **[!UICONTROL AAM Destination ID]** provided by Adobe.
1. Set the **[!UICONTROL Reconciliation process]** as needed.
1. Click **[!UICONTROL Save]**.

>[!NOTE]
>
>The **[!UICONTROL AAM Destination ID]** field is not required if you are configuring the shared data source for the [Campaign-Triggers integration](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL Priority]** è necessario solo per la configurazione degli attivatori - Integrazione campagna. Priority determina quale origine dati verrà configurata per primo. La priorità può essere un numero qualsiasi, ad esempio 1 o 100. Più alta è la priorità, maggiore è la preferenza durante la riconciliazione.

### Step 3: Configure Campaign Tracking server {#step-3--configure-campaign-tracking-server}

Per la configurazione dell'integrazione con il servizio di base Persone o Audience Manager, è necessario configurare anche il server Tracciamento campagna.

Qui, devi accertarti che il server di tracciamento campagna sia registrato sul dominio (CNAME). You can find more information about domain name delegation in [this article](https://docs.campaign.adobe.com/doc/AC/en/technicalResources/Technotes/AdobeCampaign_Deliverability_Sub_Domain_Delegation.pdf).

### Step 4: Configure the Visitor ID Service {#step-4--configure-the-visitor-id-service}

In the case that your Visitor ID service has never been configured on your web properties or websites, refer to the following [document](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-setup-aam-analytics.html) to learn how to configure your service or the following [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).

La configurazione e il provisioning sono finalizzati, l'integrazione può essere utilizzata per importare ed esportare audience o segmenti.
