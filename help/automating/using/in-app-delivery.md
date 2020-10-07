---
title: In-App delivery
description: L'attività di distribuzione in-app consente di configurare l'invio di un messaggio in-app all'interno di un flusso di lavoro.
page-status-flag: never-activated
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 43%

---


# In-App delivery{#in-app-delivery}

## Descrizione {#description}

![](assets/wkf_in_app_1.png)

L&#39;attività di consegna **** in-app consente di configurare l&#39;invio di un messaggio in-app all&#39;interno di un flusso di lavoro. La messaggistica in-app consente di visualizzare un messaggio quando l&#39;utente è attivo all&#39;interno dell&#39;applicazione. Per ulteriori informazioni sulla consegna in-app, consulta questa [sezione](../../channels/using/about-in-app-messaging.md).

## Contesto di utilizzo {#context-of-use}

The **[!UICONTROL In-App delivery]** activity is generally used to automate sending an In-App message to a target audience calculated in the same workflow.

I destinatari vengono definiti a monte dell&#39;attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni ecc.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard messaggi, puoi scegliere se richiedere o meno una conferma manuale per inviare il messaggio (richiesta per impostazione predefinita). Puoi avviare il flusso di lavoro manualmente o inserire un’attività di pianificazione nel flusso di lavoro per automatizzare l’esecuzione.

## Configurazione {#configuration}

1. Drag and drop a **[!UICONTROL Query]** activity to your workflow. Nota che la dimensione di targeting dell&#39; **[!UICONTROL Query]** attività nella **[!UICONTROL Properties]** scheda deve essere aggiornata in base al modello scelto nel passaggio 4:

   * La dimensione di targeting deve essere impostata su **[!UICONTROL mobileApp (mobileAppV5)]** per il **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** modello.
   * La dimensione di targeting deve essere impostata su **[!UICONTROL profile (profile)]** per il **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** modello.
   * La dimensione di targeting deve essere impostata su **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** per il **[!UICONTROL Target users based on their Mobile profile (inApp)]** modello.

1. Trascina e rilascia un’attività **[!UICONTROL In-App delivery]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Puoi accedere alle proprietà generali e alle opzioni avanzate dell’attività (e non della consegna stessa) tramite il pulsante ![](assets/dlv_activity_params-24px.png) dalle azioni rapide dell’attività.

   ![](assets/wkf_in_app_3.png)

1. Selezionate il tipo di messaggio in-app. Ciò dipenderà dai dati di destinazione nell&#39; **[!UICONTROL Query]** attività.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Questo tipo di messaggio consente di eseguire il targeting  profili Adobe Campaign che hanno effettuato l&#39;iscrizione all&#39;applicazione mobile e di personalizzare i messaggi in-app con gli attributi di profilo disponibili in Campaign.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Questo tipo di messaggio consente di inviare un messaggio a tutti gli utenti dell&#39;applicazione mobile anche se non dispongono di un profilo esistente in Campaign.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Questo tipo di messaggio consente di eseguire il targeting di tutti gli utenti di un&#39;app mobile con un profilo mobile in Campaign, noto o sconosciuto, e di personalizzare i messaggi in-app con eventuali attributi di profilo ottenuti da un dispositivo mobile.

   ![](assets/wkf_in_app_4.png)

1. Enter your In-App message properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.
1. Nella scheda **[!UICONTROL Triggers]**, trascina e rilascia l’evento che attiverà il messaggio. Sono disponibili tre categorie di eventi:
1. Definite il contenuto in-app. Fate riferimento alla sezione sulla personalizzazione [](../../channels/using/customizing-an-in-app-message.md)in-app.
1. Per impostazione predefinita, l’attività **[!UICONTROL In-App delivery]** non include transizioni in uscita. Se desideri aggiungere una transizione in uscita all’attività **[!UICONTROL In-App delivery]**, passa alla scheda **[!UICONTROL General]** delle opzioni di attività avanzate (pulsante ![](assets/dlv_activity_params-24px.png) nelle azioni rapide dell’attività), quindi seleziona una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: ti consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata.
   * **[!UICONTROL Add outbound transition with the population]**: questo consente di generare una transizione in uscita contenente la popolazione a cui è stato inviato il messaggio. I membri del target esclusi durante la preparazione della consegna sono esclusi da questa transizione.

   ![](assets/wkf_in_app_5.png)

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

Quando riaprite l&#39;attività, venite portati direttamente al dashboard in-app. È possibile modificarne solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L’invio di messaggi creati da un flusso di lavoro deve comunque essere confermato dopo l’avvio del flusso di lavoro. Tuttavia, puoi disattivare l’opzione **[!UICONTROL Request confirmation before sending messages]** dal dashboard messaggi e solo se il messaggio è stato creato da un flusso di lavoro. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all’interno di un flusso di lavoro sono accessibili nell’elenco delle attività di marketing dell’applicazione. Puoi visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo delle notifiche push consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna ecc.).

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL In-App delivery]** activity was configured). A tal fine, apri la visualizzazione dei dettagli del blocco **[!UICONTROL Deployment]** della consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).
