---
title: Salva pubblico
seo-title: Salva pubblico
description: Salva pubblico
seo-description: L'attività Salva audience consente di aggiornare un'audience esistente o di creare un nuovo pubblico dalla popolazione calcolata a monte in un flusso di lavoro.
page-status-flag: never-activated
uuid: 8 babb 173-fa 59-44 a 7-a 2 a 5-49 f 45 ba 6 bf 99
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: targeting-activity
discoiquuid: 1 f 6 bb 048-7 abd -499 b-a 4 b 0-187 f 9492 dc 47
context-tags: Saveaudience, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Save audience{#save-audience}

## Description {#description}

![](assets/save_audience.png)

The **[!UICONTROL Save audience]** activity allows you to update an existing audience or create a new audience from the population computed upstream in a workflow. The audiences created or updated from this activity are **List** or **File** audiences. They are added to the list of application audiences, and are made available via the **[!UICONTROL Audiences]** menu.

>[!NOTE]
>
>If the audience created through the **[!UICONTROL Save audience]** activity has been enriched with additional data, you will not be able to use these data to personalize a standalone delivery. Possono essere utilizzati solo da una distribuzione eseguita in un flusso di lavoro.

Questa attività consente anche di esportare profili come pubblico/segmenti di Adobe Experience Cloud. Questo consente di sfruttare queste audience in altre soluzioni Adobe Experience Cloud. For more information about shared audiences, refer to [Working with Campaign and People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

## Context of use {#context-of-use}

The **[!UICONTROL Save audience]** activity is essentially used to keep population groups computed in the same workflow, by converting them into reusable audiences.

## Configuration {#configuration}

1. Drop a **[!UICONTROL Save audience]** activity into your workflow.
1. Connettetela dopo le altre attività di targeting, ad esempio una query, un'intersezione, un'unione o un'esclusione.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Selezionate l'azione da eseguire:

   * **[!UICONTROL Update an existing audience]**: Selezionate un'audience esistente e scegliete il tipo di aggiornamento:

      * **[!UICONTROL Replace audience content with new data]**: Viene sostituito tutto il contenuto del pubblico. I vecchi dati vanno persi. Vengono mantenuti solo i dati provenienti dalla transizione in ingresso dell'attività del pubblico.
      * **[!UICONTROL Complete audience with new data]**: I vecchi dati del pubblico vengono mantenuti e vengono aggiunti i dati della transizione in entrata dell'attività del pubblico.
   * **[!UICONTROL Create then update an audience]**: Immettete il nome dell'audience e selezionate il tipo di aggiornamento. Se l'audience non esiste già, viene creata. Se esiste già, viene aggiornato in base alla modalità selezionata:

      * **[!UICONTROL Replace audience content with new data]**: Viene sostituito tutto il contenuto del pubblico. I vecchi dati vanno persi. Vengono mantenuti solo i dati provenienti dalla transizione in ingresso dell'attività del pubblico.

         Attenzione, questa opzione elimina il tipo di pubblico e la dimensione di targeting del pubblico aggiornato.

      * **[!UICONTROL Complete audience with new data]**: I vecchi dati del pubblico vengono mantenuti e vengono aggiunti i dati della transizione in entrata dell'attività del pubblico.

         Attenzione, questa opzione causa un errore se il tipo di pubblico o la dimensione di targeting dell'audience aggiornata non sono compatibili con la configurazione corrente del flusso di lavoro. Ad esempio, non potete completare un tipo di pubblico con profili provenienti da una query.
   * **[!UICONTROL Create a new audience]**: Inserite il nome dell'audience da creare. L'ora e la data in cui l'audience viene creata verranno automaticamente aggiunte al nome del pubblico. Questo rende il pubblico univoco ogni volta che il flusso di lavoro viene eseguito.
   * **[!UICONTROL Share in Adobe Experience Cloud]**: Se hai dei profili mirati e desideri esportare il pubblico in Adobe Experience Cloud, seleziona questa opzione, quindi seleziona un pubblico condiviso esistente o crea un nuovo pubblico.

      Also select a **[!UICONTROL Shared Data source]** that corresponds to the resource of the data contained in the audience so that the data is correctly reconciled in Adobe Experience Cloud.

      Using this option, the shared audience is not added to the list of Adobe Campaign audiences available via the **[!UICONTROL Audiences]** menu.

      >[!NOTE]
      >
      >Questa opzione è disponibile solo se la funzionalità di audience condivisa con Adobe Experience Cloud è stata configurata dall'amministratore. For more information, refer to [Working with Campaign and People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).
   Il tipo di audience salvato o disponibile durante un aggiornamento dipende dalle attività collocate a monte nel flusso di lavoro.

   If the targeting dimension of the audience is unknown when it is saved (for example if it is from an imported file), the audience is created or updated as a **[!UICONTROL File]** type audience.

   If the targeting dimension of the saved audience is already defined when it is saved (for example, if it comes from a targeting, after a query, etc.), then the audience is saved or updated as a **[!UICONTROL List]** type audience.

   The content of the saved audience is then available in the detail view of the audience, which can be accessed from the **[!UICONTROL Audiences]** menu. Le colonne disponibili da questa vista corrispondono alle colonne della transizione in ingresso dell'attività del tipo di pubblico del flusso di lavoro. Ad esempio: le colonne del file importato, i dati aggiuntivi aggiunti da una query.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

## Example {#example}

Il flusso di lavoro definito in questo esempio mostra un aggiornamento regolare dell'audience dal targeting:

* It is automatically executed once a month using a **[!UICONTROL Scheduler]**.
* You can use a **[!UICONTROL Query]** to recover all the profiles subscribed to the different application services available.
* The **[!UICONTROL Save audience]** activity updates the audience by deleting profiles that have unsubscribed from the service since the last workflow execution and by adding the newly subscribed profiles.

![](assets/save_audience_example_1.png)

The **[!UICONTROL Save audience]** activity is configured as follows:

![](assets/save_audience_example_2.png)

