---
title: Panoramica di Experience Data Model
description: Experience Data Model (XDM) è un set standard di schemi di dati in cui i dati possono essere acquisiti per l’utilizzo con soluzioni e prodotti Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: cc1aa669-30cd-4ea4-9fab-4d1b6c373744
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
source-wordcount: '249'
ht-degree: 0%
---
# Panoramica di Experience Data Model {#experience-data-model-overview}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connector è attualmente in versione beta, che potrebbe essere soggetta a frequenti aggiornamenti senza preavviso. Per accedere a queste funzionalità, i clienti devono essere ospitati su Azure (attualmente in versione beta solo per il Nord America). Per accedere, contatta l’Assistenza clienti di Adobe.

Experience Data Model (XDM) è un set standard di schemi di dati in cui i dati possono essere acquisiti per l’utilizzo con soluzioni e prodotti Adobe Experience Platform.

La creazione e la gestione di schemi XDM è disponibile con un’API dedicata o con l’interfaccia utente XDM.

## Area di lavoro XDM {#xdm-workspace}

XDM Workspace consente di visualizzare, creare ed estendere schemi di dati.

Per accedere all’interfaccia utente di XDM, apri Adobe Experience Platform. Passa alla finestra Modello dati per creare o estendere uno schema XDM.

Consulta la [documentazione completa di Workspace XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=it).

![](assets/aep_xdmworkspace.png)

## API XDM {#xdm-api}

Puoi eseguire le seguenti azioni tramite l’API dello schema XDM:

* Visualizzare un elenco degli schemi esistenti
* Visualizzare uno schema specifico Estendere uno schema esistente
* Aggiungere campi a un’estensione
* Creare e aggiornare un nuovo schema
* Visualizzare i descrittori degli schemi
* Creare, aggiornare ed eliminare i descrittori degli schemi

Tutti i dettagli per la manipolazione delle chiamate API sono disponibili nella [Guida per gli sviluppatori](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=it).
