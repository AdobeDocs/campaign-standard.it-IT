---
title: Query incrementale
description: L'attività di query incrementale consente di filtrare ed estrarre una serie di elementi dal database Adobe Campaign.
page-status-flag: mai attivato
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di targeting
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incrementale,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Query incrementale{#incremental-query}

## Descrizione {#description}

![](assets/incremental.png)

L' **[!UICONTROL Incremental query]** attività consente di filtrare ed estrarre una serie di elementi dal database di Adobe Campaign. Ogni volta che questa attività viene eseguita, i risultati delle esecuzioni precedenti sono esclusi. Questo consente di eseguire il targeting solo dei nuovi elementi.

È possibile definire **[!UICONTROL Additional data]** per la popolazione di destinazione tramite una scheda dedicata. Questi dati vengono memorizzati in colonne aggiuntive e possono essere utilizzati solo per il flusso di lavoro in corso.

L'attività utilizza lo strumento di editor di query. Questo strumento è dettagliato in una sezione [](../../automating/using/editing-queries.md#about-query-editor)dedicata.

## Contesto di utilizzo {#context-of-use}

Per definire la frequenza di esecuzione del flusso di lavoro, e quindi la query, **[!UICONTROL Incremental query]** è necessario collegare un oggetto **[!UICONTROL Scheduler]** a un oggetto.

La **[!UICONTROL Processed data]** scheda, specifica per questa attività, consente di visualizzare eventuali risultati delle esecuzioni precedenti dell'attività, se necessario.

L' **[!UICONTROL Incremental query]** attività può essere utilizzata per vari tipi di usi:

* Segmentazione di singoli utenti per definire la destinazione di un messaggio, un pubblico ecc.
* Esportazione dei dati.

## Configurazione {#configuration}

1. Trascinate e rilasciate un' **[!UICONTROL Incremental query]** attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Se desiderate eseguire una query su una risorsa diversa dalla risorsa del profilo, andate alla **[!UICONTROL Properties]** scheda dell'attività e selezionate un **[!UICONTROL Resource]** e un **[!UICONTROL Targeting dimension]**.

   Questo **[!UICONTROL Resource]** consente di perfezionare i filtri visualizzati nella palette, mentre il **[!UICONTROL Targeting dimension]**, contestuale rispetto alla risorsa selezionata, corrisponde al tipo di popolazione che si desidera ottenere (profili identificati, consegne, dati collegati alla risorsa selezionata, ecc.).

1. Nella **[!UICONTROL Target]** scheda, eseguire la query definendo e combinando le regole.
1. Nella **[!UICONTROL Processed data]** scheda, scegliete la modalità incrementale da utilizzare per le successive esecuzioni del flusso di lavoro:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: sono esclusi i risultati delle esecuzioni precedenti per ogni nuova esecuzione.
   * **[!UICONTROL Use a date field]**: le esecuzioni successive tengono conto solo dei risultati con il campo data selezionato maggiore o uguale all'ultima data di esecuzione dell' **[!UICONTROL Incremental query]** attività. È possibile selezionare qualsiasi campo data relativo alla risorsa selezionata nella **[!UICONTROL Properties]** scheda. Questa modalità offre prestazioni migliori quando si esegue una query su risorse di grandi dimensioni come i dati di registro.

      Dopo la prima esecuzione del flusso di lavoro, in questa scheda puoi vedere l'ultima data di esecuzione che verrà utilizzata per l'esecuzione successiva. Viene aggiornato automaticamente ogni volta che viene eseguito il flusso di lavoro. Potete comunque ignorare questo valore immettendo manualmente un nuovo valore in modo che sia adatto alle vostre esigenze.
   >[!NOTE]
   >
   >La **[!UICONTROL Use a date field]** modalità consente una maggiore flessibilità a seconda del campo data selezionato. Ad esempio, se il campo selezionato corrisponde a una data di modifica, la modalità campo data consente di recuperare i dati che sono stati aggiornati di recente, mentre l'altra modalità esclude semplicemente le registrazioni che erano già state oggetto di un'esecuzione precedente, anche se sono state modificate dopo l'ultima esecuzione del flusso di lavoro.

   ![](assets/incremental_query_usedatefield.png)

1. È possibile definire **[!UICONTROL Additional data]** per la popolazione di destinazione tramite una scheda dedicata. Questi dati vengono memorizzati in colonne aggiuntive e possono essere utilizzati solo per il flusso di lavoro in corso. In particolare, puoi aggiungere dati dalle tabelle del database Adobe Campaign collegate alla dimensione di targeting della query. Consultate la sezione [Arricchimento dei dati](../../automating/using/query.md#enriching-data) .
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Arricchimento dei dati {#enriching-data}

Come per una query, potete arricchire i dati da un **[!UICONTROL Incremental query]**. Consultate la sezione [Arricchimento dei dati](../../automating/using/query.md#enriching-data) .

## Esempio: query incrementale per gli abbonati a un servizio {#example--incremental-query-on-subscribers-to-a-service}

L'esempio seguente mostra la configurazione di un' **[!UICONTROL Incremental query]** attività che filtra i profili nel database Adobe Campaign sottoscritti al servizio **Running Newsletter** , per inviare loro un messaggio e-mail di benvenuto contenente un codice promozionale.

Il flusso di lavoro è costituito dai seguenti elementi:

![](assets/incremental_query_example1.png)

* Un' **[!UICONTROL Scheduler]** attività, per eseguire il flusso di lavoro ogni lunedì alle 6.

   ![](assets/incremental_query_example2.png)

* Un' **[!UICONTROL Incremental query]** attività, che esegue il targeting per tutti gli utenti correnti durante la prima esecuzione, quindi solo per i nuovi sottoscrittori della settimana durante le seguenti esecuzioni.

   ![](assets/incremental_query_example3.png)

* Un' **[!UICONTROL Email delivery]** attività. Il flusso di lavoro viene eseguito una volta alla settimana, ma potete aggregare i messaggi e-mail inviati e i risultati mensili, ad esempio per generare rapporti su un periodo di un intero mese e non solo una settimana.

   A questo scopo, scegliete di creare una **[!UICONTROL Recurring email]** struttura che raggruppa le e-mail e i risultati **[!UICONTROL By month]**.

   Definite il contenuto dell'e-mail e inserite il codice promozionale di benvenuto.

   Per ulteriori informazioni, consultate le sezioni [Invio](../../automating/using/email-delivery.md) e-mail e [Definizione del contenuto](../../designing/using/personalization.md) e-mail.

Quindi avviate l'esecuzione del flusso di lavoro. Ogni settimana i nuovi abbonati riceveranno l'e-mail di benvenuto con il codice promozionale.

## Esempio: query incrementale sui registri di consegna {#example--incremental-query-on-delivery-logs}

Potete utilizzare un' **[!UICONTROL Incremental query]** attività per esportare regolarmente nuovi file di registro. Può essere utile, ad esempio, se si desidera utilizzare i dati di registro in strumenti di reporting o BI esterni.

Un esempio completo è disponibile nella sezione [Esportazione dei registri](../../automating/using/exporting-logs.md) .
