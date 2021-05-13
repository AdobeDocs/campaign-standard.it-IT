---
solution: Campaign Standard
product: campaign
title: Profili attivi della campagna
description: Scopri come accedere alle metriche del cliente e ai profili attivi
feature: Profili
role: Business Practitioner
level: Intermediate
exl-id: 22516348-7695-4579-99eb-480e5b723ccc
source-git-commit: d2fcf2ca22bb5fe3632280f922dfed0972f6eb09
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 1%

---

# Metriche del cliente {#customer-metrics}

Gli amministratori funzionali di Campaign possono accedere al rapporto **[!UICONTROL Customer metrics]** da **[!UICONTROL Administration > Customer metrics]**.

![](assets/audience_active_profiles1.png)

Viene visualizzato il rapporto:

* ID Experience Cloud
* ID organizzazione IMS
* il numero di **profili attivi**
* l’elenco delle dimensioni di targeting disponibili nell’istanza

Questo rapporto viene generato ogni mese dal flusso di lavoro tecnico **[!UICONTROL Billing]** .

## Profili attivi{#active-profiles}

In base al contratto, a ciascuna istanza di Campaign viene fornito un numero specifico di profili attivi. Fai riferimento al tuo contratto di licenza per riferimento al numero di profili attivi acquistati.

>[!NOTE]
>
>In qualità di utente amministratore, puoi anche monitorare il numero di profili attivi utilizzati sulle istanze direttamente dal Pannello di controllo Campaign. Per ulteriori informazioni, consulta la [documentazione del Pannello di controllo Campaign](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/active-profiles-monitoring.html).


Un &quot;profilo&quot; è un record di informazioni che rappresenta un cliente finale, potenziale cliente o lead. I profili sono considerati **attivi** se sono stati targetizzati da una consegna Campaign negli ultimi 12 mesi tramite qualsiasi canale. I profili esclusi durante la preparazione della consegna (ad esempio mediante regole di tipologia o un meccanismo di quarantena) non vengono presi in considerazione. Un profilo per il quale sono state eseguite le destinazioni da più consegne verrà conteggiato una sola volta. Questo rapporto è solo informativo, non ha un impatto diretto sulla fatturazione.

![](assets/audience_active_profiles2.png)

Nella parte inferiore del rapporto, troverai l’elenco dei profili attivi per ogni dimensione di targeting. Mostra il numero di profili attivi target negli ultimi 12 mesi.

* L’ origine **[!UICONTROL NmsRecipient]** include tutti i profili contattati utilizzando le informazioni del profilo Campaign Standard.

* L’origine dei clienti **[!UICONTROL anonymous]** mostra il numero di profili target mirati utilizzando solo una parte specifica di informazioni (indirizzo e-mail, numero di telefono), senza alcuna relazione con il loro profilo Campaign.
