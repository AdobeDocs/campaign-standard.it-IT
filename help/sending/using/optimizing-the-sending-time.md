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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 100%

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

  Ad esempio, se il tuo fuso orario è GMT+1 e immetti le 9.00 nel campo **[!UICONTROL Start sending from]**, un destinatario che si trova nel fuso orario GMT+3 riceverà il messaggio alle 11.00 ora locale per quel destinatario.

* **[!UICONTROL Send at the recipient's time zone]**: tutti i destinatari riceveranno il messaggio tenendo conto del loro fuso orario.

  Ad esempio, se immetti 9.00 nel campo **[!UICONTROL Start sending from]**, un destinatario che si trova nel fuso orario GMT+3 riceverà il messaggio alle 9.00 ora locale per quel destinatario.

  Consulta [Invio di messaggi con il fuso orario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**: ciascun destinatario riceverà il messaggio alla data e all’orario configurati dalla formula specificata.

  Consulta [Calcolo della data di invio](../../sending/using/computing-the-sending-date.md).
