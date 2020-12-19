---
solution: Campaign Standard
product: campaign
title: In-App delivery
description: L'attività di distribuzione in-app consente di configurare l'invio di un messaggio in-app all'interno di un flusso di lavoro.
audience: automating
content-type: reference
topic-tags: channel-activities
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '692'
ht-degree: 43%

---


# In-App delivery{#in-app-delivery}

## Descrizione {#description}

![](assets/wkf_in_app_1.png)

L&#39;attività **Distribuzione in-app** consente di configurare l&#39;invio di un messaggio in-app all&#39;interno di un flusso di lavoro. La messaggistica in-app consente di visualizzare un messaggio quando l&#39;utente è attivo all&#39;interno dell&#39;applicazione. Per ulteriori informazioni sulla distribuzione in-app, consultate questa sezione [](../../channels/using/about-in-app-messaging.md).

## Contesto di utilizzo {#context-of-use}

L&#39;attività **[!UICONTROL In-App delivery]** viene generalmente utilizzata per automatizzare l&#39;invio di un messaggio in-app a un&#39;audience di destinazione calcolata nello stesso flusso di lavoro.

I destinatari vengono definiti a monte dell&#39;attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni ecc.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard messaggi, puoi scegliere se richiedere o meno una conferma manuale per inviare il messaggio (richiesta per impostazione predefinita). Puoi avviare il flusso di lavoro manualmente o inserire un’attività di pianificazione nel flusso di lavoro per automatizzare l’esecuzione.

## Configurazione {#configuration}

1. Trascinate e rilasciate un&#39;attività **[!UICONTROL Query]** nel flusso di lavoro. Tenere presente che la dimensione di targeting delle attività **[!UICONTROL Query]** nella scheda **[!UICONTROL Properties]** deve essere aggiornata in base al modello scelto al punto 4:

   * La dimensione di targeting deve essere impostata su **[!UICONTROL mobileApp (mobileAppV5)]** per il modello **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**.
   * La dimensione di targeting deve essere impostata su **[!UICONTROL profile (profile)]** per il modello **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**.
   * La dimensione di targeting deve essere impostata su **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** per il modello **[!UICONTROL Target users based on their Mobile profile (inApp)]**.

1. Trascina e rilascia un’attività **[!UICONTROL In-App delivery]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Puoi accedere alle proprietà generali e alle opzioni avanzate dell’attività (e non della consegna stessa) tramite il pulsante ![](assets/dlv_activity_params-24px.png) dalle azioni rapide dell’attività.

   ![](assets/wkf_in_app_3.png)

1. Selezionate il tipo di messaggio in-app. Ciò dipenderà dai dati di destinazione nell&#39;attività **[!UICONTROL Query]**.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Questo tipo di messaggio consente di eseguire il targeting  profili Adobe Campaign che hanno effettuato l&#39;iscrizione all&#39;applicazione mobile e di personalizzare i messaggi in-app con gli attributi di profilo disponibili in Campaign.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Questo tipo di messaggio consente di inviare un messaggio a tutti gli utenti dell&#39;applicazione mobile anche se non dispongono di un profilo esistente in Campaign.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Questo tipo di messaggio consente di eseguire il targeting di tutti gli utenti di un&#39;app mobile con un profilo mobile in Campaign, noto o sconosciuto, e di personalizzare i messaggi in-app con eventuali attributi di profilo ottenuti da un dispositivo mobile.

   ![](assets/wkf_in_app_4.png)

1. Immetti le proprietà del messaggio in-app e seleziona l&#39;app mobile nel campo **[!UICONTROL Associate a Mobile App to a delivery]**.
1. Nella scheda **[!UICONTROL Triggers]**, trascina e rilascia l’evento che attiverà il messaggio. Sono disponibili tre categorie di eventi:
1. Definite il contenuto in-app. Fare riferimento alla sezione relativa alla [Personalizzazione in-app](../../channels/using/customizing-an-in-app-message.md).
1. Per impostazione predefinita, l’attività **[!UICONTROL In-App delivery]** non include transizioni in uscita. Se desideri aggiungere una transizione in uscita all’attività **[!UICONTROL In-App delivery]**, passa alla scheda **[!UICONTROL General]** delle opzioni di attività avanzate (pulsante ![](assets/dlv_activity_params-24px.png) nelle azioni rapide dell’attività), quindi seleziona una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: ti consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata.
   * **[!UICONTROL Add outbound transition with the population]**: questo consente di generare una transizione in uscita contenente la popolazione a cui è stato inviato il messaggio. I membri del target esclusi durante la preparazione della consegna sono esclusi da questa transizione.

   ![](assets/wkf_in_app_5.png)

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

Quando riaprite l&#39;attività, venite portati direttamente al dashboard in-app. È possibile modificarne solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L’invio di messaggi creati da un flusso di lavoro deve comunque essere confermato dopo l’avvio del flusso di lavoro. Tuttavia, puoi disattivare l’opzione **[!UICONTROL Request confirmation before sending messages]** dal dashboard messaggi e solo se il messaggio è stato creato da un flusso di lavoro. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all’interno di un flusso di lavoro sono accessibili nell’elenco delle attività di marketing dell’applicazione. Puoi visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo delle notifiche push consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna ecc.).

Nelle consegne principali, a cui è possibile accedere dall&#39;elenco delle attività di marketing, è possibile visualizzare il numero totale di invii che sono stati elaborati (in base al periodo di aggregazione specificato al momento della configurazione dell&#39;attività **[!UICONTROL In-App delivery]**). A tal fine, apri la visualizzazione dei dettagli del blocco **[!UICONTROL Deployment]** della consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).
