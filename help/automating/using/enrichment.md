---
title: Arricchimento
seo-title: Arricchimento
description: Arricchimento
seo-description: L'attività Arricchimento è un'attività avanzata che consente di definire ulteriori dati da elaborare nel flusso di lavoro.
page-status-flag: never-activated
uuid: 8 c 1693 ef -1312-422 c-b 05 d -263553113 f 8 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: targeting-activity
discoiquuid: f 67 c 1 caf -3284-4 c 34-a 5 b 0-8654 a 95640 ae
context-tags: arricchimento, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Enrichment{#enrichment}

## Description {#description}

![](assets/enrichment.png)

The **[!UICONTROL Enrichment]** activity is an advanced activity that allows you to define additional data to process in your workflow.

## Context of use {#context-of-use}

The **[!UICONTROL Enrichment]** activity is generally used following targeting activities or after importing a file and before activities that allow the use of targeted data.

This activity contains more advanced enrichment functions than the **[!UICONTROL Query]** activity. Some simple cases of enrichment can be directly performed in the [Query activity](../../automating/using/query.md#enriching-data).

With the **[!UICONTROL Enrichment]** activity, you can leverage the inbound transition and configure the activity to complete the output transition with additional data. Consente di combinare dati provenienti da più set o di creare collegamenti a una risorsa temporanea.

## Configuration {#configuration}

To configure an **[!UICONTROL Enrichment]** activity:

1. Drag and drop an **[!UICONTROL Enrichment]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If the activity has several inbound transitions, select the **[!UICONTROL Primary set]**. I dati aggiuntivi configurati in questa attività saranno aggiunti al set principale nella transizione in uscita.

   Se il set principale contiene già dati aggiuntivi, potete scegliere di mantenerli o rimuoverli. If you uncheck the **[!UICONTROL Keep all additional data from the main set]** option, only the additional data configured in the **[!UICONTROL Enrichment]** are kept in the outbound transition.

1. If there are several inbound transitions, define relations between the primary set and the other inbound data in the **[!UICONTROL Advanced Relations]** tab of the activity. You can add several relations using the **[!UICONTROL Add element]** button.

   Quando definite una nuova relazione, selezionate il set di dati in entrata che desiderate collegare al set principale. Quindi definite il tipo di relazione. Sono disponibili diversi tipi di relazioni, a seconda dei dati in entrata e del modello dati:

   * **[!UICONTROL 1 cardinality simple link]**: Ogni record dei dati in entrata è associato a uno e un solo record dal set principale. Ogni record del set principale ha un record associato nei dati collegati.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 o più record (N) registrati dai dati collegati possono essere associati a 1 record del set principale.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: i record del set principale possono essere associati a 0 o 1 record dai dati collegati, ma non più di uno.
   Once the **[!UICONTROL Cardinality]** is defined, define a **[!UICONTROL Reconciliation criteria]**. The **[!UICONTROL Source expression]** of the reconciliation criteria can be a field from the target resource, an [expression](../../automating/using/advanced-expression-editing.md) or directly a value specified between quotes.

   Define a **[!UICONTROL Label]** and an **[!UICONTROL ID]** that will be easy to identify later in the workflow.

   >[!NOTE]
   >
   >You can only define relations between the primary set and the other inbound transitions connected to the **[!UICONTROL Enrichment]** activity. For simpler cases aiming at defining relations with database resources, use a [Reconciliation](../../automating/using/reconciliation.md) activity.

1. Define the additional data from the **[!UICONTROL Additional data]** tab of the activity. You can define additional data (simple fields, aggregates and collections) related to the targeting dimension of the primary set or based on the links created in the **[!UICONTROL Advanced relations]** tab of the **[!UICONTROL Enrichment]** activity.

   Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

The data is now available to use in the activities connected after the **[!UICONTROL Enrichment]**. For example, you can find it under the **[!UICONTROL Additional data (targetData)]** link of the personalization fields explorer in an email content.

## Example: Enriching profile data with data contained in a file {#example--enriching-profile-data-with-data-contained-in-a-file}

Questo esempio mostra come arricchire i dati di profilo con i dati di acquisto contenuti in un file. Qui si consideri che i dati di acquisto sono memorizzati in un sistema di terze parti. Ogni profilo può contenere più acquisti memorizzati nel file. L'obiettivo finale del flusso di lavoro consiste nell'inviare un messaggio e-mail ai profili di destinazione che hanno acquistato almeno due elementi per la loro fedeltà.

Il flusso di lavoro è configurato come segue:

![](assets/enrichment_example_workflow.png)

* **[!UICONTROL Query]** Un'attività che esegue il targeting dei profili che riceveranno il messaggio.
* **[!UICONTROL Load file]** Un'attività che carica i dati di acquisto. Ad esempio:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   Con questo esempio di file, useremo l'indirizzo e-mail per riconciliare i dati con i profili del database. You can also enable unique IDs as described in [this document](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* **[!UICONTROL Enrichment]** Un'attività che crea un collegamento tra i dati della transazione caricati dal file e quelli selezionati nell ' **[!UICONTROL Query]**. The link is defined in the **[!UICONTROL Advanced relations]** tab of the activity. The link is based on the transition coming from the **[!UICONTROL Load file]** activity. Utilizza il campo «email» della risorsa del profilo e la colonna «cliente» del file importato come criteri di riconciliazione.

   ![](assets/enrichment_example_workflow2.png)

   Once the link is created, two sets of **[!UICONTROL Additional data]** are added:

   * Una raccolta di due righe corrispondenti alle due ultime transazioni di ogni profilo. Per questa raccolta, il nome del prodotto, la data di transazione e il prezzo del prodotto vengono aggiunti come dati aggiuntivi. Un ordinamento decrescente viene applicato ai dati. To create the collection, from the **[!UICONTROL Additional data]** tab:

      Select the link previously defined in the **[!UICONTROL Advanced relations]** tab of the activity.

      ![](assets/enrichment_example_workflow3.png)

      Check **[!UICONTROL Collection]** and specify the number of lines to retrieve (2 in this example). In this screen, you can customize the **[!UICONTROL Alias]** and the **[!UICONTROL Label]** of the collection. Tali valori saranno visibili nelle attività seguenti del flusso di lavoro quando si fa riferimento a questa raccolta.

      ![](assets/enrichment_example_workflow4.png)

      As **[!UICONTROL Data]** to keep for the collection, select the columns that will be used in the final delivery.

      ![](assets/enrichment_example_workflow6.png)

      Applica un ordinamento decrescente alla data della transazione per recuperare le transazioni più recenti.

      ![](assets/enrichment_example_workflow7.png)

   * Un aggregato complessivo che conta il numero totale di transazioni per ogni profilo. Questo aggregato verrà utilizzato in seguito per filtrare profili con almeno due transazioni registrate. To create the aggregate, from the **[!UICONTROL Additional data]** tab:

      Select the link previously defined in the **[!UICONTROL Advanced relations]** tab of the activity.

      ![](assets/enrichment_example_workflow3.png)

      Select **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      As **[!UICONTROL Data]** to keep, define a **Count All** aggregate. Se necessario, specificate un alias personalizzato per trovarlo più rapidamente nelle attività seguenti.

      ![](assets/enrichment_example_workflow9.png)

* A **[!UICONTROL Segmentation]** activity with only one segment, that retrieves profiles of the initial target that have at least two transactions recorded. Sono esclusi i profili con una sola transazione. A tal fine, la query della segmentazione viene effettuata sull'aggregazione precedentemente definita.

   ![](assets/enrichment_example_workflow5.png)

* **[!UICONTROL Email delivery]** Un'attività che utilizza i dati aggiuntivi definiti nel metodo **[!UICONTROL Enrichment]** per recuperare in modo dinamico i due ultimi acquisti effettuati dal profilo. The additional data can be found in the **Additional data (TargetData)** node when adding a personalization field.

   ![](assets/enrichment_example_workflow10.png)

