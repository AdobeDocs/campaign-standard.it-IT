---
title: Recapito notifiche push
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
source-git-commit: accc382ca1543d648e60d53cab338537fd9ea3ef

---


# Recapito notifiche push{#push-notification-delivery}

## Descrizione {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

L&#39; **[!UICONTROL Push notification]**attività consente di configurare l&#39;invio di una notifica push in un flusso di lavoro. Può trattarsi di una** singola notifica di invio **e inviata una sola volta, oppure di una notifica** ricorrente **.

Le notifiche di invio singolo sono notifiche push standard delle app mobili, inviate una volta.

Le notifiche ricorrenti consentono di inviare la stessa notifica push dell&#39;app mobile più volte a destinazioni diverse in un periodo definito. È possibile aggregare le consegne per periodo al fine di ottenere rapporti che corrispondano alle proprie esigenze.

## Contesto di utilizzo {#context-of-use}

L&#39; **[!UICONTROL Push notification]**attività viene generalmente utilizzata per automatizzare l&#39;invio di una notifica a una destinazione calcolata nello stesso flusso di lavoro.

Se collegato a un pianificatore, puoi definire notifiche push ricorrenti.

I destinatari vengono definiti a monte dell&#39;attività nello stesso flusso di lavoro, tramite attività di targeting come query, intersezioni ecc.

La preparazione dei messaggi viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal dashboard dei messaggi, puoi scegliere se richiedere o meno una conferma manuale per l&#39;invio del messaggio (richiesta per impostazione predefinita). È possibile avviare il flusso di lavoro manualmente o inserire un&#39;attività pianificatore nel flusso di lavoro per automatizzare l&#39;esecuzione.

## Configurazione {#configuration}

1. Trascinate e rilasciate un&#39; **[!UICONTROL Push notification]**attività nel flusso di lavoro.
1. Selezionate l&#39;attività, quindi apritela utilizzando il ![](assets/edit_darkgrey-24px.png) pulsante delle azioni rapide visualizzate.

   >[!NOTE]
   >
   >Potete accedere alle proprietà generali e alle opzioni avanzate dell&#39;attività (e non della distribuzione stessa) tramite il ![](assets/dlv_activity_params-24px.png) pulsante dalle azioni rapide dell&#39;attività. Questo pulsante è specifico per l&#39; **[!UICONTROL Push notification]**attività. Le proprietà della notifica push sono accessibili tramite la barra delle azioni nel dashboard push.

1. Selezionate la modalità di invio della notifica push:

   * **[!UICONTROL Single notification]**: la notifica push viene inviata una sola volta. Potete specificare qui se desiderate aggiungere o meno una transizione in uscita all&#39;attività. I diversi tipi di transizione sono descritti nel passaggio 7 di questa procedura.
   * **[!UICONTROL Recurring notification]**: la notifica push viene inviata diverse volte, in base alla frequenza definita in un&#39;**[!UICONTROL Scheduler]** attività. Selezionare il periodo di aggregazione delle mandate. Questo consente di raggruppare tutte le invii che si verificano durante il periodo definito in un&#39;unica notifica push denominata anche esecuzione **** periodica e accessibile dall&#39;elenco delle attività di marketing dell&#39;applicazione.

      Ad esempio, per una notifica di compleanno ricorrente, inviata ogni giorno, potete scegliere di aggregare le invii al mese. Questo consente di ricevere rapporti sulla consegna su base mensile anche se la notifica viene inviata ogni giorno.

1. Selezionate un tipo di notifica. Questi tipi provengono dai modelli delle notifiche push definiti nel **[!UICONTROL Resources]**>**[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]**menu.
1. Immettete le proprietà generali per la notifica push. Potete anche allegarlo a una campagna esistente. L&#39;etichetta dell&#39;attività di consegna del flusso di lavoro viene aggiornata con l&#39;etichetta di notifica push.
1. Definite il contenuto della notifica push. Consultate [Creazione di una notifica push](../../channels/using/preparing-and-sending-a-push-notification.md)
1. Per impostazione predefinita, l&#39; **[!UICONTROL Push notification]**attività non include transizioni in uscita. Se desiderate aggiungere una transizione in uscita all&#39;**[!UICONTROL Push Notification]** attività, andate alla **[!UICONTROL General]**scheda delle opzioni di attività avanzate (![](assets/dlv_activity_params-24px.png)pulsante nelle azioni rapide dell&#39;attività), quindi selezionate una delle seguenti opzioni:

   * **[!UICONTROL Add outbound transition without the population]**: questo consente di generare una transizione in uscita che contiene esattamente la stessa popolazione della transizione in entrata.
   * **[!UICONTROL Add outbound transition with the population]**: questo consente di generare una transizione in uscita contenente la popolazione a cui è stata inviata la notifica. I membri del target esclusi durante la preparazione della consegna sono esclusi da questa transizione.

1. Confermate la configurazione dell&#39;attività e salvate il flusso di lavoro.

Quando riaprite l&#39;attività, venite portati direttamente al dashboard di notifica push. È possibile modificare solo il contenuto.

