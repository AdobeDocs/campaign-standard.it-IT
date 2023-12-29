---
title: Consegna in-app
description: L’attività di consegna in-app ti consente di configurare l’invio di un messaggio in-app all’interno di un flusso di lavoro.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d5a35c4-e22b-498e-b71c-c5922cf8c2fd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 39%

---

# Consegna in-app{#in-app-delivery}

## Descrizione {#description}

![](assets/wkf_in_app_1.png)

Il **Consegna in-app** attività ti consente di configurare l’invio di un messaggio in-app all’interno di un flusso di lavoro. La messaggistica in-app consente di visualizzare un messaggio quando l’utente è attivo all’interno dell’applicazione. Per ulteriori informazioni sulla consegna in-app, consulta questa [sezione](../../channels/using/about-in-app-messaging.md).

## Contesto di utilizzo {#context-of-use}

Il **[!UICONTROL In-App delivery]** L’attività viene generalmente utilizzata per automatizzare l’invio di un messaggio in-app a un pubblico target calcolato nello stesso flusso di lavoro.

I destinatari sono definiti a monte dell’attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni, ecc.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard messaggi, puoi scegliere se richiedere o meno una conferma manuale per inviare il messaggio (richiesta per impostazione predefinita). Puoi avviare il flusso di lavoro manualmente o inserire un’attività di pianificazione nel flusso di lavoro per automatizzare l’esecuzione.

## Configurazione {#configuration}

1. Trascina una **[!UICONTROL Query]** al flusso di lavoro. Tieni presente che **[!UICONTROL Query]** dimensione targeting di attività in **[!UICONTROL Properties]** La scheda deve essere aggiornata in base al modello scelto nel passaggio 4:

   * La dimensione di targeting deve essere impostata su **[!UICONTROL mobileApp (mobileAppV5)]** per **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** modello.
   * La dimensione di targeting deve essere impostata su **[!UICONTROL profile (profile)]** per **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** modello.
   * La dimensione di targeting deve essere impostata su **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** per **[!UICONTROL Target users based on their Mobile profile (inApp)]** modello.

1. Trascina e rilascia un’attività **[!UICONTROL In-App delivery]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Puoi accedere alle proprietà generali e alle opzioni avanzate dell’attività (e non della consegna stessa) tramite ![](assets/dlv_activity_params-24px.png) dalle azioni rapide dell’attività.

   ![](assets/wkf_in_app_3.png)

1. Seleziona il tipo di messaggio in-app. Questo dipenderà dai dati target nei **[!UICONTROL Query]** attività.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: questo tipo di messaggio ti consente di eseguire il targeting dei profili Adobe Campaign che si sono abbonati alla tua app mobile e di personalizzare i messaggi in-app con gli attributi di profilo disponibili in Campaign.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: questo tipo di messaggio ti consente di inviare un messaggio a tutti gli utenti della tua app mobile anche se non dispongono di un profilo esistente in Campaign.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: questo tipo di messaggio ti consente di eseguire il targeting per tutti gli utenti di un’app mobile con un profilo mobile in Campaign noto o sconosciuto e di personalizzare i messaggi in-app con tutti gli attributi di profilo ottenuti da dispositivi mobili.

   ![](assets/wkf_in_app_4.png)

1. Immetti le proprietà del messaggio in-app e seleziona la tua app mobile in **[!UICONTROL Associate a Mobile App to a delivery]** campo.
1. Nella scheda **[!UICONTROL Triggers]**, trascina e rilascia l’evento che attiverà il messaggio. Sono disponibili tre categorie di eventi:
1. Definisci il contenuto in-app. Consulta la sezione relativa a [Personalizzazione in-app](../../channels/using/customizing-an-in-app-message.md).
1. Per impostazione predefinita, l’attività **[!UICONTROL In-App delivery]** non include transizioni in uscita. Se desideri aggiungere una transizione in uscita all’attività **[!UICONTROL In-App delivery]**, passa alla scheda **[!UICONTROL General]** delle opzioni di attività avanzate (pulsante ![](assets/dlv_activity_params-24px.png) nelle azioni rapide dell’attività), quindi seleziona una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: ti consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata.
   * **[!UICONTROL Add outbound transition with the population]**: ti consente di generare una transizione in uscita contenente la popolazione a cui è stato inviato il messaggio. I membri del target esclusi durante la preparazione della consegna sono esclusi da questa transizione.

   ![](assets/wkf_in_app_5.png)

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

Quando riapri l’attività, accedi direttamente al dashboard in-app. È possibile modificarne solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L’invio di messaggi creati da un flusso di lavoro deve comunque essere confermato dopo l’avvio del flusso di lavoro. Tuttavia, puoi disattivare l’opzione **[!UICONTROL Request confirmation before sending messages]** dal dashboard messaggi e solo se il messaggio è stato creato da un flusso di lavoro. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all’interno di un flusso di lavoro sono accessibili nell’elenco delle attività di marketing dell’applicazione. Puoi visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo delle notifiche push ti consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, ecc.).

Nelle consegne principali, accessibili dall’elenco delle attività di marketing, puoi visualizzare il numero totale di invii che sono stati elaborati (in base al periodo di aggregazione specificato quando il **[!UICONTROL In-App delivery]** attività configurata). A tal fine, apri la visualizzazione dei dettagli del blocco **[!UICONTROL Deployment]** della consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).
