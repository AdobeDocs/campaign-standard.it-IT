---
title: Gestione di SMS in arrivo
seo-title: Gestione di SMS in arrivo
description: Gestione di SMS in arrivo
seo-description: Scopri come gestire STOP SMS e archiviare SMS in arrivo in Adobe Campaign.
page-status-flag: never-activated
uuid: f 063052 b -96 ef -41 b 6-bf 1 b -4006 de 73 f 0 b 9
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canali
content-type: riferimento
topic-tags: sms-messages
discoiquuid: ee 1970 e 6-1 ced -46 e 0-94 e 6-8337768300 ee
delivercontext-tags: delivery, smscontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Managing incoming SMS{#managing-incoming-sms}

## Managing STOP SMS {#managing-stop-sms}

Quando un profilo risponde a un messaggio SMS inviato tramite Campaign, è possibile configurare messaggi che vengono inviati automaticamente e l'azione da eseguire.

This configuration is defined in the **[!UICONTROL Automatic reply sent to the MO]** section of the [SMS Routing external account](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO è disponibile per'Mobile Originated ', che significa che potete configurare una risposta automatica al mobile che ha inviato l'SMS.

A tal fine:

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]** then the **[!UICONTROL SMS routing via SMPP]** external account.
1. Under the **[!UICONTROL Automatic reply sent to the MO]** category, click **[!UICONTROL Create element]** to start configuring your automatic reply.

   ![](assets/sms_mo_1.png)

1. Scegliete la parola chiave che attiva la risposta automatica. Le parole chiave non sono sensibili alle maiuscole/minuscole. Ad esempio, se i destinatari inviano la parola chiave "STOP", riceveranno la risposta automatica.

   Lasciate vuota questa colonna se desiderate inviare la stessa risposta indipendentemente dalla parola chiave.

   ![](assets/sms_mo_2.png)

1. In the **[!UICONTROL Short code]** field, specify a number that is usually used to send deliveries and will serve as a sender name. You can also decide to leave the **[!UICONTROL Short code]** column empty, to send the same reply no matter what the short code.

   ![](assets/sms_mo_4.png)

1. Type in the answer you want to send to your recipients in the field **[!UICONTROL Reply]**.

   To carry out an action without sending a reply, leave the **[!UICONTROL Reply]** column empty. Ad esempio, questo consente di rimuovere il numero di telefono di un utente che risponde con un messaggio diverso da "STOP".

   ![](assets/sms_mo_3.png)

1. In the **[!UICONTROL Additional action]** field, link an action to your automatic reply:

   * **[!UICONTROL Send to quarantine]** L'azione esegue automaticamente la migrazione del numero di telefono del profilo.
   * The **[!UICONTROL Remove from quarantine]** action removes the profile phone number from quarantine.
   * The **[!UICONTROL None]** action allows you to only send the message to your recipients without carrying an action.
   For example, in the configuration below, if recipients send the keyword "STOP", they will automatically receive an unsubscription confirmation and their phone number will be sent to quarantine with the **[!UICONTROL Blacklisted]** status. Questo stato fa riferimento solo al numero di telefono, il profilo non viene inserito in lista nera in modo che l'utente continui a ricevere messaggi e-mail.

   ![](assets/sms_mo.png)

I destinatari possono ora annullare la sottoscrizione ai messaggi e inviarli in quarantena con questa risposta automatica. The quarantined recipients are listed in the **[!UICONTROL Addresses]** table available through the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Quarantines]** menu. For more information on quarantines, refer to this [section](../../sending/using/understanding-quarantine-management.md).

Se necessario, questi SMS in arrivo possono essere memorizzati. For more information on this, refer to this [section](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

## Storing incoming SMS {#storing-incoming-sms}

In the **[!UICONTROL SMS routing via SMPP]** external account, you can choose to store incoming messages for example when a subscriber replies "STOP" to an SMS message in order to be removed from your recipient lists.

![](assets/sms_config_mo_1.png)

By checking **[!UICONTROL Store incoming MO in the database]** in the **[!UICONTROL SMPP channel settings]** category, all SMS will be stored in the inSMS table and can be retrieved via a query activity in a workflow.

A tal fine:

1. In the **[!UICONTROL SMPP channel settings]** field, check **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. In the **[!UICONTROL Marketing activities]** tab, click **[!UICONTROL Create]** then select **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Selezionate il tipo di flusso di lavoro.
1. Edit the properties of your workflow, then click **[!UICONTROL Create]**. For more on workflows creation, refer to this [section](../../automating/using/building-a-workflow.md).
1. Drag and drop a **[!UICONTROL Query]** activity and double-click the activity.
1. In the **[!UICONTROL Properties]** tab of the query, choose **[!UICONTROL Incoming SMS (inSMS)]** in the **[!UICONTROL Resource]** field.

   ![](assets/sms_config_mo_4.png)

1. Then, in the **[!UICONTROL Target]** tab, drag and drop the **[!UICONTROL Incoming SMS attributes]** rule.

   ![](assets/sms_config_mo_5.png)

1. Qui, vogliamo eseguire il targeting di ogni messaggio in entrata dal giorno prima. In the **[!UICONTROL Field]** category, select **[!UICONTROL Creation date (created)]**.
1. In **[!UICONTROL Filter type]**, select **[!UICONTROL Relative]** then in **[!UICONTROL Level of precision]**, choose **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Potete quindi scegliere di recuperare dati da oggi, il giorno prima o gli ultimi giorni. Click **[!UICONTROL Confirm]** when your query is configured.

Questa query recupererà ogni messaggio STOP ricevuto a seconda dell'intervallo di tempo scelto.

L'attività consente ad esempio di creare una popolazione e di personalizzare meglio le consegne.
