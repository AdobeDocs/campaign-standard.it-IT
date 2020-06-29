---
title: Invio di un’e-mail con campi arricchiti
description: L'esempio seguente mostra come inviare un'e-mail utilizzando dati aggiuntivi recuperati da un file esterno tramite l'attività del file di caricamento.
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---


# Invio di un’e-mail con campi arricchiti {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

L&#39;attività del file di caricamento consente inoltre di inviare un&#39;e-mail arricchita di dati aggiuntivi da un file esterno nello stesso flusso di lavoro.

L&#39;esempio seguente mostra come inviare un&#39;e-mail utilizzando dati aggiuntivi recuperati da un file esterno tramite l&#39;attività del file di caricamento. In questo esempio, il file esterno contiene un elenco di profili con il relativo numero di account associato. Desiderate importare questi dati per inviare un messaggio e-mail a ogni profilo con il relativo numero di account.

![](assets/load_file_workflow_ex2.png)

Per generare il flusso di lavoro, effettuate le seguenti operazioni:

1. Trascinate e rilasciate un&#39;attività [Query](../../automating/using/query.md) nel flusso di lavoro e apritela per definire la destinazione principale.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Trascinate e rilasciate un’attività [Carica file](../../automating/using/load-file.md) per assegnare alcuni dati a un profilo. In questo esempio, caricate un file contenente i numeri di account corrispondenti ad alcuni profili del database.

   ![](assets/load_file_activity.png)

1. Trascinate e rilasciate un&#39;attività di [arricchimento](../../automating/using/enrichment.md) nel flusso di lavoro e collegate il file di caricamento e le attività di query ad esso.

1. Nella **[!UICONTROL Advanced relations]** scheda dell&#39;attività di arricchimento, selezionare i campi **[!UICONTROL 0 or 1 cardinality simple link]** e definirli per la riconciliazione. Qui usiamo il cognome per riconciliare i dati con i profili del database.

   ![](assets/load_file_enrichment_relation.png)

1. Nella **[!UICONTROL Additional data]** scheda, selezionate gli elementi che desiderate utilizzare nel messaggio e-mail. Qui selezionate il numero di account (colonna dal file recuperato tramite l&#39;attività del file di caricamento).

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   Per ulteriori informazioni, vedere la sezione [Arricchimento](../../automating/using/enrichment.md) .

1. Trascina e rilascia un’attività di [segmentazione](../../automating/using/segmentation.md) nel flusso di lavoro e la apre per perfezionare la destinazione principale.

   ![](assets/load_file_segmentation.png)

   Per ulteriori informazioni, consulta la sezione [Segmentazione](../../automating/using/segmentation.md) .

1. Trascinate e rilasciate un’attività di consegna [tramite e-](../../automating/using/email-delivery.md) mail nel flusso di lavoro per aprirla.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Aggiungi un campo di personalizzazione e seleziona dal **[!UICONTROL Additional data (targetData)]** nodo i dati aggiuntivi definiti nell&#39;attività di arricchimento (qui Numero account). Questo consente di recuperare in modo dinamico il numero di account di ciascun profilo presente nel contenuto dell&#39;e-mail.

   ![](assets/load_file_perso_field.png)

1. Salvate il messaggio e-mail e avviate il flusso di lavoro.

L&#39;e-mail viene inviata alla destinazione. Ogni profilo riceve l’e-mail con il numero di account corrispondente.

![](assets/load_file_email.png)
