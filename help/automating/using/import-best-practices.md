---
title: Best practice per l’importazione
description: Ulteriori informazioni sulle procedure ottimali da seguire per l'importazione di dati nel database.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '569'
ht-degree: 2%

---


# Best practice per l’importazione {#import-best-practices}

>[!CAUTION]
>
>Ricorda i limiti di archiviazione SFTP, archiviazione DB e profilo attivo secondo il contratto Adobe Campaign  durante l&#39;utilizzo di questa funzionalità.

Essere cauti e seguire le poche semplici regole descritte di seguito aiuterà molto a garantire la coerenza dei dati all&#39;interno del database e ad evitare errori comuni durante l&#39;aggiornamento del database o le esportazioni di dati.

## Utilizzo dei modelli di importazione {#using-import-templates}

La maggior parte dei flussi di lavoro di importazione deve contenere le seguenti attività: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

Utilizzando i modelli di importazione è molto comodo preparare importazioni simili e garantire la coerenza dei dati all&#39;interno del database.

In molti progetti, le importazioni vengono create senza **[!UICONTROL Deduplication]** attività perché i file utilizzati nel progetto non hanno duplicati. Talvolta i duplicati vengono visualizzati durante l’importazione di file diversi. La deduplicazione è quindi difficile. Pertanto, un passaggio di deduplicazione è una buona precauzione in tutti i flussi di lavoro di importazione.

Non devi basarsi sul presupposto che i dati in arrivo siano coerenti e corretti, o che il reparto IT o  supervisore Adobe Campaign se ne occuperà. Durante il progetto, tenere presente la pulizia dei dati. Deduplicare, riconciliare e mantenere la coerenza quando si importano i dati.

Un esempio di modello di flusso di lavoro generico progettato per l&#39;importazione di dati è disponibile in [Esempio: Importa sezione modello](../../automating/using/creating-import-workflow-templates.md) flusso di lavoro.

>[!NOTE]
>
>Potete anche utilizzare i modelli [di](../../automating/using/importing-data-with-import-templates.md)importazione. Si tratta di modelli di workflow definiti da un amministratore che, una volta attivati, offrono solo la possibilità di specificare il file contenente i dati da importare.

**Argomenti correlati:**

* [Carica attività file](../../automating/using/load-file.md)
* [Attività di riconciliazione](../../automating/using/reconciliation.md)
* [Attività Segmentation](../../automating/using/segmentation.md)
* [Attività di deduplicazione](../../automating/using/deduplication.md)
* [Aggiorna attività dati](../../automating/using/update-data.md)

## Uso dei formati di file semplici {#using-flat-file-formats}

Il formato più efficiente per le importazioni è rappresentato dai file semplici. I file flat possono essere importati in modalità collettiva a livello di database.

Ad esempio:

* Separatore: tabulazione o punto e virgola
* Prima riga con intestazioni
* Nessun delimitatore di stringa
* Formato data: AAAA/MM/GG HH:mm:SS

Esempio di file da importare:

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

## Utilizzo della compressione {#using-compression}

Quando possibile, usate file ZIP per le importazioni e le esportazioni. GZIP è supportato per impostazione predefinita. È possibile aggiungere la pre-elaborazione durante l&#39;importazione di file o la post-elaborazione durante l&#39;estrazione di dati, rispettivamente nelle attività **[!UICONTROL Load file]** e nei **[!UICONTROL Extract file]** flussi di lavoro.

**Argomenti correlati:**

* [Carica attività file](../../automating/using/load-file.md)
* [Estrai attività file](../../automating/using/extract-file.md)

## Importazione in modalità Delta {#importing-in-delta-mode}

Le importazioni regolari devono essere effettuate in modalità delta. Ciò significa che solo i dati nuovi o modificati vengono inviati a  Adobe Campaign, invece che l&#39;intera tabella ogni volta.

Le importazioni complete devono essere utilizzate solo per il carico iniziale.

## Mantenimento della coerenza {#maintaining-consistency}

Per mantenere la coerenza dei dati nel database Adobe Campaign , attenersi ai principi seguenti:

* Se i dati importati corrispondono a una tabella di riferimento in  Adobe Campaign, è necessario riconciliarla con tale tabella nel flusso di lavoro. I record che non corrispondono devono essere rifiutati.
* Assicurarsi che i dati importati siano sempre **&quot;normalizzati&quot;** (e-mail, numero di telefono, indirizzo e-mail diretto) e che la normalizzazione sia affidabile e non cambi nel corso degli anni. In caso contrario, è probabile che nel database vengano visualizzati dei duplicati, e poiché  Adobe Campaign non fornisce strumenti per effettuare la corrispondenza &quot;fuzzy&quot;, sarà molto difficile gestirli e rimuoverli.
* I dati transazionali devono avere una chiave di riconciliazione e devono essere riconciliati con i dati esistenti al fine di evitare la creazione di duplicati.
* **Importa i file correlati in ordine**. Se l’importazione è composta da più file che dipendono l’uno dall’altro, il flusso di lavoro deve verificare che i file vengano importati nell’ordine corretto. Quando un file ha esito negativo, gli altri file non vengono importati.
* **Deduplicare**, riconciliare e mantenere la coerenza quando si importano i dati.
