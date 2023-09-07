---
title: Informazioni sul servizio Destinazioni pubblico
description: Ulteriori informazioni sul servizio Destinazioni pubblico.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: 34235749-d056-4d4c-9939-7dc52f980a76
hide: true
hidefromtoc: true
source-git-commit: 110f3ccb5865e70c78e18485b4ff4ba7a648af3f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# Informazioni sul servizio Destinazioni pubblico {#about-audiences}

>[!IMPORTANT]
>
>Il servizio Audience Destinations è attualmente in versione beta, e potrebbe essere soggetto ad aggiornamenti frequenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Contatta l’Assistenza clienti di Adobe se desideri accedervi.

Rafforza le esperienze dei consumatori sfruttando [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) creare tipi di pubblico altamente mirati basati su set di dati complessi e di grandi dimensioni. Adobe Experience Platform consolida i dati di profilo, comportamentali e di più entità tra origini online e offline, incluso Adobe Analytics, per aiutarti a creare una visualizzazione a 360 gradi del cliente, consentendoti di gestire in modo efficace le esperienze dei clienti.

Adobe Campaign Standard utilizzerà quindi **Audience Destinations** servizio per recuperare una raccolta di profili, nota come **Tipi di pubblico**, da Adobe Experience Platform per programmi di campagne multi-step e/o cross-channel.

**Tipi di pubblico** vengono create dal primo edificio **segmenti**, che sono essenzialmente un set di regole basate su praticamente qualsiasi variabile (ad esempio, profilo, evento, dati di più entità) all’interno di un profilo cliente da Adobe Experience Platform per creare un target multidimensionale. I concetti globali su Real-time Customer Profile e Segmentation Services sono riportati in questi documenti dedicati:

* [Panoramica del profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [Panoramica del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

Una volta creato un segmento, puoi attivarlo come pubblico per una consegna in [Flussi di lavoro Campaign Standard](../../integrating/using/aep-targeting-audiences.md). Inoltre, puoi utilizzare dati contestuali provenienti da Adobe Experience Platform per [personalizzare](../../integrating/using/aep-personalizing-campaigns.md) e aggiungere contenuto dinamico alle campagne.

![](assets/do-not-localize/how-to-video.png) I video dimostrativi sono disponibili anche in [questa sezione](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Termini utilizzati nelle sezioni seguenti:

* **Profilo**: profilo è un modello dati standard di Experience Platform utilizzato per definire gli attributi dei consumatori. Un profilo può anche essere un aggregato di dati evento e attributi relativi a una persona e/o a un dispositivo.

  Esempio: &quot;John Doe è un uomo di 55 anni.&quot;

* **Segmento**: un set di regole che definisce un sottoinsieme di profili dal database, utilizzando sia gli attributi che i dati evento.

  Esempio: &quot;Maschi > 50 anni&quot;.

* **Pubblico**: raccolta di profili che soddisfano le regole dei segmenti.

  Esempio: elenco dei profili corrispondenti a tutti i maschi di età > 50 anni presenti nel database.
