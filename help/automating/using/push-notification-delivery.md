---
title: Consegna notifiche push
description: L'attività di consegna delle notifiche push consente di configurare l'invio di una singola notifica push o di una notifica push ricorrente in un flusso di lavoro.
page-status-flag: never-activated
uuid: 994d8fe3-29f0-4b5c-89ee-c6be7c60a31b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: channel-activities
discoiquuid: e61bdaee-4b48-4845-a2a5-574b577ea796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eac45f6e5491703a39c19a4787be6f285e841e14
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 47%

---


# Consegna notifiche push{#push-notification-delivery}

## Descrizione {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

The **[!UICONTROL Push notification]** activity allows you to configure sending a push notification in a workflow. Può trattarsi di una singola notifica di invio e inviata una sola volta, oppure può trattarsi di una notifica ricorrente.

* **Le notifiche singole** sono notifiche push standard delle app mobili inviate una volta.
* **Le notifiche ricorrenti** consentono di inviare la stessa notifica push dell&#39;app mobile più volte a destinazioni diverse in un periodo definito. Puoi aggregare le consegne per periodo in modo da ottenere report che corrispondano alle tue esigenze.

## Contesto di utilizzo {#context-of-use}

The **[!UICONTROL Push notification]** activity is generally used to automate sending a notification to a target calculated in the same workflow.

Se collegato a un pianificatore, puoi definire notifiche push ricorrenti.

I destinatari vengono definiti a monte dell&#39;attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni ecc.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard messaggi, puoi scegliere se richiedere o meno una conferma manuale per inviare il messaggio (richiesta per impostazione predefinita). Puoi avviare il flusso di lavoro manualmente o inserire un’attività di pianificazione nel flusso di lavoro per automatizzare l’esecuzione.

**Argomenti correlati**

* [Invio di una notifica push ricorrente con un flusso di lavoro](../../automating/using/recurring-push-notifications.md)

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Push notification]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Puoi accedere alle proprietà generali e alle opzioni avanzate dell’attività (e non della consegna stessa) tramite il pulsante ![](assets/dlv_activity_params-24px.png) dalle azioni rapide dell’attività. Questo pulsante è specifico per l’attività **[!UICONTROL Push notification]**. Le proprietà della notifica push sono accessibili tramite la barra delle azioni nel dashboard push.

1. Selezionate la modalità di invio della notifica push:

   * **[!UICONTROL Single notification]**: la notifica push viene inviata una sola volta. Puoi specificare qui se desideri aggiungere o meno una transizione in uscita all’attività. I diversi tipi di transizione sono descritti nel passaggio 7 di questa procedura.
   * **[!UICONTROL Recurring notification]**: la notifica push viene inviata diverse volte, in base alla frequenza definita in un&#39; **[!UICONTROL Scheduler]** attività. Seleziona il periodo di aggregazione degli invii. This allows you to regroup all the sends that occur during the defined period in one single push notification that is also called **recurring execution** and can be accessed from the application&#39;s marketing activity list.

      Ad esempio, per una notifica di compleanno ricorrente, inviata ogni giorno, potete scegliere di aggregare le invii al mese. Questo consente di ricevere rapporti sulla consegna su base mensile anche se la notifica viene inviata ogni giorno.

1. Selezionate un tipo di notifica. Questi tipi provengono dai modelli delle notifiche push definiti nel **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** menu.
1. Immettete le proprietà generali per la notifica push. Puoi anche allegarlo a una campagna esistente. L&#39;etichetta dell&#39;attività di consegna del flusso di lavoro viene aggiornata con l&#39;etichetta di notifica push.
1. Definite il contenuto della notifica push. Consultate [Creazione di una notifica push](../../channels/using/preparing-and-sending-a-push-notification.md)
1. Per impostazione predefinita, l’attività **[!UICONTROL Push notification]** non include transizioni in uscita. Se desideri aggiungere una transizione in uscita all’attività **[!UICONTROL Push Notification]**, passa alla scheda **[!UICONTROL General]** delle opzioni di attività avanzate (pulsante ![](assets/dlv_activity_params-24px.png) nelle azioni rapide dell’attività), quindi seleziona una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: ti consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata.
   * **[!UICONTROL Add outbound transition with the population]**: questo consente di generare una transizione in uscita contenente la popolazione a cui è stata inviata la notifica. I membri del target esclusi durante la preparazione della consegna sono esclusi da questa transizione.

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

Quando riaprite l&#39;attività, venite portati direttamente al dashboard di notifica push. È possibile modificarne solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L’invio di messaggi creati da un flusso di lavoro deve comunque essere confermato dopo l’avvio del flusso di lavoro. Tuttavia, puoi disattivare l’opzione **[!UICONTROL Request confirmation before sending messages]** dal dashboard messaggi e solo se il messaggio è stato creato da un flusso di lavoro. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all’interno di un flusso di lavoro sono accessibili nell’elenco delle attività di marketing dell’applicazione. Puoi visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo delle notifiche push consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna ecc.).

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL Push notification]** activity was configured). A tal fine, apri la visualizzazione dei dettagli del blocco **[!UICONTROL Deployment]** della consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).
