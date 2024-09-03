---
title: Conservazione dei dati
description: Informazioni sui valori di conservazione predefiniti per le tabelle standard
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: 01cfa2a0-4ff5-4520-a515-11676de82528
source-git-commit: 99c092bc40c9176a25a6ec2a164ee1d3f85d5cbe
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 4%

---

# Conservazione dei dati{#data-retention}

>[!NOTE]
>
>La comunicazione dei dati è disponibile solo per gli ultimi tre anni. Per ulteriori informazioni sui periodi di conservazione dei dati, contatta i consulenti Adobe o i tuoi amministratori tecnici.

Le tabelle di registro standard in Campaign dispongono di periodi di conservazione preimpostati che limitano la durata di archiviazione dei dati, per evitare un sovraccarico del sistema.

La configurazione della conservazione dei dati è impostata dagli amministratori tecnici Adobi durante l’implementazione e i valori possono variare per ogni implementazione, in base ai requisiti dei clienti.

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

## Periodo di conservazione per le consegne {#deliveries}

Per impostazione predefinita, il periodo di conservazione per le consegne è illimitato.

Tuttavia, se nell&#39;istanza è presente un numero elevato di consegne, è possibile aggiornare l&#39;opzione **NmsCleanup_DeliveryPurgeDelay** disponibile nel menu **[!UICONTROL Administration]** > **[!UICONTROL Application settings]**.

Ogni volta che si esegue il flusso di lavoro **[!UICONTROL Database cleanup]**, le consegne che soddisfano le condizioni impostate per questa opzione verranno eliminate.

Questa azione può contribuire a velocizzare processi come il flusso di lavoro **[!UICONTROL Copy headers from delivery templates]**.

>[!NOTE]
>
>Ulteriori informazioni sui flussi di lavoro tecnici in [questa sezione](technical-workflows.md).


Il valore predefinito per l&#39;opzione **NmsCleanup_DeliveryPurgeDelay** è `-1`. In questo caso, non viene eliminata alcuna consegna.

Ad esempio, se lo imposti su `180`, tutte le consegne non basate su modello che non sono state aggiornate negli ultimi 180 giorni verranno eliminate quando viene eseguito il flusso di lavoro **[!UICONTROL Database cleanup]**.

>[!NOTE]
>
>* I modelli di consegna transazionale o di marketing non verranno eliminati.
>
>* Per le consegne ricorrenti, le consegne secondarie con periodo di aggregazione impostato come mese o anno non verranno eliminate.

Quando si aggiorna l&#39;opzione **NmsCleanup_DeliveryPurgeDelay**, si consiglia di procedere gradualmente con più iterazioni. Ad esempio, puoi impostare il valore su 300 giorni, poi su 180 giorni, quindi su 120 giorni e così via, assicurandoti che le iterazioni siano a distanza di almeno 2 giorni. In caso contrario, il flusso di lavoro **[!UICONTROL Database cleanup]** potrebbe richiedere molto più tempo a causa del numero elevato di consegne da eliminare.

