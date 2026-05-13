---
title: Informazioni sulla pianificazione dei messaggi
description: Scopri come pianificare i messaggi.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Send Time Optimization
role: User
exl-id: 6b26615b-4aa6-401d-a12d-25cef4cd0524
TQID: https://experienceleague.adobe.com/N0t5qvKiceoZEekhToXAk1PfNe1HE22vAaobLr32oME
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 276
ht-degree: 80%

---

# Informazioni sulla pianificazione dei messaggi{#about-scheduling-messages}

>[!IMPORTANT]
>
>Ogni volta che apporti modifiche alla pianificazione di una consegna, devi prepararla nuovamente facendo clic sul pulsante **Prepare** prima di fare clic su **Confirm**.

Nel dashboard dei messaggi, il blocco **[!UICONTROL Schedule]** ti consente di definire quando vengono inviati i messaggi (e-mail, SMS o notifiche push).

![](assets/delivery_dashboard.png)

Le proprietà **[!UICONTROL Schedule]** ti permettono di impostare le opzioni di invio per le e-mail, gli SMS o le notifiche push:

* **[!UICONTROL Messages to be sent once confirmed]**: i messaggi vengono inviati dopo la conferma dell’invio. Consulta [Conferma dell’invio](../../sending/using/confirming-the-send.md).

  ![](assets/delivery_planning_1.png)

* **[!UICONTROL Messages to be sent automatically on the date specified below]**: i messaggi vengono inviati in una data e in un’ora successive. Specifica la **data di contatto** nel campo **Start sending from**.

  Puoi preparare e confermare l’invio, ma i messaggi vengono inviati solo a partire dalla data e ora selezionate. La preparazione e la conferma dell’invio sono presentate nelle sezioni [Preparazione dell’invio](../../sending/using/preparing-the-send.md) e [Conferma dell’invio](../../sending/using/confirming-the-send.md).

  L’elenco a discesa **[!UICONTROL Time zone of the contact date]** ti consente di modificare il fuso orario da considerare per l’ora di invio. Ad esempio, se immetti le 9:00 nel campo **[!UICONTROL Start sending from]** e se selezioni Bruxelles, Copenaghen, Madrid, Parigi (GMT+1) nell’elenco a discesa **[!UICONTROL Time zone of the contact date]**, tutti i destinatari riceveranno il messaggio alle 9:00 ora di Parigi. Pertanto, un destinatario che si trova a Mosca (GMT+3) riceverà il messaggio alle 11:00 ora di Mosca.

  Se desideri confermare manualmente l’invio, seleziona l’opzione **[!UICONTROL Request confirmation before sending messages]**. Questa opzione è abilitata per impostazione predefinita.

  ![](assets/delivery_planning.png)

>[!IMPORTANT]
>
>Durante la duplicazione di una consegna, tutte le impostazioni di pianificazione vengono eliminate. A meno che non pianifichi una nuova data di contatto, la consegna duplicata viene inviata dopo la conferma dell’invio.

**Argomenti correlati**:

* [Ottimizzazione del tempo di invio](../../sending/using/optimizing-the-sending-time.md)
* [Invio di messaggi con il fuso orario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)
* [Calcolo della data di invio](../../sending/using/computing-the-sending-date.md)
