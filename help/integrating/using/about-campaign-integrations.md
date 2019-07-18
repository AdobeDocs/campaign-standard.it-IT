---
title: Informazioni sulle integrazioni Campaign
seo-title: Informazioni sulle integrazioni Campaign
description: Informazioni sulle integrazioni Campaign
seo-description: Adobe Campaign consente di utilizzare altre soluzioni Adobe e combinare le loro diverse funzionalità.
page-status-flag: never-activated
uuid: 59 d 7 cd 99-a 6 f 7-47 f 1-9 b 5 c-c 50 e 27 a 2 bef 8
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: about-campaign-integrations
discoiquuid: 9633 e 9 ca -3323-499 b -8259-45165 d 59 a 4 d 0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 337f2270f3f66d5172084a4e2a19d6185bf097ff

---


# About Campaign integrations{#about-campaign-integrations}

Questa sezione descrive le integrazioni funzionali disponibili tra la versione corrente di Adobe Campaign e altre soluzioni e servizi.

Le diverse integrazioni presentate di seguito consentono di combinare le funzionalità di consegna e gestione avanzate delle campagne di Adobe Campaign con un set di soluzioni create per personalizzare l'esperienza degli utenti.

>[!NOTE]
>
> Per impostazione predefinita, Adobe Campaign è già collegato a un account Adobe Experience Cloud.

A seconda dell'ambiente, anche altre soluzioni possono essere collegate ad Adobe Experience Cloud. Sono collegate come Organizzazioni (denominate anche Tenant).

Un'organizzazione è l'entità che consente all'amministratore di configurare gruppi e utenti e di controllare il single sign-on in Experience Cloud. L'organizzazione funziona come una società che si occupa di tutti i prodotti e le soluzioni Experience Cloud. Nella maggior parte dei casi, un'organizzazione è il nome della società. Tuttavia, un'azienda può avere molte organizzazioni. User and organization management is detailed in the [Adobe Experience Cloud help portal](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html).

If you would like to integrate data flows from other systems with Adobe Campaign, have a look at our [API documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

>[!NOTE]
>
>Adobe Campaign Standard può anche collegarsi a Microsoft Dynamics 365: questa integrazione consente la sincronizzazione di tutti i dati di contatto disponibili nel sistema CRM, rendendo tutti i dati di contatto pertinenti disponibili per le attività della campagna. For more on this integration, refer to [Working with Campaign and Dynamics 365](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).


<table> 
 <thead> 
  <tr> 
   <th> Solution<br /> </th> 
   <th> Use Case<br /> </th> 
   <th> Refer to<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4<br /> </td> 
   <td> Allows you to create email contents or forms mapped to the Adobe Campaign database directly in Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Utilizzo di Campaign ed Experience Manager</a><br/>, <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">Integrazione di Experience Manager e Campaign Standard</a><br/>, <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">Creazione di un'e-mail con Experience Manager e Campaign</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic, Standard<br /> </td> 
   <td> Allows you to insert images that are dynamically computed by Adobe Target when an email created and sent by Adobe Campaign is opened.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Utilizzo di Campaign e Target</a><br/>, <a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html">Integrazione di Campaign e Target</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Personalizza le immagini e-mail nel video in tempo reale</a> (passaggio 3)
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> Allows you to track the success of your email deliveries directly in Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Condividi dati Campaign con Analytics</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Condividi KPI per video di reporting</a> campagna integrata (passaggio 1
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager and People core service (Profiles &amp; Audiences)<br /> </td> 
   <td> Allow you to exchange audiences with the different Adobe Experience Cloud applications that you use.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">Servizio di base Persone (profili e pubblico)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Asset core service and Assets On Demand<br /> </td> 
   <td> Allows you to insert assets from your Adobe Experience Cloud library into emails and landing pages created in Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Servizio di base risorse</a> o Risorse su richiesta<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest (Analytics for Mobile)<br /> </td> 
   <td> Allows you to collect Points of Interest data from your mobile application's subscribers to send personalized marketing messages with Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Inviare messaggi di marketing basati sulla posizione con i dati Campagna e Punti di interesse</a> (Analytics per dispositivi mobili)<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud Triggers<br /> </td> 
   <td> Allows you to send personalized emails to your customers in Adobe Campaign as a reaction to specific behaviors that are tracked on your website by Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Utilizzate Experience Cloud Triggers in Campaign Standard</a><br/>, <a href="../../integrating/using/abandonment-triggers-use-cases.md">Acquisition Ment Triggers Casi d'uso</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Attivate i messaggi di remarketing basati sul video Activity Activity</a> (Attività del sito) (passaggio 2)
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Allows you to edit an email content from Dreamweaver and synchronize it with Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">Creare e-mail personalizzate con</a> il video <br/>di Dreamweaver, <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Utilizzare l'estensione Campaign per Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Creative SDK<br /> </td> 
   <td> Allows you to edit images and use a complete set of features powered by the Adobe Creative SDK to enhance your images directly in the content editor.<br /> </td> 
   <td> <a href="../../designing/using/modifying-images-with-the-adobe-creative-sdk.md">Modifica delle immagini con Adobe Creative SDK</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Platform SDKs<br /> </td> 
   <td> Allows automation of the Mobile App Property activation process in Adobe Campaign using the Experience Platform SDKs.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">Configurazione di un'applicazione mobile utilizzando gli SDK della piattaforma Experience Platform</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

