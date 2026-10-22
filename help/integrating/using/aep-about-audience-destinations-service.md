---
title: Informazioni sul servizio Destinazioni pubblico
description: Ulteriori informazioni sul servizio Destinazioni pubblico.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%
---
# Informazioni sul servizio Destinazioni pubblico {#about-audiences}

>[!IMPORTANT]
>
>Il servizio Audience Destinations è ora obsoleto. Le funzionalità obsolete sono ancora disponibili, ma non vengono ulteriormente migliorate né supportate. Ulteriori informazioni [in questa pagina](../../rn/using/deprecated-features.md)

Rafforza le tue esperienze dei consumatori sfruttando [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html?lang=it) per creare tipi di pubblico altamente mirati basati su set di dati complessi e di grandi dimensioni. Adobe Experience Platform consolida i dati di profilo, comportamentali e di più entità tra origini online e offline, incluso Adobe Analytics, per aiutarti a creare una visualizzazione a 360 gradi del cliente, consentendoti di gestire in modo efficace le esperienze dei clienti.

Adobe Campaign Standard utilizzerà quindi il servizio **Destinazioni pubblico** per recuperare una raccolta di profili, noti come **Tipi di pubblico**, da Adobe Experience Platform per programmi di campagne con più passaggi e/o canali diversi.

**I tipi di pubblico** vengono creati dalla prima generazione di **segmenti**, che sono essenzialmente un set di regole basate su qualsiasi variabile (ad esempio, profilo, evento, dati di più entità) all&#39;interno di un profilo cliente da Adobe Experience Platform per creare una destinazione multidimensionale. I concetti globali su Real-time Customer Profile e Segmentation Services sono riportati in questi documenti dedicati:

* [Panoramica del profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=it)
* [Panoramica del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=it)

Una volta creato un segmento, puoi attivarlo come pubblico per una consegna in [flussi di lavoro Campaign Standard](../../integrating/using/aep-targeting-audiences.md). Inoltre, puoi utilizzare dati contestuali da Adobe Experience Platform per [personalizzare](../../integrating/using/aep-personalizing-campaigns.md) e aggiungere contenuto dinamico alle campagne.

![](assets/do-not-localize/how-to-video.png) Video dimostrativi sono disponibili anche in [questa sezione](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html?lang=it).

Termini utilizzati nelle sezioni seguenti:

* **Profilo**: il profilo è un modello dati standard di Experience Platform utilizzato per definire gli attributi dei consumatori. Un profilo può anche essere un aggregato di dati evento e attributi relativi a una persona e/o a un dispositivo.

  Esempio: &quot;John Doe è un uomo di 55 anni.&quot;

* **Segmento**: un insieme di regole che definisce un sottoinsieme di profili dal database, utilizzando sia attributi che dati evento.

  Esempio: &quot;Maschi > 50 anni&quot;.

* **Pubblico**: raccolta di profili che soddisfano le regole dei segmenti.

  Esempio: elenco dei profili corrispondenti a tutti i maschi di età > 50 anni presenti nel database.
