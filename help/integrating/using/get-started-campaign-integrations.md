---
title: Introduzione alle integrazioni con Campaign
description: Usa altre soluzioni Adobe e combina le loro diverse funzionalità con Campaign.
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ecf88c7d-6729-4b3a-85c4-60427bb57442
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 77%

---

# Informazioni sulle integrazioni di Campaign{#get-started-campaign-integrations}

Questa sezione descrive le integrazioni funzionali disponibili tra l’attuale versione di Adobe Campaign e altre soluzioni e servizi.

Le diverse integrazioni indicate di seguito permettono di combinare le funzionalità di consegna e le funzionalità avanzate di gestione delle campagne di Adobe Campaign con una serie di soluzioni create per aiutarti a personalizzare la user experience.

>[!NOTE]
>
> Per impostazione predefinita, Adobe Campaign è già collegato a un account Adobe Experience Cloud.

A seconda dell’ambiente, è possibile collegare ad Adobe Experience Cloud altre soluzioni come Organizzazioni (o Tenant).

Un’organizzazione è un’entità che consente all’amministratore di configurare gruppi e utenti e di controllare il single sign-on in Experience Cloud. L’organizzazione funziona come una log-in company che abbraccia tutti i prodotti e le soluzioni di Experience Cloud. Nella maggior parte dei casi l’organizzazione corrisponde al nome aziendale, ma una stessa azienda può avere molte organizzazioni. La gestione di utenti e organizzazioni è illustrata nel dettaglio nella [Guida di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=it).

Se desideri integrare i flussi di dati da altri sistemi con Adobe Campaign, consulta la [documentazione sulle API](../../api/using/get-started-apis.md).

>[!NOTE]
>
> Adobe Campaign Standard può connettersi anche a Microsoft Dynamics 365: questa integrazione consente la sincronizzazione di tutti i dati di contatto disponibili nel sistema di gestione delle relazioni con i clienti, rendendo disponibili tutti quelli pertinenti alle attività della campagna. Per ulteriori informazioni su questa integrazione, consulta [Utilizzo di Campaign e Dynamics 365](../../integrating/using/d365-acs-get-started.md).


<table> 
 <thead> 
  <tr> 
   <th> Soluzione<br /> </th> 
   <th> Caso d’uso<br /> </th> 
   <th> Fai riferimento a<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Adobe Experience Manager<br /> </td> 
   <td> Consente di creare contenuti e-mail o forms mappati al database Adobe Campaign direttamente in Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Utilizzo di Campaign e Experience Manager</a>, <a href="https://helpx.adobe.com/it/experience-manager/6-4/sites/administering/using/campaignstandard.html">Integrazione di Experience Manager e Campaign Standard</a>, <a href="https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html?lang=it">Creazione di un messaggio e-mail con Experience Manager e Campaign</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Target<br /> </td> 
   <td> Consente di inserire immagini calcolate dinamicamente da Adobe Target quando viene aperto un messaggio e-mail creato e inviato da Adobe Campaign.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Utilizzo di Campaign e Target</a>, <a href="https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html?lang=it">Integrazione di Campaign e Target</a>, <a href="https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html">Video Personalizzazione immagini e-mail in tempo reale</a> (passaggio 3)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Analytics<br /> </td> 
   <td> Consente di tenere traccia della consegna delle comunicazioni e-mail direttamente in Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Condivisione di dati di Campaign con Analytics</a>, video <a href="https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html">Condivisione di KPI per reporting dinamico integrato di Campaign</a> (passaggio 1)
    </td> 
  </tr> 
  <tr> 
   <td> Servizio core Adobe Audience Manager e People (Profili e Audiences)<br /> </td> 
   <td> Consente di scambiare i tipi di pubblico con le diverse applicazioni Adobe Experience Cloud utilizzate.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">Servizio core People (Profiles &amp; Audiences)</a><br /> </td> 
  </tr> 
   <tr> 
   <td> Adobe Real-time Customer Data Platform (RTCDP)<br /> </td> 
   <td> L’integrazione tra Adobe Campaign e Adobe Real-time Customer Data Platform (RTCDP) consente di condividere i dati dei segmenti e importare tipi di pubblico in Adobe Campaign.</td>
   <td><a href="../../integrating/using/get-started-sources-destinations.md">Guida introduttiva a origini e destinazioni</a></td>
  </tr> 
  <tr> 
   <td> Servizio core Asset di Adobe e Assets On Demand<br /> </td> 
   <td> Consente di inserire gli assets dalla libreria di Adobe Experience Cloud nelle e-mail e nelle pagine di destinazione create in Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Servizio core Assets</a> o Assets on-demand<br /> </td> 
  </tr> 
  <tr> 
   <td> Punti di interesse (Analytics per dispositivi mobili)<br /> </td> 
   <td> Consente di raccogliere i dati dei punti di interesse dagli abbonati all’app mobile per inviare messaggi di marketing personalizzati con Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Inviare messaggi di marketing basati sulla posizione con i dati di Campaing e punti di interesse</a> (Analytics per dispositivi mobili)<br /> </td> 
  </tr> 
  <tr> 
   <td> Trigger di Adobe Experience Cloud<br /> </td> 
   <td> Consente di inviare e-mail personalizzate ai clienti in Adobe Campaign come reazione a comportamenti specifici tracciati sul sito web da Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Utilizzo dei Trigger di Experience Cloud in Campaign Standard</a>, <a href="../../integrating/using/abandonment-triggers-use-cases.md">Casi di utilizzo degli attivatori di abbandono</a>, video <a href="https://helpx.adobe.com/it/marketing-cloud/how-to/email-marketing.html">Trigger dei messaggi di remarketing basati sull’attività del sito</a> (passaggio 2)
    </td> 
  </tr> 
    <tr> 
   <td> Adobe Journey Orchestration<br /> </td> 
   <td> Consente di inviare e-mail, notifiche push e SMS utilizzando le funzionalità di messaggistica transazionale di Adobe Campaign Standard nel contesto di Adobe Journey Orchestration, tramite un'azione preconfigurata.<br /> </td> 
   <td> <a href="https://experienceleague.adobe.com/docs/journeys/using/action-journeys/working-with-adobe-campaign.html?lang=it">Utilizzo di Adobe Journey Orchestration e Adobe Campaign Standard</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Dreamweaver<br /> </td> 
   <td> Consente di modificare il contenuto di un’e-mail da Dreamweaver e di sincronizzarla con Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=it">Creazione di e-mail personalizzate con video di Dreamweaver</a>, <a href="https://helpx.adobe.com/it/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Utilizzo dell'estensione Campaign per Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> SDK di Adobe Experience Platform<br /> </td> 
   <td> Consente l’automazione del processo di attivazione della proprietà dell’app mobile in Adobe Campaign tramite gli SDK per Experience Platform .<br /> </td> 
   <td> <a href="https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html">Configurazione di un’applicazione mobile tramite SDK per Experience Platform</a><br /> </td> 
  </tr> 
 </tbody> 
</table>
