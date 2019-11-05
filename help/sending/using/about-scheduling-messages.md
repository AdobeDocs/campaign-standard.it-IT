---
title: Informazioni sulla pianificazione dei messaggi
description: Scopri come pianificare i messaggi.
page-status-flag: mai attivato
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: invio
content-type: reference
topic-tags: programmazione dei messaggi
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: consegna,pianificazione,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Informazioni sulla pianificazione dei messaggi{#about-scheduling-messages}

>[!CAUTION]
>
>Ogni volta che apportate modifiche alla pianificazione di una consegna, dovete prepararla nuovamente facendo clic sul pulsante **Prepara** prima di fare clic su **Conferma**.

Nel dashboard dei messaggi, il **[!UICONTROL Schedule]** blocco consente di definire quando verranno inviati i messaggi (e-mail, SMS o notifiche push).

![](assets/delivery_dashboard.png)

Le **[!UICONTROL Schedule]** proprietà consentono di impostare le opzioni di invio per le e-mail, gli SMS o le notifiche push:

* **[!UICONTROL Messages to be sent once confirmed]**: i messaggi vengono inviati non appena l'invio viene confermato. See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**: i messaggi verranno inviati in una data e in un'ora successive. Specifica la data **di** contatto nel campo **Inizia invio dal** .

   Puoi preparare e confermare l’invio, ma i messaggi verranno inviati solo a partire dalla data e ora selezionate. La preparazione e la conferma dell’invio sono presentate nelle sezioni [Preparazione dell’invio](../../sending/using/preparing-the-send.md) e [Conferma dell’invio](../../sending/using/confirming-the-send.md) .

   L'elenco a **[!UICONTROL Time zone of the contact date]** discesa consente di modificare il fuso orario che verrà preso in considerazione per l'ora di invio. Ad esempio, se immetti le 9:00 AM nel **[!UICONTROL Start sending from]** campo e se selezioni Bruxelles, Copenaghen, Madrid, Parigi (GMT+1) nell’elenco a **[!UICONTROL Time zone of the contact date]** discesa, tutti i destinatari riceveranno il messaggio alle 9:00 ora di Parigi. Pertanto, un destinatario residente a Mosca (GMT+3) riceverà il messaggio alle 11:00 ora di Mosca.

   Per confermare manualmente l’invio, selezionate l’ **[!UICONTROL Request confirmation before sending messages]** opzione. Questa opzione è attivata per impostazione predefinita.

   ![](assets/delivery_planning.png)

>[!CAUTION]
>
>Quando si duplica una consegna, tutte le impostazioni di pianificazione vengono eliminate. A meno che non pianifichi una nuova data di contatto, la consegna duplicata verrà inviata non appena l'invio verrà confermato.

**Argomenti** correlati:

* [Ottimizzazione del tempo di invio](../../sending/using/optimizing-the-sending-time.md)
* [Invio di messaggi con il fuso orario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [Calcolo della data di invio](../../sending/using/computing-the-sending-date.md)

