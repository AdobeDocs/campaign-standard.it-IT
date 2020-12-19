---
solution: Campaign Standard
product: campaign
title: Profili attivi
description: Puoi accedere a un rapporto dedicato sulle metriche dei clienti e visualizzare i profili attivi nel database Campaign.
audience: audiences
content-type: reference
topic-tags: managing-profiles
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 1%

---


# Profili attivi{#active-profiles}

 Adobe Campaign fornisce un rapporto che mostra il numero di profili attivi. Questo rapporto è solo informativo, non ha un impatto diretto sulla fatturazione. Solo gli amministratori possono accedere a questo rapporto, in **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>Se siete ospitati su AWS e utilizzate Campaign Standard dalla build 10368, potete anche monitorare il numero di profili attivi utilizzati sulle istanze direttamente dal Pannello di controllo Campaign. Per ulteriori informazioni, consultare la [documentazione del Pannello di controllo Campaign](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
>La metrica Profili attivi è disponibile e pertinente solo per **Istanze marketing**. Non è né applicabile né disponibile per le istanze di esecuzione, ovvero le istanze MID (mid-sourcing) e RT (Message Center / Real-time messaging).


I profili esclusi durante la preparazione della consegna (regole di tipologia, quarantena, gruppi di controllo) non vengono presi in considerazione. Un profilo di destinazione per più consegne verrà conteggiato una sola volta. Nella parte inferiore del rapporto, troverete l&#39;elenco dei profili attivi per ogni dimensione di targeting.

Questo rapporto viene generato ogni mese dal **[!UICONTROL Billing]** flusso di lavoro tecnico. Contiene il numero di profili attivi a cui è stato assegnato il targeting durante l&#39;ultimo periodo continuo di 12 mesi.

Si noti che i profili esclusi durante la preparazione della consegna (regole di tipologia, quarantena) non sono presi in considerazione. Inoltre, un profilo mirato da più consegne sarà conteggiato una sola volta.

![](assets/audience_active_profiles2.png)

In fondo al rapporto, troverai l&#39;elenco dei profili attivi elaborati dal flusso di lavoro di fatturazione:

* L&#39;origine **[!UICONTROL NmsRecipient]** include tutti i clienti che sono stati contattati utilizzando le informazioni del loro profilo Campaign Standard.

* D&#39;altro canto, i clienti con targeting basato solo su una specifica informazione (indirizzo e-mail, numero di telefono), senza alcuna relazione con il profilo Campaign, saranno inseriti nella fonte **[!UICONTROL anonymous]**.
