---
title: Invio di un’e-mail con campi arricchiti
description: L’esempio seguente mostra come inviare un’e-mail utilizzando dati aggiuntivi recuperati da un file esterno tramite l’attività di caricamento file.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5ca7571d-d4d2-4b59-86d4-4f1f3a620b54
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 68%

---

# Invio di un’e-mail con campi arricchiti {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

L’attività di caricamento file consente inoltre di inviare nello stesso flusso di lavoro un’e-mail arricchita di dati aggiuntivi proveniente da un file esterno.

L’esempio seguente illustra la procedura per l’invio di un’e-mail utilizzando dati aggiuntivi recuperati da un file esterno tramite l’attività di caricamento file. In questo esempio, il file esterno contiene un elenco di profili con il relativo numero di account associato. Vorresti importare questi dati per poter inviare un messaggio e-mail a ogni profilo insieme al relativo numero di account.

![](assets/load_file_workflow_ex2.png)

Per creare il flusso di lavoro, effettua le seguenti operazioni:

1. Trascina una [Query](../../automating/using/query.md) attività nel flusso di lavoro e aprirlo per definire la destinazione principale.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Trascina una [Carica file](../../automating/using/load-file.md) attività per assegnare alcuni dati a un profilo. In questo esempio, eseguirai il caricamento di un file contenente i numeri di account corrispondenti ad alcuni profili del database.

   ![](assets/load_file_activity.png)

1. Trascina e rilascia una [Arricchimento](../../automating/using/enrichment.md) attività nel flusso di lavoro e collegarvi le attività di caricamento file e di query.

1. Nella scheda **[!UICONTROL Advanced relations]** dell’attività Enrichment, seleziona **[!UICONTROL 0 or 1 cardinality simple link]** e definisci i campi da utilizzare per la riconciliazione. In questo caso, utilizziamo il cognome per riconciliare i dati con i profili del database.

   ![](assets/load_file_enrichment_relation.png)

1. Nella scheda **[!UICONTROL Additional data]**, seleziona gli elementi che desideri utilizzare nel messaggio e-mail. Qui puoi selezionare il numero di account, presente nella colonna del file recuperato tramite l’attività di caricamento file.

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   Per ulteriori informazioni, consulta la sezione [Enrichment](../../automating/using/enrichment.md).

1. Trascina una [Segmentazione](../../automating/using/segmentation.md) nel flusso di lavoro e aprirlo per perfezionare il target principale.

   ![](assets/load_file_segmentation.png)

   Per ulteriori informazioni, consulta la sezione [Segmentazione](../../automating/using/segmentation.md).

1. Trascina e rilascia una [Consegna e-mail](../../automating/using/email-delivery.md) nel flusso di lavoro e aprirlo.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Aggiungi un campo di personalizzazione e seleziona dal nodo **[!UICONTROL Additional data (targetData)]** i dati aggiuntivi definiti nell’attività di arricchimento, in questo caso il numero account. Questa operazione ti consente di recuperare in modo dinamico il numero di account di ciascun profilo presente nel contenuto dell’e-mail.

   ![](assets/load_file_perso_field.png)

1. Salva il messaggio e-mail e avvia il flusso di lavoro.

L’e-mail viene inviata alla destinazione. Ciascun profilo riceve l’e-mail con il numero di account corrispondente.

![](assets/load_file_email.png)
