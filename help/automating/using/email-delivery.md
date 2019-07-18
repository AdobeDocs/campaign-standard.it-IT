---
title: Consegna e-mail
seo-title: Consegna e-mail
description: Consegna e-mail
seo-description: L'attività Consegna e-mail consente di configurare l'invio di una sola e-mail di invio o di un'e-mail ricorrente in un flusso di lavoro.
page-status-flag: never-activated
uuid: 7 de 53431-84 ae -4 d 21-8361-2775 ad 314 ed 2
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automazione
content-type: riferimento
topic-tags: channel-activity
discoiquuid: 5 f 288 cf 6-f 8 ff -4 ac 9-9 c 1 a -8010260554 bb
context-tags: distribuzione, flusso di lavoro principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Email delivery{#email-delivery}

## Description {#description}

![](assets/email.png)

![](assets/recurrentemail.png)

The **[!UICONTROL Email delivery]** activity allows you to configure sending an email in a workflow. This can be a **single send** email and sent just once, or it can be a **recurring** email.

Le e-mail di invio singolo sono e-mail standard, inviate una volta.

Le e-mail ricorrenti consentono di inviare lo stesso messaggio e-mail più volte a destinazioni diverse in un determinato periodo di tempo. Puoi aggregare le consegne per periodo per ottenere rapporti che corrispondono alle tue esigenze.

## Context of use {#context-of-use}

The **[!UICONTROL Email delivery]** activity is generally used to automate sending an email to a target calculated in the same workflow.

Se collegate a un pianificatore, potete definire e-mail ricorrenti.

I destinatari e-mail vengono definiti a monte dell'attività nello stesso flusso di lavoro, mediante attività di targeting quali query, intersezioni ecc.

La preparazione del messaggio viene attivata in base ai parametri di esecuzione del flusso di lavoro. Dal pannello del messaggio, potete selezionare se richiedere o meno una conferma manuale per inviare il messaggio (richiesto per impostazione predefinita). Puoi avviare il flusso di lavoro manualmente oppure inserire un'attività pianificatore nel flusso di lavoro per automatizzare l'esecuzione.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Email delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions. This button is specific to the **[!UICONTROL Email delivery]** activity. Potete accedere alle proprietà dell'e-mail tramite la barra delle azioni nel dashboard e-mail.

1. Selezionate la modalità di invio e-mail:

   * **[!UICONTROL Email]**: l'e-mail viene inviata una sola volta. Potete specificare qui se desiderate aggiungere una transizione in uscita all'attività. I diversi tipi di transizione sono descritti al punto 7 di questa procedura.
   * **[!UICONTROL Recurring email]**: il messaggio e-mail viene inviato più volte, a seconda della frequenza definita in un **[!UICONTROL Scheduler]** 'attività. Selezionare il periodo di aggregazione delle mandate. This allows you to regroup all the sends that occur during the defined period in one single email that is also called **Recurring execution** and can be accessed from the application's marketing activity list.

      Ad esempio, per un messaggio e-mail di compleanno ricorrente inviato ogni giorno, potete scegliere di aggregare le mandate al mese. Questo consente di ricevere ogni giorno i rapporti sulla distribuzione, anche se l'e-mail viene inviata ogni giorno.

1. Selezionate un tipo di e-mail. The email types come from email templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** menu.
1. Inserite le proprietà generali dell'e-mail. Potete allegarlo a una campagna esistente. L'etichetta dell'attività di consegna del flusso di lavoro viene aggiornata con l'etichetta e-mail.
1. Definite il contenuto dell'e-mail. Refer to the section concerning [content editing](../../designing/using/about-email-content-design.md).
1. By default, the **[!UICONTROL Email delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL Email delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**: consente di generare una transizione in uscita contenente la stessa popolazione della transizione in ingresso.
   * **[!UICONTROL Add outbound transition with the population]**: consente di generare una transizione in uscita contenente la popolazione a cui è stata inviata l'e-mail. I membri della destinazione sono esclusi durante la preparazione della consegna (quarantena, e-mail non valida, ecc.) sono esclusi da questa transizione.

1. Confermate la configurazione dell'attività e salvate il flusso di lavoro.

Quando riaprite l'attività, viene portato direttamente al dashboard e-mail. Solo il relativo contenuto può essere modificato.

Per impostazione predefinita, l'avvio di un flusso di lavoro di consegna attiva solo la preparazione del messaggio. L'invio di messaggi creati da un flusso di lavoro deve comunque essere confermato dopo che il flusso di lavoro è stato avviato. But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. Deselezionando questa opzione, i messaggi vengono inviati senza ulteriore preavviso una volta completata la preparazione.

## Remarks {#remarks}

Le consegne create all'interno di un flusso di lavoro sono accessibili nell'elenco delle attività di marketing dell'applicazione. Potete visualizzare lo stato di esecuzione del flusso di lavoro utilizzando il dashboard. I collegamenti nel riquadro di riepilogo delle e-mail consentono di accedere direttamente agli elementi collegati (flusso di lavoro, campagna, consegna padre nel caso di un messaggio e-mail periodico).

![](assets/wkf_display_recurrent_executions_2.png)

Tuttavia, per impostazione predefinita, le esecuzioni di consegne ricorrenti sono mascherate. To view them, check the **[!UICONTROL Show recurring executions]** option in the marketing activities' search panel.

![](assets/wkf_display_recurrent_executions.png)

In the parent deliveries, which can be accessed from the marketing activity list or directly via the associated recurring executions, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL Email delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).

![](assets/wkf_display_recurrent_executions_3.png)

## Example {#example}

![](assets/wkf_delivery_example_1.png)

Questo esempio è un flusso di lavoro di compleanno. Ogni giorno viene inviato un messaggio e-mail a profili il cui compleanno si trova in quel giorno. A tal fine:

* The **[!UICONTROL Scheduler]** allows you to start the workflow every day at 8am.

   ![](assets/wkf_delivery_example_2.png)

* The **[!UICONTROL Query]** activity allows you to calculate the profiles who have provided an email and whose birthday it is on the current day, every time the workflow is executed. Il calcolo di compleanno viene eseguito utilizzando un filtro predefinito disponibile nella palette nello strumento di modifica query.

   ![](assets/wkf_delivery_example_3.png)

* The **[!UICONTROL Email]** is recurring. Le mandate vengono aggregate per mese. Pertanto, tutte le e-mail inviate in un mese vengono aggregate in una sola visualizzazione. In one year, 365 deliveries are therefore executed but they are regrouped into 12 views (also called **recurring executions**) in the Adobe Campaign interface. La cronologia e i dettagli del rapporto vengono visualizzati ogni mese e non per ogni invio.

   ![](assets/wkf_delivery_example_4.png)

