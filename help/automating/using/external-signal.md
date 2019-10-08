---
title: Segnale esterno
seo-title: Segnale esterno
description: Segnale esterno
seo-description: L'attività di segnale esterno attiva un flusso di lavoro quando alcune condizioni vengono soddisfatte in un altro flusso di lavoro.
page-status-flag: mai attivato
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di esecuzione
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: segnale,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 94c7649448aff859daaf2bbe9a4d17a5187ac71f

---


# Segnale esterno{#external-signal}

## Descrizione {#description}

![](assets/signal.png)

L' **[!UICONTROL External signal]** attività attiva un flusso di lavoro quando alcune condizioni vengono soddisfatte in un altro flusso di lavoro o da una chiamata REST API.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL External signal]** attività viene utilizzata per organizzare e orchestrare diversi processi che fanno parte dello stesso percorso del cliente in flussi di lavoro diversi. Consente di avviare un flusso di lavoro da un altro, consentendo di supportare percorsi cliente più complessi e di monitorare e reagire meglio in caso di problemi.

L' **[!UICONTROL External signal]** attività è progettata per essere inserita come prima attività di un flusso di lavoro. Può essere attivata dall’ **[!UICONTROL End]** attività di un altro flusso di lavoro o da una chiamata REST API (per ulteriori informazioni, consulta la documentazione [](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity) API ).

Quando viene attivato, i parametri esterni possono essere definiti e disponibili nelle variabili degli eventi del flusso di lavoro. La procedura per chiamare un flusso di lavoro con parametri esterni è descritta in [questa sezione](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>L'attività non può essere attivata più spesso di ogni 10 minuti.

Un' **[!UICONTROL External signal]** attività può essere attivata da diversi eventi diversi. In tal caso, **[!UICONTROL External signal]** viene attivato non appena viene eseguito uno dei flussi di lavoro di origine o una chiamata API. Non richiede che tutti i flussi di lavoro di origine siano completati.

## Configurazione {#configuration}

Durante la configurazione di un segnale esterno, è importante prima configurare l' **[!UICONTROL External signal]** attività nel flusso di lavoro di destinazione. Al termine della configurazione, l' **[!UICONTROL External signal]** attività di questo flusso di lavoro diventa disponibile per configurare l' **[!UICONTROL End]** attività del flusso di lavoro di origine.

1. Trascinate e rilasciate un' **[!UICONTROL External signal]** attività nel flusso di lavoro di destinazione.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Modificate l'etichetta dell'attività. Questa etichetta è necessaria per configurare il flusso di lavoro di origine che attiva l' **[!UICONTROL External signal]**.

   Se desiderate richiamare il flusso di lavoro con i parametri, utilizzate l' **[!UICONTROL Parameters]** area per dichiararli. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).

   ![](assets/external_signal_configuration.png)

1. Confermate la configurazione dell'attività, aggiungete qualsiasi altra attività necessaria e salvate il flusso di lavoro.

   >[!NOTE]
   >
   >Per attivare il flusso di lavoro di destinazione da un altro flusso di lavoro, procedere come segue. Se desiderate attivare il flusso di lavoro di destinazione da una chiamata REST API, consultate la documentazione [](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity) API per ulteriori dettagli.

1. Aprite il flusso di lavoro di origine e selezionate un' **[!UICONTROL End]** attività. Se non è disponibile alcuna **[!UICONTROL End]** attività, aggiungerne una dopo l'ultima attività di un ramo del flusso di lavoro.

   Per impostazione predefinita, alcune attività non hanno alcuna transizione in uscita. Dalla **[!UICONTROL Properties]** scheda di queste attività, è possibile aggiungere una transizione in uscita.

   Ad esempio, in un' **[!UICONTROL Update data]** attività, andate alla **[!UICONTROL Transitions]** scheda e selezionate l' **[!UICONTROL Add an outbound transition without the population]** opzione. Questa opzione consente di aggiungere una transizione che non contiene dati e non richiede spazio inutile sul sistema. Viene utilizzato solo per collegare l'attività supplementare **[!UICONTROL End]** che attiva il flusso di lavoro di destinazione.

   ![](assets/external_signal_empty_transition.png)

1. Nella **[!UICONTROL External signal]** scheda dell' **[!UICONTROL End]** attività, selezionate il flusso di lavoro di destinazione e l' **[!UICONTROL External signal]** attività da attivare all'interno di tale flusso di lavoro.

   Quando impostate un' **[!UICONTROL End]** attività per attivare un altro flusso di lavoro, la relativa icona viene aggiornata con un ulteriore simbolo di segnale.

   Se desiderate richiamare il flusso di lavoro con parametri, utilizzate l' **[!UICONTROL Parameters and values]** area. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow).

   ![](assets/external_signal_end.png)

1. Salvate il flusso di lavoro di origine.

Una volta eseguita l'attività **[!UICONTROL End]** del flusso di lavoro di origine o la chiamata REST API, il flusso di lavoro di destinazione viene attivato automaticamente dall' **[!UICONTROL External signal]** attività.

>[!NOTE]
>
>Per poter avviare il flusso di lavoro di destinazione, è necessario avviarlo manualmente. Quando viene avviato, **[!UICONTROL External activity]** viene attivato e attende il segnale dal flusso di lavoro di origine.

## Esempio {#example}

L'esempio seguente illustra l' **[!UICONTROL External signal]** attività in un caso d'uso tipico. Un'importazione di dati viene eseguita in un flusso di lavoro di origine. Dopo l'importazione e l'aggiornamento del database, viene attivato un secondo flusso di lavoro. Questo secondo flusso di lavoro viene utilizzato per aggiornare un aggregato sui dati importati.

Il flusso di lavoro di origine viene presentato come segue:

* Un'attività [Carica file](../../automating/using/load-file.md) carica carica un file contenente nuovi dati di acquisto. Si noti che il [database è stato esteso](../../developing/using/data-model-concepts.md) di conseguenza, in quanto i dati di acquisto non sono presenti per impostazione predefinita nel datamart.

   Ad esempio:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2015;dannymars@example.com;A2;799
   aze124;28/05/2015;dannymars@example.com;A7;8
   aze125;31/07/2015;john.smith@example.com;A7;8
   aze126;14/12/2015;john.smith@example.com;A10;4
   aze127;02/01/2016;dannymars@example.com;A3;79
   aze128;04/03/2016;clara.smith@example.com;A8;149
   ```

* Un'attività di [riconciliazione](../../automating/using/reconciliation.md) crea i collegamenti tra i dati importati e il database in modo che i dati delle transazioni siano correttamente collegati a profili e prodotti.
* Un'attività [Aggiorna dati](../../automating/using/update-data.md) inserisce e aggiorna la risorsa Transazioni del database con i dati in arrivo.
* Un' **[!UICONTROL End]** attività attiva il flusso di lavoro di destinazione, utilizzato per aggiornare gli aggregati.

![](assets/signal_example_source1.png)

Il flusso di lavoro di destinazione viene presentato come segue:

* Un' **[!UICONTROL External signal]** attività attende il completamento del flusso di lavoro di origine.
* Un'attività [Query](../../automating/using/query.md#enriching-data) esegue il targeting dei profili e li arricchisce con una raccolta impostata per recuperare l'ultima data di acquisto.
* Un'attività [Aggiorna dati](../../automating/using/update-data.md) memorizza i dati aggiuntivi in un campo personalizzato dedicato. La risorsa profilo è stata estesa per aggiungere il campo Data **** ultimo acquisto.

![](assets/signal_example_source2.png)

