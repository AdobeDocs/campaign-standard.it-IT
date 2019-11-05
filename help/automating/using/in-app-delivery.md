---
title: Distribuzione in-app
description: L'attività di distribuzione in-app consente di configurare l'invio di un messaggio in-app all'interno di un flusso di lavoro.
page-status-flag: mai attivato
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: attività di canale
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Distribuzione in-app{#in-app-delivery}

## Descrizione {#description}

![](assets/wkf_in_app_1.png)

L'attività di consegna **** in-app consente di configurare l'invio di un messaggio in-app all'interno di un flusso di lavoro. La messaggistica in-app consente di visualizzare un messaggio quando l'utente è attivo all'interno dell'applicazione. Per ulteriori informazioni sulla consegna in-app, consultate questa [sezione](../../channels/using/about-in-app-messaging.md).

## Contesto di utilizzo {#context-of-use}

L' **[!UICONTROL In-App delivery]** attività viene generalmente utilizzata per automatizzare l'invio di un messaggio in-app a un'audience di destinazione calcolata nello stesso flusso di lavoro.

I destinatari vengono definiti a monte dell'attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni ecc.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard dei messaggi, puoi scegliere se richiedere o meno una conferma manuale per l'invio del messaggio (richiesta per impostazione predefinita). È possibile avviare il flusso di lavoro manualmente o inserire un'attività pianificatore nel flusso di lavoro per automatizzare l'esecuzione.

## Configurazione {#configuration}

1. Trascinate e rilasciate un' **[!UICONTROL Query]** attività nel flusso di lavoro. Nota che la dimensione di targeting dell' **[!UICONTROL Query]** attività nella **[!UICONTROL Properties]** scheda deve essere aggiornata in base al modello scelto nel passaggio 4:

   * La dimensione di targeting deve essere impostata su **[!UICONTROL mobileApp (mobileAppV5)]** per il **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** modello.
   * La dimensione di targeting deve essere impostata su **[!UICONTROL profile (profile)]** per il **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** modello.
   * La dimensione di targeting deve essere impostata su **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** per il **[!UICONTROL Target users based on their Mobile profile (inApp)]** modello.

1. Trascinate e rilasciate un' **[!UICONTROL In-App delivery]** attività nel flusso di lavoro.
1. Selezionate l'attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Potete accedere alle proprietà generali e alle opzioni avanzate dell'attività (e non della distribuzione stessa) tramite il ![](assets/dlv_activity_params-24px.png) pulsante dalle azioni rapide dell'attività.

   ![](assets/wkf_in_app_3.png)

1. Selezionate il tipo di messaggio in-app. Ciò dipenderà dai dati di destinazione nell' **[!UICONTROL Query]** attività.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Questo tipo di messaggio consente di eseguire il targeting dei profili di Adobe Campaign che si sono iscritti all'applicazione mobile e di personalizzare i messaggi in-app con gli attributi di profilo disponibili in Campaign.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Questo tipo di messaggio consente di inviare un messaggio a tutti gli utenti dell'applicazione mobile anche se non dispongono di un profilo esistente in Campaign.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Questo tipo di messaggio consente di eseguire il targeting di tutti gli utenti di un'app mobile con un profilo mobile in Campaign, noto o sconosciuto, e di personalizzare i messaggi in-app con eventuali attributi di profilo ottenuti da un dispositivo mobile.
   ![](assets/wkf_in_app_4.png)

1. Immetti le proprietà del messaggio in-app e seleziona l'app mobile nel **[!UICONTROL Associate a Mobile App to a delivery]** campo.
1. Nella **[!UICONTROL Triggers]** scheda, trascina e rilascia l’evento che attiverà il messaggio. Sono disponibili tre categorie di eventi:
1. Definite il contenuto in-app. Fate riferimento alla sezione sulla personalizzazione [](../../channels/using/customizing-an-in-app-message.md)in-app.
1. Per impostazione predefinita, l' **[!UICONTROL In-App delivery]** attività non include transizioni in uscita. Se desiderate aggiungere una transizione in uscita all' **[!UICONTROL In-App delivery]** attività, andate alla **[!UICONTROL General]** scheda delle opzioni di attività avanzate ( ![](assets/dlv_activity_params-24px.png) pulsante nelle azioni rapide dell'attività), quindi selezionate una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: questo consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata.
   * **[!UICONTROL Add outbound transition with the population]**: questo consente di generare una transizione in uscita contenente la popolazione a cui è stato inviato il messaggio. I membri del target esclusi durante la preparazione della consegna sono esclusi da questa transizione.
   ![](assets/wkf_in_app_5.png)

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

Quando riaprite l'attività, venite portati direttamente al dashboard in-app. È possibile modificare solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L'invio di messaggi creati da un flusso di lavoro deve ancora essere confermato dopo l'avvio del flusso di lavoro. Tuttavia, dal dashboard dei messaggi e solo se il messaggio è stato creato da un flusso di lavoro, potete disattivare l' **[!UICONTROL Request confirmation before sending messages]** opzione. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all'interno di un flusso di lavoro sono accessibili nell'elenco delle attività di marketing dell'applicazione. Potete visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo delle notifiche push consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna ecc.).

Nelle consegne principali, a cui è possibile accedere dall'elenco delle attività di marketing, è possibile visualizzare il numero totale di invii che sono stati elaborati (in base al periodo di aggregazione specificato al momento della configurazione dell' **[!UICONTROL In-App delivery]** attività). A tal fine, aprire la visualizzazione dettagli del **[!UICONTROL Deployment]** blocco di consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).