Per impostazione predefinita, l’avvio di un flusso di lavoro di consegna attiva solo la preparazione dei messaggi. L&#39;invio di messaggi creati da un flusso di lavoro deve ancora essere confermato dopo l&#39;avvio del flusso di lavoro. Tuttavia, dal dashboard dei messaggi e solo se il messaggio è stato creato da un flusso di lavoro, potete disattivare l&#39; **[!UICONTROL Request confirmation before sending messages]**opzione. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Osservazioni {#remarks}

Le consegne create all&#39;interno di un flusso di lavoro sono accessibili nell&#39;elenco delle attività di marketing dell&#39;applicazione. Potete visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo delle notifiche push consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna ecc.).

Nelle consegne principali, a cui è possibile accedere dall&#39;elenco delle attività di marketing, è possibile visualizzare il numero totale di invii che sono stati elaborati (in base al periodo di aggregazione specificato al momento della configurazione dell&#39; **[!UICONTROL Push notification]**attività). A tal fine, aprire la visualizzazione dettagli del**[!UICONTROL Deployment]** blocco di consegna principale selezionando ![](assets/wkf_dlv_detail_button.png).

## Invio di una notifica push ricorrente con un flusso di lavoro {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

In questo esempio, una notifica push personalizzata viene inviata ogni primo giorno del mese alle 20:00 agli abbonati dell&#39;applicazione mobile a seconda dei fusi orari. Per eseguire questa operazione:

1. L&#39; **[!UICONTROL Scheduler]**attività consente di avviare i giorni del flusso di lavoro prima dell&#39;inizio della consegna per poter inviare la notifica a tutti gli abbonati alle 20:00 in un dato fuso orario:

   * Nel **[!UICONTROL Execution frequency]**campo, selezionare Mensile.
   * Selezionare le 20:00 nel **[!UICONTROL Time]**campo.
   * Scegliere il giorno in cui verrà inviata la consegna ogni mese.
   * Selezionate una data di inizio per il flusso di lavoro, almeno un giorno prima dell’inizio della consegna. In caso contrario, alcuni destinatari potrebbero ricevere il messaggio un giorno dopo se l’ora selezionata è già passata nei loro fusi orari.
   * Nella **[!UICONTROL Execution options]**scheda, selezionare il fuso orario in cui il flusso di lavoro verrà avviato nel**[!UICONTROL Time zone]** campo. Qui, ad esempio, il flusso di lavoro inizia alle 20:00 ora del Pacifico, una settimana prima del primo giorno del mese, per consentire la creazione di un certo numero di consegne per tutti i fusi orari applicabili.
   >[!NOTE]
   >
   >Per impostazione predefinita, il fuso orario selezionato è quello definito nelle proprietà del flusso di lavoro (vedere [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)).

   ![](assets/wkf_push_example_5.png)

1. L&#39;attività **Query** consente di eseguire il targeting dei clienti VIP di età compresa tra i 20 e i 30 anni, che si sono abbonati all&#39;applicazione mobile e che non hanno aperto l&#39;e-mail inviata:

   * Selezionate un&#39;audience (i vostri clienti VIP) e filtratene l&#39;età.
   * Trascinate le **iscrizioni a un elemento applicazione** nell’area di lavoro. Selezionate **Esiste** e selezionate l’applicazione mobile da usare.
   * Selezionate l’e-mail inviata ai clienti.
   * Trascinate e rilasciate l’elemento dei registri di **consegna (file di registro)** nell’area di lavoro e selezionate **Esiste** per indirizzare tutti i clienti che hanno ricevuto l’e-mail.
   * Trascinate l’elemento dei registri di **tracciamento (tracciamento)** nell’area di lavoro e selezionate **Non esiste** per indirizzare tutti i clienti che non hanno aperto l’e-mail.

      ![](assets/wkf_push_example_2.png)

1. L&#39;attività di notifica **** push consente di immettere il contenuto del messaggio e selezionare i campi di personalizzazione che si desidera utilizzare:

   * Selezionate l’ **[!UICONTROL Recurring notification]**opzione.
   * Definite il contenuto della notifica push. Per ulteriori informazioni sul contenuto delle notifiche push, consultate questa [sezione](../../channels/using/preparing-and-sending-a-push-notification.md).
   * Nel **[!UICONTROL Schedule]**blocco selezionare**[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Qui abbiamo scelto il **[!UICONTROL Time zone of the contact date]**Pacifico come nel flusso di lavoro**[!UICONTROL Scheduler]**.
   * Nel **[!UICONTROL Optimize the sending time per recipient]**campo selezionare**[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Fate clic sul **[!UICONTROL Start]**pulsante per avviare il flusso di lavoro periodico.

   ![](assets/wkf_push_example_3.png)

Il flusso di lavoro è ora in esecuzione. Comincerà dalla data di inizio scelta delle **[!UICONTROL Scheduler]**20:00 ora del Pacifico, il push periodico verrà inviato ogni primo giorno del mese alle 20:00 a seconda del fuso orario dei clienti.
