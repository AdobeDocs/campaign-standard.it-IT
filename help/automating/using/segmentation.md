---
title: Segmentazione
description: L'attività di segmentazione consente di creare uno o più segmenti da una popolazione calcolata dalle attività inserite in precedenza nel flusso di lavoro.
page-status-flag: mai attivato
uuid: 77796f18-cad5-4e7a-9d7b-4ed0dd8943bf
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di targeting
discoiquuid: 0ccd9d02-772e-406b-874a-5381dd0c8709
context-tags: segmentazione,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Segmentazione{#segmentation}

## Descrizione {#description}

![](assets/segmentation.png)

L' **[!UICONTROL Segmentation]** attività consente di creare uno o più segmenti da una popolazione calcolata dalle attività inserite in precedenza nel flusso di lavoro. Al termine dell'attività, possono essere elaborati in un'unica transizione o in diverse transizioni.

>[!NOTE]
>
>Per impostazione predefinita, un membro della popolazione in entrata può appartenere a un solo segmento. I filtri vengono applicati in base all'ordine dei segmenti nell'attività.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL Segmentation]** attività viene generalmente posizionata dopo attività di targeting (query, intersezione, unione, esclusione, ecc.) per definire la popolazione standard in base alla quale si formano i segmenti.

## Configurazione {#configuration}

1. Trascinate e rilasciate un' **[!UICONTROL Segmentation]** attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Selezionare **[!UICONTROL Resource type]** su cui eseguire la segmentazione:

   * **[!UICONTROL Database resource]** se la segmentazione viene eseguita su dati già presenti nel database. Seleziona i dati **[!UICONTROL Filtering dimension]** a seconda dei dati da segmentare. Per impostazione predefinita, la segmentazione viene eseguita sui **profili**.
   * **[!UICONTROL Temporary resource]** se la segmentazione viene eseguita sui dati temporanei del flusso di lavoro: selezionare il **[!UICONTROL Targeted set]** contenitore dei dati da segmentare. Questo caso di utilizzo può essere rilevato dopo l'importazione di un file o se i dati nel database sono stati arricchiti.

1. Selezionare il tipo di transizione in uscita che si desidera utilizzare:

   * **[!UICONTROL Generate one transition per segment]**: viene aggiunta una transizione in uscita per ciascun segmento configurato alla fine dell'attività.
   * **[!UICONTROL Generate all segments in one transition]**: tutti i segmenti configurati vengono raggruppati in un'unica transizione in uscita. Specificate l'etichetta della transizione. I membri di ciascun segmento mantengono il codice del segmento che è stato loro assegnato.

1. Aggiungi un segmento utilizzando il ![](assets/add_darkgrey-24px.png) pulsante o **[!UICONTROL Add an element]** e specifica le proprietà standard:

   * **[!UICONTROL Do not activate the transition if the population is empty]**: il segmento sarà attivato solo se i dati vengono recuperati.
   * **[!UICONTROL Filter initial population (query)]**: consente di filtrare la popolazione di questo segmento.
   * **[!UICONTROL Limit segment population]**: consente di limitare la dimensione del segmento.
   * **[!UICONTROL Filter and limit segment population]**: consente di filtrare la popolazione del segmento e di limitarne le dimensioni.
   * **[!UICONTROL Label]**: etichetta del segmento.
   * **[!UICONTROL Segment code]**: codice assegnato alla popolazione del segmento.Il codice del segmento può essere personalizzato utilizzando un'espressione standard e variabili di eventi (vedere [Personalizzazione di attività con variabili](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables)di eventi).
   * **[!UICONTROL Exclude segment from population]**: consente di escludere il segmento specificato dalla popolazione in uscita dell'attività. Questa opzione può essere utilizzata solo se l’ **[!UICONTROL Generate all segments in the same transition]** opzione è selezionata.
   ![](assets/wkf_segment_new_segment.png)

1. Aprite la visualizzazione dettagliata del segmento per accedere alle opzioni di configurazione di quest'ultimo. A questo scopo, selezionate la casella pertinente nell'elenco dei segmenti dell'attività, quindi selezionate ![](assets/wkf_segment_parameters_24px.png).
1. Se l'opzione per filtrare la popolazione iniziale è selezionata, aprite la **[!UICONTROL Filter]** scheda e specificate la popolazione del segmento. I filtri si basano sulla dimensione di filtraggio selezionata al punto 4. Consultate la sezione [Modifica](../../automating/using/editing-queries.md) query per ulteriori informazioni sul filtro della popolazione.

   Se la segmentazione viene eseguita su una risorsa temporanea, il conteggio e l'anteprima della popolazione non sono disponibili in questa scheda.

