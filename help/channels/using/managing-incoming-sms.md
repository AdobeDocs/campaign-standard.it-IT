---
title: Gestione degli SMS in arrivo
description: Scopri come gestire l’SMS STOP e archiviare gli SMS in arrivo in Adobe Campaign.
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

## Gestione dell’SMS STOP {#managing-stop-sms}

Quando un profilo risponde a un messaggio SMS inviato tramite Campaign, puoi configurare messaggi che vengono loro automaticamente inviati di nuovo, nonché l’azione da eseguire.

Questa configurazione è definita nella **[!UICONTROL Automatic reply sent to the MO]** della sezione [Account esterno di indirizzamento SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO sta per &quot;Mobile Originato&quot;, il che significa che puoi configurare una risposta automatica al cellulare che ha inviato l’SMS.

Per eseguire questa operazione:

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration > Application settings > External accounts]** quindi il **[!UICONTROL SMS routing via SMPP]** conto esterno.
1. Sotto la **[!UICONTROL Automatic reply sent to the MO]** categoria, fai clic su **[!UICONTROL Create element]** per iniziare a configurare la risposta automatica.

   ![](assets/sms_mo_1.png)

1. Scegliere la parola chiave che attiverà questa risposta automatica. Le parole chiave non sono sensibili all’uso di maiuscole e minuscole. Ad esempio, in questo caso, se i destinatari inviano la parola chiave &quot;STOP&quot;, riceveranno la risposta automatica.

   Lasciare vuota questa colonna se si desidera inviare la stessa risposta indipendentemente dalla parola chiave.

   >[!IMPORTANT]
   >
   >Sono autorizzati solo i caratteri alfanumerici.

   ![](assets/sms_mo_2.png)

1. In **[!UICONTROL Short code]** Specifica un numero utilizzato di solito per inviare consegne e fungerà da nome del mittente. Puoi anche decidere di lasciare il **[!UICONTROL Short code]** colonna vuota, per inviare la stessa risposta indipendentemente dal codice breve.

   ![](assets/sms_mo_4.png)

1. Digita la risposta da inviare ai destinatari nel campo . **[!UICONTROL Reply]**.

   Per eseguire un&#39;azione senza inviare una risposta, lasciare **[!UICONTROL Reply]** colonna vuota. Ad esempio, questo consente di rimuovere dalla quarantena il numero di telefono di un utente che risponde con un messaggio diverso da &quot;STOP&quot;.

   ![](assets/sms_mo_3.png)

1. In **[!UICONTROL Additional action]** campo , collega un&#39;azione alla tua risposta automatica:

   * La **[!UICONTROL Send to quarantine]** l’azione mette automaticamente in quarantena il numero di telefono del profilo.
   * La **[!UICONTROL Remove from quarantine]** rimuove il numero di telefono del profilo dalla quarantena.
   * La **[!UICONTROL None]** consente di inviare il messaggio solo ai destinatari senza eseguire un’azione.

   Ad esempio, nella configurazione seguente, se i destinatari inviano la parola chiave &quot;STOP&quot;, riceveranno automaticamente una conferma dell’annullamento dell’abbonamento e il loro numero di telefono verrà messo in quarantena con il **[!UICONTROL On denylist]** stato. Questo stato si riferisce solo al numero di telefono, il profilo è in modo che l&#39;utente continui a ricevere messaggi e-mail.

   ![](assets/sms_mo.png)

1. Fai clic su **[!UICONTROL Save]**.

1. Da **[!UICONTROL Advanced parameters]** della consegna SMS **[!UICONTROL Properties]**, puoi impostare un **[!UICONTROL Short code]** per escludere automaticamente i destinatari che hanno rinunciato. Per ulteriori informazioni, consulta [questa sezione](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).

Ora i destinatari possono annullare automaticamente l’iscrizione ai messaggi e metterli in quarantena con questa risposta automatica. I destinatari messi in quarantena sono elencati nella **[!UICONTROL Addresses]** tabella disponibile tramite **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** menu. Per ulteriori informazioni sulle quarantena, consulta questo [sezione](../../sending/using/understanding-quarantine-management.md).

Se necessario, questi SMS in arrivo possono essere memorizzati. Per ulteriori informazioni, consulta questo [sezione](#storing-incoming-sms).

## Memorizzazione degli SMS in arrivo {#storing-incoming-sms}

In **[!UICONTROL SMS routing via SMPP]** account esterno, è possibile scegliere di memorizzare i messaggi in arrivo, ad esempio quando un utente iscritto risponde &quot;STOP&quot; a un messaggio SMS per essere rimosso dagli elenchi dei destinatari.

![](assets/sms_config_mo_1.png)

Controllando **[!UICONTROL Store incoming MO in the database]** in **[!UICONTROL SMPP channel settings]** categoria , tutti gli SMS verranno memorizzati nella tabella inSMS e possono essere recuperati tramite un’attività di query in un flusso di lavoro.

Per eseguire questa operazione:

1. In **[!UICONTROL SMPP channel settings]** campo, controllo **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. In **[!UICONTROL Marketing activities]** scheda , fai clic su **[!UICONTROL Create]** quindi seleziona **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Seleziona il tipo di flusso di lavoro.
1. Modifica le proprietà del flusso di lavoro, quindi fai clic su **[!UICONTROL Create]**. Per ulteriori informazioni sulla creazione di flussi di lavoro, consulta questo [sezione](../../automating/using/building-a-workflow.md).
1. Trascina e rilascia una **[!UICONTROL Query]** e fai doppio clic sull’attività.
1. In **[!UICONTROL Properties]** scheda della query, scegli **[!UICONTROL Incoming SMS (inSMS)]** in **[!UICONTROL Resource]** campo .

   ![](assets/sms_config_mo_4.png)

1. Quindi, nella **[!UICONTROL Target]** , trascina e rilascia **[!UICONTROL Incoming SMS attributes]** regola.

   ![](assets/sms_config_mo_5.png)

1. In questo caso, vogliamo eseguire il targeting di ogni messaggio in arrivo dal giorno precedente. In **[!UICONTROL Field]** categoria, seleziona **[!UICONTROL Creation date (created)]**.
1. In **[!UICONTROL Filter type]**, seleziona **[!UICONTROL Relative]** quindi in **[!UICONTROL Level of precision]**, scegli **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Puoi quindi scegliere di recuperare i dati da oggi, il giorno precedente o gli ultimi giorni. Fai clic su **[!UICONTROL Confirm]** quando la query è configurata.

Questa query recupererà ogni messaggio STOP ricevuto a seconda dell&#39;intervallo di tempo scelto.

L’attività ti consente ad esempio di generare una popolazione e di personalizzare meglio le consegne.
