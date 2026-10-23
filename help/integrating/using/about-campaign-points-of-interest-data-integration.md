---
title: Informazioni sull’integrazione di Campaign con i dati Punti di interesse
description: Raccogliendo i dati dei punti di interesse dagli abbonati all’app mobile, puoi inviare messaggi di marketing basati sulla posizione agli abbonati tramite l’integrazione in Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
TQID: 'https://experienceleague.adobe.com/NMHm-sHLhsjMqprniSnxca27zpoxGEhRGKlt1IJXfVg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 6%
---
# Informazioni sull’integrazione di Campaign con i dati Punti di interesse{#about-campaign-points-of-interest-data-integration}

Oltre a monitorare la presenza online dei clienti, puoi sfruttare anche le loro posizioni fisiche. Grazie all’integrazione con Adobe Analytics per dispositivi mobili, puoi utilizzare Adobe Campaign per inviare messaggi di marketing basati sulla posizione agli abbonati alla tua app mobile.

I punti di interesse sono costituiti da una latitudine, una longitudine e un raggio associati a un’etichetta. Sono definiti nell&#39;interfaccia [Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html?lang=it).

Quando un abbonato apre la tua app mobile, se la posizione corrisponde a un punto di interesse, Adobe Campaign acquisisce i dati tramite Experience Cloud Mobile SDK. Puoi utilizzare queste informazioni per inviare messaggi personalizzati in base alla posizione dell’utente (ad esempio e-mail, notifiche push, messaggi SMS).

Ad esempio, puoi inviare un’offerta di sconto del 10% ai clienti che utilizzano la tua applicazione e hanno visitato uno dei tuoi negozi a Boston nelle ultime due settimane.

Un caso d&#39;uso è presentato nella sezione [Personalizzazione dei messaggi di Campaign con i dati dei punti di interesse](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md).
