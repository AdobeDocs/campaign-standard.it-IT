---
title: Informazioni sul servizio Destinazioni pubblico
description: Ulteriori informazioni sul servizio Destinazioni di pubblico.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e1fa546313e8d543685ef30a072ae2d97c5bf236

---


# Informazioni sul servizio Destinazioni pubblico {#about-audiences}

>[!IMPORTANT]
>
>Il servizio Destinazioni audience è attualmente in versione beta, che potrebbe essere soggetto a frequenti aggiornamenti senza preavviso. I clienti devono essere ospitati in Azure (attualmente nella versione beta solo per il Nord America) per accedere a tali funzionalità. Per accedere, contatta l&#39;Assistenza clienti Adobe.

Consentono di migliorare le esperienze dei clienti sfruttando [Adobe Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/landing/home.html) per creare audience altamente mirate basate su set di dati complessi e di grandi dimensioni. Adobe Experience Platform riunisce i dati di profilo, comportamentali e a più entità tra le origini online e offline, incluso Adobe Analytics, per aiutarti a creare una vista a 360 gradi del cliente, consentendoti di gestire efficacemente le esperienze dei clienti.

Adobe Campaign Standard utilizzerà quindi il servizio Destinazioni **** audience per recuperare una raccolta di profili, noti come **Audiences**, da Adobe Experience Platform per i programmi di campagna con più passaggi e/o tra canali.

**I tipi di pubblico** vengono creati dai primi **segmenti** di creazione, che sono essenzialmente un insieme di regole basate praticamente su qualsiasi variabile (ad esempio, profilo, evento, dati multi-entità) all&#39;interno di un profilo cliente da Adobe Experience Platform per creare un target multidimensionale. I concetti globali relativi ai servizi di profilo e segmentazione unificati sono riportati nei seguenti documenti dedicati:

* [Panoramica del profilo cliente in tempo reale](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)
* [Panoramica del servizio di segmentazione](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html)

Dopo aver creato un segmento, puoi attivarlo come pubblico per una distribuzione nei flussi di lavoro [](../../automating/using/aep-targeting-audiences.md)Campaign Standard. Inoltre, puoi utilizzare i dati contestuali di Adobe Experience Platform per [personalizzare](../../automating/using/aep-personalizing-campaigns.md) e aggiungere contenuti dinamici alle campagne.

In [questa sezione](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html)sono disponibili anche i video introduttivi.

Termini utilizzati in queste sezioni:

* **Profilo**: Profile è un modello di dati standard della piattaforma Experience che consente di definire gli attributi dei consumatori. Un profilo può anche essere un insieme di dati e attributi dell&#39;evento relativi a una persona e/o a un dispositivo.

   Esempio: &quot;John Doe è un maschio di 55 anni.&quot;

* **Segmento**: Un insieme di regole che definisce un sottoinsieme di profili dal database, utilizzando sia gli attributi che i dati dell&#39;evento.

   Esempio: &quot;Maschi > 50 anni.&quot;

* **Pubblico**: Raccolta di profili che soddisfano le regole del segmento.

   Esempio: Elenco di profili corrispondenti a tutti i maschi di età superiore ai 50 anni nel database.
