---
title: Segmentazione
seo-title: Segmentazione
description: Segmentazione
seo-description: L'attività Segmentazione consente di creare uno o più segmenti da una popolazione calcolata in precedenza nel flusso di lavoro.
page-status-flag: never-activated
uuid: 77796 f 18-cad 5-4 e 7 a -9 d 7 b -4 ed 0 dd 8943 bf
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: targeting-activity
discoiquuid: 0 ccd 9 d 02-772 e -406 b -874 a -5381 dd 0 c 8709
context-tags: segmentazione, principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Segmentation{#segmentation}

## Description {#description}

![](assets/segmentation.png)

The **[!UICONTROL Segmentation]** activity lets you create one or several segments from a population calculated by activities placed earlier in the workflow. Alla fine dell'attività, possono essere elaborate con una singola transizione o con transizioni diverse.

>[!NOTE]
>
>Per impostazione predefinita, un membro della popolazione in entrata può appartenere solo a un singolo segmento. I filtri vengono applicati in base all'ordine dei segmenti nell'attività.

## Context of use {#context-of-use}

The **[!UICONTROL Segmentation]** activity is generally placed after targeting activities (query, intersection, union, exclusion, etc.) per definire la popolazione standard in base alla quale vengono composti i segmenti.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Segmentation]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Resource type]** on which the segmentation has to be carried out:

   * **[!UICONTROL Database resource]** se la segmentazione viene eseguita sui dati già esistenti nel database. Select the **[!UICONTROL Filtering dimension]** depending on the data that you want to segment. By default, segmentation is carried out on the **profiles**.
   * **[!UICONTROL Temporary resource]** se la segmentazione viene eseguita sui dati temporanei del flusso di lavoro: seleziona i **[!UICONTROL Targeted set]** dati che contengono i dati da segmentare. Questo caso d'uso può essere rilevato dopo l'importazione di un file o se i dati nel database sono stati arricchiti.

1. Selezionate il tipo di transizione in uscita da usare:

   * **[!UICONTROL Generate one transition per segment]**: Una transizione in uscita viene aggiunta per ogni segmento configurato alla fine dell'attività.
   * **[!UICONTROL Generate all segments in one transition]**: tutti i segmenti configurati vengono raggruppati in una singola transizione in uscita. Specificate l'etichetta della transizione. I membri di ogni segmento mantengono il codice del segmento assegnato loro.

1. Add a segment by using the ![](assets/add_darkgrey-24px.png) or **[!UICONTROL Add an element]** button and specify the standard properties:

   * **[!UICONTROL Do not activate the transition if the population is empty]**: il segmento verrà abilitato solo se i dati vengono recuperati.
   * **[!UICONTROL Filter initial population (query)]**: consente di filtrare la popolazione del segmento.
   * **[!UICONTROL Limit segment population]**: consente di limitare le dimensioni del segmento.
   * **[!UICONTROL Filter and limit segment population]**: consente di filtrare la popolazione dei segmenti e limitare le dimensioni.
   * **[!UICONTROL Label]**: etichetta del segmento.
   * **[!UICONTROL Segment code]**: il codice assegnato alla popolazione dei segmenti. Il codice del segmento può essere personalizzato utilizzando una variabile standard di espressioni ed eventi (consultate [Personalizzazione delle attività con variabili degli eventi](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)).
   * **[!UICONTROL Exclude segment from population]**: consente di escludere il segmento specificato dalla popolazione in uscita dell'attività. This option can only be used if the **[!UICONTROL Generate all segments in the same transition]** option is selected.
   ![](assets/wkf_segment_new_segment.png)

1. Apri la visualizzazione dettagli del segmento per accedere alle opzioni di configurazione di quest'ultimo. To do this, check the relevant box in the activity's segment list, then select ![](assets/wkf_segment_parameters_24px.png).
1. If the option to filter the initial population is checked, open the **[!UICONTROL Filter]** tab and specify your segment's population. I filtri si basano sulla dimensione di filtro selezionata al punto 4. Consult the [Query editing](../../automating/using/editing-queries.md) section for further information on population filtering.

   Se la segmentazione viene eseguita su una risorsa temporanea, il conteggio e l'anteprima della popolazione non sono disponibili in questa scheda.

