---
title: Consegna SMS
seo-title: Consegna SMS
description: Consegna SMS
seo-description: L'attività di consegna SMS consente di configurare l'invio di un SMS singolo o di un SMS periodico in un flusso di lavoro.
page-status-flag: never-activated
uuid: 736078 c 6-ac 91-4440-825 b -4 a 6 ae 31894 ef
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: channel-activity
discoiquuid: 978592 b 8-989 a -446 a -8 a 84-12 b 7 fecfc 130
context-tags: sms, main; delivery, smscontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# SMS delivery{#sms-delivery}

## Description {#description}

![](assets/sms.png)

![](assets/recurrentsms.png)

The **[!UICONTROL SMS delivery]** activity allows you to configure sending an SMS in a workflow. This can be a **single send** SMS and sent just once, or it can be a **recurring** SMS.

I messaggi SMS singolo sono SMS standard, inviati una volta.

I messaggi SMS ricorrenti consentono di inviare lo stesso SMS più volte a destinazioni diverse in un determinato periodo di tempo. Puoi aggregare le consegne per periodo per ottenere rapporti che corrispondono alle tue esigenze.

## Context of use {#context-of-use}

The **[!UICONTROL SMS delivery]** activity is generally used to automate sending an SMS to a target calculated in the same workflow.

Se collegati a un pianificatore, puoi definire messaggi SMS ricorrenti.

I destinatari SMS vengono definiti a monte dell'attività nello stesso flusso di lavoro, mediante attività di targeting quali query, intersezioni ecc.

La preparazione del messaggio viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal pannello del messaggio, potete selezionare se richiedere o meno una conferma manuale per inviare il messaggio (richiesto per impostazione predefinita). Puoi avviare il flusso di lavoro manualmente oppure inserire un'attività pianificatore nel flusso di lavoro per automatizzare l'esecuzione.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL SMS delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button in the workflow's action bar. This button is specific to the **[!UICONTROL SMS delivery]** activity. Le proprietà SMS sono accessibili tramite la barra delle azioni nel dashboard SMS.

1. Selezionate la modalità di invio SMS:

   * **[!UICONTROL SMS]**: l'SMS viene inviato una sola volta. Potete specificare qui se desiderate aggiungere una transizione in uscita all'attività. I diversi tipi di transizione sono descritti al punto 7 di questa procedura.
   * **[!UICONTROL Recurring SMS]**: il SMS viene inviato più volte, a seconda della frequenza definita in un **[!UICONTROL Scheduler]** 'attività. Selezionare il periodo di aggregazione delle mandate. This allows you to regroup all the sends that occur during the defined period into one single view that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      Ad esempio, per un SMS ricorrente che viene inviato ogni giorno, potete scegliere di aggregare le mandate al mese. Questo consente di ricevere ogni giorno rapporti sulla distribuzione, anche se l'SMS viene inviato ogni giorno.

1. Selezionate un tipo di SMS. The SMS types come from SMS templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. Immettete le proprietà generali dell'SMS. Potete allegarlo a una campagna esistente. L'etichetta dell'attività di consegna del flusso di lavoro viene aggiornata con l'etichetta SMS.
1. Definire il contenuto SMS. Refer to the section concerning [Creating an SMS message](../../channels/using/creating-an-sms-message.md).
1. By default, the **[!UICONTROL SMS delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL SMS delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**: consente di generare una transizione in uscita contenente la stessa popolazione della transizione in ingresso.
   * **[!UICONTROL Add outbound transition with the population]**: consente di generare una transizione in uscita contenente la popolazione a cui è stato inviato l'SMS. I membri della destinazione esclusi durante la preparazione della consegna (quarantena, numero non valido, ecc.) sono esclusi da questa transizione.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

Quando riaprite l'attività, verrete indirizzati direttamente al dashboard SMS. Solo il relativo contenuto può essere modificato.

Per impostazione predefinita, l'avvio di un flusso di lavoro di consegna attiva solo la preparazione del messaggio. L'invio di messaggi creati da un flusso di lavoro deve comunque essere confermato dopo che il flusso di lavoro è stato avviato. But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Remarks {#remarks}

Le consegne create all'interno di un flusso di lavoro sono accessibili nell'elenco delle attività di marketing dell'applicazione. Potete visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo SMS consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, consegna padre nel caso di SMS periodico).

Tuttavia, per impostazione predefinita, le esecuzioni di consegne ricorrenti sono mascherate. To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL SMS delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

## Example {#example}

![](assets/wkf_sms_example_1.png)

Questo esempio è un flusso di lavoro di compleanno. Ogni giorno viene inviato un SMS a profili il cui compleanno si trova in quel giorno. A tal fine:

* The **[!UICONTROL Scheduler]** allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* The **[!UICONTROL Query]** activity allows you to calculate the profiles who have provided a mobile phone number and whose birthday is on the current day, every time the workflow is executed. Il calcolo di compleanno viene eseguito utilizzando un filtro predefinito disponibile nella palette nello strumento di modifica query.

   ![](assets/wkf_delivery_example_3.png)

* The **[!UICONTROL SMS]** is recurring. Le mandate vengono aggregate per mese. Pertanto, tutti i messaggi SMS inviati in un mese vengono aggregati in una sola visualizzazione. In one year, 365 deliveries are therefore executed but they are regrouped into 12 views (also called **recurring executions**) in the Adobe Campaign interface. La cronologia e i dettagli del rapporto vengono visualizzati ogni mese e non per ogni invio.

   ![](assets/wkf_sms_example_4.png)

