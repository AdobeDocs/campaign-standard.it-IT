---
solution: Campaign Standard
product: campaign
title: Profili attivi
description: Puoi accedere a un rapporto dedicato sulle metriche del cliente e visualizzare i profili attivi nel database Campaign.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profili
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 1%

---


# Profili attivi{#active-profiles}

Adobe Campaign fornisce un rapporto che mostra il numero di profili attivi. Questo rapporto è solo informativo, non ha un impatto diretto sulla fatturazione. Solo gli amministratori possono accedere a questo rapporto, in **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

>[!NOTE]
>
>Se utilizzi AWS e Campaign Standard dalla build 10368, puoi anche monitorare il numero di profili attivi utilizzati sulle istanze direttamente dal Pannello di controllo Campaign. Per ulteriori informazioni, consulta la [documentazione del Pannello di controllo Campaign](https://docs.adobe.com/content/help/en/control-panel/using/performance-monitoring/active-profiles-monitoring.html).
>
>La metrica dei profili attivi è disponibile e pertinente solo per **istanze di marketing**. Non è né applicabile né disponibile per le istanze di esecuzione, ovvero le istanze MID (mid sourcing) e RT (Message Center / Real-time messaging [Centro messaggi/Messaggistica in tempo reale]).


I profili esclusi durante la preparazione della consegna (regole di tipologia, quarantena, gruppi di controllo) non vengono presi in considerazione. Un profilo per il quale sono state eseguite le destinazioni da più consegne verrà conteggiato una sola volta. Nella parte inferiore del rapporto, troverai l’elenco dei profili attivi per ogni dimensione di targeting.

Questo rapporto viene generato ogni mese dal flusso di lavoro tecnico **[!UICONTROL Billing]** . Contiene il numero di profili attivi oggetto di targeting durante l’ultimo periodo continuo di 12 mesi.

I profili esclusi durante la preparazione della consegna (regole di tipologia, quarantena) non vengono presi in considerazione. Inoltre, un profilo che è stato oggetto di targeting da diverse consegne verrà conteggiato una sola volta.

![](assets/audience_active_profiles2.png)

Nella parte inferiore del rapporto trovi l’elenco dei profili attivi elaborati dal flusso di lavoro di fatturazione:

* La sorgente **[!UICONTROL NmsRecipient]** include tutti i clienti che sono stati contattati utilizzando informazioni dal loro profilo Campaign Standard.

* D’altro canto, i clienti target mirati utilizzando solo una parte specifica di informazioni (indirizzo e-mail, numero di telefono), senza alcuna relazione con il loro profilo Campaign, saranno inclusi nella **[!UICONTROL anonymous]** sorgente.
