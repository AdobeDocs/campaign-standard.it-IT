---
title: '"Workflow use-case: Distribuzione tra canali"'
description: '"Workflow use-case: Distribuzione tra canali"'
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8f0460eeadb388fef2a3304623086afd36e68962

---


# Caso di utilizzo del flusso di lavoro: Creazione di una distribuzione tra canali{#cross-channel-delivery}

Questo documento consente di scoprire le seguenti funzionalità di Adobe Campaign tramite un caso di utilizzo standard: creazione di un flusso di lavoro per la distribuzione tra canali.

L&#39;obiettivo è selezionare un&#39;audience dai destinatari del database e segmentarla in due diversi gruppi allo scopo di inviare un&#39;e-mail al primo gruppo e un messaggio SMS al secondo gruppo.

![](assets/wkf_segment_overview.png)

Per maggiori dettagli sui flussi di lavoro e sui diversi canali disponibili in Adobe Campaign, consulta i documenti seguenti:

* [Esplorazione dei flussi di lavoro](../../automating/using/discovering-workflows.md)
* [Canali di comunicazione](../../channels/using/discovering-communication-channels.md)

## Creazione di un flusso di lavoro {#creating-workflow}

Per inviare due consegne diverse a un determinato gruppo, è innanzitutto necessario definire la destinazione.

A tal fine, dovrete creare una query per identificare i destinatari, quindi dovrete creare un flusso di lavoro.

Crea un nuovo flusso di lavoro nel programma o nella campagna di tua scelta:

1. In **[!UICONTROL Marketing Activities]**, fate clic**[!UICONTROL Create]** e selezionate **[!UICONTROL Workflow]**.
1. Selezionate **[!UICONTROL New Workflow]**come tipo di flusso di lavoro e fate clic su**[!UICONTROL Next]**.
1. Immettete le proprietà del flusso di lavoro e fate clic su **[!UICONTROL Create]**.

I passaggi dettagliati per creare un flusso di lavoro sono descritti nella sezione [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md) .

## Creazione di un&#39;attività Query {#creating-query-activity}

Una volta creato il flusso di lavoro, potete accedere alla relativa interfaccia.

Inserite un&#39;attività Query nel flusso di lavoro per eseguire il targeting dei profili che riceveranno le consegne.

1. In **[!UICONTROL Activities]**>**[!UICONTROL Targeting]**, trascina e rilascia un **[!UICONTROL Query activity]**.
1. Fate doppio clic sull&#39;attività.
1. Nella **[!UICONTROL Target]**scheda, individuate le scelte rapide da tastiera e selezionate una delle[audience](../../audiences/using/about-audiences.md).
1. Trascinate la scelta rapida nella zona di modifica. A seconda del tipo di scelta rapida selezionato, verrà visualizzata una finestra.
1. Configurate gli elementi di targeting e quindi confermate la query.

![](assets/wkf_segment_query.png)

Potete creare una query su uno o più elementi.

Utilizzate il **[!UICONTROL Count]**pulsante per visualizzare una stima del numero di profili interessati dalla query.

I passaggi dettagliati per creare un&#39;attività Query sono descritti nella sezione [Query](../../automating/using/query.md) .

## Creazione di un&#39;attività di segmentazione {#creating-segmentation-activity}

Una volta identificato il target dall&#39;attività Query, è necessario selezionare un criterio per segmentare il target in due popolazioni diverse: uno riceverà un&#39;e-mail e l&#39;altro riceverà un SMS.

È necessario utilizzare un&#39;attività di segmentazione per creare uno o più segmenti da una popolazione calcolata a monte in una query.

![](assets/wkf_segment_activity.png)

Il gruppo **E-mail** verrà indirizzato ai destinatari con un indirizzo e-mail definito ma nessun numero di telefono cellulare. Il gruppo **SMS** conterrà i destinatari il cui numero di telefono cellulare è salvato nel loro profilo.

Per configurare la prima transizione (E-mail):

1. Nella **[!UICONTROL Segments]**scheda, per impostazione predefinita è presente un primo segmento. Modificatene le proprietà per configurare quel segmento.

   ![](assets/wkf_segment_properties.png)

1. Selezionare il profilo **[!UICONTROL Email]**come criterio di filtraggio.

   ![](assets/wkf_segment_email.png)

1. Nella nuova finestra visualizzata sullo schermo, selezionare l&#39; **[!UICONTROL Is not empty]**operatore.

   ![](assets/wkf_segment_email_not_empty.png)

1. Aggiungere un secondo criterio di filtraggio **[!UICONTROL Mobile]**, quindi selezionare l&#39;operatore**[!UICONTROL Is empty]**.

   ![](assets/wkf_segment_mobile_empty.png)

   Tutti i profili provenienti dalla query che dispongono di un&#39;e-mail, ma non di un numero di telefono cellulare definito, saranno in questa transizione.

