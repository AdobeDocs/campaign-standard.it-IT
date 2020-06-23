---
title: Utilizzo di Triggers in Campaign
description: null
page-status-flag: never-activated
uuid: d844d013-b38a-4e69-9df5-0edc01fa9c6e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: a524c700-bad6-4fcf-857a-c31bfae4d30c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 1%

---


# Utilizzo di Triggers in Campaign{#using-triggers-in-campaign}

## Creazione di un trigger mappato in Campaign {#creating-a-mapped-trigger-in-campaign}

Devi accertarti di definire i comportamenti da monitorare in anticipo in Adobe Experience Cloud (servizio **[!UICONTROL Triggers]** di base). Per ulteriori informazioni, consulta la documentazione [di](https://docs.adobe.com/content/help/en/core-services/interface/activation/triggers.html)Adobe Experience Cloud. Quando si definisce il trigger, è necessario abilitare gli alias. Per ogni comportamento (navigazione/abbandono moduli, aggiunta/eliminazione di prodotti, sessione scaduta ecc.), in Adobe Experience Cloud è necessario aggiungere un nuovo attivatore.

È ora necessario creare un evento di attivazione in  Adobe Campaign basato su un trigger Adobe Experience Cloud esistente.

Guardate questo [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) per comprendere in che modo i trigger sono configurati  Adobe Campaign.

I passi per la realizzazione di questo progetto sono:

1. Fate clic sul **[!UICONTROL Adobe Campaign]** logo, nell’angolo in alto a sinistra, quindi selezionate **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Fai clic sul pulsante **[!UICONTROL Create]**. Viene visualizzata la procedura guidata di creazione, che elenca tutti gli attivatori definiti in Adobe Experience Cloud. Nella **[!UICONTROL Fired by Analytics]** colonna viene visualizzato il numero di eventi inviati dall&#39;attivatore Adobe Experience Cloud a Campaign. Si tratta della mappatura dei trigger creati nell&#39;interfaccia Experience Cloud .

   ![](assets/remarketing_2.png)

1. Seleziona l’attivatore Adobe Experience Cloud da usare e fai clic su **[!UICONTROL Next]**.
1. Configurare le proprietà generali del trigger. In questa fase della procedura guidata, specificate anche il canale e la dimensione di targeting da utilizzare per il trigger (consultate Dimensioni e risorse [di](../../automating/using/query.md#targeting-dimensions-and-resources)targeting). Quindi, confermate la creazione dell&#39;attivatore.
1. Fare clic sul pulsante a destra del **[!UICONTROL Event content and enrichment]** campo per visualizzare il contenuto del payload. Questa schermata consente inoltre di arricchire i dati dell&#39;evento con i dati del profilo memorizzati nel database del Adobe Campaign . L&#39;arricchimento viene effettuato come per un messaggio transazionale standard.

   ![](assets/remarketing_3.png)

1. Nel **[!UICONTROL Transactional message validity duration]** campo, definite la durata di validità del messaggio dopo l&#39;invio dell&#39;evento da parte di  Analytics. Se viene definita una durata di 2 giorni, il messaggio non verrà più inviato dopo che tale durata è passata. Se si mettono in pausa diversi messaggi, questi non verranno inviati se vengono ripresi dopo un certo periodo di tempo.

   ![](assets/remarketing_4.png)

1. Fate clic sul **[!UICONTROL Publish]** pulsante per avviare la pubblicazione dell&#39;evento di attivazione.
1. Se è necessario apportare una modifica allo schema di attivazione anche dopo la pubblicazione dell&#39;evento di attivazione, fare clic sul **[!UICONTROL Update schema]** pulsante per recuperare le modifiche più recenti.

   Nota: questa azione consente di annullare la pubblicazione dell&#39;attivatore e del messaggio di transazione. Successivamente, sarà necessario ripubblicarlo.

   ![](assets/remarketing_11.png)

Il **[!UICONTROL Show Trigger in Experience Cloud]** pulsante consente di visualizzare la definizione dell&#39;attivatore in Adobe Experience Cloud.

Una volta pubblicato l’evento, viene automaticamente creato un modello transazionale collegato al nuovo evento. È quindi necessario modificare e pubblicare il modello appena creato. Per ulteriori informazioni, consultare la sezione [Modifica del modello](../../start/using/marketing-activity-templates.md) .

## Modifica del modello di messaggio transazionale {#editing-the-transactional-message-template}

Dopo aver creato e pubblicato l&#39;evento di attivazione, il modello transazionale corrispondente viene creato automaticamente. Per ulteriori informazioni, consulta la sezione [Creazione di un trigger mappato nella sezione Campagna](#creating-a-mapped-trigger-in-campaign) .

Affinché l’evento attivi l’invio di un messaggio transazionale, è necessario personalizzare il modello, testarlo e pubblicarlo. Questi passaggi sono gli stessi di un messaggio transazionale standard. Per ulteriori informazioni, consulta la sezione Modello [](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message) transazionale.

>[!NOTE]
>
>Se annullate la pubblicazione del modello, l&#39;evento di attivazione verrà automaticamente annullato.

Durante la modifica dei contenuti, puoi aggiungere un campo di personalizzazione in base alle informazioni inviate dal trigger Analytics . Se arricchite i dati dell&#39;evento con  dati del profilo di Adobe Campaign, potete personalizzare il messaggio in base a tali informazioni. Per personalizzare il messaggio, seleziona **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]** e seleziona un campo.

![](assets/remarketing_8.png)

## Accesso ai rapporti {#accessing-the-reports}

Per visualizzare il rapporto di attivazione dedicato in  Adobe Campaign, aprire l&#39;evento di attivazione creato in precedenza e fare clic **[!UICONTROL Show trigger report]**.

![](assets/remarketing_9.png)

Il rapporto mostra il numero di eventi elaborati rispetto al numero di eventi inviati da  Analytics. Inoltre, viene visualizzato un elenco di tutte le attivazioni recenti.

![](assets/trigger_uc_browse_14.png)

