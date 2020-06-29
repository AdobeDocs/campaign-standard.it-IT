---
title: Segnale esterno
description: L'attività di segnale esterno attiva un flusso di lavoro quando alcune condizioni vengono soddisfatte in un altro flusso di lavoro.
page-status-flag: never-activated
uuid: 884b6daf-bfd9-440b-8336-004b80c76def
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 911c71b5-da8b-4916-b645-13bba6d21715
context-tags: signal,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 16afc307df6902584624d6457954a472b11c5129
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 3%

---


# Segnale esterno{#external-signal}

## Descrizione {#description}

![](assets/signal.png)

L&#39; **[!UICONTROL External signal]** attività attiva un flusso di lavoro quando alcune condizioni vengono soddisfatte in un altro flusso di lavoro o da una chiamata REST API.

## Contesto di utilizzo {#context-of-use}

L&#39; **[!UICONTROL External signal]** attività viene utilizzata per organizzare e orchestrare diversi processi che fanno parte dello stesso percorso del cliente in flussi di lavoro diversi. Consente di avviare un flusso di lavoro da un altro, consentendo di supportare percorsi cliente più complessi e di monitorare e reagire meglio in caso di problemi.

L&#39; **[!UICONTROL External signal]** attività è progettata per essere inserita come prima attività di un flusso di lavoro. Può essere attivata dall’ **[!UICONTROL End]** attività di un altro flusso di lavoro o da una chiamata REST API (per ulteriori informazioni, consulta la documentazione [](../../api/using/triggering-a-signal-activity.md)API).

Quando viene attivato, i parametri esterni possono essere definiti e disponibili nelle variabili degli eventi del flusso di lavoro. La procedura per chiamare un flusso di lavoro con parametri esterni è descritta in [questa sezione](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>L&#39;attività non può essere attivata più spesso di ogni 10 minuti.

Un&#39; **[!UICONTROL External signal]** attività può essere attivata da diversi eventi diversi. In tal caso, **[!UICONTROL External signal]** viene attivato non appena viene eseguito uno dei flussi di lavoro di origine o una chiamata API. Non richiede che tutti i flussi di lavoro di origine siano completati.

**Argomenti correlati**

* [Caso di utilizzo: Attività esterna del segnale e importazione](../../automating/using/external-signal-data-import.md)dei dati.
* [Caso di utilizzo: Chiamata di un flusso di lavoro per creare un&#39;audience da un file utilizzando parametri esterni](../../automating/using/calling-a-workflow-with-external-parameters.md#use-case)

## Configurazione {#configuration}

Durante la configurazione di un segnale esterno, è importante prima configurare l&#39; **[!UICONTROL External signal]** attività nel flusso di lavoro di destinazione. Al termine della configurazione, l&#39; **[!UICONTROL External signal]** attività di questo flusso di lavoro diventa disponibile per configurare l&#39; **[!UICONTROL End]** attività del flusso di lavoro di origine.

1. Trascinate e rilasciate un&#39; **[!UICONTROL External signal]** attività nel flusso di lavoro di destinazione.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Modificate l&#39;etichetta dell&#39;attività. Questa etichetta è necessaria per configurare il flusso di lavoro di origine che attiva l&#39; **[!UICONTROL External signal]**.

   Se desiderate richiamare il flusso di lavoro con i parametri, utilizzate l&#39; **[!UICONTROL Parameters]** area per dichiararli. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).

   ![](assets/external_signal_configuration.png)

1. Confermate la configurazione dell&#39;attività, aggiungete qualsiasi altra attività necessaria e salvate il flusso di lavoro.

   >[!NOTE]
   >
   >Per attivare il flusso di lavoro di destinazione da un altro flusso di lavoro, procedere come segue. Se desiderate attivare il flusso di lavoro di destinazione da una chiamata REST API, consultate la documentazione [](../../api/using/triggering-a-signal-activity.md) API per ulteriori dettagli.

1. Aprite il flusso di lavoro di origine e selezionate un&#39; **[!UICONTROL End]** attività. Se non è disponibile alcuna **[!UICONTROL End]** attività, aggiungerne una dopo l&#39;ultima attività di un ramo del flusso di lavoro.

   Per impostazione predefinita, alcune attività non hanno alcuna transizione in uscita. Dalla **[!UICONTROL Properties]** scheda di queste attività, è possibile aggiungere una transizione in uscita.

   Ad esempio, in un&#39; **[!UICONTROL Update data]** attività, andate alla **[!UICONTROL Transitions]** scheda e selezionate l&#39; **[!UICONTROL Add an outbound transition without the population]** opzione. Questa opzione consente di aggiungere una transizione che non contiene dati e non richiede spazio inutile sul sistema. Viene utilizzato solo per collegare l&#39;attività supplementare **[!UICONTROL End]** che attiva il flusso di lavoro di destinazione.

   ![](assets/external_signal_empty_transition.png)

1. Nella **[!UICONTROL External signal]** scheda dell&#39; **[!UICONTROL End]** attività, selezionate il flusso di lavoro di destinazione e l&#39; **[!UICONTROL External signal]** attività da attivare all&#39;interno di tale flusso di lavoro.

   Quando impostate un&#39; **[!UICONTROL End]** attività per attivare un altro flusso di lavoro, la relativa icona viene aggiornata con un ulteriore simbolo di segnale.

   Se desiderate richiamare il flusso di lavoro con parametri, utilizzate l&#39; **[!UICONTROL Parameters and values]** area. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow).

   ![](assets/external_signal_end.png)

1. Salvate il flusso di lavoro di origine.

Una volta eseguita l&#39;attività **[!UICONTROL End]** del flusso di lavoro di origine o la chiamata REST API, il flusso di lavoro di destinazione viene attivato automaticamente dall&#39; **[!UICONTROL External signal]** attività.

>[!NOTE]
>
>Per poter avviare il flusso di lavoro di destinazione, è necessario avviarlo manualmente. Quando viene avviato, **[!UICONTROL External activity]** viene attivato e attende il segnale dal flusso di lavoro di origine.
