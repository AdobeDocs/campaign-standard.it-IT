---
title: Ottimizzazione del tempo di invio
description: Scopri come impostare il tempo di invio e migliorare il tasso di apertura dei messaggi.
page-status-flag: mai attivato
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: invio
content-type: reference
topic-tags: programmazione dei messaggi
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Ottimizzazione del tempo di invio{#optimizing-the-sending-time}

Per migliorare la frequenza di apertura dei messaggi, puoi definire manualmente un orario di invio per destinatario. Ogni profilo riceve il messaggio alla data e all'ora specificate, quando possibile.

È possibile definire un orario di invio a livello di consegna o utilizzando un flusso di lavoro.

Per le e-mail, a seconda del carico del server e della quantità di tentativi, è consigliabile inviare il messaggio in base alla data e all'ora pianificate per ciascun destinatario.

* I tentativi dipendono dal provider Internet e dalla tua reputazione. Il messaggio potrebbe non essere accettato al primo tentativo e potrebbero essere eseguiti diversi tentativi. Consultate [Elenco dei parametri](../../administration/using/configuring-email-channel.md)dei canali e-mail.
* I ritardi nella ricezione dell’e-mail possono verificarsi a causa di larghezza di banda insufficiente.

Puoi vedere quando il messaggio è stato inviato a ogni destinatario nei registri [di](../../sending/using/monitoring-a-delivery.md#sending-logs)invio.

Sono disponibili diverse opzioni:

* **[!UICONTROL No optimization]**: I messaggi vengono inviati al momento dell'utente.

   Ad esempio, se il tuo fuso orario è GMT+1 e immetti le 9:00 AM nel **[!UICONTROL Start sending from]** campo, un destinatario che si trova nel fuso orario GMT+3 riceverà il messaggio alle 11:00 ora locale per quel destinatario.

* **[!UICONTROL Send at the recipient's time zone]**: Tutti i destinatari riceveranno il messaggio tenendo conto del loro fuso orario.

   Ad esempio, se immetti 9:00 AM nel **[!UICONTROL Start sending from]** campo, un destinatario che si trova nel fuso orario GMT+3 riceverà il messaggio alle 9:00 ora locale per quel destinatario.

   See [Sending messages at the recipient's time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**: Ogni destinatario riceve il messaggio alla data e all'ora configurate dalla formula specificata.

   See [Computing the sending date](../../sending/using/computing-the-sending-date.md).

