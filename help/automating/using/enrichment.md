---
title: Enrichment
description: L’attività Enrichment è un’attività avanzata che ti consente di definire i dati aggiuntivi da elaborare nel flusso di lavoro.
page-status-flag: never-activated
uuid: 8c1693ef-1312-422c-b05d-263553113f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: f67c1caf-3284-4c34-a5b0-8654a95640ae
context-tags: enrichment,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 87e0611fae0560aca276caa3c4cf793e9c095d72
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 96%

---


# Enrichment{#enrichment}

## Descrizione {#description}

![](assets/enrichment.png)

L’attività avanzata **[!UICONTROL Enrichment]** ti consente di definire i dati aggiuntivi da elaborare nel flusso di lavoro.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Enrichment]** viene generalmente utilizzata dopo attività di targeting o dopo l’importazione di un file e prima di attività che consentono l’utilizzo di dati oggetto di targeting.

Questa attività contiene funzioni di arricchimento più avanzate rispetto all’attività **[!UICONTROL Query]**. Alcuni semplici casi di arricchimento possono essere eseguiti direttamente nell’attività [Query](../../automating/using/query.md#enriching-data).

Con l’attività **[!UICONTROL Enrichment]**, puoi sfruttare la transizione in entrata e configurare l’attività in modo da completare la transizione in uscita con l’inserimento di dati aggiuntivi. L’attività ti permette di combinare i dati provenienti da più set o di creare collegamenti a una risorsa temporanea.

**Argomenti correlati**

* [Caso di utilizzo: Arricchimento dei dati del profilo con i dati contenuti in un file](../../automating/using/enriching-profile-data-file.md).
* [Caso di utilizzo: Invio di un’e-mail con campi arricchiti](../../automating/using/sending-email-enriched-fields.md)

## Configurazione {#configuration}

Per configurare un’attività **[!UICONTROL Enrichment]**:

1. Trascina e rilascia un’attività **[!UICONTROL Enrichment]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Se l’attività dispone di diverse transizioni in entrata, seleziona l’opzione **[!UICONTROL Primary set]**. I dati aggiuntivi configurati al suo interno saranno aggiunti a questo set principale nella transizione in uscita.

   Se il set principale contiene già altri dati, puoi scegliere se mantenerli o rimuoverli. Se deselezioni l’opzione **[!UICONTROL Keep all additional data from the main set]**, nella transizione in uscita vengono mantenuti solo i dati aggiuntivi configurati in **[!UICONTROL Enrichment]**.

1. In presenza di varie transizioni in entrata, nella scheda **[!UICONTROL Advanced Relations]** dell’attività puoi definire le relazioni tra il set principale e gli altri dati in entrata. Puoi aggiungere più relazioni utilizzando il pulsante **[!UICONTROL Add element]**.

   Quando stabilisci una nuova relazione, seleziona il set di dati in entrata da collegare a quello principale. A questo punto, specifica il tipo di relazione. A seconda dei dati in entrata e del modello dati, sono disponibili diversi tipi di relazioni:

   * **[!UICONTROL 1 cardinality simple link]**: ogni record dei dati in arrivo è associato a un solo record del set principale. Ciascun record del set principale presenta un record associato all’interno dei dati collegati.
   * **[!UICONTROL N cardinality collection link]**: è possibile associare 0, 1 o più record (N) dei dati collegati a 1 record del set principale.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: i record del set principale possono essere associati a 0 o 1 record dei dati collegati, ma non a più di uno.

   Una volta definito **[!UICONTROL Cardinality]**, imposta anche **[!UICONTROL Reconciliation criteria]**. L’**[!UICONTROL Source expression]** dei criteri di riconciliazione può essere un campo della risorsa di destinazione, un’[espressione](../../automating/using/advanced-expression-editing.md) o direttamente un valore specificato tra virgolette.

   Definisci **[!UICONTROL Label]** e **[!UICONTROL ID]**, i quali risulteranno di facile identificazione in una seconda fase del flusso di lavoro.

   >[!NOTE]
   >
   >È possibile definire esclusivamente le relazioni tra il set principale e le altre transizioni in entrata connesse all’attività **[!UICONTROL Enrichment]** . Per casi più semplici che si propongono di definire le relazioni con le risorse del database, utilizza un’attività di [riconciliazione](../../automating/using/reconciliation.md).

1. Dalla scheda **[!UICONTROL Additional data]** dell’attività puoi definire i dati aggiuntivi. Qui è possibile specificare i dati aggiuntivi (campi semplici, aggregati e raccolte) relativi alla dimensione di targeting del set principale o basati sui collegamenti creati nella scheda **[!UICONTROL Advanced relations]** dell’attività **[!UICONTROL Enrichment]**.

   Consulta la sezione [Arricchimento dei dati](../../automating/using/query.md#enriching-data).

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

Adesso i dati sono disponibili per l’utilizzo nelle attività connesse dopo l’attività **[!UICONTROL Enrichment]**. Ad esempio, li puoi trovare sotto il collegamento **[!UICONTROL Additional data (targetData)]** dell’esploratore dei campi di personalizzazione all’interno del contenuto dell’e-mail.
