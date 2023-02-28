---
title: Profili attivi della campagna
description: Scopri come accedere alle metriche del cliente e ai profili attivi
feature: Profiles
role: User
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: 0ae2501b5c3ecf6dc9562bb53b5354c52aff7323
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# Profili attivi{#active-profiles}

Puoi accedere ai dettagli dei profili attivi dalla sezione **[!UICONTROL Customer metrics]** rapporto. Questo rapporto è disponibile solo per gli amministratori funzionali di Campaign. Per accedere a questo rapporto, fai clic sull’icona Adobe Campaign in alto a sinistra [interfaccia utente](../../start/using/interface-description.md#advanced-menu), e sfogliare per **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_customer_metrics.png)

Questo rapporto viene generato ogni mese dal **[!UICONTROL Billing]** flusso di lavoro tecnico e visualizza il numero di **profili attivi**. Ulteriori informazioni sui flussi di lavoro tecnici in [questa pagina](../../administration/using/technical-workflows.md).

Un &quot;profilo&quot; è un record di informazioni che rappresenta un cliente finale, potenziale cliente o lead. I profili sono considerati **attivo** se sono stati targetizzati da una consegna Campaign negli ultimi 12 mesi tramite qualsiasi canale.

In base al contratto, a ciascuna istanza di Campaign viene fornito un numero specifico di profili attivi. Fai riferimento al tuo contratto di licenza per riferimento al numero di profili attivi acquistati.

![](assets/audience_active_profiles_list.png)



* I profili esclusi durante la preparazione della consegna (ad esempio mediante regole di tipologia o un meccanismo di quarantena) non vengono presi in considerazione.

* I destinatari dei messaggi transazionali vengono conteggiati in Profili attivi.

* Un profilo per il quale sono state eseguite le destinazioni da più consegne verrà conteggiato una sola volta.

* Questo rapporto è solo informativo, non ha un impatto diretto sulla fatturazione.

Nella parte inferiore della pagina, le dimensioni di targeting sono elencate con il numero di profili per ciascuna. I destinatari dei messaggi transazionali sono associati al **Anonimo** dimensione.

>[!NOTE]
>
>In qualità di utente amministratore, puoi anche monitorare il numero di profili attivi utilizzati sulle istanze direttamente dal Pannello di controllo Campaign. Per ulteriori informazioni, consulta la sezione [Documentazione del Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
