---
title: Salva audience
description: L'attività Salva audience consente di aggiornare un'audience esistente o di creare una nuova audience dalla popolazione calcolata a monte in un flusso di lavoro.
page-status-flag: mai attivato
uuid: 8babb173-fa59-44a7-a2a5-49f45ba6bf99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di targeting
discoiquuid: 1f6bb048-7abd-499b-a4b0-187f9492dc47
context-tags: saveAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Salva audience{#save-audience}

## Descrizione {#description}

![](assets/save_audience.png)

L' **[!UICONTROL Save audience]** attività consente di aggiornare un'audience esistente o di creare una nuova audience dalla popolazione calcolata a monte in un flusso di lavoro. Le audience create o aggiornate da questa attività sono audience **List** o **File** . Vengono aggiunti all'elenco dei tipi di pubblico delle applicazioni e sono disponibili tramite il **[!UICONTROL Audiences]** menu.

>[!NOTE]
>
>Se l'audience creata tramite l' **[!UICONTROL Save audience]** attività è stata arricchita di dati aggiuntivi, non sarà possibile utilizzare questi dati per personalizzare una distribuzione autonoma. Possono essere utilizzati solo da una consegna eseguita in un flusso di lavoro.

Questa attività consente anche di esportare i profili come audience/segmenti di Adobe Experience Cloud. Questo consente di sfruttare questi tipi di pubblico in altre soluzioni Adobe Experience Cloud. Per ulteriori informazioni sui tipi di pubblico condivisi, consulta [Utilizzo dei servizi](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)di base Campaign e People.

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL Save audience]** attività è essenzialmente utilizzata per mantenere i gruppi di popolazione calcolati nello stesso flusso di lavoro, convertendoli in audience riutilizzabili.

## Configurazione {#configuration}

1. Rilascia un' **[!UICONTROL Save audience]** attività nel flusso di lavoro.
1. Connettilo dopo le altre attività di targeting, come una query, un'intersezione, un'unione o un'esclusione.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.
1. Selezionate l’azione da eseguire:

   * **[!UICONTROL Update an existing audience]**: Selezionate un'audience esistente e scegliete il tipo di aggiornamento:

      * **[!UICONTROL Replace audience content with new data]**: Viene sostituito l'intero contenuto del pubblico. I vecchi dati sono persi. Vengono conservati solo i dati provenienti dalla transizione in entrata dell'attività Salva audience.
      * **[!UICONTROL Complete audience with new data]**: I vecchi dati del pubblico vengono conservati e i dati provenienti dalla transizione in entrata dell'attività di salvataggio del pubblico vengono aggiunti ad essa.
   * **[!UICONTROL Create then update an audience]**: Immettete il nome dell'audience e selezionate il tipo di aggiornamento. Se l'audience non esiste già, viene creata. Se esiste già, viene aggiornato in base alla modalità selezionata:

      * **[!UICONTROL Replace audience content with new data]**: Viene sostituito l'intero contenuto del pubblico. I vecchi dati sono persi. Vengono conservati solo i dati provenienti dalla transizione in entrata dell'attività Salva audience.

         Attenzione, questa opzione elimina il tipo di pubblico e la dimensione di targeting dell'audience aggiornata.

      * **[!UICONTROL Complete audience with new data]**: I vecchi dati del pubblico vengono conservati e i dati provenienti dalla transizione in entrata dell'attività di salvataggio del pubblico vengono aggiunti ad essa.

         Attenzione: questa opzione genera un errore se il tipo di pubblico o la dimensione di targeting dell'audience aggiornata non sono compatibili con la configurazione corrente del flusso di lavoro. Ad esempio, non è possibile completare un pubblico di tipo file con profili provenienti da una query.
   * **[!UICONTROL Create a new audience]**: Immettete il nome dell'audience da creare. L'ora e la data di creazione dell'audience verranno automaticamente aggiunte al nome dell'audience. Questo rende l'audience univoca ogni volta che viene eseguito il flusso di lavoro.
   * **[!UICONTROL Share in Adobe Experience Cloud]**: Se hai dei profili di destinazione e desideri esportare il pubblico in Adobe Experience Cloud, seleziona questa opzione, quindi seleziona un'audience condivisa esistente o crei una nuova audience.

      Seleziona anche un elemento **[!UICONTROL Shared Data source]** che corrisponda alla risorsa dei dati contenuti nel pubblico in modo che i dati vengano correttamente riconciliati in Adobe Experience Cloud.

      Utilizzando questa opzione, l'audience condivisa non viene aggiunta all'elenco dei tipi di pubblico di Adobe Campaign disponibili tramite il **[!UICONTROL Audiences]** menu.

      >[!NOTE]
      >
      >Questa opzione è disponibile solo se l'amministratore ha configurato la funzionalità di audience condivise con Adobe Experience Cloud. Per ulteriori informazioni, consulta [Utilizzo dei servizi](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)di base Campaign and People.
   Il tipo di audience salvato o disponibile durante un aggiornamento dipende dalle attività posizionate a monte nel flusso di lavoro.

   Se la dimensione di targeting dell'audience è sconosciuta al momento del salvataggio (ad esempio, se proviene da un file importato), l'audience viene creata o aggiornata come **[!UICONTROL File]** tipo di pubblico.

   Se la dimensione di targeting dell'audience salvata è già definita quando viene salvata (ad esempio, se proviene da un targeting, dopo una query, ecc.), l'audience viene salvata o aggiornata come **[!UICONTROL List]** tipo di pubblico.

   Il contenuto dell'audience salvata è quindi disponibile nella visualizzazione Dettagli dell'audience, a cui è possibile accedere dal **[!UICONTROL Audiences]** menu. Le colonne disponibili in questa visualizzazione corrispondono alle colonne della transizione in entrata dell'attività Salva audience del flusso di lavoro. Ad esempio: le colonne del file importato, i dati aggiuntivi aggiunti da una query.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Esempio {#example}

Il flusso di lavoro definito in questo esempio mostra un aggiornamento regolare del pubblico dal targeting:

* Viene eseguito automaticamente una volta al mese utilizzando un **[!UICONTROL Scheduler]**.
* Potete utilizzare un **[!UICONTROL Query]** per recuperare tutti i profili sottoscritti ai diversi servizi applicativi disponibili.
* L' **[!UICONTROL Save audience]** attività aggiorna l'audience eliminando i profili che hanno annullato la sottoscrizione al servizio dall'ultima esecuzione del flusso di lavoro e aggiungendo i profili con sottoscrizione nuova.

![](assets/save_audience_example_1.png)

L' **[!UICONTROL Save audience]** attività è configurata come segue:

![](assets/save_audience_example_2.png)

