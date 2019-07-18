---
title: Utilizzo degli attivatori in Campaign
seo-title: Utilizzo degli attivatori in Campaign
description: Utilizzo degli attivatori in Campaign
seo-description: null
page-status-flag: never-activated
uuid: d 844 d 013-b 38 a -4 e 69-9 df 5-0 edc 01 fa 9 c 6 e
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrazione
content-type: riferimento
topic-tags: working-with-campaign-and-triggers
discoiquuid: a 524 c 700-bad 6-4 fcf -857 a-c 31 bfae 4 d 30 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Using Triggers in Campaign{#using-triggers-in-campaign}

## Creating a mapped trigger in Campaign {#creating-a-mapped-trigger-in-campaign}

You should make sure to define the behaviors that you want to monitor beforehand in Adobe Experience Cloud ( **[!UICONTROL Triggers]** core service). For more on this, refer to the [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html). Tenere presente che quando si definisce il trigger, è necessario abilitare gli alias. Per ogni comportamento (abbandono/abbandono del modulo, aggiunta/eliminazione di prodotti, sessione scaduta ecc.), è necessario aggiungere un nuovo trigger in Adobe Experience Cloud.

Ora è necessario creare un evento trigger in Adobe Campaign in base a un attivatore Adobe Experience Cloud esistente.

You can watch this [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) to help you understand how triggers are set up in Adobe Campaign.

I passaggi per posizionarlo sono:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Click the **[!UICONTROL Create]** button. La procedura guidata di creazione visualizzata mostra l'elenco di tutte le attivazioni definite in Adobe Experience Cloud. The **[!UICONTROL Fired by Analytics]** column displays the number of events sent by the Adobe Experience Cloud trigger to Campaign. Questo è il mapping di trigger creati nell'interfaccia Experience Cloud.

   ![](assets/remarketing_2.png)

1. Select the Adobe Experience Cloud trigger that you want to use and click **[!UICONTROL Next]**.
1. Configurate le proprietà generali del trigger. At this step of the wizard, also specify the channel and the targeting dimension to use for the trigger (see [targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)). Quindi confermate la creazione dell'attivazione.
1. Click the button to the right of the **[!UICONTROL Event content and enrichment]** field to view the content of the payload. Questa schermata consente anche di arricchire i dati evento con i dati di profilo archiviati nel database Adobe Campaign. L'arricchimento viene eseguito allo stesso modo di un messaggio transazionale standard.

   ![](assets/remarketing_3.png)

1. In the **[!UICONTROL Transactional message validity duration]** field, define the duration for which the message will stay valid after the event is sent by Analytics. Se è definita una durata di 2 giorni, il messaggio non verrà più inviato dopo la trasmissione della durata. Se metti in attesa diversi messaggi, assicurati che questi messaggi non vengano inviati se li riprendi dopo un determinato periodo di tempo.

   ![](assets/remarketing_4.png)

1. If a propensity scoring is defined in Analytics (see the [Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/insight/client/c_visitor_propensity.html)), you can choose not to send the message if the customer has a high probability of coming back to the website in the near future. Il contenuto della valutazione e la soglia sono disponibili nel contenuto del payload per poter utilizzare tali valori per personalizzare il messaggio. Per utilizzare questa opzione, controllate la casella nella parte inferiore della schermata. I client con una probabilità elevata di tornare al sito in futuro non riceveranno un messaggio.
1. Click the **[!UICONTROL Publish]** button to start publishing the trigger event.
1. If you need to make a change in your trigger schema even after publishing your trigger event, click the **[!UICONTROL Update schema]** button to retrieve the latest changes.

   Nota: l'azione annullerà la pubblicazione del trigger e del messaggio transazionale, che sarà necessario ripubblicare successivamente.

   ![](assets/remarketing_11.png)

**[!UICONTROL Show Trigger in Experience Cloud]** Il pulsante consente di visualizzare la definizione del trigger in Adobe Experience Cloud.

Una volta pubblicato l'evento, viene creato automaticamente un modello transazionale collegato al nuovo evento. Dovete quindi modificare e pubblicare il modello appena creato. For more on this, refer to the [Editing the template](../../start/using/about-templates.md) section.

## Editing the transactional message template {#editing-the-transactional-message-template}

Dopo aver creato e pubblicato l'evento trigger, il modello transazionali corrispondente viene creato automaticamente. For more on this, refer to the [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) section.

Affinché l'evento attivi l'invio di un messaggio transazionale, dovete personalizzare il modello, quindi testarlo e pubblicarlo. Questi passaggi sono identici a quelli di un messaggio transazionale standard. For more on this, refer to the [Transactional template](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message) section.

>[!NOTE]
>
>Se annullate la pubblicazione del modello, verrà automaticamente annullata la pubblicazione dell'evento di attivazione.

Quando si modificano i contenuti, è possibile aggiungere un campo personalizzato in base alle informazioni inviate dal trigger di Analytics. Se arricchisci i dati dell'evento con i dati del profilo Adobe Campaign, puoi personalizzare il messaggio in base a tali informazioni. To personalize your message, select **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]** and select a field.

![](assets/remarketing_8.png)

## Accessing the reports {#accessing-the-reports}

To view the dedicated trigger report in Adobe Campaign, open the trigger event that you previously created, and click **[!UICONTROL Show trigger report]**.

![](assets/remarketing_9.png)

Il rapporto mostra il numero di eventi elaborati rispetto al numero di eventi inviati da Analytics. Viene inoltre visualizzato un elenco di tutte le attivazioni recenti.

![](assets/trigger_uc_browse_14.png)

