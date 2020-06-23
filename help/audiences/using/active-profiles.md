---
title: Profili attivi
description: Puoi accedere a un rapporto dedicato sulle metriche dei clienti e visualizzare i profili attivi nel database Campaign.
page-status-flag: never-activated
uuid: ee8ac493-c297-49ca-aed4-3976d8a685a4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: e029213f-0b65-41b1-8adf-34fa813b0c70
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4575c1152f1a33ff18b2200151346cc6e56b45fa
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 2%

---


# Profili attivi{#active-profiles}

 Adobe Campaign fornisce un rapporto che mostra il numero di profili attivi. Questo rapporto è solo informativo, non ha un impatto diretto sulla fatturazione. Solo gli amministratori possono accedere a questo rapporto, in **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

Il flusso di lavoro **[!UICONTROL Billing]** tecnico genera ogni mese un rapporto contenente il numero di profili attivi per i quali è stato eseguito il targeting negli ultimi 12 mesi.

I profili esclusi durante la preparazione della consegna (regole di tipologia, quarantena) non vengono presi in considerazione. Un profilo di destinazione per più consegne verrà conteggiato una sola volta. Nella parte inferiore del rapporto, troverete l&#39;elenco dei profili attivi per ogni dimensione di targeting.

![](assets/audience_active_profiles2.png)

Se siete ospitati su AWS e utilizzate Campaign Standard dalla build 10368, potete anche monitorare il numero di profili attivi utilizzati sulle istanze direttamente dal Pannello di controllo. Per ulteriori informazioni, consulta la documentazione [del Pannello di](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html)controllo.
