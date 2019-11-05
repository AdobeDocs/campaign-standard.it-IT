---
title: Utilizzo di Triggers in Campaign
description: null
page-status-flag: mai attivato
uuid: d844d013-b38a-4e69-9df5-0edc01fa9c6e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integration
content-type: reference
topic-tags: utilizzo di attivatori per campagne
discoiquuid: a524c700-bad6-4fcf-857a-c31bfae4d30c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Utilizzo di Triggers in Campaign{#using-triggers-in-campaign}

## Creazione di un trigger mappato in Campaign {#creating-a-mapped-trigger-in-campaign}

Devi accertarti di definire i comportamenti da monitorare in anticipo in Adobe Experience Cloud (servizio **[!UICONTROL Triggers]** di base). Per ulteriori informazioni, consulta la documentazione [di](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html)Adobe Experience Cloud. Quando si definisce il trigger, è necessario abilitare gli alias. Per ogni comportamento (navigazione/abbandono moduli, aggiunta/eliminazione di prodotti, sessione scaduta ecc.), in Adobe Experience Cloud è necessario aggiungere un nuovo attivatore.

Ora devi creare un evento di attivazione in Adobe Campaign basato su un attivatore Adobe Experience Cloud esistente.

Guardate questo [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) per comprendere meglio in che modo i trigger sono configurati in Adobe Campaign.

I passi per la realizzazione di questo progetto sono:

1. Fate clic sul **[!UICONTROL Adobe Campaign]** logo, nell’angolo in alto a sinistra, quindi selezionate **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Fate clic sul **[!UICONTROL Create]** pulsante. Viene visualizzata la procedura guidata di creazione, che elenca tutti gli attivatori definiti in Adobe Experience Cloud. Nella **[!UICONTROL Fired by Analytics]** colonna viene visualizzato il numero di eventi inviati dall'attivatore Adobe Experience Cloud a Campaign. Si tratta della mappatura dei trigger creati nell'interfaccia Experience Cloud.

   ![](assets/remarketing_2.png)

1. Seleziona l’attivatore Adobe Experience Cloud da usare e fai clic su **[!UICONTROL Next]**.
1. Configurare le proprietà generali del trigger. In questa fase della procedura guidata, specificate anche il canale e la dimensione di targeting da utilizzare per il trigger (consultate Dimensioni e risorse [di](../../automating/using/query.md#targeting-dimensions-and-resources)targeting). Quindi, confermate la creazione dell'attivatore.
1. Fare clic sul pulsante a destra del **[!UICONTROL Event content and enrichment]** campo per visualizzare il contenuto del payload. Questa schermata consente inoltre di arricchire i dati dell'evento con i dati del profilo memorizzati nel database Adobe Campaign. L'arricchimento viene effettuato come per un messaggio transazionale standard.

   ![](assets/remarketing_3.png)

1. Nel **[!UICONTROL Transactional message validity duration]** campo, definite la durata di validità del messaggio dopo l'invio dell'evento da parte di Analytics. Se viene definita una durata di 2 giorni, il messaggio non verrà più inviato dopo che tale durata è passata. Se si mettono in pausa diversi messaggi, questi non verranno inviati se vengono ripresi dopo un certo periodo di tempo.

   ![](assets/remarketing_4.png)

1. Se in Analytics è definito un punteggio di propensione (consultate la documentazione [di](https://marketing.adobe.com/resources/help/en_US/insight/client/c_visitor_propensity.html)Experience Cloud), puoi scegliere di non inviare il messaggio se il cliente ha un'alta probabilità di tornare sul sito Web nel prossimo futuro. Il contenuto della valutazione e della soglia è disponibile nel contenuto del payload in modo da poter utilizzare tali valori per personalizzare il messaggio. Per utilizzare questa opzione, selezionate la casella in fondo allo schermo. I clienti con una forte probabilità di tornare sul sito nel prossimo futuro non riceveranno alcun messaggio.
1. Fate clic sul **[!UICONTROL Publish]** pulsante per avviare la pubblicazione dell'evento di attivazione.
1. Se è necessario apportare una modifica allo schema di attivazione anche dopo la pubblicazione dell'evento di attivazione, fare clic sul **[!UICONTROL Update schema]** pulsante per recuperare le modifiche più recenti.

   Nota: questa azione consente di annullare la pubblicazione dell'attivatore e del messaggio di transazione. Successivamente, sarà necessario ripubblicarlo.

   ![](assets/remarketing_11.png)

Il **[!UICONTROL Show Trigger in Experience Cloud]** pulsante consente di visualizzare la definizione dell'attivatore in Adobe Experience Cloud.

Una volta pubblicato l’evento, viene automaticamente creato un modello transazionale collegato al nuovo evento. È quindi necessario modificare e pubblicare il modello appena creato. Per ulteriori informazioni, consultare la sezione [Modifica del modello](../../start/using/about-templates.md) .

## Modifica del modello di messaggio transazionale {#editing-the-transactional-message-template}

Dopo aver creato e pubblicato l'evento di attivazione, il modello transazionale corrispondente viene creato automaticamente. Per ulteriori informazioni, consulta la sezione [Creazione di un trigger mappato nella sezione Campagna](#creating-a-mapped-trigger-in-campaign) .

Affinché l’evento attivi l’invio di un messaggio transazionale, è necessario personalizzare il modello, testarlo e pubblicarlo. Questi passaggi sono gli stessi di un messaggio transazionale standard. Per ulteriori informazioni, consulta la sezione Modello [](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message) transazionale.

>[!NOTE]
>
>Se annullate la pubblicazione del modello, l'evento di attivazione verrà automaticamente annullato.

Durante la modifica del contenuto, puoi aggiungere un campo di personalizzazione in base alle informazioni inviate dall'attivatore di Analytics. Se arricchisci i dati dell'evento con i dati del profilo di Adobe Campaign, puoi personalizzare il messaggio in base a tali informazioni. Per personalizzare il messaggio, seleziona **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]** e seleziona un campo.

![](assets/remarketing_8.png)

## Accesso ai rapporti {#accessing-the-reports}

Per visualizzare il rapporto di attivazione dedicato in Adobe Campaign, apri l'evento di attivazione creato in precedenza e fai clic su **[!UICONTROL Show trigger report]**.

![](assets/remarketing_9.png)

Il rapporto mostra il numero di eventi elaborati rispetto al numero di eventi inviati da Analytics. Inoltre, viene visualizzato un elenco di tutte le attivazioni recenti.

![](assets/trigger_uc_browse_14.png)