1. If the option to limit the segment size is checked, open the **[!UICONTROL Limitation]** tab.

   First, select the **[!UICONTROL Type of limit]** that you would like to use:

   * **[!UICONTROL Random sampling]**: la popolazione dei segmenti è selezionata in modo casuale tenendo conto della configurazione della **[!UICONTROL Filter]** scheda, se necessario.
   * **[!UICONTROL Ordered sampling]**: la popolazione del segmento è selezionata in modo ordinato. È pertanto necessario specificare le colonne da prendere in considerazione e il tipo di ordinamento da applicare. For example, if you select the **Age** field as the sort column while applying a **[!UICONTROL Descending sort]** and setting a limit of 100, only the profiles of the top 100 oldest people will be kept.
   Now specify the size **[!UICONTROL Limit]** of the segment:

   * **[!UICONTROL Size (as a % of the initial population)]**: specificate le dimensioni del segmento utilizzando una percentuale della popolazione iniziale dell'attività.
   * **[!UICONTROL Maximum size]**: specificate un numero massimo di membri per la popolazione dei segmenti.
   * **[!UICONTROL By data grouping]**: potete limitare la popolazione del segmento in base ai valori di un campo specifico della popolazione in entrata. Selezionate il campo per il raggruppamento, quindi specificate i valori da utilizzare.
   * **[!UICONTROL By data grouping (as a %)]**: Potete limitare la popolazione del segmento in base ai valori di un campo di popolazione in entrata specifico utilizzando una percentuale. Selezionate il campo per applicare il raggruppamento, quindi specificate i valori da utilizzare.

      >[!NOTE]
      >
      >È possibile utilizzare limitazioni diverse per ogni valore. For example, you can specify a grouping for the **[!UICONTROL Gender]** field and limit the population with **[!UICONTROL Male]** members to 10 and the population with **[!UICONTROL Female]** members to 30 people. Se utilizzate più campi di raggruppamento dati, tutti i raggruppamenti devono avere le stesse dimensioni.
   ![](assets/wkf_segment_limit_by_grouping.png)

1. Conferma la configurazione del segmento.
1. Aggiungere tutti i segmenti necessari ripetendo i passaggi da 6 a 10 di questa procedura.
1. If necessary, edit the parameters in the **[!UICONTROL Advanced options]** tab:

   * Check the **[!UICONTROL Enable overlapping of outbound populations]** option if you want a member of the inbound population to belong to several segments at the same time. La popolazione in uscita dell'attività può superare la popolazione in ingresso.
   * Check the **[!UICONTROL Concatenate the code of each segment]** option if the inbound population has already been assigned a segment code that you want to keep. Il codice del segmento specificato nell'attività verrà aggiunto al codice iniziale del segmento.
   * Check the **[!UICONTROL Generate complement]** option if you would like to exploit the remaining population.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example {#example}

L'esempio seguente mostra una segmentazione dei profili di database in base al gruppo di età. Lo scopo del flusso di lavoro è quello di inviare un messaggio e-mail specifico per ogni gruppo di età. Considerando il fatto che questo flusso di lavoro fa parte di una campagna di test, ogni segmento può contenere solo un massimo di 100 profili selezionati in modo casuale, per utilizzare le audience limitate e rappresentative allo stesso tempo.

![](assets/wkf_segment_example_4.png)

Il flusso di lavoro è costituito dai seguenti elementi:

* **[!UICONTROL Scheduler]** Un'attività per specificare la data di esecuzione del flusso di lavoro. Refer to the [Scheduler](../../automating/using/scheduler.md) section.
* **[!UICONTROL Query]** Un'attività per il targeting dei profili di persone il cui compleanno e indirizzo e-mail sono stati inseriti. Refer to the [Query](../../automating/using/query.md) section.
* A **[!UICONTROL Segmentation]** activity to create 3 segments divided into different outbound transitions: 18-25-year old, 26-32-year old and profiles that are over 32 years old. I segmenti sono definiti in base ai seguenti parametri:

   ![](assets/wkf_segment_example_3.png)

   * Filtro sull'età per definire il gruppo di età del segmento

      ![](assets/wkf_segment_new_segment.png)

   * A **[!UICONTROL Random sampling]** type limit that is linked to a **[!UICONTROL Maximum size]** limit of 100

      ![](assets/wkf_segment_example_1.png)

* An **[!UICONTROL Email delivery]** activity per segment. Refer to the [Email delivery](../../automating/using/email-delivery.md) section.

