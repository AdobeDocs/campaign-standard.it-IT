---
title: Utilizzo di Triggers in Campaign
description: Crea un evento trigger in Adobe Campaign basato su un trigger Adobe Experience Cloud esistente.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6b8d5118-89ed-49c2-b601-0aff472fcadd
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 74%

---

# Utilizzo di Triggers in Campaign{#using-triggers-in-campaign}

## Creazione di un trigger mappato in Campaign {#creating-a-mapped-trigger-in-campaign}

>[!NOTE]
>
>Per creare Triggers, è necessario il ruolo **[!UICONTROL Administration]** o appartenere al gruppo di sicurezza **[!UICONTROL Administrators]**. Per ulteriori informazioni, consulta questa [pagina](../../administration/using/list-of-roles.md).

È necessario assicurarsi di definire in anticipo i comportamenti che si desidera monitorare in Adobe Experience Cloud (**[!UICONTROL Triggers]** servizio core). Per ulteriori informazioni, consulta la [documentazione di Adobe Experience Cloud](https://experienceleague.adobe.com/docs/experience-cloud/triggers/create.html). Quando definisci il trigger, devi abilitare gli alias. Per ogni comportamento (navigazione/abbandono moduli, aggiunta/eliminazione di prodotti, sessione scaduta e così via), è necessario aggiungere un nuovo trigger all’interno di Adobe Experience Cloud.

Ora devi creare un evento trigger in Adobe Campaign basato su un trigger esistente di Adobe Experience Cloud.

I passaggi per implementare ciò sono i seguenti:

1. Fai clic sul logo **Adobe** nell&#39;angolo in alto a sinistra, quindi seleziona **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Fai clic sul pulsante **[!UICONTROL Create]**. Viene visualizzata la procedura guidata di creazione, che elenca tutti i trigger definiti all’interno di Adobe Experience Cloud. Nella colonna **[!UICONTROL Fired by Analytics]** viene visualizzato il numero di eventi inviati dal trigger di Adobe Experience Cloud a Campaign. Si tratta della mappatura dei trigger creati all’interno dell’interfaccia Experience Cloud.

   ![](assets/remarketing_2.png)

1. Seleziona il trigger di Adobe Experience Cloud che vuoi utilizzare e fai clic su **[!UICONTROL Next]**.
1. Configura le proprietà generali del trigger. In questo passaggio della procedura guidata, specifica anche il canale e la dimensione targeting da utilizzare per il trigger (consulta [dimensioni targeting e risorse](../../automating/using/query.md#targeting-dimensions-and-resources)). Quindi, conferma la creazione del trigger.
1. Per visualizzare il contenuto del payload, fai clic sul pulsante a destra del campo **[!UICONTROL Event content and enrichment]**. Questa schermata ti consente inoltre di arricchire i dati dell’evento con i dati del profilo memorizzati nel database di Adobe Campaign. L’arricchimento viene effettuato con la medesima procedura di un messaggio transazionale standard.

   ![](assets/remarketing_3.png)

1. Nel campo **[!UICONTROL Transactional message validity duration]**, definisci la durata della validità del messaggio dopo l’invio dell’evento da parte di Analytics. Se è stata definita una durata di 2 giorni, il messaggio non verrà più inviato, una volta trascorsa tale durata. Se metti in pausa vari messaggi, questi non verranno inviati se li riprendi dopo un certo periodo di tempo.

   ![](assets/remarketing_4.png)

1. Ora puoi pubblicare i trigger. Per ulteriori informazioni, consulta [Pubblicazione di un trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#publishing-trigger-in-campaign).

## Pubblicazione di un trigger in Campaign {#publishing-trigger-in-campaign}

Dopo aver creato un evento trigger in Adobe Campaign basato su un trigger Adobe Experience Cloud esistente, ora devi pubblicarlo.

1. Dal trigger creato in precedenza, fare clic sul pulsante **[!UICONTROL Publish]** per avviare la pubblicazione dell&#39;evento trigger.

   ![](assets/trigger_publish_1.png)

1. Puoi controllare l&#39;avanzamento della pubblicazione del trigger in **[!UICONTROL Publication]**.

   ![](assets/trigger_publish_2.png)

1. Al termine della pubblicazione, il seguente messaggio verrà visualizzato in **[!UICONTROL Publication]**.

   ![](assets/trigger_publish_3.png)

1. Se è necessario apportare una modifica allo schema del trigger anche dopo la pubblicazione dell’evento trigger, fai clic sul pulsante **[!UICONTROL Update schema]** per recuperare le modifiche più recenti.

   Nota: questa azione annullerà la pubblicazione del trigger e del messaggio transazionale. Successivamente, sarà necessario ripubblicarlo.

   ![](assets/trigger_publish_4.png)

1. Fare clic sul pulsante **[!UICONTROL Show Trigger in Experience Cloud]** per visualizzare la definizione del trigger in Adobe Experience Cloud.

Una volta pubblicato l’evento, viene automaticamente creato un modello transazionale collegato al nuovo evento. Dovrai quindi modificare e pubblicare il modello appena creato. Per ulteriori informazioni, consulta la sezione [Modifica del modello](../../start/using/marketing-activity-templates.md) .

## Modifica del modello di messaggio transazionale {#editing-the-transactional-message-template}

Dopo aver creato e pubblicato l’evento trigger, viene creato il modello transazionale corrispondente. Per ulteriori informazioni, consulta la sezione [Creazione di un trigger mappato in Campaign](#creating-a-mapped-trigger-in-campaign).

Affinché l’evento attivi l’invio di un messaggio transazionale, è necessario personalizzare il modello, testarlo e infine pubblicarlo. Questi passaggi sono i medesimi di un messaggio transazionale standard. Per ulteriori informazioni, consulta la sezione [Modifica di un messaggio sulle transazioni](../../channels/using/editing-transactional-message.md).

>[!NOTE]
>
>Se annulli la pubblicazione del modello, ciò annullerà automaticamente la pubblicazione dell’evento trigger.

Durante la modifica del contenuto, puoi aggiungere un campo di personalizzazione in base alle informazioni inviate dal trigger di Analytics. Se arricchisci i dati dell’evento con i dati del profilo di Adobe Campaign, puoi personalizzare il messaggio in base a tali informazioni. Per personalizzare il messaggio, seleziona **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]** e quindi fai clic su un campo.

![](assets/remarketing_8.png)

## Accesso ai rapporti {#accessing-the-reports}

Per visualizzare il report del trigger dedicato all’interno di Adobe Campaign, apri l’evento trigger creato in precedenza e fai clic su **[!UICONTROL Show trigger report]**.

![](assets/remarketing_9.png)

Il rapporto mostra il numero di eventi elaborati rispetto al numero di eventi inviati da Analytics. Inoltre, visualizza un elenco di tutti i trigger recenti.

![](assets/trigger_uc_browse_14.png)
