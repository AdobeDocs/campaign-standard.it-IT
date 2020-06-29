---
title: Deduplicazione
description: L'attività di deduplicazione consente di eliminare i duplicati nei risultati delle attività in entrata.
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
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 1%

---


# Deduplicazione{#deduplication}

## Descrizione {#description}

![](assets/deduplication.png)

L&#39; **[!UICONTROL Deduplication]** attività consente di eliminare duplicati nei risultati delle attività in entrata.

## Contesto di utilizzo {#context-of-use}

L&#39; **[!UICONTROL Deduplication]** attività viene generalmente utilizzata dopo le attività di targeting o dopo l&#39;importazione di un file e prima di attività che consentono l&#39;uso di dati con targeting.

Durante la deduplicazione, le transizioni in entrata vengono elaborate separatamente. Ad esempio, se il profilo &#39;A&#39; è presente nel risultato della query 1 e anche nel risultato della query 2, non verrà deduplicato.

Si consiglia pertanto che una deduplicazione abbia una sola transizione in entrata. A questo scopo, potete combinare le vostre diverse query utilizzando attività che corrispondono alle vostre esigenze di targeting, come un&#39;attività dell&#39;unione, un&#39;attività di intersezione, ecc. Ad esempio:

![](assets/dedup_bonnepratique.png)

**Argomenti correlati**

* [Caso di utilizzo: Identificazione di duplicati prima della consegna](../../automating/using/identifying-duplicated-before-delivery.md)
* [Caso di utilizzo: Deduplicazione dei dati da un file importato](../../automating/using/deduplicating-data-imported-file.md)

## Configurazione {#configuration}

Per configurare un&#39;attività di deduplicazione, è necessario immettere un&#39;etichetta, il metodo e i criteri di deduplicazione, nonché le opzioni relative al risultato.

1. Trascinate e rilasciate un&#39; **[!UICONTROL Deduplication]** attività nel flusso di lavoro.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.

   ![](assets/deduplication_1.png)

1. Selezionare **[!UICONTROL Resource type]** su cui eseguire la deduplicazione:

   * **[!UICONTROL Database resource]** se la deduplicazione viene eseguita su dati già presenti nel database. Selezionate il **[!UICONTROL Filtering dimension]** e il **[!UICONTROL Targeting dimension]**, a seconda dei dati da deduplicare. Per impostazione predefinita, la deduplicazione viene eseguita sui **profili**.
   * **[!UICONTROL Temporary resource]** se la deduplicazione viene eseguita sui dati temporanei del flusso di lavoro: selezionare il **[!UICONTROL Targeted set]** contenitore dei dati da deduplicare. Questo caso di utilizzo può essere rilevato dopo l’importazione di un file o se i dati nel database sono stati arricchiti (ad esempio con un codice del segmento).

1. Selezionare il **[!UICONTROL Number of unique records to keep]**. Il valore predefinito per questo campo è 1. Il valore 0 consente di conservare tutti i duplicati.

   Ad esempio, se i record A e B sono considerati duplicati del record Y e il record C è considerato un duplicato del record Z:

   * Se il valore del campo è 1: vengono conservati solo i record Y e Z.
   * Se il valore del campo è 0: tutti i documenti sono conservati.
   * Se il valore del campo è 2: i record C e Z sono conservati e due record da A, B e Y sono conservati, per caso o a seconda del metodo di deduplicazione selezionato successivamente.

1. Definite i **[!UICONTROL Duplicate identification]** criteri aggiungendo le condizioni nell&#39;elenco fornito. Specificare i campi e/o le espressioni per i quali i valori identici consentono l&#39;identificazione dei duplicati: indirizzo e-mail, nome, cognome, ecc. L&#39;ordine delle condizioni consente di specificare quali elaborare per primi.
1. Nell&#39;elenco a discesa, selezionate l&#39;opzione **[!UICONTROL Deduplication method]** da utilizzare:

   * **[!UICONTROL Choose for me]**: seleziona in modo casuale il record da escludere dai duplicati.
   * **[!UICONTROL Following a list of values]**: consente di definire un valore di priorità per uno o più campi. Per definire i valori, selezionare un campo o creare un&#39;espressione, quindi aggiungere i valori nella tabella appropriata. Per definire un nuovo campo, fare clic sul **[!UICONTROL Add]** pulsante situato sopra l&#39;elenco dei valori.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: consente di conservare i record per i quali il valore dell&#39;espressione selezionata non è vuoto come priorità.

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: questo consente di conservare i record in cui il valore dell&#39;espressione immessa è il più piccolo o il più grande.

      ![](assets/deduplication_4.png)

1. Se necessario, gestite le [Transizioni](../../automating/using/activity-properties.md) dell&#39;attività per accedere alle opzioni avanzate per la popolazione in uscita.
1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.
