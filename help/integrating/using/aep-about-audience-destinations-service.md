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
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '335'
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
