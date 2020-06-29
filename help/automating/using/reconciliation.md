---
title: Riconciliazione
description: L’attività Riconciliazione consente di collegare dati non identificati a risorse esistenti.
page-status-flag: never-activated
uuid: 7884db8c-1717-4724-be15-3b0b32ccc071
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: cb8c43f4-9cdd-4e85-99a4-004b36b336aa
context-tags: reconciliation,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 1%

---


# Riconciliazione{#reconciliation}

## Descrizione {#description}

![](assets/reconciliation.png)

L&#39; **[!UICONTROL Reconciliation]** attività consente di collegare dati non identificati a risorse esistenti.

## Contesto di utilizzo {#context-of-use}

L&#39; **[!UICONTROL Reconciliation]** attività è essenzialmente utilizzata a scopo di gestione dei dati e implica due diversi casi d&#39;uso:

* Aggiunta di relazioni: una **[!UICONTROL Links]** scheda consente di aggiungere collegamenti tra i dati in entrata e diverse altre dimensioni del database  Adobe Campaign.

   Ad esempio, un file contenente i dati di acquisto può contenere anche informazioni per identificare i prodotti acquistati e l&#39;acquirente. Due dimensioni aggiuntive (oltre a quelle degli **acquisti**) sono pertanto interessate dai dati del file: le dimensioni **Prodotti** e **Profili** . Le relazioni devono quindi essere create tra queste e la dimensione **Acquisti** (fare riferimento all&#39;esempio seguente).

   Quando si definisce una relazione, ai dati in entrata viene aggiunta una colonna per fare riferimento alla chiave esterna della dimensione collegata.

   >[!NOTE]
   >
   >Questa operazione implica che i dati delle dimensioni collegate sono già presenti nel database. Ad esempio, se importate un file di acquisti che mostra quale prodotto è stato acquistato, in quale momento, da quale client, ecc., il prodotto e il client devono già esistere nel database.

* Identificazione dei dati: una **[!UICONTROL Identification]** scheda consente di collegare semplicemente i dati in entrata alle colonne di una dimensione esistente nel database del Adobe Campaign . Dopo l&#39;attività, i dati sono identificati come appartenenti alla dimensione definita.

   Ad esempio, potete eseguire un salvataggio di audience, un aggiornamento del database, ecc.

Ad esempio, l&#39; **[!UICONTROL Reconciliation]** attività può essere posizionata dopo un&#39;attività di dati di caricamento allo scopo di importare dati non standard nel database.

**Argomenti correlati:**

* [Caso di utilizzo: Riconciliazione dei dati mediante le relazioni](../../automating/using/reconciliation-using-relations.md)
* [Caso di utilizzo: Aggiornamento dei dati tramite riconciliazione](../../automating/using/data-update-reconciliation.md)
* [Caso di utilizzo: Riconciliare un pubblico di file con il database](../../automating/using/reconcile-file-audience-with-database.md)

## Configurazione {#configuration}

1. Trascinate e rilasciate un&#39; **[!UICONTROL Reconciliation]** attività nel flusso di lavoro, dopo una transizione contenente una popolazione la cui dimensione di targeting non proviene direttamente da  Adobe Campaign. Per ulteriori informazioni, consulta [Impostazione del targeting di dimensioni e risorse](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Per definire i collegamenti tra i dati in entrata e altre dimensioni del database, passare alla **[!UICONTROL Links]** scheda.

   Aggiungi tutte le relazioni necessarie. Per ogni relazione, selezionate prima la dimensione collegata, quindi nei dettagli del collegamento, specificate i campi corrispondenti.

1. Per identificare semplicemente i dati in entrata, passare alla **[!UICONTROL Identification]** scheda e selezionare la **[!UICONTROL Identify the document from the working data]** casella.

   Selezionare la dimensione di targeting a cui si desidera riconciliare i dati in entrata.

   Aggiungi criteri di riconciliazione per collegare un record di transizione in entrata a un record dimensione di targeting selezionato. Se vengono specificati più criteri, questi devono essere verificati per consentire il funzionamento del collegamento tra tutti i dati.

   Scegliete la **[!UICONTROL Processing unidentified source lines]** modalità:

   * **[!UICONTROL Ignore them]**: solo i dati identificabili vengono conservati nella transizione in uscita dell&#39;attività.
   * **[!UICONTROL Keep in the outbound population]**: tutti i dati della transizione in entrata vengono conservati nella transizione in uscita dell&#39;attività.

1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.
