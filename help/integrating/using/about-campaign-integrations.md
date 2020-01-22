---
title: Informazioni sulle integrazioni di Campaign
description: Adobe Campaign consente di utilizzare altre soluzioni Adobe e combinare le loro diverse funzionalità.
page-status-flag: never-activated
uuid: 59d7cd99-a6f7-47f1-9b5c-c50e27a2bef8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: about-campaign-integrations
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# Informazioni sulle integrazioni di Campaign{#about-campaign-integrations}

Questa sezione descrive le integrazioni funzionali disponibili tra la versione corrente di Adobe Campaign e altre soluzioni e servizi.

Le diverse integrazioni presentate di seguito consentono di combinare le funzionalità di distribuzione e gestione avanzata delle campagne di Adobe Campaign con una serie di soluzioni create per personalizzare l&#39;esperienza degli utenti.

>[!NOTE]
>
> Per impostazione predefinita, Adobe Campaign è già collegato a un account Adobe Experience Cloud.

A seconda dell&#39;ambiente, altre soluzioni possono essere collegate ad Adobe Experience Cloud. Sono collegate come organizzazioni (o tenant).

Un&#39;organizzazione è l&#39;entità che consente all&#39;amministratore di configurare gruppi e utenti e di controllare il single sign-on in Experience Cloud. L&#39;organizzazione funziona come un&#39;azienda che abbraccia tutti i prodotti e le soluzioni Experience Cloud. Nella maggior parte dei casi, un&#39;organizzazione è il vostro nome aziendale. Tuttavia, un&#39;azienda può avere molte organizzazioni. La gestione di utenti e organizzazioni è dettagliata nel portale [dell&#39;Aiuto di](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)Adobe Experience Cloud.

Per integrare i flussi di dati provenienti da altri sistemi con Adobe Campaign, consulta la documentazione [sulle](../../api/using/about-campaign-standard-apis.md)API.

>[!NOTE]
>
>Adobe Campaign Standard può anche connettersi a Microsoft Dynamics 365: questa integrazione consente la sincronizzazione di tutti i dati di contatto disponibili nel sistema CRM, rendendo disponibili tutti i dati di contatto pertinenti per le attività della campagna. Per ulteriori informazioni su questa integrazione, consulta [Utilizzo di Campaign e Dynamics 365](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).


<table> 
 <thead> 
  <tr> 
   <th> Soluzione<br /> </th> 
   <th> Caso di utilizzo<br /> </th> 
   <th> Consultare<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4<br /> </td> 
   <td> Consente di creare contenuti e-mail o moduli mappati al database Adobe Campaign direttamente in Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Utilizzo di Campaign ed Experience Manager</a><br/>, <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">Integrate Experience Manager e Campaign Standard</a> <br/>, <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">Create un'e-mail con Experience Manager e Campaign</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic, Standard<br /> </td> 
   <td> Consente di inserire immagini calcolate in modo dinamico da Adobe Target all'apertura di un'e-mail creata e inviata da Adobe Campaign.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Utilizzo di Campaign e Target</a> <br/>, <a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html">integrazione di Campaign e Target</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">personalizzazione delle immagini e-mail in video in tempo</a> reale (passaggio 3)
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> Consente di tenere traccia del successo delle comunicazioni e-mail direttamente in Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Condivisione di dati delle campagne con Analytics</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">condivisione di KPI per video di reporting</a> delle campagne integrato (passaggio 1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager e il servizio di base Persone (profili e audience)<br /> </td> 
   <td> Consente di scambiare tipi di pubblico con le diverse applicazioni Adobe Experience Cloud utilizzate.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">Servizio di base Persone (profili e audience)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Servizio di base delle risorse e risorse su richiesta<br /> </td> 
   <td> Consente di inserire le risorse dalla libreria Adobe Experience Cloud nelle e-mail e nelle pagine di destinazione create in Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Servizio</a> di base risorse o risorse su richiesta<br /> </td> 
  </tr> 
  <tr> 
   <td> Punti di interesse (Analytics for Mobile)<br /> </td> 
   <td> Consente di raccogliere i dati dei punti di interesse dagli abbonati dell'applicazione mobile per inviare messaggi di marketing personalizzati con Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Inviare messaggi di marketing basati sulla posizione con i dati</a> Campagna e Punti di interesse (Analytics for Mobile)<br /> </td> 
  </tr> 
  <tr> 
   <td> Experience Cloud Triggers<br /> </td> 
   <td> Consente di inviare e-mail personalizzate ai clienti in Adobe Campaign in risposta a comportamenti specifici tracciati sul sito Web da Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Usa attivatori Experience Cloud Triggers in Campaign Standard</a><br/>, Triggers <a href="../../integrating/using/abandonment-triggers-use-cases.md">di abbandono-Casi</a><br/>di utilizzo delle campagne, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Attiva messaggi di commento in base al video Attività</a> sito (passaggio 2)
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Consente di modificare un contenuto e-mail da Dreamweaver e di sincronizzarlo con Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">Creare e-mail personalizzate con il video di Dreamweaver</a> <br/>, <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">utilizzare l'estensione Campaign per Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Creative SDK<br /> </td> 
   <td> Consente di modificare le immagini e di utilizzare un set completo di funzioni basato su Adobe Creative SDK per migliorare le immagini direttamente nell’editor dei contenuti.<br /> </td> 
   <td> <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">Modifica delle immagini con Adobe Creative SDK</a><br /> </td> 
  </tr> 
  <tr> 
   <td> SDK della piattaforma Experience<br /> </td> 
   <td> Consente l'automazione del processo di attivazione delle proprietà dell'app mobile in Adobe Campaign tramite gli SDK della piattaforma Experience.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">Configurazione di un’applicazione mobile mediante gli SDK di Experience Platform</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

