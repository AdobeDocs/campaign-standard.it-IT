---
title: Arricchimento
description: L'attività Arricchimento è un'attività avanzata che consente di definire dati aggiuntivi da elaborare nel flusso di lavoro.
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
ht-degree: 0%

---


# Arricchimento{#enrichment}

## Descrizione {#description}

![](assets/enrichment.png)

L&#39; **[!UICONTROL Enrichment]** attività è un&#39;attività avanzata che consente di definire dati aggiuntivi da elaborare nel flusso di lavoro.

## Contesto di utilizzo {#context-of-use}

L&#39; **[!UICONTROL Enrichment]** attività viene generalmente utilizzata dopo le attività di targeting o dopo l&#39;importazione di un file e prima di attività che consentono l&#39;uso di dati con targeting.

Questa attività contiene funzioni di arricchimento più avanzate rispetto all&#39; **[!UICONTROL Query]** attività. Alcuni semplici casi di arricchimento possono essere eseguiti direttamente nell&#39;attività [](../../automating/using/query.md#enriching-data)Query.

Con l&#39; **[!UICONTROL Enrichment]** attività, potete sfruttare la transizione in entrata e configurare l&#39;attività per completare la transizione in uscita con dati aggiuntivi. Consente di combinare i dati provenienti da più set o di creare collegamenti a una risorsa temporanea.

**Argomenti correlati**

* [Caso di utilizzo: Arricchimento dei dati del profilo con i dati contenuti in un file](../../automating/using/enriching-profile-data-file.md).
* [Caso di utilizzo: Invio di un’e-mail con campi arricchiti](../../automating/using/sending-email-enriched-fields.md)

## Configurazione {#configuration}

Per configurare un&#39; **[!UICONTROL Enrichment]** attività:

1. Trascinate e rilasciate un&#39; **[!UICONTROL Enrichment]** attività nel flusso di lavoro.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Se l&#39;attività dispone di diverse transizioni in entrata, selezionate l&#39;opzione **[!UICONTROL Primary set]**. I dati aggiuntivi configurati in questa attività saranno aggiunti a questo set primario nella transizione in uscita.

   Se il set primario contiene già altri dati, potete scegliere di mantenerli o di rimuoverli. Se deselezionate l&#39; **[!UICONTROL Keep all additional data from the main set]** opzione, nella transizione in uscita **[!UICONTROL Enrichment]** vengono mantenuti solo i dati aggiuntivi configurati.

1. In presenza di diverse transizioni in entrata, definite le relazioni tra il set principale e gli altri dati in entrata nella **[!UICONTROL Advanced Relations]** scheda dell&#39;attività. È possibile aggiungere più relazioni utilizzando il **[!UICONTROL Add element]** pulsante.

   Quando si definisce una nuova relazione, selezionare il set di dati in entrata che si desidera collegare al set principale. Definite quindi il tipo di relazione. Sono disponibili diversi tipi di relazioni, a seconda dei dati in entrata e del modello dati:

   * **[!UICONTROL 1 cardinality simple link]**: ogni record dei dati in arrivo è associato a un solo record del set primario. Ogni record del set primario ha un record associato nei dati collegati.
   * **[!UICONTROL N cardinality collection link]**: 0, 1 o più record (N) dai dati collegati possono essere associati a 1 record del set primario.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: i record del set primario possono essere associati a 0 o 1 record dai dati collegati, ma non a più di uno.
   Una volta **[!UICONTROL Cardinality]** definito, definire un **[!UICONTROL Reconciliation criteria]**. Il **[!UICONTROL Source expression]** criterio di riconciliazione può essere un campo della risorsa di destinazione, un&#39; [espressione](../../automating/using/advanced-expression-editing.md) o direttamente un valore specificato tra virgolette.

   Definire un **[!UICONTROL Label]** e un **[!UICONTROL ID]** che sarà facile identificare in un secondo momento nel flusso di lavoro.

   >[!NOTE]
   >
   >È possibile definire solo le relazioni tra il set principale e le altre transizioni in entrata connesse all&#39; **[!UICONTROL Enrichment]** attività. Per casi più semplici volti a definire le relazioni con le risorse del database, utilizzare un&#39;attività di [riconciliazione](../../automating/using/reconciliation.md) .

1. Definite i dati aggiuntivi dalla **[!UICONTROL Additional data]** scheda dell&#39;attività. Potete definire dati aggiuntivi (campi semplici, aggregati e raccolte) relativi alla dimensione di targeting del set primario o basati sui collegamenti creati nella **[!UICONTROL Advanced relations]** scheda dell&#39; **[!UICONTROL Enrichment]** attività.

   Consulta la sezione [Arricchimento dei dati](../../automating/using/query.md#enriching-data) .

1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.

I dati sono ora disponibili per l&#39;utilizzo nelle attività connesse dopo l&#39;evento **[!UICONTROL Enrichment]**. Ad esempio, potete trovarlo sotto il **[!UICONTROL Additional data (targetData)]** collegamento dell&#39;esploratore dei campi di personalizzazione in un contenuto e-mail.
