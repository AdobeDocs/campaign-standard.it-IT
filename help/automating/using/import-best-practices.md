---
title: Best practice per l’importazione
description: Ulteriori informazioni sulle best practice da seguire per importare dati nel database.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
exl-id: bb651b91-145f-4e87-92dd-a8b04662e380
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 3%

---

# Best practice per l’importazione {#import-best-practices}

>[!CAUTION]
>
>Tieni presente i limiti di archiviazione SFTP, archiviazione DB e profilo attivo in base al tuo contratto Adobe Campaign durante l’utilizzo di questa funzionalità.

Prestare attenzione e seguire le poche e semplici regole descritte di seguito aiuterà a garantire la coerenza dei dati all’interno del database e a evitare errori comuni durante l’aggiornamento del database o le esportazioni di dati.

## Utilizzo dei modelli di importazione {#using-import-templates}

La maggior parte dei flussi di lavoro di importazione deve contenere le seguenti attività: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

L’utilizzo dei modelli di importazione rende molto utile preparare importazioni simili e garantire la coerenza dei dati all’interno del database.

In molti progetti, le importazioni vengono generate senza **[!UICONTROL Deduplication]** perché i file utilizzati nel progetto non contengono duplicati. I duplicati vengono talvolta visualizzati quando si importano file diversi. La deduplicazione è quindi difficile. Pertanto, un passaggio di deduplicazione è una buona precauzione in tutti i flussi di lavoro di importazione.

Non partire dal presupposto che i dati in arrivo siano coerenti e corretti o che il reparto IT o il supervisore Adobe Campaign se ne occuperanno. Durante il progetto, tieni presente la pulizia dei dati. Deduplicare, riconciliare e mantenere la coerenza durante l&#39;importazione dei dati.

Un esempio di modello di flusso di lavoro generico progettato per l’importazione di dati è disponibile nella sezione [Esempio: importare un modello di workflow](../../automating/using/creating-import-workflow-templates.md) sezione.

>[!NOTE]
>
>Puoi anche utilizzare [modelli di importazione](../../automating/using/importing-data-with-import-templates.md). Si tratta di modelli di flusso di lavoro definiti da un amministratore che, una volta attivati, offrono solo la possibilità di specificare il file contenente i dati da importare.

**Argomenti correlati:**

* [Attività di caricamento file](../../automating/using/load-file.md)
* [Attività di riconciliazione](../../automating/using/reconciliation.md)
* [Attività di segmentazione](../../automating/using/segmentation.md)
* [Attività Deduplica](../../automating/using/deduplication.md)
* [Aggiornare l’attività dati](../../automating/using/update-data.md)

## Utilizzo dei formati di file flat {#using-flat-file-formats}

Il formato più efficiente per le importazioni è costituito dai file flat. I file Flat possono essere importati in modalità collettiva a livello di database.

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

Se possibile, utilizzate file compressi per le importazioni e le esportazioni. GZIP è supportato per impostazione predefinita. È possibile aggiungere la pre-elaborazione durante l’importazione di file o la post-elaborazione durante l’estrazione di dati, rispettivamente, in **[!UICONTROL Load file]** e **[!UICONTROL Extract file]** attività del flusso di lavoro.

**Argomenti correlati:**

* [Attività di caricamento file](../../automating/using/load-file.md)
* [Attività Extract file](../../automating/using/extract-file.md)

## Importazione in modalità Delta {#importing-in-delta-mode}

Le importazioni regolari devono essere effettuate in modalità delta. Significa che ad Adobe Campaign vengono inviati solo dati nuovi o modificati, invece che l’intera tabella ogni volta.

Le importazioni complete devono essere utilizzate solo per il carico iniziale.

## Mantenimento della coerenza {#maintaining-consistency}

Per mantenere la coerenza dei dati nel database di Adobe Campaign, segui i principi riportati di seguito:

* Se i dati importati corrispondono a una tabella di riferimento in Adobe Campaign, devono essere riconciliati con tale tabella nel flusso di lavoro. I record che non corrispondono devono essere rifiutati.
* Assicurati che i dati importati siano sempre **&quot;normalizzato&quot;** (e-mail, numero di telefono, indirizzo di direct mailing) e che questa normalizzazione è affidabile e non cambierà nel corso degli anni. In caso contrario, è probabile che alcuni duplicati vengano visualizzati nel database e, poiché Adobe Campaign non fornisce strumenti per effettuare una corrispondenza &quot;fuzzy&quot;, sarà molto difficile gestirli e rimuoverli.
* I dati transazionali devono avere una chiave di riconciliazione ed essere riconciliati con i dati esistenti al fine di evitare la creazione di duplicati.
* **Importa i file correlati in ordine**. Se l’importazione è composta da più file che dipendono l’uno dall’altro, il flusso di lavoro deve assicurarsi che i file vengano importati nell’ordine corretto. Quando un file ha esito negativo, gli altri file non vengono importati.
* **Deduplica**, riconciliare e mantenere la coerenza durante l&#39;importazione dei dati.