1. Se è selezionata l’opzione per limitare la dimensione del segmento, aprite la **[!UICONTROL Limitation]** scheda.

   Innanzitutto, selezionate l’ **[!UICONTROL Type of limit]** opzione da usare:

   * **[!UICONTROL Random sampling]**: la popolazione del segmento viene selezionata in modo casuale tenendo conto, se necessario, della configurazione della **[!UICONTROL Filter]** scheda.
   * **[!UICONTROL Ordered sampling]**: la popolazione del segmento viene selezionata in modo ordinato. È pertanto necessario specificare le colonne da prendere in considerazione e il tipo di ordinamento da applicare. Ad esempio, se selezionate il campo **Età** come colonna di ordinamento mentre applicate un limite **[!UICONTROL Descending sort]** e impostate un limite di 100, verranno mantenuti solo i profili delle prime 100 persone meno recenti.
   Ora specifica la dimensione **[!UICONTROL Limit]** del segmento:

   * **[!UICONTROL Size (as a % of the initial population)]**: specificate la dimensione del segmento utilizzando una percentuale della popolazione iniziale dell'attività.
   * **[!UICONTROL Maximum size]**: specifica un numero massimo di membri per la popolazione del segmento.
   * **[!UICONTROL By data grouping]**: è possibile limitare la popolazione del segmento in base ai valori di un campo specifico della popolazione in entrata. Selezionate il campo da raggruppare, quindi specificate i valori da utilizzare.
   * **[!UICONTROL By data grouping (as a %)]**: è possibile limitare la popolazione del segmento in base ai valori di un campo popolazione in entrata specifico utilizzando una percentuale. Selezionate il campo da applicare al raggruppamento, quindi specificate i valori da utilizzare.

      >[!NOTE]
      >
      >È possibile utilizzare limitazioni diverse per ciascun valore. Ad esempio, è possibile specificare un raggruppamento per il **[!UICONTROL Gender]** campo e limitare la popolazione con **[!UICONTROL Male]** i membri a 10 e la popolazione con **[!UICONTROL Female]** i membri a 30. Se si utilizzano più campi di raggruppamento dati, tutti i raggruppamenti devono avere la stessa dimensione.
   ![](assets/wkf_segment_limit_by_grouping.png)

1. Conferma la configurazione del segmento.
1. Aggiungi tutti i segmenti necessari ripetendo i passaggi da 6 a 10 di questa procedura.
1. Se necessario, modificate i parametri nella **[!UICONTROL Advanced options]** scheda:

   * Selezionare l' **[!UICONTROL Enable overlapping of outbound populations]** opzione se si desidera che un membro della popolazione in entrata appartenga a più segmenti contemporaneamente. La popolazione in uscita dell'attività può superare quella in entrata.
   * Selezionare l' **[!UICONTROL Concatenate the code of each segment]** opzione se alla popolazione in entrata è già stato assegnato un codice di segmento da mantenere. Il codice del segmento specificato nell'attività verrà aggiunto al codice del segmento iniziale.
   * Selezionare l' **[!UICONTROL Generate complement]** opzione se si desidera sfruttare la popolazione rimanente.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Esempio {#example}

L'esempio seguente mostra una segmentazione dei profili di database in base al gruppo di età. Lo scopo del flusso di lavoro è quello di inviare un messaggio e-mail specifico per ogni gruppo di età. Dato che questo flusso di lavoro fa parte di una campagna di test, ogni segmento può contenere solo un massimo di 100 profili selezionati in modo casuale, al fine di utilizzare audience allo stesso tempo limitate e rappresentative.

![](assets/wkf_segment_example_4.png)

Il flusso di lavoro è costituito dai seguenti elementi:

* Un' **[!UICONTROL Scheduler]** attività per specificare la data di esecuzione del flusso di lavoro. Fare riferimento alla sezione [Pianificatore](../../automating/using/scheduler.md) .
* Un' **[!UICONTROL Query]** attività per il targeting dei profili di persone il cui compleanno e indirizzo e-mail sono stati immessi. Fare riferimento alla sezione [Query](../../automating/using/query.md) .
* Un' **[!UICONTROL Segmentation]** attività per creare 3 segmenti divisi in diverse transizioni in uscita: 18-25 anni, 26-32 anni e profili che hanno più di 32 anni. I segmenti sono definiti in base ai seguenti parametri:

   ![](assets/wkf_segment_example_3.png)

   * Filtro sulla pagina per definire il gruppo di età del segmento

      ![](assets/wkf_segment_new_segment.png)

   * Limite **[!UICONTROL Random sampling]** del tipo collegato a un **[!UICONTROL Maximum size]** limite di 100

      ![](assets/wkf_segment_example_1.png)

* Un' **[!UICONTROL Email delivery]** attività per segmento. Fare riferimento alla sezione [Invio](../../automating/using/email-delivery.md) e-mail.

