---
title: Deduplicazione dei dati da un file importato
description: Questo esempio mostra come deduplicare i dati da un file importato prima di caricare i dati nel database.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---


# Deduplicazione dei dati da un file importato {#deduplicating-the-data-from-an-imported-file}

Questo esempio mostra come deduplicare i dati da un file importato prima di caricare i dati nel database. Questa procedura migliora la qualità dei dati caricati nel database.

Il flusso di lavoro è costituito da:

![](assets/deduplication_example2_workflow.png)

* Un file che contiene un elenco di profili viene importato utilizzando un&#39;attività [Carica file](../../automating/using/load-file.md) . In questo esempio, il file importato è in formato .csv e contiene 10 profili:

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

   Questo file può essere utilizzato anche come file di esempio per rilevare e definire il formato delle colonne. Dalla **[!UICONTROL Column definition]** scheda, accertatevi che ogni colonna del file importato sia configurata correttamente.

   ![](assets/deduplication_example2_fileloading.png)

* Un&#39;attività di [deduplicazione](../../automating/using/deduplication.md) . La deduplicazione viene eseguita direttamente dopo l&#39;importazione del file e prima di inserire i dati nel database. Dovrebbe pertanto basarsi sul **[!UICONTROL Temporary resource]** risultato dell&#39; **[!UICONTROL Load file]** attività.

   Per questo esempio, desideriamo mantenere una voce singola per indirizzo e-mail univoco contenuto nel file. L’identificazione duplicata viene quindi eseguita nella colonna **e-mail** della risorsa temporanea. Tuttavia, due indirizzi e-mail vengono visualizzati due volte nel file. Due righe sono pertanto considerate duplicati.

   ![](assets/deduplication_example2_dedup.png)

* Un&#39;attività [Aggiorna dati](../../automating/using/update-data.md) consente di inserire nel database i dati conservati dal processo di deduplicazione. È solo quando i dati vengono aggiornati che i dati importati vengono identificati come appartenenti alla dimensione del profilo.

   A questo punto, vorremmo vedere **[!UICONTROL Insert only]** i profili che non esistono già nel database. A tal fine, utilizzeremo la colonna e-mail del file e il campo e-mail dalla dimensione **Profilo** come chiave di riconciliazione.

   ![](assets/deduplication_example2_writer1.png)

   Specificare i mapping tra le colonne del file da cui si desidera inserire i dati e i campi del database dalla **[!UICONTROL Fields to update]** scheda.

   ![](assets/deduplication_example2_writer2.png)

Quindi avviate il flusso di lavoro. I record salvati dal processo di deduplicazione vengono quindi aggiunti ai profili nel database.
