---
title: Gestione degli SMS in arrivo
description: Scopri come gestire gli SMS STOP e archiviare gli SMS in arrivo in Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: 86cb6f4c-a5a7-4d9d-bbfd-4a70af38cf3a
source-git-commit: 30d0c2552bea3a7cbd8500be4e8c0c74e5a40a99
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 2%

---

# Gestione degli SMS in arrivo{#managing-incoming-sms}

## Gestione di STOP SMS {#managing-stop-sms}

Quando un profilo risponde a un messaggio SMS inviato tramite Campaign, puoi configurare i messaggi che vengono inviati automaticamente e l’azione da eseguire.

Questa configurazione è definita nella sezione **[!UICONTROL Automatic reply sent to the MO]** dell&#39;account esterno di indirizzamento [SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO sta per &quot;Mobile Originated&quot; (Originato da dispositivo mobile), il che significa che puoi configurare una risposta automatica al dispositivo mobile che ha inviato l’SMS.

Per eseguire questa operazione:

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration > Application settings > External accounts]** e quindi l&#39;account esterno **[!UICONTROL SMS routing via SMPP]**.
1. Nella categoria **[!UICONTROL Automatic reply sent to the MO]**, fai clic su **[!UICONTROL Create element]** per iniziare a configurare la risposta automatica.

   ![](assets/sms_mo_1.png)

1. Scegli la parola chiave che attiverà questa risposta automatica. Le parole chiave non fanno distinzione tra maiuscole e minuscole. Ad esempio, in questo caso, i destinatari che inviano la parola chiave &quot;STOP&quot; riceveranno la risposta automatica.

   Lascia vuota questa colonna se vuoi inviare la stessa risposta indipendentemente dalla parola chiave.

   >[!IMPORTANT]
   >
   >Sono autorizzati solo i caratteri alfanumerici.

   ![](assets/sms_mo_2.png)

1. Nel campo **[!UICONTROL Short code]**, specifica un numero utilizzato solitamente per inviare le consegne e che fungerà da nome del mittente. Puoi anche decidere di lasciare vuota la colonna **[!UICONTROL Short code]**, per inviare la stessa risposta indipendentemente dal codice breve.

   ![](assets/sms_mo_4.png)

1. Digitare la risposta da inviare ai destinatari nel campo **[!UICONTROL Reply]**.

   Per eseguire un&#39;azione senza inviare una risposta, lasciare vuota la colonna **[!UICONTROL Reply]**. Ad esempio, questo consente di rimuovere dalla quarantena il numero di telefono di un utente che risponde con un messaggio diverso da &quot;STOP&quot;.

   ![](assets/sms_mo_3.png)

1. Nel campo **[!UICONTROL Additional action]**, collega un&#39;azione alla risposta automatica:

   * L&#39;azione **[!UICONTROL Send to quarantine]** mette automaticamente in quarantena il numero di telefono del profilo.
   * L&#39;azione **[!UICONTROL Remove from quarantine]** rimuove il numero di telefono del profilo dalla quarantena.
   * L&#39;azione **[!UICONTROL None]** consente di inviare il messaggio solo ai destinatari senza includere un&#39;azione.

   Ad esempio, nella configurazione seguente, se i destinatari inviano la parola chiave &quot;STOP&quot;, riceveranno automaticamente una conferma di annullamento dell&#39;abbonamento e il loro numero di telefono verrà messo in quarantena con lo stato **[!UICONTROL On denylist]**. Questo stato si riferisce solo al numero di telefono, il profilo è tale che l’utente continua a ricevere messaggi e-mail.

   ![](assets/sms_mo.png)

1. Fai clic su **[!UICONTROL Save]**.

1. Dal **[!UICONTROL Advanced parameters]** della consegna SMS **[!UICONTROL Properties]**, puoi impostare un **[!UICONTROL Short code]** specifico per escludere automaticamente i destinatari che hanno rinunciato. Per ulteriori informazioni, consulta [questa sezione](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).

Con questa risposta automatica, i destinatari possono annullare automaticamente l’abbonamento ai messaggi e metterli in quarantena. I destinatari in quarantena sono elencati nella tabella **[!UICONTROL Addresses]** disponibile tramite il menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]**. Per ulteriori informazioni sulle quarantene, consulta questa [sezione](../../sending/using/understanding-quarantine-management.md).

Se necessario, questi SMS in entrata possono essere archiviati. Per ulteriori informazioni, consulta questa [sezione](#storing-incoming-sms).

## Memorizzazione degli SMS in arrivo {#storing-incoming-sms}

Nell&#39;account esterno **[!UICONTROL SMS routing via SMPP]** è possibile scegliere di memorizzare i messaggi in arrivo, ad esempio quando un utente iscritto risponde &quot;STOP&quot; a un messaggio SMS per essere rimosso dagli elenchi dei destinatari.

![](assets/sms_config_mo_1.png)

Selezionando **[!UICONTROL Store incoming MO in the database]** nella categoria **[!UICONTROL SMPP channel settings]**, tutti gli SMS verranno memorizzati nella tabella inSMS e potranno essere recuperati tramite un&#39;attività Query in un flusso di lavoro.

Per eseguire questa operazione:

1. Nel campo **[!UICONTROL SMPP channel settings]**, selezionare **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. Nella scheda **[!UICONTROL Marketing activities]**, fai clic su **[!UICONTROL Create]**, quindi seleziona **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Seleziona il tipo di flusso di lavoro.
1. Modifica le proprietà del flusso di lavoro, quindi fai clic su **[!UICONTROL Create]**. Per ulteriori informazioni sulla creazione di flussi di lavoro, consulta questa [sezione](../../automating/using/building-a-workflow.md).
1. Trascinare e rilasciare un&#39;attività **[!UICONTROL Query]** e fare doppio clic sull&#39;attività.
1. Nella scheda **[!UICONTROL Properties]** della query, scegliere **[!UICONTROL Incoming SMS (inSMS)]** nel campo **[!UICONTROL Resource]**.

   ![](assets/sms_config_mo_4.png)

1. Quindi, nella scheda **[!UICONTROL Target]**, trascina e rilascia la regola **[!UICONTROL Incoming SMS attributes]**.

   ![](assets/sms_config_mo_5.png)

1. In questo caso, vogliamo eseguire il targeting di ogni messaggio in arrivo del giorno precedente. Nella categoria **[!UICONTROL Field]**, selezionare **[!UICONTROL Creation date (created)]**.
1. In **[!UICONTROL Filter type]** selezionare **[!UICONTROL Relative]**, quindi in **[!UICONTROL Level of precision]** scegliere **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Puoi quindi scegliere di recuperare i dati da oggi, il giorno precedente o gli ultimi giorni. Fai clic su **[!UICONTROL Confirm]** quando la query è configurata.

Questa query recupererà ogni messaggio STOP ricevuto a seconda dell’intervallo di tempo scelto.

L’attività ti consente, ad esempio, di creare una popolazione e personalizzare meglio le consegne.