1. Per rendere più chiaro il flusso di lavoro, potete modificare l’etichetta della transizione. Confermate le modifiche.

   ![](assets/wkf_segment_transition_label.png)

La prima transizione è configurata. Per configurare la seconda transizione (SMS):

1. Fate clic sul **[!UICONTROL Add an element]**pulsante per aggiungere una nuova transizione.
1. Definire una condizione che consenta di recuperare tutti i profili i cui numeri di telefono cellulare sono stati forniti. A tal fine, creare una regola sul **[!UICONTROL Mobile]**campo con l&#39;operatore**[!UICONTROL Is not empty]** logico.

   ![](assets/wkf_segment_mobile_not_empty.png)

   Tutti i profili provenienti dalla query per i quali è stato definito un numero di telefono cellulare saranno in questa transizione.

1. Potete modificare l’etichetta della transizione. Confermate le modifiche.

Ora è configurata anche la seconda transizione.

![](assets/wkf_segment_transitions.png)

I passaggi dettagliati per creare un&#39;attività di segmentazione sono descritti nella sezione [Segmentazione](../../automating/using/segmentation.md) .

## Creazione di consegne {#creating-deliveries}

Poiché sono già state create due transizioni, è ora necessario aggiungere due tipi di consegne alle transizioni in uscita dell&#39;attività Segmentazione: un **[!UICONTROL Email delivery]**e un**[!UICONTROL SMS delivery]**.

Adobe Campaign consente di aggiungere consegne a un flusso di lavoro. A questo scopo, selezionate una consegna dalla **[!UICONTROL Channels]**categoria della palette Attività del flusso di lavoro.

![](assets/wkf_segment_deliveries1.png)

Per creare una consegna e-mail:

1. Trascinare un segmento **[!UICONTROL Email delivery]**dopo il primo.
1. Fate doppio clic sull&#39;attività per modificarla.
1. Selezionare **[!UICONTROL Simple email]**.
1. Selezionate **[!UICONTROL Add an outbound transition with the population]**e fate clic su**[!UICONTROL Next]**.

   ![](assets/wkf_segment_deliveries2.png)

   La transizione in uscita vi permetterà di recuperare la popolazione e i registri di tracciamento. Sarà possibile utilizzare questo, ad esempio, per inviare una seconda posta alle persone che non hanno fatto clic nella prima posta.

1. Selezionate un modello e-mail e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà e-mail e fate clic su **[!UICONTROL Next]**.
1. Per creare il layout del messaggio e-mail, selezionate **[!UICONTROL Use the Email Designer]**.
1. Modificate e salvate il contenuto.
1. Nella **[!UICONTROL Schedule]**sezione del dashboard dei messaggi, deselezionate l&#39;opzione**[!UICONTROL Request Confirm before sent messages}**(Conferma richiesta CONTROL prima dell&#39;invio dei messaggi).

I passaggi dettagliati per creare un&#39;attività e-mail sono descritti nella sezione relativa alla consegna [](../../automating/using/email-delivery.md) delle e-mail.

Per creare un invio SMS:

1. Trascinate e rilasciate un segmento **[!UICONTROL SMS delivery]**dopo l’altro.
1. Fate doppio clic sull&#39;attività per modificarla.
1. Selezionate **[!UICONTROL SMS]**e fate clic su**[!UICONTROL Next]**.
1. Selezionate un modello SMS e fate clic su **[!UICONTROL Next]**.
1. Immettete le proprietà SMS e fate clic su **[!UICONTROL Next]**.
1. Modificate e salvate il contenuto.

I passaggi dettagliati per la creazione di un&#39;attività SMS sono descritti nella sezione relativa alla consegna [di](../../automating/using/sms-delivery.md) SMS.

Una volta create e modificate le consegne, il flusso di lavoro è pronto per essere avviato.

![](assets/wkf_segment_deliveries.png)

## Esecuzione del flusso di lavoro {#running-the-workflow}

Una volta avviato il flusso di lavoro, la popolazione di destinazione dell&#39;attività Query sarà segmentata per ricevere una consegna tramite e-mail o SMS.

Per eseguire il flusso di lavoro, fate clic sul **[!UICONTROL Start]**pulsante nella barra delle azioni.

Puoi accedere alle tue consegne dal menu **[!UICONTROL Marketing plans]**>**[!UICONTROL Marketing activities]** Avanzate tramite il logo Adobe Campaign. Fate clic sul **[!UICONTROL Reports]**pulsante consegna e quindi sul pulsante per accedere ai rapporti[di](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports)consegna, ad esempio il riepilogo della consegna, il tasso di apertura o il rendering dell&#39;e-mail in base alla inbox del messaggio dei destinatari.