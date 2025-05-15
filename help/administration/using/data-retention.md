---
title: Conservazione dei dati
description: Informazioni sui valori di conservazione predefiniti per le tabelle standard
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 2bc6ce04d2580b561bfdaafe29985353fd116a42
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 5%

---

# Conservazione dei dati{#data-retention}

>[!NOTE]
>
>La segnalazione dei dati è disponibile solo per gli ultimi due anni. Per ulteriori informazioni sui periodi di conservazione dei dati, contatta i consulenti Adobe o i tuoi amministratori tecnici.

Le tabelle di registro standard in Campaign dispongono di periodi di conservazione preimpostati che limitano la durata di archiviazione dei dati, per evitare un sovraccarico del sistema.

La configurazione della conservazione dei dati viene impostata dagli amministratori tecnici di Adobe durante l’implementazione e i valori possono variare per ogni implementazione, in base ai requisiti dei clienti.

Rivolgiti ai consulenti o agli amministratori tecnici di Adobe per ulteriori informazioni sui periodi di conservazione applicabili al tuo ambiente o per impostare periodi di conservazione personalizzati.

Tieni presente che utilizzando la funzionalità standard del flusso di lavoro, è possibile impostare periodi di conservazione per qualsiasi tabella personalizzata.

Di seguito sono riportati i periodi di conservazione predefiniti per le tabelle standard. Quando possibile, e a seconda dell’utilizzo dei dati, Adobe ti consiglia di passare ai periodi di conservazione consigliati per migliorare le prestazioni dell’istanza Campaign.

* **Tracciamento consolidato**: 6 mesi (consigliato: 1 mese)
* **Registri di consegna**: 6 mesi (consigliato: 1 mese)
* **Registri di tracciamento**: 6 mesi (consigliato: 1 mese)
* **Eventi**: 1 mese
* **Statistiche sull&#39;elaborazione dell&#39;evento**: 6 mesi (consigliato: 1 mese)
* **Eventi archiviati**: 6 mesi (consigliato: 1 mese)
* **Entità temporanee**: 7 giorni
* **Eventi pipeline ignorati**: 1 mese
* **Avvisi di consegna**: 1 mese
* **Controllo delle esportazioni**: 6 mesi (consigliato: 1 mese)
* **Consegne**: 2 anni

## Periodo di conservazione per le consegne {#deliveries}

<!-- By default, the retention period for deliveries is unlimited.-->

A decorrere dal 1° giugno 2025, solo le consegne degli ultimi due anni rimarranno disponibili nel sistema. Di seguito sono riportati ulteriori dettagli:

* Tutte le consegne più vecchie di due anni verranno rimosse definitivamente e non saranno più accessibili.
* Questa pulizia include solo le consegne inviate e non riuscite; le consegne ricorrenti, le bozze e i modelli non saranno interessati.
* Dopo la rimozione di una consegna, verranno eliminate in modo permanente anche tutte le informazioni di tracciamento o invio collegate.
* I modelli di consegna transazionale o di marketing non verranno eliminati.
* Per le consegne ricorrenti, le consegne secondarie con periodo di aggregazione impostato come mese o anno non verranno eliminate.

Se desideri velocizzare processi come il flusso di lavoro **[!UICONTROL Copy headers from delivery templates]**, il periodo di conservazione della consegna può essere ridotto. Per farlo, contatta il tuo rappresentante Adobe.

<!--

However, if there is a high volume of deliveries on your instance, you can update the **NmsCleanup_DeliveryPurgeDelay** option available from the **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** menu.

Each time the **[!UICONTROL Database cleanup]** workflow is run, the deliveries meeting the conditions set for this option will be deleted.

-->

<!--

When updating the **NmsCleanup_DeliveryPurgeDelay** option, it is recommended to proceed gradually with multiple iterations. For example, you can start by setting the value to 300 days, then 180 days, then 120 days, and so on - making sure iterations are at least 2 days apart. Otherwise, the **[!UICONTROL Database cleanup]** workflow may take much longer because of a large number of deliveries to delete.

This action can help speeding up processes such as the **[!UICONTROL Copy headers from delivery templates]** workflow. Learn more on technical workflows in [this section](technical-workflows.md).

The default value for the **NmsCleanup_DeliveryPurgeDelay** option is `-1`. In this case, no delivery is deleted.

For example, if you set it to `180`, any non-template deliveries that have not been updated in the last 180 days will be deleted when the **[!UICONTROL Database cleanup]** workflow is run.

-->


