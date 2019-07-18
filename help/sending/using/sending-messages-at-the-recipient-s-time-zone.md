---
title: Invio di messaggi al fuso orario del destinatario
seo-title: Invio di messaggi al fuso orario del destinatario
description: Invio di messaggi al fuso orario del destinatario
seo-description: Scopri come inviare messaggi nel fuso orario del destinatario.
page-status-flag: never-activated
uuid: 70228 c 07-451 f -4 ddb -8 d 26-92 a 5 a 4814 e 3 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: invio
content-type: riferimento
topic-tags: sheduling-messages
discoiquuid: daa 980 ba -8 c 7 c -4673-a 68 f -379 d 63 e 4 b 8 bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Sending messages at the recipient's time zone{#sending-messages-at-the-recipient-s-time-zone}

Quando gestite una campagna in cui la data e l'ora sono importanti, potete pianificare una consegna che riporti l'ora locale di ciascun destinatario: riceveranno un'e-mail, SMS o noftficazioni push al momento programmato, nel loro fuso orario.

>[!NOTE]
>
>To use this functionality, make sure that all profiles targeted by your delivery have a time zone specified in the **[!UICONTROL Address]** section of their properties. For more information on accessing profile properties, refer to this [section](../../audiences/using/editing-profiles.md).

To send a delivery at the recipient's time zone, you can also use the **[!UICONTROL Scheduler]** activity in a workflow. For more on this, refer to this [page](../../automating/using/scheduler.md).

Nell'esempio seguente, desideriamo inviare un codice promozionale valido solo per San Valentino a tutti i clienti in tutto il mondo. Per fornire un tempo sufficiente a utilizzarlo durante il giorno, tutti i clienti devono ricevere il messaggio il 14 febbraio alle 8:00, a seconda dei loro fusi orari.

1. In the **[!UICONTROL Marketing activities]** tab, start creating your delivery, in our case an email. To learn more on delivery creation, refer to this [section](../../channels/using/creating-an-email.md).
1. After designing your Valentine's Day email, click **[!UICONTROL Create]** to access the delivery dashboard. For more on email designing, refer to this [page](../../designing/using/example--email-personalization.md).

   ![](assets/send-time_opt_valentine_1.png)

1. From the delivery dashboard, select the **[!UICONTROL Schedule]** block.

   ![](assets/send-time_opt_valentine_2.png)

1. Select the **[!UICONTROL Messages to be sent automatically on the date]** option specified below. Then in the **[!UICONTROL Start sending from]** field, set the contact date, in our case February 14th at 8:00 AM so that every recipient receives it on Valentine's Day.

   ![](assets/send-time_opt_valentine.png)

1. In the **[!UICONTROL Time zone of the contact date]** field, select at which time zone your delivery should be sent by default.

   If a profile's **[!UICONTROL Time zone]** is left as **[!UICONTROL Default]**, the recipients will receive the delivery depending on the chosen time zone here.

1. From the **[!UICONTROL Optimize the sending time per recipient]** drop-down menu, choose **[!UICONTROL Send at the recipient's time zone]**. Questo consente ai destinatari di ricevere il giorno di San Valentino nel 14 di febbraio a seconda del fuso orario.

   ![](assets/send-time_opt_valentine_3.png)

1. After confirming your schedule for your delivery, click the **[!UICONTROL Prepare]** button then **[!UICONTROL Confirm]** your delivery.

   Assicurati di confermare l'invio in anticipo di almeno 24 ore. In caso contrario, a seconda delle posizioni, alcuni destinatari potrebbero ricevere la consegna prima dell'evento giorno di San Valentino.

   ![](assets/send-time_opt_valentine_4.png)

A prescindere da dove si trovano, tutti i destinatari riceveranno il messaggio il 14 febbraio alle 8:00 dell'ora locale.
