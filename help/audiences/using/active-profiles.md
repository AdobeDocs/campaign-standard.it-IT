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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 1%

---


# Profili attivi{#active-profiles}

 Adobe Campaign fornisce un rapporto che mostra il numero di profili attivi. Questo rapporto è solo informativo, non ha un impatto diretto sulla fatturazione. Solo gli amministratori possono accedere a questo rapporto, in **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>Se siete ospitati su AWS e utilizzate Campaign Standard dalla build 10368, potete anche monitorare il numero di profili attivi utilizzati sulle istanze direttamente dal Pannello di controllo Campaign. For more on this, refer to the [Control Panel documentation](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
>La metrica Profili attivi è disponibile e pertinente solo per le istanze **** Marketing. Non è né applicabile né disponibile per le istanze di esecuzione, ovvero le istanze MID (mid-sourcing) e RT (Message Center / Real-time messaging).


I profili esclusi durante la preparazione della consegna (regole di tipologia, quarantena, gruppi di controllo) non vengono presi in considerazione. Un profilo di destinazione per più consegne verrà conteggiato una sola volta. Nella parte inferiore del rapporto, troverete l&#39;elenco dei profili attivi per ogni dimensione di targeting.

Questo rapporto viene generato ogni mese dal flusso di lavoro **[!UICONTROL Billing]** tecnico. Contiene il numero di profili attivi a cui è stato assegnato il targeting durante l&#39;ultimo periodo continuo di 12 mesi.

Si noti che i profili esclusi durante la preparazione della consegna (regole di tipologia, quarantena) non sono presi in considerazione. Inoltre, un profilo mirato da più consegne sarà conteggiato una sola volta.

![](assets/audience_active_profiles2.png)

In fondo al rapporto, troverai l&#39;elenco dei profili attivi elaborati dal flusso di lavoro di fatturazione:

* L&#39; **[!UICONTROL NmsRecipient]** origine include tutti i clienti che sono stati contattati utilizzando informazioni provenienti dal loro profilo Campaign Standard.

* D&#39;altro canto, i clienti ai quali è stato eseguito il targeting utilizzando solo un&#39;informazione specifica (indirizzo e-mail, numero di telefono), senza alcuna relazione con il loro profilo Campaign, saranno inclusi nella **[!UICONTROL anonymous]** fonte.
