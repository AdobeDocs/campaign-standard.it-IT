---
title: Riconciliazione
description: L’attività Riconciliazione consente di collegare dati non identificati a risorse esistenti.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: ed2e3793-6164-48af-9043-42dc43fa8ed4
source-git-commit: c2c8d2d05bbc376e2153448ca0a9e6ba0f367420
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 78%

---

# Riconciliazione{#reconciliation}

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

Ad esempio, l&#39;attività **[!UICONTROL Reconciliation]** può essere inserita dopo un caricamento di dati per importare dati non standard nel database.

Mentre l&#39;attività **Enrichment** ti consente di definire i dati aggiuntivi da elaborare nel flusso di lavoro (utilizza un&#39;attività **Enrichment** per combinare i dati provenienti da più set o per creare collegamenti a una risorsa temporanea), l&#39;attività **Reconciliation** ti consente di collegare dati non identificati a risorse esistenti. L&#39;operazione Reconciliation implica che i dati delle dimensioni collegate siano già presenti nel database. I casi d&#39;uso sono disponibili in [questa sezione](#use-cases-reconciliation).


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


## Casi d’uso{#use-cases-reconciliation}

Scopri come utilizzare questa attività nei seguenti casi d’uso:

* [Caso di utilizzo: riconciliazione dei dati tramite relazioni](../../automating/using/reconciliation-using-relations.md)
* [Caso di utilizzo: aggiornamento dei dati tramite riconciliazione](../../automating/using/data-update-reconciliation.md)
* [Caso d’uso: riconciliare un pubblico di tipo File con il database](../../automating/using/reconcile-file-audience-with-database.md)