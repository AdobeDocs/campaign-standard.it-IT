---
title: Save audience
description: L’attività Save audience ti consente di aggiornare un pubblico esistente o crearne uno nuovo dalla popolazione calcolata a monte in un flusso di lavoro.
page-status-flag: never-activated
uuid: 8babb173-fa59-44a7-a2a5-49f45ba6bf99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 1f6bb048-7abd-499b-a4b0-187f9492dc47
context-tags: saveAudience,main
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '803'
ht-degree: 100%

---


# Save audience{#save-audience}

## Descrizione {#description}

![](assets/save_audience.png)

L’attività **[!UICONTROL Save audience]** ti consente di aggiornare un pubblico esistente o crearne uno nuovo dalla popolazione calcolata a monte in un flusso di lavoro. I tipi di pubblico creati o aggiornati da questa attività sono tipi di pubblico **List** o **File**. Vengono aggiunti all’elenco dei tipi di pubblico delle applicazioni e sono disponibili tramite il menu **[!UICONTROL Audiences]**.

>[!NOTE]
>
>Se il pubblico creato tramite l’attività **[!UICONTROL Save audience]** è stata arricchita di dati aggiuntivi, non puoi utilizzare questi dati per personalizzare una consegna autonoma. È possibile utilizzarli solo da una consegna eseguita in un flusso di lavoro.

Questa attività ti consente anche di esportare profili come tipi di pubblico/segmenti di Adobe Experience Cloud. Quindi ti consente di sfruttare questi tipi di pubblico in altre soluzioni di Adobe Experience Cloud. Per ulteriori informazioni sui tipi di pubblico condivisi, consulta [Utilizzo di Campaign e del servizio core People](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

## Contesto di utilizzo {#context-of-use}

L’attività **[!UICONTROL Save audience]** è essenzialmente utilizzata per mantenere i gruppi di popolazione calcolati nello stesso flusso di lavoro, convertendoli in tipi di pubblico riutilizzabili.

## Configurazione {#configuration}

1. Rilascia un’attività **[!UICONTROL Save audience]** nel flusso di lavoro.
1. Connettila dopo le altre attività di targeting, come una query, un’intersezione, un’unione o un’esclusione.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.
1. Seleziona l’azione da eseguire:

   * **[!UICONTROL Update an existing audience]**: seleziona un pubblico esistente e scegli il tipo di aggiornamento:

      * **[!UICONTROL Replace audience content with new data]**: viene sostituito l’intero contenuto del pubblico. I vecchi dati sono persi. Vengono conservati solo i dati della transizione in entrata dell’attività Save audience.
      * **[!UICONTROL Complete audience with new data]**: i vecchi dati del pubblico vengono conservati e i dati della transizione in entrata dell’attività Save audience vengono aggiunti a essi.
   * **[!UICONTROL Create then update an audience]**: immetti il nome del pubblico e seleziona il tipo di aggiornamento. Se il pubblico non esiste già, viene quindi creato. Se esiste già, viene aggiornato in base alla modalità selezionata:

      * **[!UICONTROL Replace audience content with new data]**: viene sostituito l’intero contenuto del pubblico. I vecchi dati sono persi. Vengono conservati solo i dati della transizione in entrata dell’attività Save audience.

         Attenzione: questa opzione elimina il tipo di pubblico e la dimensione di targeting del pubblico aggiornato.

      * **[!UICONTROL Complete audience with new data]**: i vecchi dati del pubblico vengono conservati e i dati della transizione in entrata dell’attività Save audience vengono aggiunti a essi.

         Attenzione: questa opzione genera un errore se il tipo di pubblico o la dimensione di targeting del pubblico aggiornato non sono compatibili con la configurazione corrente del flusso di lavoro. Ad esempio, non puoi completare un pubblico di tipo file con profili provenienti da una query.
   * **[!UICONTROL Create a new audience]**: immetti il nome del pubblico da creare. L’ora e la data della creazione del pubblico vengono automaticamente aggiunte al nome del pubblico. In questo modo il pubblico risulta unico ogni volta che viene eseguito il flusso di lavoro.
   * **[!UICONTROL Share in Adobe Experience Cloud]**: se hai eseguito il targeting dei profili e desideri esportare il pubblico in Adobe Experience Cloud, seleziona questa opzione, quindi seleziona un pubblico condiviso esistente o creane uno nuovo.

      Seleziona anche un elemento **[!UICONTROL Shared Data source]** che corrisponda alla risorsa dei dati contenuti nel pubblico in modo che vengano correttamente riconciliati in Adobe Experience Cloud.

      Utilizzando questa opzione, il pubblico condiviso non viene aggiunto all’elenco dei tipi di pubblico di Adobe Campaign disponibili tramite il menu **[!UICONTROL Audiences]**.

      >[!NOTE]
      >
      >Questa opzione è disponibile solo se l’amministratore ha configurato la funzionalità dei tipi di pubblico condivisi con Adobe Experience Cloud. Per ulteriori informazioni, consulta [Utilizzo di Campaign e del servizio core People](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).
   I tipi di pubblico salvati o disponibili durante un aggiornamento dipende dalle attività inserite a monte nel flusso di lavoro.

   Se la dimensione di targeting del pubblico è sconosciuta al momento del salvataggio (ad esempio se proviene da un file importato), il pubblico viene creato o aggiornato come un pubblico di tipo **[!UICONTROL File]**.

   Se la dimensione di targeting del pubblico salvato è già definita durante il salvataggio (ad esempio se proviene da un targeting, in base a una query, ecc.), il pubblico viene salvato o aggiornato come pubblico di tipo **[!UICONTROL List]**.

   Il contenuto del pubblico salvato è quindi disponibile nella relativa visualizzazione dettagliata, accessibile dal menu **[!UICONTROL Audiences]**. Le colonne disponibili in questa visualizzazione corrispondono alle colonne della transizione in entrata dell’attività Save audience del flusso di lavoro. Ad esempio: le colonne del file importato, i dati aggiuntivi aggiunti da una query.

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

## Esempio {#example}

Il flusso di lavoro definito in questo esempio mostra un aggiornamento regolare del pubblico dal targeting:

* Viene eseguito automaticamente una volta al mese utilizzando uno **[!UICONTROL Scheduler]**.
* Puoi utilizzare una **[!UICONTROL Query]** per recuperare tutti i profili abbonati ai diversi servizi delle applicazioni disponibili.
* L’attività **[!UICONTROL Save audience]** aggiorna il pubblico eliminando i profili che hanno annullato l’abbonamento al servizio dall’ultima esecuzione del flusso di lavoro e aggiungendo i nuovi profili abbonati.

![](assets/save_audience_example_1.png)

L’attività **[!UICONTROL Save audience]** viene configurata come segue:

![](assets/save_audience_example_2.png)

