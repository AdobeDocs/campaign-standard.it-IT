---
title: Informazioni sulla pianificazione dei messaggi
seo-title: Informazioni sulla pianificazione dei messaggi
description: Informazioni sulla pianificazione dei messaggi
seo-description: Scopri come pianificare i messaggi.
page-status-flag: never-activated
uuid: 286 fceee -65 a 9-4 cb 9-b 205-9 ce 5 d 024675 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: invio
content-type: riferimento
topic-tags: sheduling-messages
discoiquuid: 9 c 7 fd 670-bba 9-4 f 3 c -8 cb 1-87397 a 1 acd 27
context-tags: consegna, pianificazione, indietro
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# About scheduling messages{#about-scheduling-messages}

>[!CAUTION]
>
>Whenever making changes to a delivery’s schedule, you must re-prepare the delivery by clicking on the **Prepare** button before clicking **Confirm**.

In the message dashboard, the **[!UICONTROL Schedule]** block allows you to define when messages (email, SMS or Push notifications) will be sent.

![](assets/delivery_dashboard.png)

The **[!UICONTROL Schedule]** properties let you set sending options for your emails, SMS or push notifications:

* **[!UICONTROL Messages to be sent once confirmed]**: messaggi vengono inviati non appena l'invio viene confermato. See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**: messaggi verranno inviati in una data e in un'ora successive. Specify the **contact date** in the **Start sending from** field.

   Puoi preparare e confermare l'invio, ma i messaggi saranno inviati solo a partire dalla data e ora selezionate. Preparing and confirming the send are presented in the [Preparing the send](../../sending/using/preparing-the-send.md) and [Confirming the send](../../sending/using/confirming-the-send.md) sections.

   The **[!UICONTROL Time zone of the contact date]** drop-down list allows you to modify the time zone that will be taken into account for the sending time. For example, if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field and if you select Brussels, Copenhagen, Madrid, Paris (GMT+1) in the **[!UICONTROL Time zone of the contact date]** drop-down list, all recipients will receive the message at 9:00 AM Paris time. Pertanto, un destinatario che si trova a Mosca (GMT +3) riceverà il messaggio alle 11:00 ora di Mosca.

   If you would like to manually confirm the send, check the **[!UICONTROL Request confirmation before sending messages]** option. Questa opzione è attivata per impostazione predefinita.

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>Durante la duplicazione di una distribuzione, tutte le impostazioni di pianificazione vengono eliminate. A meno che non programmate una nuova data di contatto, la consegna duplicata verrà inviata non appena l'invio viene confermato.

**Argomenti correlati**:

* [Ottimizzazione dell'ora di invio](../../sending/using/optimizing-the-sending-time.md)
* [Invio di messaggi al fuso orario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [Calcolo della data di invio](../../sending/using/computing-the-sending-date.md)

