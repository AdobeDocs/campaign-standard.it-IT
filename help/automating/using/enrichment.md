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
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# Arricchimento{#enrichment}

## Descrizione {#description}

![](assets/enrichment.png)

L' **[!UICONTROL Enrichment]** attività è un'attività avanzata che consente di definire dati aggiuntivi da elaborare nel flusso di lavoro.

## Contesto di utilizzo {#context-of-use}

L **[!UICONTROL Enrichment]** 'attività viene utilizzata in genere per attività di targeting o dopo l'importazione di un file e prima delle attività che consentono l'uso di dati mirati.

Questa attività contiene funzioni di arricchimento più avanzate dell' **[!UICONTROL Query]** attività. Alcuni casi semplici di arricchimento possono essere eseguiti direttamente nell'attività [Query](../../automating/using/query.md#enriching-data).

Con l' **[!UICONTROL Enrichment]** attività, potete sfruttare la transizione in entrata e configurare l'attività per completare la transizione di output con dati aggiuntivi. Consente di combinare dati provenienti da più set o di creare collegamenti a una risorsa temporanea.

## Configurazione {#configuration}

Per configurare un **[!UICONTROL Enrichment]** 'attività:

1. Trascina un **[!UICONTROL Enrichment]** 'attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante dalle azioni rapide visualizzate.
1. Se l'attività ha diverse transizioni in entrata, selezionate l ' **[!UICONTROL Primary set]**. I dati aggiuntivi configurati in questa attività saranno aggiunti al set principale nella transizione in uscita.

   Se il set principale contiene già dati aggiuntivi, potete scegliere di mantenerli o rimuoverli. Se deselezionate questa **[!UICONTROL Keep all additional data from the main set]** opzione, solo i dati aggiuntivi configurati in **[!UICONTROL Enrichment]** vengono mantenuti nella transizione in uscita.

1. In presenza di diverse transizioni in entrata, definite le relazioni tra il set principale e gli altri dati in entrata nella **[!UICONTROL Advanced Relations]** scheda dell'attività. È possibile aggiungere più rapporti utilizzando il **[!UICONTROL Add element]** pulsante.

   Quando definite una nuova relazione, selezionate il set di dati in entrata che desiderate collegare al set principale. Quindi definite il tipo di relazione. Sono disponibili diversi tipi di relazioni, a seconda dei dati in entrata e del modello dati:

   * **[!UICONTROL 1 cardinality simple link]**: Ogni record dei dati in entrata è associato a uno e un solo record dal set principale. Ogni record del set principale ha un record associato nei dati collegati.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 o più record (N) registrati dai dati collegati possono essere associati a 1 record del set principale.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: i record del set principale possono essere associati a 0 o 1 record dai dati collegati, ma non più di uno.
   Una volta definito, **[!UICONTROL Cardinality]** definire un **[!UICONTROL Reconciliation criteria]**. I **[!UICONTROL Source expression]** criteri di riconciliazione possono essere un campo dalla risorsa di destinazione, un ['espressione](../../automating/using/advanced-expression-editing.md) o direttamente un valore specificato tra virgolette.

   Definite una **[!UICONTROL Label]** e un' **[!UICONTROL ID]** altra che sarà facilmente individuabile più avanti nel flusso di lavoro.

   >[!NOTE]
   >
   >Potete definire solo le relazioni tra il set principale e le altre transizioni in entrata collegate all' **[!UICONTROL Enrichment]** attività. Per casi più semplici destinati alla definizione delle relazioni con le risorse del database, utilizzate un'attività [di riconciliazione](../../automating/using/reconciliation.md) .

1. Definite i dati aggiuntivi dalla **[!UICONTROL Additional data]** scheda dell'attività. Potete definire ulteriori dati (campi semplici, aggregati e raccolte) correlati alla dimensione di targeting del set principale o in base ai collegamenti creati nella **[!UICONTROL Advanced relations]** scheda dell **[!UICONTROL Enrichment]** 'attività.

   Consultare la [sezione Arricchimento dei dati](../../automating/using/query.md#enriching-data) .

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

I dati sono ora disponibili per l'utilizzo nelle attività connesse dopo l ' **[!UICONTROL Enrichment]**. Ad esempio, è possibile trovarlo sotto il **[!UICONTROL Additional data (targetData)]** collegamento dei campi di personalizzazione in un contenuto e-mail.

## Esempio: Arricchimento dei dati di profilo con i dati contenuti in un file {#example--enriching-profile-data-with-data-contained-in-a-file}

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

   Con questo esempio di file, useremo l'indirizzo e-mail per riconciliare i dati con i profili del database. Potete inoltre abilitare ID univoci come descritto in [questo documento](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* **[!UICONTROL Enrichment]** Un'attività che crea un collegamento tra i dati della transazione caricati dal file e quelli selezionati nell ' **[!UICONTROL Query]**. Il collegamento è definito nella **[!UICONTROL Advanced relations]** scheda dell'attività. Il collegamento si basa sulla transizione proveniente dall' **[!UICONTROL Load file]** attività. Utilizza il campo «email» della risorsa del profilo e la colonna «cliente» del file importato come criteri di riconciliazione.

   ![](assets/enrichment_example_workflow2.png)

   Una volta creato il collegamento, vengono aggiunti **[!UICONTROL Additional data]** due set:

   * Una raccolta di due righe corrispondenti alle due ultime transazioni di ogni profilo. Per questa raccolta, il nome del prodotto, la data di transazione e il prezzo del prodotto vengono aggiunti come dati aggiuntivi. Un ordinamento decrescente viene applicato ai dati. Per creare la raccolta, dalla **[!UICONTROL Additional data]** scheda:

      Selezionate il collegamento precedentemente definito nella **[!UICONTROL Advanced relations]** scheda dell'attività.

      ![](assets/enrichment_example_workflow3.png)

      Controllate **[!UICONTROL Collection]** e specificate il numero di righe da recuperare (2 in questo esempio). In questa schermata, potete personalizzare l' **[!UICONTROL Alias]** e la **[!UICONTROL Label]** raccolta. Tali valori saranno visibili nelle attività seguenti del flusso di lavoro quando si fa riferimento a questa raccolta.

      ![](assets/enrichment_example_workflow4.png)

      Come **[!UICONTROL Data]** per la raccolta, selezionate le colonne che verranno utilizzate nella distribuzione finale.

      ![](assets/enrichment_example_workflow6.png)

      Applica un ordinamento decrescente alla data della transazione per recuperare le transazioni più recenti.

      ![](assets/enrichment_example_workflow7.png)

   * Un aggregato complessivo che conta il numero totale di transazioni per ogni profilo. Questo aggregato verrà utilizzato in seguito per filtrare profili con almeno due transazioni registrate. Per creare l'aggregazione, dalla **[!UICONTROL Additional data]** scheda:

      Selezionate il collegamento precedentemente definito nella **[!UICONTROL Advanced relations]** scheda dell'attività.

      ![](assets/enrichment_example_workflow3.png)

      Seleziona **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      Come **[!UICONTROL Data]** per mantenere, definite un **Totale complessivo** . Se necessario, specificate un alias personalizzato per trovarlo più rapidamente nelle attività seguenti.

      ![](assets/enrichment_example_workflow9.png)

* Un **[!UICONTROL Segmentation]** 'attività con un solo segmento, che recupera profili della destinazione iniziale con almeno due transazioni registrate. Sono esclusi i profili con una sola transazione. A tal fine, la query della segmentazione viene effettuata sull'aggregazione precedentemente definita.

   ![](assets/enrichment_example_workflow5.png)

* **[!UICONTROL Email delivery]** Un'attività che utilizza i dati aggiuntivi definiti nel metodo **[!UICONTROL Enrichment]** per recuperare in modo dinamico i due ultimi acquisti effettuati dal profilo. Durante l'aggiunta di un campo personalizzato **si possono trovare dati aggiuntivi nel** nodo dati aggiuntivi (targetdata).

   ![](assets/enrichment_example_workflow10.png)

**Argomento correlato:**

* [Arricchimento dei profili cliente con dati esterni](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)

