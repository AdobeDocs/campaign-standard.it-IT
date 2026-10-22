---
title: Informazioni sui profili
description: I contatti vengono memorizzati come profili nel database Campaign e aggiornati nel corso dell’intero ciclo di vita.
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: recipient,overview
feature: Profiles
role: User
level: Beginner
exl-id: 65310e00-567f-4fae-89bc-b1d5591fca77
TQID: 'https://experienceleague.adobe.com/8netKX93BsN9JxgyckV44tpKK5uPjFMrrnD8F4FCpJM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 74%
---
# Informazioni sui profili{#about-profiles}

Adobe Campaign consente di gestire i contatti durante l’intero ciclo di vita: creazione, importazione, targeting, tracciamento delle azioni, aggiornamenti, ecc. I contatti vengono memorizzati nel database come profili contenenti le informazioni ad essi collegate: cognome, nome, indirizzo, abbonamenti, consegne, ecc.

>[!NOTE]
>
>I profili sono disponibili anche utilizzando l’API di Adobe Campaign Standard. Per ulteriori informazioni, consulta la [documentazione dedicata](../../api/using/retrieving-profiles.md).

![](assets/marketing_history.png)

Quando crei delle campagne, puoi definire la destinazione delle consegne selezionando i profili secondo criteri semplici o avanzati. Tecnicamente, un profilo è una voce nel database che contiene tutte le informazioni necessarie per il targeting, la qualifica e il tracciamento dei comportamenti.

Un profilo può essere: un cliente, un potenziale cliente, una persona iscritta a una newsletter, un destinatario, un utente o qualsiasi altra denominazione a seconda dell’organizzazione. Per definire vari tipi di profili, utilizza le [dimensioni targeting](../../automating/using/query.md#targeting-dimensions-and-resources).
