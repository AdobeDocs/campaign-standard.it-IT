---
title: External signal
description: L’attività External signal attiva un flusso di lavoro quando alcune condizioni vengono soddisfatte in un altro flusso di lavoro.
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
source-git-commit: 3cb37426410eeb8be04c9c75afa4505894b15140
workflow-type: tm+mt
source-wordcount: '600'
ht-degree: 96%

---


# External signal{#external-signal}

## Descrizione {#description}

![](assets/signal.png)

L’attività **[!UICONTROL External signal]** attiva un flusso di lavoro quando alcune condizioni vengono soddisfatte in un altro flusso di lavoro o da una chiamata API REST.

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL External signal]** viene utilizzata per organizzare e orchestrare diversi processi che fanno parte dello stesso customer journey in flussi di lavoro diversi. Consente di avviare un flusso di lavoro a partire da un altro, permettendo di supportare customer journey più complessi e al tempo stesso di monitorare e reagire meglio in caso di problemi.

L’attività **[!UICONTROL External signal]** è progettata per essere inserita come prima attività di un flusso di lavoro. Può essere attivata dall’attività **[!UICONTROL End]** di un altro flusso di lavoro o da una chiamata API REST (per ulteriori informazioni, consulta la [documentazione API](../../api/using/triggering-a-signal-activity.md)).

Quando viene attivata, i parametri esterni possono essere definiti ed essere disponibili nelle variabili degli eventi del flusso di lavoro. Il processo per chiamare un flusso di lavoro con parametri esterni è descritto in [questa sezione](../../automating/using/calling-a-workflow-with-external-parameters.md).

>[!NOTE]
>
>L’attività può essere attivata non più di una volta ogni 10 minuti.

Tieni presente che un’attività **[!UICONTROL External signal]** può essere attivata da diversi eventi differenti. In tal caso, il **[!UICONTROL External signal]** viene attivato non appena viene eseguito uno dei flussi di lavoro sorgente o una chiamata API. Non è necessario che tutti i flussi di lavoro sorgente siano completati.

**Argomenti correlati**

* [Caso di utilizzo: Attività esterna del segnale e importazione](../../automating/using/external-signal-data-import.md)dei dati.
* [Caso di utilizzo: Chiamata di un flusso di lavoro per creare un&#39;audience da un file utilizzando parametri esterni](../../automating/using/use-case-calling-workflow.md)

## Configurazione {#configuration}

Durante la configurazione di un segnale esterno, è importante per prima cosa configurare l’attività **[!UICONTROL External signal]** nel flusso di lavoro di destinazione. Al termine della configurazione, l’attività **[!UICONTROL External signal]** di questo flusso di lavoro diventa disponibile per configurare l’attività **[!UICONTROL End]** del flusso di lavoro sorgente.

1. Trascina e rilascia un’attività **[!UICONTROL External signal]** nel flusso di lavoro di destinazione.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Modifica l’etichetta dell’attività. Questa etichetta è necessaria per configurare il flusso di lavoro sorgente che attiva il **[!UICONTROL External signal]**.

   Se desideri chiamare il flusso di lavoro con i parametri, utilizza l’area **[!UICONTROL Parameters]** per dichiararli. Per ulteriori informazioni al riguardo, consulta questa sezione: [](../../automating/using/declaring-parameters-external-signal.md).

   ![](assets/external_signal_configuration.png)

1. Conferma la configurazione dell’attività, aggiungi qualsiasi altra attività necessaria e salva il flusso di lavoro.

   >[!NOTE]
   >
   >Se desideri attivare il flusso di lavoro di destinazione da un altro flusso di lavoro, procedi come segue. Se desideri attivare il flusso di lavoro di destinazione da una chiamata API REST, consulta la [documentazione API](../../api/using/triggering-a-signal-activity.md) per ulteriori dettagli.

1. Apri il flusso di lavoro sorgente e seleziona un’attività **[!UICONTROL End]**. Se non è disponibile alcuna attività **[!UICONTROL End]**, aggiungine una dopo l’ultima attività di un ramo del flusso di lavoro.

   Per impostazione predefinita, alcune attività non hanno alcuna transizione in uscita. Puoi aggiungere una transizione in uscita dalla scheda **[!UICONTROL Properties]** di tali attività.

   Ad esempio, in un’attività **[!UICONTROL Update data]**, passa alla scheda **[!UICONTROL Transitions]** e seleziona l’opzione **[!UICONTROL Add an outbound transition without the population]**. Questa opzione consente di aggiungere una transizione che non contiene dati e non richiede spazio superfluo sul sistema. Viene utilizzata solo per collegare l’attività **[!UICONTROL End]** aggiuntiva che attiva il flusso di lavoro di destinazione.

   ![](assets/external_signal_empty_transition.png)

1. Nella scheda **[!UICONTROL External signal]** dell’attività **[!UICONTROL End]**, seleziona il flusso di lavoro di destinazione e l’attività **[!UICONTROL External signal]** da attivare all’interno di tale flusso di lavoro.

   Quando imposti un’attività **[!UICONTROL End]** per attivare un altro flusso di lavoro, la relativa icona viene aggiornata con un simbolo di segnale aggiuntivo.

   Se desideri chiamare il flusso di lavoro con i parametri, utilizza l’area **[!UICONTROL Parameters and values]**. Per ulteriori informazioni al riguardo, consulta questa sezione: [](../../automating/using/defining-parameters-calling-workflow.md).

   ![](assets/external_signal_end.png)

1. Salva il flusso di lavoro sorgente.

Una volta eseguita l’attività **[!UICONTROL End]** del flusso di lavoro sorgente o la chiamata API REST, il flusso di lavoro di destinazione viene attivato automaticamente dall’attività **[!UICONTROL External signal]**.

>[!NOTE]
>
>Il flusso di lavoro di destinazione deve essere avviato manualmente per poter essere attivato. Quando viene avviato, l’**[!UICONTROL External activity]** viene attivata e attende il segnale dal flusso di lavoro sorgente.
