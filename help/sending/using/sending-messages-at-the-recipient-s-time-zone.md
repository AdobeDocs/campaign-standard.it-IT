---
title: Invio di messaggi al fuso orario del destinatario
seo-title: Invio di messaggi al fuso orario del destinatario
description: Invio di messaggi al fuso orario del destinatario
seo-description: Scopri come inviare messaggi al fuso orario del destinatario.
page-status-flag: mai attivato
uuid: 70228c07-451f-4ddb-8d26-92a5a4814e3a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: invio
content-type: reference
topic-tags: programmazione dei messaggi
discoiquuid: data980ba-8c7c-4673-a68f-379d63e4b8bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 781904d58f520987e978ad5d1cdc9e34871ca876

---


# Invio di messaggi al fuso orario del destinatario{#sending-messages-at-the-recipient-s-time-zone}

Quando gestisci una campagna in cui la data e l'ora sono importanti, puoi pianificare una consegna che tenga conto dell'ora locale di ciascun destinatario: riceveranno e-mail, SMS o notifiche push al momento previsto, nel loro fuso orario.

>[!NOTE]
>
>Per utilizzare questa funzionalità, accertati che tutti i profili di destinazione per la consegna abbiano un fuso orario specificato nella **[!UICONTROL Address]** sezione delle relative proprietà. Per ulteriori informazioni sull'accesso alle proprietà del profilo, consulta questa [sezione](../../audiences/using/editing-profiles.md).

Per inviare una consegna al fuso orario del destinatario, puoi anche utilizzare l' **[!UICONTROL Scheduler]** attività in un flusso di lavoro. Per ulteriori informazioni, consultare questa [pagina](../../automating/using/scheduler.md).

Nell'esempio seguente, desideriamo inviare un codice promozionale valido solo per il giorno di San Valentino a tutti i clienti di tutto il mondo. Per avere il tempo sufficiente per utilizzarlo durante il giorno, tutti i clienti devono ricevere il messaggio il 14 febbraio alle 08:00 a seconda del fuso orario.

1. Nella **[!UICONTROL Marketing activities]** scheda, inizia a creare la consegna, nel nostro caso un'e-mail. Per ulteriori informazioni sulla creazione della distribuzione, consulta questa [sezione](../../channels/using/creating-an-email.md).
1. Dopo aver progettato l'e-mail di San Valentino, fai clic **[!UICONTROL Create]** per accedere al dashboard di consegna. Per ulteriori informazioni sulla progettazione delle e-mail, consultate questa [pagina](../../designing/using/personalization.md#example-email-personalization).

   ![](assets/send-time_opt_valentine_1.png)

1. Dal dashboard consegna, selezionare il **[!UICONTROL Schedule]** blocco.

   ![](assets/send-time_opt_valentine_2.png)

1. Selezionare l' **[!UICONTROL Messages to be sent automatically on the date]** opzione specificata di seguito. Quindi nel **[!UICONTROL Start sending from]** campo, imposta la data di contatto, nel nostro caso il 14 febbraio alle 8:00 AM in modo che ogni destinatario lo riceva il giorno di San Valentino.

   ![](assets/send-time_opt_valentine.png)

1. Nel **[!UICONTROL Time zone of the contact date]** campo, selezionate il fuso orario in cui la consegna deve essere inviata per impostazione predefinita.

   Se un profilo **[!UICONTROL Time zone]** viene lasciato come **[!UICONTROL Default]**, i destinatari riceveranno la consegna a seconda del fuso orario scelto.

1. Dal **[!UICONTROL Optimize the sending time per recipient]** menu a discesa, scegliete **[!UICONTROL Send at the recipient's time zone]**. Questo consente ai destinatari di ricevere l'e-mail del giorno di San Valentino il 14 febbraio, a seconda del fuso orario.

   ![](assets/send-time_opt_valentine_3.png)

1. Dopo aver confermato il programma per la consegna, fare clic sul **[!UICONTROL Prepare]** pulsante e quindi sulla **[!UICONTROL Confirm]** consegna.

   Assicurarsi di confermare l'invio almeno 24 ore prima. In caso contrario, a seconda della posizione, alcuni destinatari potrebbero ricevere la consegna prima dell'evento effettivo del giorno di San Valentino.

   ![](assets/send-time_opt_valentine_4.png)

Indipendentemente dal luogo in cui si trovano, tutti i destinatari riceveranno il messaggio il 14 febbraio alle 8:00 ora locale.
