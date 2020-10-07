---
title: Personalizzazione di un’e-mail con dati aggiuntivi
description: Questo caso di utilizzo illustra come aggiungere diversi tipi di dati aggiuntivi a una query e utilizzarli come campo di personalizzazione in un messaggio e-mail.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 86%

---


# Personalizzazione di un’e-mail con dati aggiuntivi {#example--personalizing-an-email-with-additional-data}

L’esempio seguente illustra l’aggiunta di diversi tipi di dati aggiuntivi a una query e il relativo utilizzo come campo di personalizzazione in un messaggio e-mail. Per ulteriori informazioni su come arricchire i dati di destinazione per un&#39; **[!UICONTROL Query]** attività, consulta [questa sezione](../../automating/using/query.md#enriching-data).

In questo esempio vengono utilizzate [risorse personalizzate](../../developing/using/data-model-concepts.md):

* La risorsa **profilo** è stata estesa per aggiungere un campo che consente di salvare i punti fedeltà di ogni profilo.
* È stata creata una risorsa **transazioni** che identifica tutti gli acquisti effettuati dai profili nel database. La data, il prezzo e il prodotto acquistato vengono salvati per ogni transazione.
* È stata creata una risorsa **prodotti** che fa riferimento ai prodotti disponibili per l’acquisto.

L’obiettivo è quello di inviare un messaggio e-mail ai profili per i quali è stata salvata almeno una transazione. Tramite questa e-mail, i clienti ricevono un promemoria dell’ultima transazione effettuata e una panoramica di tutte le loro transazioni: il numero di prodotti acquistati, il totale speso, un promemoria del numero totale dei punti fedeltà maturati.

Il flusso di lavoro viene presentato come segue:

![](assets/enrichment_example1.png)

1. Add a [Query](../../automating/using/query.md) activity, which allows you to target the profiles that have carried out at least one transaction.

   ![](assets/enrichment_example2.png)

1. Definisci i diversi dati da visualizzare nell’e-mail finale dalla scheda **[!UICONTROL Additional data]** della query:

   * Il campo semplice della dimensione **profilo** corrispondente ai punti fedeltà. Consulta la sezione [Aggiunta di un campo semplice](../../automating/using/query.md#adding-a-simple-field).
   * Due aggregati basati sulla raccolta delle transazioni: il numero dei prodotti acquistati e l’importo totale speso. Puoi aggiungerli dalla scheda **[!UICONTROL Data]** della finestra di configurazione dell’aggregato utilizzando gli aggregati **Count** e **Sum**. Consulta la sezione [Aggiunta di un aggregato](../../automating/using/query.md#adding-an-aggregate).
   * Una raccolta che restituisce l’importo speso, la data e il prodotto dell’ultima transazione effettuata.

      A questo scopo, devi aggiungere i diversi campi da visualizzare dalla scheda **[!UICONTROL Data]** della finestra di configurazione della raccolta.

      Per restituire solo la transazione più recente, devi immettere &quot;1&quot; per il **[!UICONTROL Number of lines to return]** e dalla scheda **[!UICONTROL Sort]** applicare un ordinamento decrescente nel campo **Date** della raccolta.

      Consulta le sezioni [Aggiunta di una raccolta](../../automating/using/query.md#adding-a-collection) e [Ordinamento dei dati aggiuntivi](../../automating/using/query.md#sorting-additional-data).
   ![](assets/enrichment_example4.png)

1. Se desideri verificare che i dati siano correttamente trasferiti dalla transizione in uscita dell’attività, avvia il flusso di lavoro per la prima volta (senza l’attività **[!UICONTROL Email delivery]**) e apri la transizione in uscita della query.

   ![](assets/enrichment_example5.png)

1. Aggiungete un&#39;attività di consegna [tramite e-](../../automating/using/email-delivery.md) mail. Nel contenuto dell’e-mail, inserisci i campi di personalizzazione corrispondenti ai dati calcolati nella query. Puoi trovarli tramite il collegamento **[!UICONTROL Additional data (targetData)]** dell’explorer dei campi di personalizzazione.

   ![](assets/enrichment_example3.png)

Puoi ora eseguire il flusso di lavoro. I profili interessati dal targeting nella query ricevono un’e-mail personalizzata contenente i dati calcolati a partire dalle loro transazioni.
