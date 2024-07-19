---
title: Monitoraggio delle modifiche al modello dati
description: Scopri come diagnosticare il modello dati di Adobe Campaign.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ced9a897-47e9-4128-84fb-35660c553cd4
source-git-commit: 5fef74296a4790102c75e609c270e52d5ead1d58
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 8%

---

# Monitoraggio delle modifiche al modello dati{#monitoring-data-model-changes}

Dal menu **[!UICONTROL Diagnosis]** è possibile visualizzare gli oggetti tecnici generati dall&#39;applicazione per analizzarli.

>[!NOTE]
>
>Le schermate di questo menu sono di sola lettura.

![](assets/diagnostic.png)

È possibile visualizzare i seguenti tipi di oggetti:

* Schemi di dati
* Pagine web
* Filtri
* Navigazione
* Componenti
* Processi batch

Puoi modificare la configurazione dell’elenco:

* È possibile aggiungere e rimuovere colonne.
* Puoi definire i nomi delle colonne.
* È possibile definire l&#39;ordine di visualizzazione delle colonne nell&#39;elenco.
* È possibile scegliere l&#39;ordinamento dei valori nell&#39;elenco.

Puoi filtrare l’elenco:

* Puoi includere o escludere schemi di dati nativi, pagine web, filtri e oggetti di navigazione.
* È possibile cercare gli oggetti in base al nome.
* È possibile filtrare i processi batch in base al loro stato, alla data di inizio e alla data di fine.

Puoi scaricare l’elenco visualizzato in un file in formato TXT con valori separati da virgola.

È possibile visualizzare i dettagli dell&#39;oggetto selezionato.

Ad esempio, puoi utilizzare questa funzione per visualizzare i criteri di filtraggio dei filtri preconfigurati. Questo esempio mostra il codice visualizzato per i criteri di filtro di un filtro preconfigurato:

```xml
<where displayFilter="Has clicked an offer">
  <condition boolOperator="AND" enabledIf="$(offer) != ''" expr="trackingLog" internalId="1" setOperator="EXISTS">
    <condition boolOperator="AND" expr="[url/offer] = $RestKey(offer)" internalId="2"/>
    <condition boolOperator="AND" expr="[@url-id] != 1" internalId="3"/>
  </condition>
</where>
```

![](assets/diagnosis_filter_criteria.png)