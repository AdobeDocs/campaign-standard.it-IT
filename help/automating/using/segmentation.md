---
title: Segmentation
description: L’attività Segmentation ti consente di creare uno o più segmenti da un gruppo calcolato dalle attività inserite in precedenza nel flusso di lavoro.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3761ee4a-1ce5-4f9e-b2a5-84388b6b9db8
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '885'
ht-degree: 82%

---

# Segmentazione{#segmentation}

## Descrizione {#description}

![](assets/segmentation.png)

L’attività **[!UICONTROL Segmentation]** ti consente di creare uno o più segmenti da un gruppo calcolato dalle attività inserite in precedenza nel flusso di lavoro. Al termine dell’attività, puoi elaborarli in un’unica transizione o in diverse transizioni.

>[!NOTE]
>
>Per impostazione predefinita, un iscritto del gruppo in entrata può appartenere a un solo segmento. I filtri vengono applicati in base all’ordine dei segmenti nell’attività.

**Argomenti correlati:**
* [Caso di utilizzo: segmentazione sulla posizione](../../automating/using/workflow-segmentation-location.md)
* [Caso d’uso: segmentazione in base ai gruppi di età](../../automating/using/segmentation-age-groups.md)

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Segmentation]** viene generalmente inserita dopo le attività di targeting (query, intersezione, unione, esclusione, ecc.) per definire il gruppo standard in base al quale vengono formati i segmenti.

**Argomenti correlati**

* [Caso d&#39;uso: segmentazione dei profili in base ai gruppi di età](../../automating/using/segmentation-age-groups.md).

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Segmentation]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Nella scheda **[!UICONTROL General]**, seleziona **[!UICONTROL Resource type]** su cui deve essere eseguita la segmentazione:

   * **[!UICONTROL Database resource]** se la segmentazione viene eseguita sui dati già presenti nel database. Seleziona la **[!UICONTROL Filtering dimension]** a seconda dei dati che desideri segmentare. Per impostazione predefinita, la segmentazione viene eseguita sui **profili**.
   * **[!UICONTROL Temporary resource]** se la segmentazione viene eseguita sui dati temporanei del flusso di lavoro: seleziona il **[!UICONTROL Targeted set]** contenente i dati da segmentare. Puoi rilevare questo caso di utilizzo dopo l’importazione di un file o se i dati nel database sono stati arricchiti.

1. Seleziona il tipo di transizione in uscita che desideri utilizzare:

   * **[!UICONTROL Generate one transition per segment]**: viene aggiunta una transizione in uscita per ciascun segmento configurato alla fine dell’attività.
   * **[!UICONTROL Generate all segments in one transition]**: tutti i segmenti configurati vengono raggruppati in un’unica transizione in uscita. Specifica l’etichetta della transizione. Gli iscritti di ciascun segmento mantengono il codice del segmento che è stato loro assegnato.

1. Aggiungi un segmento utilizzando il pulsante ![](assets/add_darkgrey-24px.png) o **[!UICONTROL Add an element]** e specifica le proprietà standard:

   * **[!UICONTROL Do not activate the transition if the population is empty]**: il segmento viene attivato solo se i dati vengono recuperati.
   * **[!UICONTROL Filter initial population (query)]**: ti consente di filtrare il gruppo di questo segmento.
   * **[!UICONTROL Limit segment population]**: ti consente di limitare la dimensione del segmento.
   * **[!UICONTROL Filter and limit segment population]**: ti consente di filtrare il gruppo del segmento e di limitarne le dimensioni.
   * **[!UICONTROL Label]**: etichetta del segmento.
   * **[!UICONTROL Segment code]**: codice assegnato al gruppo del segmento. Il codice del segmento può essere personalizzato utilizzando un&#39;espressione standard e variabili di eventi (vedi [questa pagina](../../automating/using/customizing-workflow-external-parameters.md)).
   * **[!UICONTROL Exclude segment from population]**: ti consente di escludere il segmento specificato dal gruppo in uscita dell’attività. Puoi utilizzare questa opzione solo se quella **[!UICONTROL Generate all segments in the same transition]** è selezionata.

   ![](assets/wkf_segment_new_segment.png)

