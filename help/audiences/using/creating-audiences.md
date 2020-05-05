---
title: Creazione di audience
description: Scopri come creare audience in Adobe Campaign.
page-status-flag: never-activated
uuid: fe99b31b-a949-4832-b0e6-2b36d1c8be80
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: df8bdcfb-be5e-4044-bc26-aa3466accbbe
context-tags: readAudience,main;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Creazione di audience{#creating-audiences}

## Creazione di audience di query {#creating-query-audiences}

Questa sezione descrive come creare un&#39;audience **Query** . Potete anche creare audience dall&#39;importazione di un file o dal targeting in un [flusso di lavoro](../../automating/using/get-started-workflows.md).

Dall&#39;elenco dei tipi di pubblico, puoi creare dei tipi di pubblico eseguendo delle query sui profili di Adobe Campaign o importando un pubblico Adobe Experience Cloud.

1. Passate all&#39;elenco delle audience tramite la **[!UICONTROL Audiences]** scheda o la scheda.

   ![](assets/audiences_query_1.png)

1. Selezionate **[!UICONTROL Create]** per accedere alla schermata e creare una nuova audience.

   ![](assets/audiences_query.png)

1. Denominate il pubblico. L&#39;etichetta dell&#39;audience viene utilizzata nell&#39;elenco delle audience e nella palette dello strumento di query.
1. Scegliete un tipo di **[!UICONTROL Query]** pubblico: le audience definite da una query vengono ricalcolate a ogni ulteriore utilizzo.

   ![](assets/audience_type_selection.png)

1. Quindi selezionate il **[!UICONTROL Targeting dimension]** tipo di filtro che desiderate utilizzare per filtrare i clienti. Ogni audience è costituita da una singola dimensione di targeting. Ad esempio, non potete creare un&#39;audience composta da profili, profili di test e sottoscrittori. Per ulteriori informazioni sulle dimensioni di targeting, consultate [questa pagina](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Create la query per definire la popolazione di audience. Fare riferimento alla sezione sulla [modifica delle query](../../automating/using/editing-queries.md).
1. Fate clic sul **[!UICONTROL Create]** pulsante per salvare il pubblico.

>[!NOTE]
>
>Puoi aggiungere una descrizione a questo pubblico e definire le autorizzazioni di accesso tramite l&#39; **[!UICONTROL Edit properties]** icona.

## Creazione di tipi di pubblico di elenchi {#creating-list-audiences}

Questa sezione descrive come creare un pubblico **Elenco** dopo il targeting in un flusso di lavoro. Potete anche creare audience importando un file in un [flusso di lavoro](../../automating/using/get-started-workflows.md) o tramite una query dal **[!UICONTROL Audiences]** menu.

Per creare un pubblico **Elenco** , procedere come segue:

1. Nella scheda Attività **** marketing, fai clic su **Crea** , quindi seleziona **Flusso di lavoro**.

   ![](assets/audiences_list_1.png)

1. Trascinare e rilasciare, quindi configurare le attività di targeting che consentiranno di selezionare una popolazione con una dimensione **nota** . L&#39;elenco delle attività disponibili e la relativa configurazione sono descritti in dettaglio nella sezione Attività [di](../../automating/using/about-targeting-activities.md) targeting.

   È possibile utilizzare un&#39; **[!UICONTROL Query]** attività, o importare dati utilizzando un&#39; **[!UICONTROL Load file]** attività prima di utilizzare un&#39; **[!UICONTROL Reconciliation]** attività per identificare la dimensione dei dati importati. Qui, vogliamo indirizzare i destinatari che si sono iscritti a Sport Newsletter con un&#39; **[!UICONTROL Query]** attività .

   ![](assets/audiences_list_2.png)

1. Dopo il targeting, trascina e rilascia un&#39; **[!UICONTROL Save audience]** attività nel flusso di lavoro. Ad esempio, potete scegliere di **[!UICONTROL Create or update an audience]** creare e aggiornare automaticamente il pubblico con nuovi dati. In questo caso, aggiungete un&#39; **[!UICONTROL Scheduler]** attività all&#39;inizio del flusso di lavoro.

   Per ulteriori informazioni sulla configurazione di questa attività, consultate la sezione [Salva pubblico](../../automating/using/save-audience.md) .

   ![](assets/audiences_list_3.png)

1. Salvate e avviate il flusso di lavoro.

   Dal momento che **[!UICONTROL Save audience]** viene posizionato dopo un targeting con una dimensione nota, le audience create tramite questa attività sono audience **List** .

   Il contenuto dell&#39;audience salvata è quindi disponibile nella visualizzazione dettagliata dell&#39;audience a cui è possibile accedere tramite l&#39;elenco delle audience. Le colonne disponibili in questa visualizzazione corrispondono alle colonne della transizione in entrata dell&#39;attività di salvataggio del flusso di lavoro. Ad esempio: le colonne del file importato, i dati aggiuntivi aggiunti da una query.

   ![](assets/audiences_list_4.png)

## Creazione di audience di file {#creating-file-audiences}

In questa sezione viene illustrato come creare un pubblico di **file** importando un file in un flusso di lavoro. Potete anche creare audience da un&#39;attività di targeting in un [flusso di lavoro](../../automating/using/get-started-workflows.md) o tramite una query dal **[!UICONTROL Audiences]** menu.

Per creare un pubblico di **file** , procedere come segue:

1. Nella scheda Attività **** marketing, fai clic su **Crea** , quindi seleziona **Flusso di lavoro**.
1. Trascinare e rilasciare, quindi configurare un&#39; **[!UICONTROL Load file]** attività che consenta di importare una popolazione con una dimensione **sconosciuta** al momento dell&#39;esecuzione del flusso di lavoro. Per ulteriori informazioni sulla configurazione di questa attività, consultate la sezione [Carica file](../../automating/using/load-file.md) .

   ![](assets/audience_files_1.png)

1. Trascinate e rilasciate un&#39; **[!UICONTROL Save audience]** attività dopo l&#39; **[!UICONTROL Load file]** attività. Per ulteriori informazioni sulla configurazione di questa attività, consultate la sezione [Salva pubblico](../../automating/using/save-audience.md) .
1. Salvate e avviate il flusso di lavoro.

   ![](assets/audience_files_2.png)

   Poiché la dimensione dati **[!UICONTROL Save audience]** viene inserita dopo un&#39;importazione, è sconosciuta e le audience create tramite questa attività sono audience **File** .

   Il contenuto dell&#39;audience salvata è quindi disponibile nella visualizzazione dettagliata dell&#39;audience a cui è possibile accedere tramite l&#39;elenco delle audience. Le colonne disponibili in questa visualizzazione corrispondono alle colonne della transizione in entrata dell&#39;attività di salvataggio del flusso di lavoro. Ad esempio: le colonne del file importato, i dati aggiuntivi aggiunti da una query.

   ![](assets/audience_files_3.png)

## Creazione di audience Experience Cloud {#creating-experience-cloud-audiences}

Adobe Campaign consente di condividere e scambiare audience con Adobe Experience Cloud. Un pubblico di tipo **Experience Cloud** viene importato direttamente dal servizio di base Persone ad Adobe Campaign con il flusso di lavoro **[!UICONTROL Import shared audience]** tecnico.

A differenza del tipo di pubblico **Query** che eseguirà query sui profili da Adobe Campaign, il pubblico di **Experience Cloud** è composto da un elenco di ID visitatore.

Per il corretto funzionamento di questa integrazione, è innanzitutto necessario configurarla. Per ulteriori informazioni sulla configurazione e su come importare o esportare audience con il servizio di base Persone, consulta la [sezione](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)seguente.

![](assets/audience_peoplecore.png)

## Modifica delle audience {#editing-audiences}

Esistono diversi modi per modificare un&#39;audience in base al tipo:

* Per modificare un&#39;audience di **Query** , andate all&#39;elenco dei tipi di pubblico tramite il **[!UICONTROL Audiences]** menu o la **[!UICONTROL Audiences]** scheda dalla home page di Adobe Campaign.

   Apri il pubblico interessato. È possibile modificare tutti gli elementi di un&#39;audience creata in precedenza.

   >[!CAUTION]
   >
   >Se si modifica la query, **[!UICONTROL Filtering dimension]** le regole precedentemente definite andranno perdute.

* Per modificare un pubblico **Elenco** o **File** , modificate il flusso di lavoro da cui è stato creato e modificate l&#39; **[!UICONTROL Save audience]** attività. Avviate il flusso di lavoro in modo che l&#39;audience venga modificata.
* Per modificare un pubblico di **Experience Cloud** , fai riferimento alla sezione [Importazione/Esportazione di tipi di pubblico con il servizio](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md) di base Persone.

## Eliminazione dei tipi di pubblico {#deleting-audiences}

Esistono due modi per eliminare uno o più tipi di pubblico. Per prima cosa puoi aggiungere una data di scadenza al tuo pubblico

A questo scopo:

1. Accedi a uno dei tuoi destinatari.
1. Fate clic sul ![](assets/edit_darkgrey-24px.png) pulsante per accedere alla configurazione del pubblico.

   ![](assets/audience_delete_2.png)

1. Nel **[!UICONTROL Expires on]** campo, aggiungi una data di scadenza al pubblico.

   ![](assets/audience_delete_3.png)

1. Fate clic **[!UICONTROL Confirm]** quindi **[!UICONTROL Save]**.

La data di scadenza è ora configurata. Non appena questa data viene raggiunta, il pubblico viene eliminato automaticamente.

Oppure, se devi eliminare un&#39;audience, puoi semplicemente selezionare una o più audience e fare clic sul **[!UICONTROL Delete element]** pulsante.

![](assets/audience_delete_1.png)

