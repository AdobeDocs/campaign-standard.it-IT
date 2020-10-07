---
title: Reconciliation
description: L’attività Reconciliation ti consente di collegare dati non identificati a risorse esistenti.
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 95%

---


# Reconciliation{#reconciliation}

## Descrizione {#description}

![](assets/reconciliation.png)

L’attività **[!UICONTROL Reconciliation]** ti consente di collegare dati non identificati a risorse esistenti.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Reconciliation]** viene essenzialmente utilizzata a scopo di gestione dei dati e implica due diversi casi d’uso:

* Aggiunta di relazioni: una scheda **[!UICONTROL Links]** ti consente di aggiungere collegamenti tra dati in entrata e diverse altre dimensioni del database di Adobe Campaign.

   Ad esempio, un file contenente dati di acquisto può contenere anche informazioni per identificare prodotti acquistati e acquirenti. Due dimensioni aggiuntive (oltre a quella di **Purchases**) sono pertanto interessate dai dati del file: le dimensioni **Products** e **Profiles**. È necessario quindi creare relazioni tra queste e la dimensione **Purchases** (consulta l’esempio seguente).

   Quando viene definita una relazione, ai dati in entrata viene aggiunta una colonna per rimandare alla chiave esterna della dimensione collegata.

   >[!NOTE]
   >
   >Questa operazione implica che i dati delle dimensioni collegate siano già presenti nel database. Ad esempio, se importi un file di acquisti che mostra quale prodotto è stato acquistato in un determinato momento da uno specifico cliente, ecc., il prodotto e il cliente devono già esistere nel database.

* Identificazione di dati: una scheda **[!UICONTROL Identification]** ti consente di collegare semplicemente i dati in entrata alle colonne di una dimensione esistente nel database di Adobe Campaign. Dopo l’attività, i dati sono identificati come appartenenti alla dimensione definita.

   Ad esempio, puoi eseguire un salvataggio di pubblico, un aggiornamento del database, ecc.

Ad esempio, puoi inserire l’attività **[!UICONTROL Reconciliation]** dopo un caricamento di dati allo scopo di importare dati non standard nel database.

**Argomenti correlati:**

* [Caso di utilizzo: Riconciliazione dei dati mediante le relazioni](../../automating/using/reconciliation-using-relations.md)
* [Caso di utilizzo: Aggiornamento dei dati tramite riconciliazione](../../automating/using/data-update-reconciliation.md)
* [Caso di utilizzo: Riconciliare un pubblico di file con il database](../../automating/using/reconcile-file-audience-with-database.md)

## Configurazione {#configuration}

1. Trascina e rilascia l’attività **[!UICONTROL Reconciliation]** nel flusso di lavoro, facendo seguire una transizione contenente un gruppo con il targeting di una dimensione che non proviene direttamente da Adobe Campaign. Per ulteriori informazioni, consulta [Dimensioni di targeting e risorse](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Se desideri definire collegamenti tra dati in entrata e altre dimensioni del database, passa alla scheda **[!UICONTROL Links]**.

   Aggiungi il maggior numero di relazioni necessario. Per ogni relazione, seleziona innanzitutto la dimensione collegata, quindi nei dettagli del collegamento, specifica i campi corrispondenti.

1. Se desideri semplicemente identificare i dati in entrata, passa alla scheda **[!UICONTROL Identification]** e seleziona la casella **[!UICONTROL Identify the document from the working data]**.

   Seleziona la dimensione di targeting desiderata per riconciliare i dati in entrata.

   Aggiungi criteri di riconciliazione per collegare un record di transizione in entrata alla dimensione di targeting selezionata. Se specifichi più criteri, devi verificarli per consentire il funzionamento del collegamento tra tutti i dati.

   Scegli la modalità **[!UICONTROL Processing unidentified source lines]**:

   * **[!UICONTROL Ignore them]**: nella transizione in uscita dell’attività vengono conservati solo i dati identificabili.
   * **[!UICONTROL Keep in the outbound population]**: nella transizione in uscita dell’attività vengono conservati tutti i dati della transizione in entrata.

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.
