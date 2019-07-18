---
title: Deduplicazione
seo-title: Deduplicazione
description: Deduplicazione
seo-description: L'attività Deduplicazione consente di eliminare duplicati nei risultati delle attività in entrata.
page-status-flag: never-activated
uuid: 11 a 22 a 9 c -3 bfe -4953-8 a 52-2 f 4 e 93 c 128 fb
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: targeting-activity
discoiquuid: e 7 a 5 e 1 e 7-4680-46 c 7-98 b 8-0 a 47 bb 7 be 2 b 8
context-tags: dedup, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Deduplication{#deduplication}

## Description {#description}

![](assets/deduplication.png)

The **[!UICONTROL Deduplication]** activity allows you to delete duplicates in the result(s) of the inbound activities.

## Context of use {#context-of-use}

The **[!UICONTROL Deduplication]** activity is generally used following targeting activities or after importing a file and before activities that allow the use of targeted data.

Durante la deduplicazione, le transizioni in entrata vengono elaborate separatamente. Ad esempio, se il profilo «A» è presente nel risultato di query 1 e anche nel risultato della query 2, non verrà deduplicato.

Si consiglia quindi di applicare una transizione solo in ingresso. A tal fine, puoi combinare le diverse query utilizzando attività che corrispondono alle tue esigenze di targeting, come ad esempio un'attività sindacale, un'attività di intersezione, ecc. Ad esempio:

![](assets/dedup_bonnepratique.png)

## Configuration {#configuration}

Per configurare un'attività di deduplicazione, dovete immettere un'etichetta, il metodo e i criteri di deduplicazione, nonché le opzioni relative al risultato.

1. Drag and drop a **[!UICONTROL Deduplication]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   ![](assets/deduplication_1.png)

1. Select the **[!UICONTROL Resource type]** on which the deduplication has to be carried out:

   * **[!UICONTROL Database resource]** se la deduplicazione viene eseguita sui dati già esistenti nel database. Select the **[!UICONTROL Filtering dimension]** and the **[!UICONTROL Targeting dimension]**, depending on the data that you want to deduplicate. By default, deduplication is carried out on the **profiles**.
   * **[!UICONTROL Temporary resource]** se la deduplicazione viene eseguita sui dati temporanei del flusso di lavoro: selezionare i **[!UICONTROL Targeted set]** dati da duplicare. Questo caso d'uso può essere rilevato dopo l'importazione di un file o se i dati nel database sono stati arricchiti (ad esempio, con un codice del segmento).

1. Select the **[!UICONTROL Number of unique records to keep]**. Il valore predefinito per questo campo è 1. Il valore 0 consente di tenere tutti i duplicati.

   Ad esempio, se i record A e B sono considerati duplicati del record Y e un record C viene considerato come duplicato del record Z:

   * Se il valore del campo è 1: vengono mantenuti solo i record Y e Z.
   * Se il valore del campo è 0: tutti i record vengono conservati.
   * Se il valore del campo è 2: i record C e Z vengono conservati e due record A, B e Y vengono conservati, per casualità o in base al metodo di deduplicazione selezionato successivamente.

1. Define the **[!UICONTROL Duplicate identification]** criteria by adding conditions in the list provided. Specificate i campi e/o espressioni per i quali i valori identici consentono l'identificazione dei duplicati: indirizzo e-mail, nome, cognome, ecc. L'ordine delle condizioni consente di specificare per prima cosa chi elabora.
1. In the drop-down list, select the **[!UICONTROL Deduplication method]** to use:

   * **[!UICONTROL Choose for me]**: Seleziona in modo casuale il record da tenere fuori dai duplicati.
   * **[!UICONTROL Following a list of values]**: consente di definire una priorità di valore per uno o più campi. Per definire i valori, selezionare un campo o creare un'espressione, quindi aggiungere i valori nella tabella appropriata. To define a new field, click the **[!UICONTROL Add]** button located above the list of values.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: Ciò consente di conservare i record per i quali il valore dell'espressione selezionata non è vuoto come priorità.

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: Ciò consente di mantenere i record in cui il valore dell'espressione immesso è il più piccolo o il più grande.

      ![](assets/deduplication_4.png)

1. If needed, manage the activity's [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) to access the advanced options for the outbound population.
1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example 1: Identifying duplicates before a delivery {#example-1--identifying-duplicates-before-a-delivery}

L'esempio seguente illustra una deduplicazione che consente di escludere i duplicati di un target prima di inviare un'e-mail. Ciò significa che evitate di inviare più volte una comunicazione allo stesso profilo.

Il flusso di lavoro è costituito da:

![](assets/deduplication_example_workflow.png)

* A **[!UICONTROL Query]** which allows you to define the target of the email. Qui, il flusso di lavoro fa riferimento a tutti i profili compresi tra 18 e 25 che sono presenti nel database client per più di un anno.

   ![](assets/deduplication_example_query.png)

* **[!UICONTROL Deduplication]** Un'attività, che consente di identificare i duplicati derivanti dalla query precedente. In questo esempio, per ogni duplicato viene salvato un solo record. I duplicati vengono identificati utilizzando l'indirizzo e-mail. Ciò significa che la consegna e-mail può essere inviata solo una volta affinché ogni indirizzo e-mail sia presente nel targeting.

   The deduplication method selected is **[!UICONTROL Non-empty value]**. This allows you to ensure that amongst the records kept in case of duplicates, priority is given to those in which the **First name** has been provided. Questo rende più coerente se il primo nome viene utilizzato nei campi di personalizzazione del contenuto e-mail.

   Inoltre, viene aggiunta una transizione aggiuntiva per mantenere i duplicati e per poterli elencare.

   ![](assets/deduplication_example_dedup.png)

* An **[!UICONTROL Email delivery]** placed after the main outbound transition of the deduplication. The configuration for email deliveries is detailed in the [Email delivery](../../automating/using/email-delivery.md) section.
* **[!UICONTROL Save audience]** Un'attività inserita dopo l'ulteriore transizione della deduplicazione per salvare i duplicati in un **pubblico duplicato** . Questo pubblico può essere riutilizzato per escludere direttamente i membri da ogni consegna di posta elettronica.

## Example 2: Deduplicating the data from an imported file {#example-2--deduplicating-the-data-from-an-imported-file}

Questo esempio mostra come duplicare i dati da un file importato prima di caricare i dati nel database. Questa procedura migliora la qualità dei dati caricati nel database.

Il flusso di lavoro è costituito da:

![](assets/deduplication_example2_workflow.png)

* A file that contains a list of profiles is imported using a **[!UICONTROL Load file]** activity. In questo esempio, il file importato è in formato. csv e contiene 10 profili:

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

   Questo file può essere usato anche come file di esempio per rilevare e definire il formato delle colonne. From the **[!UICONTROL Column definition]** tab, make sure that each column of the imported file is configured correctly.

   ![](assets/deduplication_example2_fileloading.png)

* A **[!UICONTROL Deduplication]** activity. La deduplicazione viene eseguita direttamente dopo l'importazione del file e prima di inserire i dati nel database. It should therefore be based on the **[!UICONTROL Temporary resource]** from the **[!UICONTROL Load file]** activity.

   Per questo esempio, desideriamo conservare una singola voce per indirizzo e-mail univoco contenuto nel file. Duplicate identification is therefore carried out on the **email** column of the temporary resource. Due indirizzi e-mail vengono visualizzati due volte nel file. Sono quindi considerate doppie due righe.

   ![](assets/deduplication_example2_dedup.png)

* An **[!UICONTROL Update data]** activity allows you to insert the data kept from the deduplication process into the database. È solo quando i dati vengono aggiornati che i dati importati sono identificati come appartenenti alla dimensione del profilo.

   Here, we would like to **[!UICONTROL Insert only]** the profiles that do not already exist in the database. We are going to do this by using the file's email column and the email field from the **Profile** dimension as the reconciliation key.

   ![](assets/deduplication_example2_writer1.png)

   Specify the mappings between the file's columns from which you want to insert the data and the database fields from the **[!UICONTROL Fields to update]** tab.

   ![](assets/deduplication_example2_writer2.png)

Quindi avviate il flusso di lavoro. I record salvati dal processo di deduplicazione vengono quindi aggiunti ai profili nel database.
