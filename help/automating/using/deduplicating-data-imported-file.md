---
title: Deduplica di dati da un file importato
description: In questo esempio viene illustrato come deduplicare i dati da un file importato prima di caricarli nel database.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 631eb661-a696-4352-aa58-9097b391723e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 83%

---

# Deduplica di dati da un file importato {#deduplicating-the-data-from-an-imported-file}

Questo esempio mostra come deduplicare dati da un file importato prima di caricarli nel database. Questa procedura migliora la qualità dei dati caricati nel database.

Il flusso di lavoro è costituito da:

![](assets/deduplication_example2_workflow.png)

* Un file che contiene un elenco di profili viene importato utilizzando un&#39;attività [Load file](../../automating/using/load-file.md). In questo esempio, il file importato è in formato .csv e contiene 10 profili:

  ```
  lastname;firstname;dateofbirth;email
  Smith;Hayden;23/05/1989;hayden.smith@example.com
  Mars;Daniel;17/11/1987;dannymars@example.com
  Smith;Clara;08/02/1989;hayden.smith@example.com
  Durance;Allison;15/12/1978;allison.durance@example.com
  Lucassen;Jody;28/03/1988;jody.lucassen@example.com
  Binder;Tom;19/01/1982;tombinder@example.com
  Binder;Tommy;19/01/1915;tombinder@example.com
  Connor;Jade;10/10/1979;connor.jade@example.com
  Mack;Clarke;02/03/1985;clarke.mack@example.com
  Ross;Timothy;04/07/1986;timross@example.com
  ```

  Questo file può essere utilizzato anche come file campione per rilevare e definire il formato delle colonne. Dalla scheda **[!UICONTROL Column definition]**, accertati che ogni colonna del file importato sia configurata correttamente.

  ![](assets/deduplication_example2_fileloading.png)

* Un&#39;attività [Deduplication](../../automating/using/deduplication.md). La deduplicazione viene eseguita direttamente dopo l’importazione del file e prima dell’inserimento dei dati nel database. Dovrebbe pertanto basarsi sulla **[!UICONTROL Temporary resource]** dell’attività **[!UICONTROL Load file]**.

  Per questo esempio, desideriamo conservare una singola voce per indirizzo e-mail univoco contenuto nel file. L’identificazione dei duplicati viene quindi eseguita nella colonna **e-mail** della risorsa temporanea. Tuttavia, due indirizzi e-mail vengono visualizzati due volte nel file. Due righe saranno pertanto considerate come duplicati.

  ![](assets/deduplication_example2_dedup.png)

* Un&#39;attività [Update data](../../automating/using/update-data.md) consente di inserire nel database i dati conservati dal processo di deduplicazione. È solo quando i dati vengono aggiornati che i dati importati vengono identificati come appartenenti alla dimensione di profilo.

  A questo punto, desideriamo **[!UICONTROL Insert only]** i profili che non esistono già nel database. A tal fine, utilizzeremo la colonna e-mail del file e il campo e-mail dalla dimensione di **Profilo** come chiave di riconciliazione.

  ![](assets/deduplication_example2_writer1.png)

  Specifica le mappature tra le colonne del file da cui desideri inserire i dati e i campi del database dalla scheda **[!UICONTROL Fields to update]**.

  ![](assets/deduplication_example2_writer2.png)

Quindi avvia il flusso di lavoro. I record salvati dal processo di deduplicazione vengono quindi aggiunti ai profili nel database.
