---
title: Consegna notifica push
description: L’attività Push notification delivery ti consente di configurare l’invio di una notifica push singola o ricorrente in un flusso di lavoro.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: b6a43d51-32d4-4806-b4e4-33236f1e27f5
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 46%

---

# Consegna notifica push{#push-notification-delivery}

## Descrizione {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

L&#39;attività **[!UICONTROL Push notification]** consente di configurare l&#39;invio di una notifica push in un flusso di lavoro. Può trattarsi di una singola notifica di invio e inviata solo una volta oppure di una notifica ricorrente.

* **Le notifiche di invio singole** sono consegne di notifiche push standard per app mobili, inviate una sola volta.
* **Notifiche ricorrenti** ti consentono di inviare la stessa consegna di notifiche push per app mobile più volte a destinazioni diverse in un determinato periodo di tempo. Puoi aggregare le consegne per periodo in modo da ottenere report che corrispondano alle tue esigenze.

## Contesto di utilizzo {#context-of-use}

L&#39;attività **[!UICONTROL Push notification]** viene generalmente utilizzata per automatizzare l&#39;invio di una notifica a una destinazione calcolata nello stesso flusso di lavoro.

Se collegata a una pianificazione, consente di definire notifiche push ricorrenti.

I destinatari sono definiti a monte dell’attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni, ecc.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard messaggi, puoi scegliere se richiedere o meno una conferma manuale per inviare il messaggio (richiesta per impostazione predefinita). Puoi avviare il flusso di lavoro manualmente o inserire un’attività di pianificazione nel flusso di lavoro per automatizzare l’esecuzione.

**Argomenti correlati**

* [Invio di una notifica push ricorrente con un flusso di lavoro](../../automating/using/recurring-push-notifications.md)

## Configurazione {#configuration}

1. Trascina e rilascia un’attività **[!UICONTROL Push notification]** nel flusso di lavoro.
1. Seleziona l’attività, quindi aprila utilizzando il pulsante ![](assets/edit_darkgrey-24px.png) delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Puoi accedere alle proprietà generali e alle opzioni avanzate dell’attività (e non della consegna stessa) tramite il pulsante ![](assets/dlv_activity_params-24px.png) dalle azioni rapide dell’attività. Questo pulsante è specifico per l’attività **[!UICONTROL Push notification]**. Le proprietà della notifica push sono accessibili tramite la barra delle azioni nel dashboard push.

1. Seleziona la modalità di invio della notifica push:

   * **[!UICONTROL Single notification]**: notifica push inviata una sola volta. Puoi specificare qui se desideri aggiungere o meno una transizione in uscita all’attività. I diversi tipi di transizione sono descritti nel passaggio 7 di questa procedura.
   * **[!UICONTROL Recurring notification]**: la notifica push viene inviata diverse volte, in base alla frequenza definita in un&#39;attività **[!UICONTROL Scheduler]**. Seleziona il periodo di aggregazione degli invii. Ciò ti consente di raggruppare tutti gli invii che avvengono durante il periodo definito in un&#39;unica notifica push, denominata anche **esecuzione ricorrente**, e a cui è possibile accedere dall&#39;elenco delle attività di marketing dell&#39;applicazione.

     Ad esempio, per una notifica di compleanno ricorrente, inviata ogni giorno, puoi scegliere di aggregare gli invii al mese. Questo ti consente di ricevere report sulla consegna su base mensile, anche se la notifica viene inviata ogni giorno.

1. Seleziona un tipo di notifica. Questi tipi provengono dai modelli di notifiche push definiti nel menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**.
1. Immetti le proprietà generali per la notifica push. Puoi anche allegarlo a una campagna esistente. L’etichetta dell’attività di consegna del flusso di lavoro viene aggiornata con l’etichetta della notifica push.
1. Definisci il contenuto della notifica push. Vedi [Creazione di una notifica push](../../channels/using/preparing-and-sending-a-push-notification.md)
1. Per impostazione predefinita, l’attività **[!UICONTROL Push notification]** non include transizioni in uscita. Se desideri aggiungere una transizione in uscita all’attività **[!UICONTROL Push Notification]**, passa alla scheda **[!UICONTROL General]** delle opzioni di attività avanzate (pulsante ![](assets/dlv_activity_params-24px.png) nelle azioni rapide dell’attività), quindi seleziona una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: ti consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata.
   * **[!UICONTROL Add outbound transition with the population]**: consente di generare una transizione in uscita contenente la popolazione a cui è stata inviata la notifica. I membri del target esclusi durante la preparazione della consegna sono esclusi da questa transizione.

1. Conferma la configurazione dell’attività e salva il flusso di lavoro.

Quando riapri l’attività, accedi direttamente al dashboard delle notifiche push. È possibile modificarne solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L’invio di messaggi creati da un flusso di lavoro deve comunque essere confermato dopo l’avvio del flusso di lavoro. Tuttavia, puoi disattivare l’opzione **[!UICONTROL Request confirmation before sending messages]** dal dashboard messaggi e solo se il messaggio è stato creato da un flusso di lavoro. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all’interno di un flusso di lavoro sono accessibili nell’elenco delle attività di marketing dell’applicazione. Puoi visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo delle notifiche push ti consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, ecc.).

Nelle consegne principali, accessibili dall&#39;elenco delle attività di marketing, è possibile visualizzare il numero totale di invii che sono stati elaborati (in base al periodo di aggregazione specificato al momento della configurazione dell&#39;attività **[!UICONTROL Push notification]**). A tal fine, apri la visualizzazione dei dettagli del blocco **[!UICONTROL Deployment]** della consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).
