---
title: Incremental query
description: L’attività Incremental query ti consente di filtrare ed estrarre una popolazione di elementi dal database di Adobe Campaign.
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 98%

---


# Incremental query{#incremental-query}

## Descrizione {#description}

![](assets/incremental.png)

L’attività **[!UICONTROL Incremental query]** ti consente di filtrare ed estrarre una popolazione di elementi dal database di Adobe Campaign. Ogni volta che questa attività viene eseguita, i risultati delle esecuzioni precedenti sono esclusi. Ciò ti consente di eseguire il targeting solo per nuovi elementi.

Puoi definire **[!UICONTROL Additional data]** per la popolazione target tramite una scheda dedicata. Questi dati vengono memorizzati in colonne aggiuntive e possono essere utilizzati solo per il flusso di lavoro in corso.

L’attività utilizza lo strumento editor delle query. Questo strumento è descritto in una [sezione dedicata](../../automating/using/editing-queries.md#about-query-editor).

## Contesto di utilizzo {#context-of-use}

Per definire la frequenza di esecuzione del flusso di lavoro, e quindi della query, è necessario collegare una **[!UICONTROL Incremental query]** a una **[!UICONTROL Scheduler]**.

La scheda **[!UICONTROL Processed data]**, specifica per questa attività, ti consente di visualizzare eventuali risultati delle esecuzioni precedenti dell’attività, se necessario.

L’attività **[!UICONTROL Incremental query]** può avere vari tipi di utilizzi:

* Segmentazione di singoli utenti per definire il target di un messaggio, un pubblico, ecc.

* Esportazione dei dati.

   Puoi utilizzare un’attività **[!UICONTROL Incremental query]** per esportare regolarmente i nuovi registri in file. Può essere utile, ad esempio, se desideri utilizzare i dati di registro in strumenti di reporting o BI esterni. Un esempio completo è disponibile nella sezione [Esportazione dei registri](../../automating/using/exporting-logs.md).

**Argomenti correlati**

* [Caso di utilizzo: Query incrementale sugli abbonati a un servizio](../../automating/using/incremental-query-on-subscribers.md)

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Incremental query]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Se desideri eseguire una query su una risorsa diversa da quella del profilo, passa alla scheda **[!UICONTROL Properties]** dell’attività e seleziona una **[!UICONTROL Resource]** e una **[!UICONTROL Targeting dimension]**.

   La **[!UICONTROL Resource]** ti consente di perfezionare i filtri visualizzati nella palette, mentre la **[!UICONTROL Targeting dimension]**, contestuale rispetto alla risorsa selezionata, corrisponde al tipo di popolazione che desideri ottenere (profili identificati, consegne, dati collegati alla risorsa selezionata, ecc.).

1. Nella scheda **[!UICONTROL Target]**, esegui la query definendo e combinando regole.
1. Nella scheda **[!UICONTROL Processed data]**, scegli la modalità incrementale da utilizzare per le successive esecuzioni del flusso di lavoro:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: i risultati delle esecuzioni precedenti per ciascuna nuova esecuzione sono esclusi.
   * **[!UICONTROL Use a date field]**: le esecuzioni successive tengono conto solo dei risultati con il campo data selezionato maggiore o uguale all’ultima data di esecuzione dell’attività **[!UICONTROL Incremental query]**. Puoi selezionare qualsiasi campo data relativo alla risorsa selezionata nella scheda **[!UICONTROL Properties]**. Questa modalità offre prestazioni migliori quando viene eseguita una query su risorse di grandi dimensioni quali i dati di registro.

      Dopo la prima esecuzione del flusso di lavoro, in questa scheda puoi vedere l’ultima data di esecuzione che verrà utilizzata per l’esecuzione successiva. Viene aggiornata automaticamente ogni volta che il flusso di lavoro viene eseguito. Puoi comunque ignorare questo valore immettendone manualmente uno nuovo in modo tale che sia adatto alle tue esigenze.
   >[!NOTE]
   >
   >La modalità **[!UICONTROL Use a date field]** consente una maggiore flessibilità a seconda del campo data selezionato. Ad esempio, se il campo selezionato corrisponde a una data di modifica, la modalità campo data ti consente di recuperare i dati che sono stati aggiornati di recente, mentre l’altra modalità esclude semplicemente le registrazioni che erano già state oggetto di targeting in un’esecuzione precedente, anche se sono state modificate dopo l’ultima esecuzione del flusso di lavoro.

   ![](assets/incremental_query_usedatefield.png)

1. Puoi definire **[!UICONTROL Additional data]** per la popolazione target tramite una scheda dedicata. Questi dati vengono memorizzati in colonne aggiuntive e possono essere utilizzati solo per il flusso di lavoro in corso. In particolare, puoi aggiungere dati dalle tabelle del database di Adobe Campaign collegate alla dimensione di targeting della query. Consulta la sezione [Arricchimento dei dati](../../automating/using/query.md#enriching-data).
1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

## Arricchimento dei dati {#enriching-data}

Proprio come per una query, puoi arricchire i dati da una **[!UICONTROL Incremental query]**. Consulta la sezione [Arricchimento dei dati](../../automating/using/query.md#enriching-data).