1. Apri la visualizzazione dettagliata del segmento per accedere alle opzioni di configurazione di quest’ultimo. A questo scopo, spunta la casella pertinente nell’elenco dei segmenti dell’attività, quindi seleziona ![](assets/wkf_segment_parameters_24px.png).
1. Se l’opzione per filtrare il gruppo iniziale è selezionata, apri la scheda **[!UICONTROL Filter]** e specifica il gruppo del segmento. I filtri si basano sulla dimensione di filtro selezionata nel passaggio 4. Consulta la sezione [Modifica query](../../automating/using/editing-queries.md) per ulteriori informazioni sul filtro del gruppo.

   Se la segmentazione viene eseguita su una risorsa temporanea, il conteggio e l’anteprima del gruppo non sono disponibili in questa scheda.

1. Se è selezionata l’opzione per limitare la dimensione del segmento, apri la scheda **[!UICONTROL Limitation]**.

   Innanzitutto, seleziona l’opzione **[!UICONTROL Type of limit]** che desideri utilizzare:

   * **[!UICONTROL Random sampling]**: la popolazione del segmento viene selezionata in modo casuale tenendo conto, se necessario, della configurazione della scheda **[!UICONTROL Filter]**.
   * **[!UICONTROL Ordered sampling]**: il gruppo del segmento viene selezionato in modo ordinato. Devi pertanto specificare le colonne da prendere in considerazione e il tipo di ordinamento da applicare. Ad esempio, se selezioni il campo **Age** come colonna di ordinamento mentre applichi un **[!UICONTROL Descending sort]** e imposti un limite di 100, mantieni solo i profili delle prime 100 persone più anziane.

   Ora specifica la dimensione **[!UICONTROL Limit]** del segmento:

   * **[!UICONTROL Size (as a % of the initial population)]**: specifica la dimensione del segmento utilizzando una percentuale del gruppo iniziale dell’attività.
   * **[!UICONTROL Maximum size]**: specifica un numero massimo di iscritti per il gruppo del segmento.
   * **[!UICONTROL By data grouping]**: puoi limitare il gruppo del segmento in base ai valori di un campo specifico del gruppo in entrata. Seleziona il campo da raggruppare, quindi specifica i valori da utilizzare.
   * **[!UICONTROL By data grouping (as a %)]**: puoi limitare il gruppo del segmento in base ai valori di un campo specifico del gruppo in entrata utilizzando una percentuale. Seleziona il campo da applicare al raggruppamento, quindi specifica i valori da utilizzare.

     >[!NOTE]
     >
     >È possibile utilizzare limitazioni diverse per ciascun valore. Ad esempio, puoi specificare un raggruppamento per il campo **[!UICONTROL Gender]** e limitare il gruppo con iscritti **[!UICONTROL Male]** a 10 e il gruppo con iscritti **[!UICONTROL Female]** a 30. Se utilizzi più campi di raggruppamento di dati, devono avere tutti la stessa dimensione.

   ![](assets/wkf_segment_limit_by_grouping.png)

1. Conferma la configurazione del segmento.
1. Aggiungi il maggior numero di segmenti necessario ripetendo i passaggi da 6 a 10 di questa procedura.
1. Se necessario, modifica i parametri nella scheda **[!UICONTROL Advanced options]**:

   * L&#39;opzione **[!UICONTROL Enable overlapping of outbound populations]** definisce come gestire i profili appartenenti a diversi segmenti:
      * Quando l&#39;opzione non è abilitata, l&#39;attività **[!UICONTROL Segmentation]** controlla che un profilo non sia presente in diverse transizioni di output, anche se questo profilo soddisfa i criteri di diversi sottoinsiemi.
      * Quando l’opzione è abilitata, i profili possono essere trovati in diversi sottoinsiemi se soddisfano i relativi criteri di filtro.
   * Se al gruppo in entrata è già stato assegnato un codice di segmento che desideri mantenere, seleziona l&#39;opzione **[!UICONTROL Concatenate the code of each segment]**. Il codice del segmento specificato nell’attività viene aggiunto al codice del segmento iniziale.
   * Se è necessario sfruttare il gruppo rimanente, selezionare l&#39;opzione **[!UICONTROL Generate complement]**. Vedi [Caso d&#39;uso: creazione di consegne con un complemento](../../automating/using/workflow-created-query-with-complement.md).

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.
