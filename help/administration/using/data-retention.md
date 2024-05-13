---
title: Conservazione dei dati
description: Informazioni sui valori di conservazione predefiniti per le tabelle standard
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 2e81a05b1b647991250d13d7d37f5da275a8db44
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 5%

---

# Conservazione dei dati{#data-retention}

Le tabelle di registro standard in Campaign dispongono di periodi di conservazione preimpostati che limitano la durata di archiviazione dei dati, per evitare un sovraccarico del sistema.

La configurazione della conservazione dei dati è impostata dagli amministratori tecnici Adobi durante l’implementazione e i valori possono variare per ogni implementazione, in base ai requisiti dei clienti.

Rivolgiti ai consulenti o agli amministratori tecnici di Adobe per ulteriori informazioni sui periodi di conservazione applicabili al tuo ambiente o per impostare periodi di conservazione personalizzati.

Tieni presente che utilizzando la funzionalità standard del flusso di lavoro, è possibile impostare periodi di conservazione per qualsiasi tabella personalizzata.

Di seguito sono riportati i periodi di conservazione predefiniti per le tabelle standard. Quando possibile, e a seconda dell’utilizzo dei dati, Adobe ti consiglia di passare ai periodi di conservazione consigliati per migliorare le prestazioni dell’istanza Campaign.

* **Tracciamento consolidato**: 6 mesi (consigliato: 1 mese)
* **Registri di consegna**: 6 mesi (consigliato: 1 mese)
* **Registri di tracciamento**: 6 mesi (consigliato: 1 mese)
* **Eventi**: 1 mese
* **Statistiche sull’elaborazione degli eventi**: 6 mesi (consigliato: 1 mese)
* **Eventi archiviati**: 6 mesi (consigliato: 1 mese)
* **Entità temporanee**: 7 giorni
* **Eventi pipeline ignorati**: 1 mese
* **Avvisi di consegna**: 1 mese
* **Esporta controllo**: 6 mesi (consigliato: 1 mese)

## Periodo di conservazione per le consegne {#deliveries}

Per impostazione predefinita, il periodo di conservazione per le consegne è illimitato.

Tuttavia, se il volume di consegne nell’istanza è elevato, puoi aggiornare **NmsCleanup_DeliveryPurgeDelay** opzione disponibile dal **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** menu.

Ogni volta che **[!UICONTROL Database cleanup]** viene eseguito il flusso di lavoro, le consegne che soddisfano le condizioni impostate per questa opzione verranno eliminate.

Questa azione può contribuire ad accelerare processi quali **[!UICONTROL Copy headers from delivery templates]** flusso di lavoro.

>[!NOTE]
>
>Ulteriori informazioni sui flussi di lavoro tecnici in [questa sezione](technical-workflows.md).


Il valore predefinito per **NmsCleanup_DeliveryPurgeDelay** l&#39;opzione è `-1`. In questo caso, non viene eliminata alcuna consegna.

Ad esempio, se lo imposti su `180`, tutte le consegne non basate su modello che non sono state aggiornate negli ultimi 180 giorni verranno eliminate quando **[!UICONTROL Database cleanup]** flusso di lavoro eseguito.

>[!NOTE]
>
>* I modelli di consegna transazionale o di marketing non verranno eliminati.
>
>* Per le consegne ricorrenti, le consegne secondarie con periodo di aggregazione impostato come mese o anno non verranno eliminate.

Quando si aggiorna **NmsCleanup_DeliveryPurgeDelay** opzione, si consiglia di procedere gradualmente con più iterazioni. Ad esempio, puoi impostare il valore su 300 giorni, poi su 180 giorni, quindi su 120 giorni e così via, assicurandoti che le iterazioni siano a distanza di almeno 2 giorni. In caso contrario, **[!UICONTROL Database cleanup]** il flusso di lavoro potrebbe richiedere molto più tempo a causa del numero elevato di consegne da eliminare.

