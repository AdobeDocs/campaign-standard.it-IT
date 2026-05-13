---
title: Profili attivi di Campaign
description: Scopri come accedere alle metriche cliente e profili attivi
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
TQID: https://experienceleague.adobe.com/XKRIP6jfP3ROPWTN4moJKsBLQcRqmR3gSWZ-hi5P8I4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 272
ht-degree: 0%

---

# Profili attivi{#active-profiles}

È possibile accedere ai dettagli dei profili attivi dal report **[!UICONTROL Customer metrics]**. Questo rapporto è disponibile solo per gli amministratori funzionali di Campaign. Per accedere a questo report, fare clic sull&#39;icona Adobe Campaign in alto a sinistra nell&#39;[interfaccia utente](../../start/using/interface-description.md#advanced-menu) e passare a **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_customer_metrics.png)

Questo report viene generato ogni mese dal flusso di lavoro tecnico **[!UICONTROL Billing]** e visualizza il numero di **profili attivi**. Ulteriori informazioni sui flussi di lavoro tecnici in [questa pagina](../../administration/using/technical-workflows.md).

Un &quot;profilo&quot; è un record di informazioni che rappresenta un cliente finale, potenziale cliente o lead. I profili sono considerati **attivi** se sono stati targetizzati da una consegna Campaign negli ultimi 12 mesi tramite qualsiasi canale.

In base al contratto, a ciascuna istanza di Campaign viene fornito un numero specifico di profili attivi. Per informazioni sul numero di profili attivi acquistati, fai riferimento al contratto di licenza.

![](assets/audience_active_profiles_list.png)



* I profili esclusi durante la preparazione della consegna (ad esempio per regole di tipologia o meccanismo di quarantena) non vengono presi in considerazione.

* I destinatari dei messaggi transazionali vengono conteggiati nei profili attivi.

* Un profilo che è stato oggetto di targeting per diverse consegne verrà conteggiato una sola volta.

* Questo report è solo informativo, non ha un impatto diretto sulla fatturazione.

Nella parte inferiore della pagina, sono elencate le dimensioni di targeting con il numero di profili per ciascuno di essi. I destinatari dei messaggi transazionali sono associati alla dimensione **Anonimo**.

>[!NOTE]
>
>In qualità di utente amministratore, puoi anche monitorare il numero di profili attivi utilizzati sulle istanze direttamente dal Pannello di controllo Campaign. Per ulteriori informazioni, consulta la [documentazione del Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
