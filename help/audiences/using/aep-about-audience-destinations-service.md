---
solution: Campaign Standard
product: campaign
title: Informazioni sul servizio Destinazioni pubblico
description: Ulteriori informazioni sul servizio Destinazioni di pubblico.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Informazioni sul servizio Destinazioni pubblico {#about-audiences}

>[!IMPORTANT]
>
>Il servizio Destinazioni audience è attualmente in versione beta, che potrebbe essere soggetto a frequenti aggiornamenti senza preavviso. I clienti devono essere ospitati in Azure (attualmente nella versione beta solo per il Nord America) per accedere a tali funzionalità. Per accedere, contatta  Assistenza clienti di Adobe.

Consentono di migliorare le esperienze dei consumatori sfruttando l&#39;[Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html) per creare audience altamente mirate basate su set di dati complessi e di grandi dimensioni. Adobe Experience Platform consolida i dati di profilo, comportamentali e a più entità tra le origini online e offline, incluso  Adobe Analytics, per aiutarti a creare una vista a 360 gradi del cliente, consentendo di gestire efficacemente le esperienze dei clienti.

 Adobe Campaign Standard utilizzerà quindi il servizio **Destinazioni di pubblico** per recuperare una raccolta di profili, noti come **Audiences**, da Adobe Experience Platform per programmi di campagna a più fasi e/o tra canali.

**I** tipi di pubblico sono creati dai primi  **segmenti** di creazione, che sono essenzialmente un insieme di regole basate praticamente su qualsiasi variabile (ad esempio, profilo, evento, dati multi-entità) all&#39;interno di un profilo cliente da Adobe Experience Platform per creare un target multidimensionale. I concetti globali sui servizi di Segmentazione e profilo cliente in tempo reale sono citati in questi documenti dedicati:

* [Panoramica del profilo cliente in tempo reale](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)
* [Panoramica del servizio di segmentazione](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

Dopo aver creato un segmento, puoi attivarlo come audience per una distribuzione nei flussi di lavoro [Campaign Standard](../../automating/using/aep-targeting-audiences.md). È inoltre possibile utilizzare dati contestuali dall&#39;Adobe Experience Platform per [personalizzare](../../automating/using/aep-personalizing-campaigns.md) e aggiungere contenuti dinamici alle campagne.

![](assets/do-not-localize/how-to-video.png) In  [questa sezione](https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html) sono disponibili anche i video introduttivi.

Termini utilizzati in queste sezioni:

* **Profilo**: Profilo è un modello di dati standard  Experience Platform utilizzato per definire gli attributi dei consumatori. Un profilo può anche essere un insieme di dati e attributi dell&#39;evento relativi a una persona e/o a un dispositivo.

   Esempio: &quot;John Doe è un maschio di 55 anni.&quot;

* **Segmento**: Un insieme di regole che definisce un sottoinsieme di profili dal database, utilizzando sia gli attributi che i dati dell&#39;evento.

   Esempio: &quot;Maschi > 50 anni.&quot;

* **Pubblico**: Raccolta di profili che soddisfano le regole del segmento.

   Esempio: Elenco di profili corrispondenti a tutti i maschi di età superiore ai 50 anni nel database.
