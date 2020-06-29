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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---


# Personalizzazione di un’e-mail con dati aggiuntivi {#example--personalizing-an-email-with-additional-data}

L’esempio seguente illustra l’aggiunta di diversi tipi di dati aggiuntivi a una query e il relativo utilizzo come campo di personalizzazione in un messaggio e-mail. Per ulteriori informazioni su come arricchire i dati di destinazione per un&#39; **[!UICONTROL Query]** attività, consulta [questa sezione](../../automating/using/query.md#enriching-data).

In questo esempio vengono utilizzate risorse [](../../developing/using/data-model-concepts.md) personalizzate:

* La risorsa del **profilo** è stata estesa per aggiungere un campo che consente di salvare i punti fedeltà di ciascun profilo.
* È stata creata una risorsa di **transazioni** e identifica tutti gli acquisti effettuati dai profili nel database. La data, il prezzo e il prodotto acquistato vengono salvati per ogni transazione.
* È stata creata una risorsa **prodotto** che fa riferimento ai prodotti disponibili per l&#39;acquisto.

L&#39;obiettivo è quello di inviare un&#39;e-mail ai profili per i quali è stata salvata almeno una transazione. Tramite questa e-mail, i clienti riceveranno un promemoria dell&#39;ultima transazione effettuata e una panoramica di tutte le loro transazioni: il numero di prodotti acquistati, il totale speso, un promemoria del numero totale di punti fedeltà maturati.

Il flusso di lavoro viene presentato come segue:

![](assets/enrichment_example1.png)

1. Aggiungete un&#39;attività [Query](../../automating/using/query.md) , che consente di eseguire il targeting dei profili che hanno eseguito almeno una transazione.

   ![](assets/enrichment_example2.png)

   Dalla **[!UICONTROL Additional data]** scheda della query, definire i diversi dati da visualizzare nell&#39;e-mail finale:

   * Campo semplice della dimensione del **profilo** corrispondente ai punti fedeltà. Fare riferimento alla sezione [Aggiunta di un campo](../../automating/using/query.md#adding-a-simple-field) semplice.
   * Due aggregati basati sulla raccolta delle transazioni: il numero di prodotti acquistati e l&#39;importo totale speso. È possibile aggiungerli dalla **[!UICONTROL Data]** scheda della finestra di configurazione dell&#39;aggregato utilizzando gli aggregati **Count** e **Sum** . Fare riferimento alla sezione [Aggiunta di un aggregato](../../automating/using/query.md#adding-an-aggregate) .
   * Una raccolta che restituisce l&#39;importo speso, la data e il prodotto dell&#39;ultima operazione effettuata.

      A questo scopo, è necessario aggiungere i diversi campi che si desidera visualizzare dalla **[!UICONTROL Data]** scheda della finestra di configurazione della raccolta.

      Per restituire solo la transazione più recente, è necessario immettere &quot;1&quot; per l&#39;oggetto **[!UICONTROL Number of lines to return]** e applicare un ordinamento decrescente nel campo **Data** della raccolta dalla **[!UICONTROL Sort]** scheda.

      Fare riferimento alle sezioni [Aggiunta di una raccolta](../../automating/using/query.md#adding-a-collection) e [Ordinamento di dati](../../automating/using/query.md#sorting-additional-data) aggiuntivi.
   ![](assets/enrichment_example4.png)

   Per verificare che i dati siano correttamente trasferiti dalla transizione in uscita dell&#39;attività, avviate il flusso di lavoro per la prima volta (senza l&#39; **[!UICONTROL Email delivery]** attività) e aprite la transizione in uscita della query.

   ![](assets/enrichment_example5.png)

1. Aggiungete un&#39;attività di consegna [tramite e-](../../automating/using/email-delivery.md) mail. Nel contenuto dell’e-mail, inserite i campi di personalizzazione corrispondenti ai dati calcolati nella query. Puoi trovarlo tramite il **[!UICONTROL Additional data (targetData)]** collegamento dell&#39;esploratore dei campi di personalizzazione.

   ![](assets/enrichment_example3.png)

Il flusso di lavoro è ora pronto per essere eseguito. I profili interessati dalla query riceveranno un&#39;e-mail personalizzata contenente i dati calcolati a partire dalle relative transazioni.
