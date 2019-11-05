---
title: Arricchimento
description: L'attività Arricchimento è un'attività avanzata che consente di definire dati aggiuntivi da elaborare nel flusso di lavoro.
page-status-flag: mai attivato
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di targeting
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: arricchimento,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Arricchimento{#enrichment}

## Descrizione {#description}

![](assets/enrichment.png)

L' **[!UICONTROL Enrichment]** attività è un'attività avanzata che consente di definire dati aggiuntivi da elaborare nel flusso di lavoro.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL Enrichment]** attività viene generalmente utilizzata dopo le attività di targeting o dopo l'importazione di un file e prima di attività che consentono l'uso di dati con targeting.

Questa attività contiene funzioni di arricchimento più avanzate rispetto all' **[!UICONTROL Query]** attività. Alcuni semplici casi di arricchimento possono essere eseguiti direttamente nell'attività [](../../automating/using/query.md#enriching-data)Query.

Con l' **[!UICONTROL Enrichment]** attività, potete sfruttare la transizione in entrata e configurare l'attività per completare la transizione in uscita con dati aggiuntivi. Consente di combinare i dati provenienti da più set o di creare collegamenti a una risorsa temporanea.

## Configurazione {#configuration}

Per configurare un' **[!UICONTROL Enrichment]** attività:

1. Trascinate e rilasciate un' **[!UICONTROL Enrichment]** attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Se l'attività dispone di diverse transizioni in entrata, selezionate l'opzione **[!UICONTROL Primary set]**. I dati aggiuntivi configurati in questa attività saranno aggiunti a questo set primario nella transizione in uscita.

   Se il set primario contiene già altri dati, potete scegliere di mantenerli o di rimuoverli. Se deselezionate l' **[!UICONTROL Keep all additional data from the main set]** opzione, nella transizione in uscita **[!UICONTROL Enrichment]** vengono mantenuti solo i dati aggiuntivi configurati.

1. In presenza di diverse transizioni in entrata, definite le relazioni tra il set primario e gli altri dati in entrata nella **[!UICONTROL Advanced Relations]** scheda dell'attività. È possibile aggiungere più relazioni utilizzando il **[!UICONTROL Add element]** pulsante.

   Quando si definisce una nuova relazione, selezionare il set di dati in entrata che si desidera collegare al set principale. Definite quindi il tipo di relazione. Sono disponibili diversi tipi di relazioni, a seconda dei dati in entrata e del modello dati:

   * **[!UICONTROL 1 cardinality simple link]**: ogni record dei dati in arrivo è associato a un solo record del set primario. Ogni record del set primario ha un record associato nei dati collegati.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 o più record (N) dai dati collegati possono essere associati a 1 record del set primario.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: i record del set primario possono essere associati a 0 o 1 record dai dati collegati, ma non più di uno.
   Una volta **[!UICONTROL Cardinality]** definito, definire un **[!UICONTROL Reconciliation criteria]**. I criteri **[!UICONTROL Source expression]** di riconciliazione possono essere campi della risorsa di destinazione, un' [espressione](../../automating/using/advanced-expression-editing.md) o direttamente un valore specificato tra virgolette.

   Definire un **[!UICONTROL Label]** e un **[!UICONTROL ID]** che sarà facile identificare in un secondo momento nel flusso di lavoro.

   >[!NOTE]
   >
   >È possibile definire solo le relazioni tra il set principale e le altre transizioni in entrata connesse all' **[!UICONTROL Enrichment]** attività. Per casi più semplici volti a definire le relazioni con le risorse del database, utilizzare un'attività di [riconciliazione](../../automating/using/reconciliation.md) .

1. Definite i dati aggiuntivi dalla **[!UICONTROL Additional data]** scheda dell'attività. Potete definire dati aggiuntivi (campi semplici, aggregati e raccolte) relativi alla dimensione di targeting del set primario o basati sui collegamenti creati nella **[!UICONTROL Advanced relations]** scheda dell' **[!UICONTROL Enrichment]** attività.

   Consultate la sezione [Arricchimento dei dati](../../automating/using/query.md#enriching-data) .

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

I dati sono ora disponibili per l'utilizzo nelle attività connesse dopo l'evento **[!UICONTROL Enrichment]**. Ad esempio, potete trovarlo sotto il **[!UICONTROL Additional data (targetData)]** collegamento dell'esploratore dei campi di personalizzazione in un contenuto e-mail.

## Esempio: Arricchimento dei dati del profilo con i dati contenuti in un file {#example--enriching-profile-data-with-data-contained-in-a-file}

Questo esempio mostra come arricchire i dati del profilo con i dati di acquisto contenuti in un file. A questo punto, i dati di acquisto vengono memorizzati in un sistema di terze parti. Ciascun profilo può contenere diversi acquisti memorizzati nel file. L'obiettivo finale del flusso di lavoro è quello di inviare un'e-mail ai profili di destinazione che hanno acquistato almeno due elementi per ringraziarli della loro fedeltà.

Il flusso di lavoro è configurato come segue:

![](assets/enrichment_example_workflow.png)

* Un' **[!UICONTROL Query]** attività che esegue il targeting dei profili che riceveranno il messaggio.
* Un' **[!UICONTROL Load file]** attività che carica i dati di acquisto. Ad esempio:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   Con questo file di esempio, utilizzeremo l'indirizzo e-mail per riconciliare i dati con i profili del database. Potete inoltre abilitare ID univoci come descritto in [questo documento](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* Un' **[!UICONTROL Enrichment]** attività che crea un collegamento tra i dati della transazione caricati dal file e i profili selezionati nella **[!UICONTROL Query]**. Il collegamento è definito nella **[!UICONTROL Advanced relations]** scheda dell'attività. Il collegamento è basato sulla transizione proveniente dall' **[!UICONTROL Load file]** attività. Utilizza il campo "email" della risorsa profilo e la colonna "customer" del file importato come criteri di riconciliazione.

   ![](assets/enrichment_example_workflow2.png)

   Una volta creato il collegamento, **[!UICONTROL Additional data]** vengono aggiunti due set:

   * Un insieme di due righe corrispondenti alle due ultime transazioni di ciascun profilo. Per questa raccolta, il nome del prodotto, la data della transazione e il prezzo del prodotto vengono aggiunti come dati aggiuntivi. Sui dati viene applicato un ordinamento decrescente. Per creare la raccolta, dalla **[!UICONTROL Additional data]** scheda:

      Selezionate il collegamento precedentemente definito nella **[!UICONTROL Advanced relations]** scheda dell'attività.

      ![](assets/enrichment_example_workflow3.png)

      Selezionare **[!UICONTROL Collection]** e specificare il numero di righe da recuperare (2 in questo esempio). In questa schermata, potete personalizzare l'oggetto **[!UICONTROL Alias]** e l'oggetto **[!UICONTROL Label]** della raccolta. Questi valori saranno visibili nelle seguenti attività del flusso di lavoro quando si fa riferimento a questa raccolta.

      ![](assets/enrichment_example_workflow4.png)

      Per **[!UICONTROL Data]** mantenere la raccolta, selezionate le colonne che verranno utilizzate per la consegna finale.

      ![](assets/enrichment_example_workflow6.png)

      Applica un ordinamento decrescente alla data della transazione per essere certi di recuperare le transazioni più recenti.

      ![](assets/enrichment_example_workflow7.png)

   * Un aggregato che conta il numero totale di transazioni per ciascun profilo. Questo aggregato verrà utilizzato successivamente per filtrare i profili in cui sono registrate almeno due transazioni. Per creare l'aggregazione, dalla **[!UICONTROL Additional data]** scheda:

      Selezionate il collegamento precedentemente definito nella **[!UICONTROL Advanced relations]** scheda dell'attività.

      ![](assets/enrichment_example_workflow3.png)

      Selezionare **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      Per **[!UICONTROL Data]** mantenere, definire un aggregato **Count All** . Se necessario, specificate un alias personalizzato per trovarlo più rapidamente nelle seguenti attività.

      ![](assets/enrichment_example_workflow9.png)

* Un' **[!UICONTROL Segmentation]** attività con un solo segmento, che recupera i profili della destinazione iniziale con almeno due transazioni registrate. Sono esclusi i profili con una sola transazione. A tal fine, la query della segmentazione viene eseguita sull'aggregazione definita in precedenza.

   ![](assets/enrichment_example_workflow5.png)

* Un' **[!UICONTROL Email delivery]** attività che utilizza i dati aggiuntivi definiti in **[!UICONTROL Enrichment]** per recuperare in modo dinamico gli ultimi due acquisti effettuati dal profilo. I dati aggiuntivi si trovano nel nodo **Dati** aggiuntivi (TargetData)quando si aggiunge un campo di personalizzazione.

   ![](assets/enrichment_example_workflow10.png)

**Argomento correlato:**

* [Arricchimento dei profili cliente con dati esterni](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)

