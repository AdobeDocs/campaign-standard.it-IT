---
title: Ottimizzazione del tempo di invio
description: Scopri come impostare il tempo di invio e migliorare il tasso di apertura dei messaggi.
audience: sending
content-type: reference
topic-tags: sheduling-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: f35b46c6-de88-4efa-b3b7-8bb9024e40a8
TQID: https://experienceleague.adobe.com/FjL5t1ohvrgDdqLiCr03z1Nbq6IukIBysKkmXJ7561c
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 279
ht-degree: 74%

---

# Ottimizzazione del tempo di invio{#optimizing-the-sending-time}

Per migliorare il tasso di apertura dei messaggi, puoi definire manualmente un orario di invio per destinatario. Laddove possibile, ogni profilo riceverà il messaggio alla data e all’orario specificati.

La definizione di un orario di invio può essere effettuata a livello di consegna o utilizzando un flusso di lavoro.

Per le e-mail, a seconda del carico del server e della quantità di tentativi, è consigliabile inviare il messaggio in base alla data e all’orario pianificati per ciascun destinatario.

* I tentativi dipendono dal fornitore Internet e dalla tua reputazione. Il messaggio potrebbe non essere accettato al primo tentativo e potrebbero essere eseguiti diversi tentativi. Consulta [Elenco dei parametri del canale e-mail](../../administration/using/configuring-email-channel.md).
* Possono verificarsi ritardi nella ricezione dell’e-mail a causa di una larghezza di banda insufficiente.

Puoi visualizzare quando il messaggio è stato inviato a ciascun destinatario nei [registri di invio](../../sending/using/monitoring-a-delivery.md#sending-logs).

Sono disponibili diverse opzioni:

* **[!UICONTROL No optimization]**: i messaggi vengono inviati in base all’orario dell’utente.

  Ad esempio, se il tuo fuso orario è GMT+1 e immetti le 9:00 nel campo **[!UICONTROL Start sending from]**, un destinatario che si trova nel fuso orario GMT+3 riceverà il messaggio alle 11:00 ora locale per quel destinatario.

* **[!UICONTROL Send at the recipient's time zone]**: tutti i destinatari riceveranno il messaggio tenendo conto del loro fuso orario.

  Ad esempio, se immetti 9:00 AM nel campo **[!UICONTROL Start sending from]**, un destinatario che si trova nel fuso orario GMT+3 riceverà il messaggio alle 9:00 AM ora locale per quel destinatario.

  Consulta [Invio di messaggi con il fuso orario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**: ciascun destinatario riceverà il messaggio alla data e all’orario configurati dalla formula specificata.

  Consulta [Calcolo della data di invio](../../sending/using/computing-the-sending-date.md).
