---
title: Deduplication
description: L’attività Deduplication ti consente di eliminare i duplicati nei risultati delle attività in entrata.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 97%

---


# Deduplication{#deduplication}

## Descrizione {#description}

![](assets/deduplication.png)

L’attività **[!UICONTROL Deduplication]** ti consente di eliminare i duplicati nei risultati delle attività in entrata.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Deduplication]** viene generalmente utilizzata dopo attività di targeting o dopo l’importazione di un file e prima di attività che consentono l’utilizzo di dati oggetto di targeting.

Durante la deduplicazione, le transizioni in entrata vengono elaborate separatamente. Ad esempio, se il profilo “A” è presente nel risultato della query 1 e anche nel risultato della query 2, non verrà deduplicato.

È consigliabile pertanto che una deduplicazione abbia una sola transizione in entrata. A questo scopo, puoi combinare le diverse query utilizzando attività che corrispondono alle tue esigenze di targeting, come un’attività di unione, un’attività di intersezione, ecc. Ad esempio:

![](assets/dedup_bonnepratique.png)

**Argomenti correlati**

* [Caso di utilizzo: Identificazione di duplicati prima della consegna](../../automating/using/identifying-duplicated-before-delivery.md)
* [Caso di utilizzo: Deduplicazione dei dati da un file importato](../../automating/using/deduplicating-data-imported-file.md)

## Configurazione {#configuration}

Per configurare un’attività di deduplicazione, devi immettere un’etichetta, il metodo e i criteri di deduplicazione, nonché le opzioni relative al risultato.

1. Trascina e rilascia un’attività **[!UICONTROL Deduplication]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.

   ![](assets/deduplication_1.png)

1. Seleziona il **[!UICONTROL Resource type]** su cui eseguire la deduplicazione:

   * **[!UICONTROL Database resource]** se la deduplicazione viene eseguita su dati già presenti nel database. Seleziona la **[!UICONTROL Filtering dimension]** e la **[!UICONTROL Targeting dimension]**, a seconda dei dati da deduplicare. Per impostazione predefinita, la deduplicazione viene eseguita sui **profili**.
   * **[!UICONTROL Temporary resource]** se la deduplicazione viene eseguita sui dati temporanei del flusso di lavoro: seleziona il **[!UICONTROL Targeted set]** che contiene i dati da deduplicare. Questo caso di utilizzo può essere rilevato dopo l’importazione di un file o se i dati nel database sono stati arricchiti (ad esempio con un codice di segmento).

1. Seleziona **[!UICONTROL Number of unique records to keep]**. Il valore predefinito per questo campo è 1. Il valore 0 ti consente di conservare tutti i duplicati.

   Ad esempio, se i record A e B sono considerati duplicati del record Y e il record C è considerato un duplicato del record Z:

   * Se il valore del campo è 1: vengono conservati solo i record Y e Z.
   * Se il valore del campo è 0: vengono conservati tutti i record.
   * Se il valore del campo è 2: vengono conservati i record C e Z e due record tra A, B e Y, per caso o a seconda del metodo di deduplicazione selezionato successivamente.

1. Definisci i criteri di **[!UICONTROL Duplicate identification]** aggiungendo condizioni nell’elenco fornito. Specifica i campi e/o le espressioni per i quali i valori identici consentono l’identificazione dei duplicati: indirizzo e-mail, nome, cognome, ecc. L’ordine delle condizioni ti consente di specificare quali elaborare per prime.
1. Nell’elenco a discesa, seleziona il **[!UICONTROL Deduplication method]** da utilizzare:

   * **[!UICONTROL Choose for me]**: seleziona in modo casuale il record da escludere dai duplicati.
   * **[!UICONTROL Following a list of values]**: ti consente di definire un valore di priorità per uno o più campi. Per definire i valori, seleziona un campo o crea un’espressione, quindi aggiungi i valori nella tabella appropriata. Per definire un nuovo campo, fai clic sul pulsante **[!UICONTROL Add]** situato sopra l’elenco dei valori.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Non-empty value]**: questo ti consente di conservare i record per i quali il valore dell’espressione selezionata non è vuoto come priorità.

      ![](assets/deduplication_3.png)

   * **[!UICONTROL Using an expression]**: questo ti consente di conservare i record in cui il valore dell’espressione immessa è il minore o il maggiore.

      ![](assets/deduplication_4.png)

1. Se necessario, gestisci le [Transizioni](../../automating/using/activity-properties.md) dell’attività per accedere alle opzioni avanzate per la popolazione in uscita.
1. Conferma la configurazione dell’attività e salva il flusso di lavoro.
