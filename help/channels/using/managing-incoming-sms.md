---
solution: Campaign Standard
product: campaign
title: Gestione degli SMS in arrivo
description: Scopri come gestire l’SMS STOP e archiviare gli SMS in arrivo in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
feature: SMS
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 7%

---


# Gestione degli SMS in arrivo{#managing-incoming-sms}

## Gestione dell’SMS STOP {#managing-stop-sms}

Quando un profilo risponde a un messaggio SMS inviato tramite Campaign, puoi configurare messaggi da inviargli automaticamente e l’azione da eseguire.

Questa configurazione è definita nella sezione **[!UICONTROL Automatic reply sent to the MO]** dell’ [account esterno di indirizzamento SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO sta per &quot;Mobile Originato&quot;, il che significa che puoi configurare una risposta automatica al cellulare che ha inviato l’SMS.

Per eseguire questa operazione:

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration > Application settings > External accounts]** , quindi l’ account esterno **[!UICONTROL SMS routing via SMPP]**.
1. Sotto la categoria **[!UICONTROL Automatic reply sent to the MO]**, fare clic su **[!UICONTROL Create element]** per iniziare a configurare la risposta automatica.

   ![](assets/sms_mo_1.png)

1. Scegliere la parola chiave che attiverà questa risposta automatica. Le parole chiave non sono sensibili all’uso di maiuscole e minuscole. Ad esempio, in questo caso, se i destinatari inviano la parola chiave &quot;STOP&quot;, riceveranno la risposta automatica.

   Lasciare vuota questa colonna se si desidera inviare la stessa risposta indipendentemente dalla parola chiave.

   ![](assets/sms_mo_2.png)

1. Nel campo **[!UICONTROL Short code]** , specifica un numero generalmente utilizzato per inviare consegne e fungerà da nome del mittente. Puoi anche decidere di lasciare vuota la colonna **[!UICONTROL Short code]**, per inviare la stessa risposta indipendentemente dal codice breve.

   ![](assets/sms_mo_4.png)

1. Digita la risposta da inviare ai destinatari nel campo **[!UICONTROL Reply]**.

   Per eseguire un&#39;azione senza inviare una risposta, lasciare vuota la colonna **[!UICONTROL Reply]**. Ad esempio, questo consente di rimuovere dalla quarantena il numero di telefono di un utente che risponde con un messaggio diverso da &quot;STOP&quot;.

   ![](assets/sms_mo_3.png)

1. Nel campo **[!UICONTROL Additional action]** , collega un’azione alla risposta automatica:

   * L’azione **[!UICONTROL Send to quarantine]** mette automaticamente in quarantena il numero di telefono del profilo.
   * L’azione **[!UICONTROL Remove from quarantine]** rimuove il numero di telefono del profilo dalla quarantena.
   * L’azione **[!UICONTROL None]** ti consente di inviare il messaggio solo ai destinatari senza eseguire alcuna azione.

   Ad esempio, nella configurazione seguente, se i destinatari inviano la parola chiave &quot;STOP&quot;, riceveranno automaticamente una conferma dell’annullamento dell’abbonamento e il loro numero di telefono verrà messo in quarantena con lo stato **[!UICONTROL On denylist]** . Questo stato si riferisce solo al numero di telefono, il profilo è in modo che l&#39;utente continui a ricevere messaggi e-mail.

   ![](assets/sms_mo.png)

Ora i destinatari possono annullare automaticamente l’iscrizione ai messaggi e metterli in quarantena con questa risposta automatica. I destinatari messi in quarantena sono elencati nella tabella **[!UICONTROL Addresses]** disponibile dal menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** . Per ulteriori informazioni sulle quarantena, consulta questa sezione [a1/> .](../../sending/using/understanding-quarantine-management.md)

Se necessario, questi SMS in arrivo possono essere memorizzati. Per ulteriori informazioni, consulta questa [sezione](#storing-incoming-sms).

## Memorizzazione degli SMS in arrivo {#storing-incoming-sms}

Nell’account esterno **[!UICONTROL SMS routing via SMPP]**, puoi scegliere di memorizzare i messaggi in arrivo, ad esempio quando un utente con sottoscrizione risponde &quot;STOP&quot; a un messaggio SMS per essere rimosso dagli elenchi dei destinatari.

![](assets/sms_config_mo_1.png)

Selezionando **[!UICONTROL Store incoming MO in the database]** nella categoria **[!UICONTROL SMPP channel settings]** , tutti gli SMS verranno memorizzati nella tabella inSMS e possono essere recuperati tramite un’attività di query in un flusso di lavoro.

Per eseguire questa operazione:

1. Nel campo **[!UICONTROL SMPP channel settings]** , seleziona **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. Nella scheda **[!UICONTROL Marketing activities]** , fai clic su **[!UICONTROL Create]**, quindi seleziona **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Seleziona il tipo di flusso di lavoro.
1. Modifica le proprietà del flusso di lavoro, quindi fai clic su **[!UICONTROL Create]**. Per ulteriori informazioni sulla creazione dei flussi di lavoro, consulta questa [sezione](../../automating/using/building-a-workflow.md).
1. Trascina e rilascia un’attività **[!UICONTROL Query]** e fai doppio clic su di essa.
1. Nella scheda **[!UICONTROL Properties]** della query, scegli **[!UICONTROL Incoming SMS (inSMS)]** nel campo **[!UICONTROL Resource]** .

   ![](assets/sms_config_mo_4.png)

1. Quindi, nella scheda **[!UICONTROL Target]** , trascina e rilascia la regola **[!UICONTROL Incoming SMS attributes]** .

   ![](assets/sms_config_mo_5.png)

1. In questo caso, vogliamo eseguire il targeting di ogni messaggio in arrivo dal giorno precedente. Nella categoria **[!UICONTROL Field]**, selezionare **[!UICONTROL Creation date (created)]**.
1. In **[!UICONTROL Filter type]**, seleziona **[!UICONTROL Relative]** quindi in **[!UICONTROL Level of precision]**, scegli **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Puoi quindi scegliere di recuperare i dati da oggi, il giorno precedente o gli ultimi giorni. Fai clic su **[!UICONTROL Confirm]** quando la query è configurata.

Questa query recupererà ogni messaggio STOP ricevuto a seconda dell&#39;intervallo di tempo scelto.

L’attività ti consente ad esempio di generare una popolazione e di personalizzare meglio le consegne.
