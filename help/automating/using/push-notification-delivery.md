---
title: Consegna delle notifiche push
seo-title: Consegna delle notifiche push
description: Consegna delle notifiche push
seo-description: L'attività di consegna delle notifiche push consente di configurare l'invio di una notifica push singola o periodica in un flusso di lavoro.
page-status-flag: never-activated
uuid: 994 d 8 fe 3-29 f 0-4 b 5 c -89 ee-c 6 be 7 c 60 a 31 b
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: channel-activity
discoiquuid: e 61 bdaee -4 b 48-4845-a 2 a 5-574 b 577 ea 796
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Push notification delivery{#push-notification-delivery}

## Description {#description}

![](assets/push.png)

![](assets/recurrentpush.png)

The **[!UICONTROL Push notification]** activity allows you to configure sending a push notification in a workflow. This can be a **single send** notification and sent just once, or it can be a **recurring** notification.

Le notifiche di invio singole sono consegne standard di notifiche push per dispositivi mobili, inviate una volta.

Le notifiche ricorrenti consentono di inviare più volte la stessa notifica push dell'app mobile a target diversi in un determinato periodo di tempo. Puoi aggregare le consegne per periodo per ottenere rapporti che corrispondono alle tue esigenze.

## Context of use {#context-of-use}

The **[!UICONTROL Push notification]** activity is generally used to automate sending a notification to a target calculated in the same workflow.

Se collegate a un pianificatore, potete definire notifiche push ricorrenti.

I destinatari vengono definiti a monte dell'attività nello stesso flusso di lavoro, mediante attività di targeting quali query, intersezioni ecc.

La preparazione del messaggio viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal pannello del messaggio, potete selezionare se richiedere o meno una conferma manuale per inviare il messaggio (richiesto per impostazione predefinita). Puoi avviare il flusso di lavoro manualmente oppure inserire un'attività pianificatore nel flusso di lavoro per automatizzare l'esecuzione.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Push notification]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. This button is specific to the **[!UICONTROL Push notification]** activity. Potete accedere alle proprietà della notifica push tramite la barra delle azioni nella dashboard push.

1. Seleziona la modalità di invio notifica push:

   * **[!UICONTROL Single notification]**: la notifica push viene inviata una sola volta. Potete specificare qui se desiderate aggiungere una transizione in uscita all'attività. I diversi tipi di transizione sono descritti al punto 7 di questa procedura.
   * **[!UICONTROL Recurring notification]**: la notifica push viene inviata più volte, a seconda della frequenza definita in un **[!UICONTROL Scheduler]** 'attività. Selezionare il periodo di aggregazione delle mandate. This allows you to regroup all the sends that occur during the defined period in one single push notification that is also called **recurring execution** and can be accessed from the application's marketing activity list.

      Ad esempio, per una notifica di compleanno ricorrente inviata ogni giorno, potete scegliere di aggregare le mandate al mese. Questo consente di ricevere rapporti sulla distribuzione mensile, anche se la notifica viene inviata ogni giorno.

1. Selezionate un tipo di notifica. These types come from push notifications templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. Immettete le proprietà generali della notifica push. Potete allegarlo a una campagna esistente. L'etichetta dell'attività di consegna del flusso di lavoro viene aggiornata con l'etichetta di notifica push.
1. Definire il contenuto delle notifiche push. See [Creating a push notification](../../channels/using/preparing-and-sending-a-push-notification.md)
1. By default, the **[!UICONTROL Push notification]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Push Notification]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**: consente di generare una transizione in uscita contenente la stessa popolazione della transizione in ingresso.
   * **[!UICONTROL Add outbound transition with the population]**: consente di generare una transizione in uscita contenente la popolazione a cui è stata inviata la notifica. I membri della destinazione esclusi durante la preparazione di consegna sono esclusi da questa transizione.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

Quando riaprite l'attività, viene portato direttamente al dashboard delle notifiche push. Solo il relativo contenuto può essere modificato.

Per impostazione predefinita, l'avvio di un flusso di lavoro di consegna attiva solo la preparazione del messaggio. L'invio di messaggi creati da un flusso di lavoro deve comunque essere confermato dopo che il flusso di lavoro è stato avviato. But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Remarks {#remarks}

Le consegne create all'interno di un flusso di lavoro sono accessibili nell'elenco delle attività di marketing dell'applicazione. Potete visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro riepilogo delle notifiche push consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna ecc.).

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL Push notification]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

## Sending a recurring push notification with a workflow {#sending-a-recurring-push-notification-with-a-workflow}

![](assets/wkf_push_example_1.png)

In questo esempio, una notifica push personalizzata viene inviata ogni giorno del mese alle 8 per gli abbonati dell'applicazione mobile a seconda dei loro fusi orari. A tal fine:

1. The **[!UICONTROL Scheduler]** activity allows you to start the workflow days before the start of the delivery to be able to send the notification to every subscriber at 8 pm in any given time zone:

   * In the **[!UICONTROL Execution frequency]** field, select Monthly.
   * Select 8 pm in the **[!UICONTROL Time]** field.
   * Scegli il giorno in cui la consegna verrà inviata ogni mese.
   * Seleziona una data di inizio per il flusso di lavoro, almeno un giorno prima dell'inizio della distribuzione. In caso contrario, alcuni destinatari ricevono il messaggio un giorno dopo se l'ora selezionata è già trascorsa nei relativi fusi orari.
   * In the **[!UICONTROL Execution options]** tab, select at which time zone your workflow will start in the **[!UICONTROL Time zone]** field. Qui, ad esempio, il flusso di lavoro inizierà dalle 8 alle, una settimana prima del primo giorno del mese, per consentire la creazione delle consegne per tutti i fusi orari applicabili.
   ![](assets/wkf_push_example_5.png)

1. The **Query** activity allows you to target your VIP customers aged between 20-30, who have subscribed to your mobile application and who did not open the email you sent:

   * Selezionate un'audience (i clienti VIP) e filtrate l'età.
   * Drag and drop the **Subscriptions to an application** element into the workspace. Select **Exists** and select the mobile application that you want to use.
   * Selezionate l'e-mail inviata ai clienti.
   * Drag and drop the **Delivery logs (logs)** element into the workspace and select **Exists** to target all of the customers who received the email.
   * Drag and drop the **Tracking logs (tracking)** element into the workspace and select **Does not exist** to target all of the customers who did not open the email.

      ![](assets/wkf_push_example_2.png)

1. The **Push notification** activity allows you to enter the content of your message and to select the personalization fields that you want to use:

   * Select the **[!UICONTROL Recurring notification]** option.
   * Definire il contenuto delle notifiche push. For more information on push notification content, refer to this [section](../../channels/using/preparing-and-sending-a-push-notification.md).
   * In the **[!UICONTROL Schedule]** block, select **[!UICONTROL Messages to be sent automatically on the time zone specified below]**. Here, we chose the **[!UICONTROL Time zone of the contact date]** Pacific as in the workflow **[!UICONTROL Scheduler]**.
   * In the **[!UICONTROL Optimize the sending time per recipient]** field, select **[!UICONTROL Send at the recipient's time zone]**.

      ![](assets/wkf_push_example_4.png)

1. Click the **[!UICONTROL Start]** button to start your recurring workflow.

   ![](assets/wkf_push_example_3.png)

Il flusso di lavoro è ora in esecuzione. It will start at the chosen start date of the **[!UICONTROL Scheduler]** at 8 pm Pacific time, the recurring push will then be sent every first day of the month at 8 pm depending on the customers time zone.
