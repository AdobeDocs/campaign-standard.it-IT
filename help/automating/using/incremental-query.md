---
title: Query incrementale
description: L'attività query incrementale consente di filtrare ed estrarre una serie di elementi dal database del Adobe Campaign .
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
source-wordcount: '0'
ht-degree: 0%

---


# Query incrementale{#incremental-query}

## Descrizione {#description}

![](assets/incremental.png)

L&#39; **[!UICONTROL Incremental query]** attività consente di filtrare ed estrarre una serie di elementi dal database del Adobe Campaign . Ogni volta che questa attività viene eseguita, i risultati delle esecuzioni precedenti sono esclusi. Questo consente di eseguire il targeting solo dei nuovi elementi.

È possibile definire **[!UICONTROL Additional data]** per la popolazione di destinazione tramite una scheda dedicata. Questi dati vengono memorizzati in colonne aggiuntive e possono essere utilizzati solo per il flusso di lavoro in corso.

L&#39;attività utilizza lo strumento di editor di query. Questo strumento è dettagliato in una sezione [](../../automating/using/editing-queries.md#about-query-editor)dedicata.

## Contesto di utilizzo {#context-of-use}

Per definire la frequenza di esecuzione del flusso di lavoro, e quindi la query, **[!UICONTROL Incremental query]** è necessario collegare un oggetto **[!UICONTROL Scheduler]** a un oggetto.

La **[!UICONTROL Processed data]** scheda, specifica per questa attività, consente di visualizzare eventuali risultati delle esecuzioni precedenti dell&#39;attività, se necessario.

L&#39; **[!UICONTROL Incremental query]** attività può essere utilizzata per vari tipi di usi:

* Segmentazione di singoli utenti per definire la destinazione di un messaggio, un pubblico ecc.

* Esportazione dei dati.

   Potete utilizzare un&#39; **[!UICONTROL Incremental query]** attività per esportare regolarmente nuovi file di registro. Può essere utile, ad esempio, se si desidera utilizzare i dati di registro in strumenti di reporting o BI esterni. Un esempio completo è disponibile nella sezione [Esportazione dei registri](../../automating/using/exporting-logs.md) .

**Argomenti correlati**

* [Caso di utilizzo: Query incrementale sugli abbonati a un servizio](../../automating/using/incremental-query-on-subscribers.md)

## Configurazione {#configuration}

1. Trascinate e rilasciate un&#39; **[!UICONTROL Incremental query]** attività nel flusso di lavoro.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Se desiderate eseguire una query su una risorsa diversa dalla risorsa del profilo, andate alla **[!UICONTROL Properties]** scheda dell&#39;attività e selezionate un **[!UICONTROL Resource]** e un **[!UICONTROL Targeting dimension]**.

   Questo **[!UICONTROL Resource]** consente di perfezionare i filtri visualizzati nella palette, mentre il **[!UICONTROL Targeting dimension]**, contestuale rispetto alla risorsa selezionata, corrisponde al tipo di popolazione che si desidera ottenere (profili identificati, consegne, dati collegati alla risorsa selezionata, ecc.).

1. Nella **[!UICONTROL Target]** scheda, eseguire la query definendo e combinando le regole.
1. Nella **[!UICONTROL Processed data]** scheda, scegliete la modalità incrementale da utilizzare per le successive esecuzioni del flusso di lavoro:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: sono esclusi i risultati delle esecuzioni precedenti per ogni nuova esecuzione.
   * **[!UICONTROL Use a date field]**: le esecuzioni successive tengono conto solo dei risultati con il campo data selezionato maggiore o uguale all&#39;ultima data di esecuzione dell&#39; **[!UICONTROL Incremental query]** attività. È possibile selezionare qualsiasi campo data relativo alla risorsa selezionata nella **[!UICONTROL Properties]** scheda. Questa modalità offre prestazioni migliori quando si esegue una query su risorse di grandi dimensioni come i dati di registro.

      Dopo la prima esecuzione del flusso di lavoro, in questa scheda puoi vedere l&#39;ultima data di esecuzione che verrà utilizzata per l&#39;esecuzione successiva. Viene aggiornato automaticamente ogni volta che viene eseguito il flusso di lavoro. Potete comunque ignorare questo valore immettendo manualmente un nuovo valore in modo che sia adatto alle vostre esigenze.
   >[!NOTE]
   >
   >La **[!UICONTROL Use a date field]** modalità consente una maggiore flessibilità a seconda del campo data selezionato. Ad esempio, se il campo selezionato corrisponde a una data di modifica, la modalità campo data consente di recuperare i dati che sono stati aggiornati di recente, mentre l&#39;altra modalità esclude semplicemente le registrazioni che erano già state oggetto di un&#39;esecuzione precedente, anche se sono state modificate dopo l&#39;ultima esecuzione del flusso di lavoro.

   ![](assets/incremental_query_usedatefield.png)

1. È possibile definire **[!UICONTROL Additional data]** per la popolazione di destinazione tramite una scheda dedicata. Questi dati vengono memorizzati in colonne aggiuntive e possono essere utilizzati solo per il flusso di lavoro in corso. In particolare, è possibile aggiungere dati dalle tabelle del database del Adobe Campaign  collegate alla dimensione di targeting della query. Consulta la sezione [Arricchimento dei dati](../../automating/using/query.md#enriching-data) .
1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.

## Arricchimento dei dati {#enriching-data}

Come per una query, potete arricchire i dati da un **[!UICONTROL Incremental query]**. Consulta la sezione [Arricchimento dei dati](../../automating/using/query.md#enriching-data) .
