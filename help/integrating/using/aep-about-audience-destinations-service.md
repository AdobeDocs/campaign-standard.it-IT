---
title: Informazioni sul servizio Destinazioni pubblico
description: Ulteriori informazioni sul servizio Audience Destinations.
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
source-git-commit: 26394f3f6fd9b67996c30924c376533380e8f4d6
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 2%

---

# Informazioni sul servizio Destinazioni pubblico {#about-audiences}

>[!IMPORTANT]
>
>Il servizio Audience Destinations è attualmente in versione beta e potrebbe essere soggetto a frequenti aggiornamenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Per accedere, contatta l’Assistenza clienti di Adobe.

Offri ai tuoi clienti la possibilità di sfruttare le [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html) creare tipi di pubblico altamente mirati basati su set di dati grandi e complessi. Adobe Experience Platform consolida i dati di profilo, comportamentali e con più entità tra le origini online e offline, incluso Adobe Analytics, per aiutarti a creare una vista a 360 gradi del cliente, consentendoti di gestire in modo efficace le esperienze dei clienti.

Adobe Campaign Standard utilizzerà quindi il **Destinazioni pubblico** per recuperare una raccolta di profili, noti come **Tipi di pubblico**, da Adobe Experience Platform per programmi di campagne a più passaggi e/o cross-channel.

**Tipi di pubblico** sono creati dalla prima costruzione **segmenti**, che è essenzialmente un set di regole basato su praticamente qualsiasi variabile (ad esempio, profilo, evento, dati multi-entità) all’interno di un profilo cliente da Adobe Experience Platform per creare un target multidimensionale. I concetti globali su Profilo cliente in tempo reale e servizi di segmentazione sono indicati in questi documenti dedicati:

* [Panoramica del profilo cliente in tempo reale](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html)
* [Panoramica del servizio di segmentazione](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html)

Una volta creato un segmento, puoi attivarlo come pubblico per una consegna in [Flussi di lavoro Campaign Standard](../../integrating/using/aep-targeting-audiences.md). Inoltre, puoi utilizzare dati contestuali da Adobe Experience Platform a [personalizzare](../../integrating/using/aep-personalizing-campaigns.md) e aggiungi contenuto dinamico alle campagne.

![](assets/do-not-localize/how-to-video.png) I video dimostrativi sono disponibili anche in [questa sezione](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html).

Termini utilizzati in queste sezioni:

* **Profilo**: Il profilo è un modello dati standard di Experience Platform utilizzato per definire gli attributi dei consumatori. Un profilo può anche essere un aggregato di dati evento e attributi relativi a una persona e o a un dispositivo.

   Esempio: &quot;John Doe è un maschio di 55 anni.&quot;

* **Segmento**: Un set di regole che definisce un sottoinsieme di profili dal database, utilizzando sia gli attributi che i dati evento.

   Esempio: &quot;Maschi che hanno più di 50 anni.&quot;

* **Pubblico**: Una raccolta di profili che soddisfano le regole dei segmenti.

   Esempio: Elenco di profili corrispondenti a tutti i maschi di età superiore ai 50 anni nel database.
