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

Questa configurazione è definita nella **[!UICONTROL Automatic reply sent to the MO]** sezione del [Account esterno di indirizzamento SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO sta per &quot;Mobile Originated&quot; (Originato da dispositivo mobile), il che significa che puoi configurare una risposta automatica al dispositivo mobile che ha inviato l’SMS.

Per eseguire questa operazione:

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration > Application settings > External accounts]** quindi il **[!UICONTROL SMS routing via SMPP]** account esterno.
1. Sotto **[!UICONTROL Automatic reply sent to the MO]** categoria, fai clic su **[!UICONTROL Create element]** per iniziare a configurare la risposta automatica.

   ![](assets/sms_mo_1.png)

1. Scegli la parola chiave che attiverà questa risposta automatica. Le parole chiave non fanno distinzione tra maiuscole e minuscole. Ad esempio, in questo caso, i destinatari che inviano la parola chiave &quot;STOP&quot; riceveranno la risposta automatica.

   Lascia vuota questa colonna se vuoi inviare la stessa risposta indipendentemente dalla parola chiave.

   >[!IMPORTANT]
   >
   >Sono autorizzati solo i caratteri alfanumerici.

   ![](assets/sms_mo_2.png)

1. In **[!UICONTROL Short code]** , specifica un numero utilizzato solitamente per inviare le consegne e che fungerà da nome del mittente. Puoi anche decidere di lasciare il **[!UICONTROL Short code]** colonna vuota, per inviare la stessa risposta indipendentemente dal codice breve.

   ![](assets/sms_mo_4.png)

1. Digita la risposta che desideri inviare ai destinatari nel campo **[!UICONTROL Reply]**.

   Per eseguire un&#39;azione senza inviare una risposta, lasciare **[!UICONTROL Reply]** colonna vuota. Ad esempio, questo consente di rimuovere dalla quarantena il numero di telefono di un utente che risponde con un messaggio diverso da &quot;STOP&quot;.

   ![](assets/sms_mo_3.png)

1. In **[!UICONTROL Additional action]** collegare un&#39;azione alla risposta automatica:

   * Il **[!UICONTROL Send to quarantine]** azione mette automaticamente in quarantena il numero di telefono del profilo.
   * Il **[!UICONTROL Remove from quarantine]** rimuove il numero di telefono del profilo dalla quarantena.
   * Il **[!UICONTROL None]** consente di inviare il messaggio solo ai destinatari senza eseguire alcuna azione.

   Ad esempio, nella configurazione seguente, se i destinatari inviano la parola chiave &quot;STOP&quot;, riceveranno automaticamente una conferma di annullamento dell’abbonamento e il loro numero di telefono verrà messo in quarantena con **[!UICONTROL On denylist]** stato. Questo stato si riferisce solo al numero di telefono, il profilo è tale che l’utente continua a ricevere messaggi e-mail.

   ![](assets/sms_mo.png)

1. Fai clic su **[!UICONTROL Save]**.

1. Dalla sezione **[!UICONTROL Advanced parameters]** della consegna SMS **[!UICONTROL Properties]**, è possibile impostare un **[!UICONTROL Short code]** per escludere automaticamente i destinatari che hanno rinunciato. Per ulteriori informazioni, consulta [questa sezione](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).

Con questa risposta automatica, i destinatari possono annullare automaticamente l’abbonamento ai messaggi e metterli in quarantena. I destinatari in quarantena sono elencati nella **[!UICONTROL Addresses]** tabella disponibile tramite **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** menu. Per ulteriori informazioni sulle quarantene, consulta questa [sezione](../../sending/using/understanding-quarantine-management.md).

Se necessario, questi SMS in entrata possono essere archiviati. Per ulteriori informazioni, consulta questa [sezione](#storing-incoming-sms).

## Memorizzazione degli SMS in arrivo {#storing-incoming-sms}

In **[!UICONTROL SMS routing via SMPP]** account esterno, puoi scegliere di memorizzare i messaggi in arrivo, ad esempio quando un abbonato risponde &quot;STOP&quot; a un messaggio SMS per essere rimosso dagli elenchi dei destinatari.

![](assets/sms_config_mo_1.png)

Selezionando **[!UICONTROL Store incoming MO in the database]** nel **[!UICONTROL SMPP channel settings]** categoria, tutti gli SMS verranno memorizzati nella tabella inSMS e possono essere recuperati tramite un’attività di query in un flusso di lavoro.

Per eseguire questa operazione:

1. In **[!UICONTROL SMPP channel settings]** campo, spunta **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. In **[!UICONTROL Marketing activities]** , fare clic su **[!UICONTROL Create]** quindi seleziona **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Seleziona il tipo di flusso di lavoro.
1. Modifica le proprietà del flusso di lavoro, quindi fai clic su **[!UICONTROL Create]**. Per ulteriori informazioni sulla creazione di flussi di lavoro, consulta questa [sezione](../../automating/using/building-a-workflow.md).
1. Trascina una **[!UICONTROL Query]** e fare doppio clic sull&#39;attività.
1. In **[!UICONTROL Properties]** della query, scegli **[!UICONTROL Incoming SMS (inSMS)]** nel **[!UICONTROL Resource]** campo.

   ![](assets/sms_config_mo_4.png)

1. Quindi, nella **[!UICONTROL Target]** , trascina e rilascia la **[!UICONTROL Incoming SMS attributes]** regola.

   ![](assets/sms_config_mo_5.png)

1. In questo caso, vogliamo eseguire il targeting di ogni messaggio in arrivo del giorno precedente. In **[!UICONTROL Field]** categoria, seleziona **[!UICONTROL Creation date (created)]**.
1. In entrata **[!UICONTROL Filter type]**, seleziona **[!UICONTROL Relative]** allora in **[!UICONTROL Level of precision]**, scegli **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Puoi quindi scegliere di recuperare i dati da oggi, il giorno precedente o gli ultimi giorni. Clic **[!UICONTROL Confirm]** quando la query è configurata.

Questa query recupererà ogni messaggio STOP ricevuto a seconda dell’intervallo di tempo scelto.

L’attività ti consente, ad esempio, di creare una popolazione e personalizzare meglio le consegne.
