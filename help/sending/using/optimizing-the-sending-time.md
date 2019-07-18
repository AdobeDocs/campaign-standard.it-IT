---
title: Ottimizzazione dell'ora di invio
seo-title: Ottimizzazione dell'ora di invio
description: Ottimizzazione dell'ora di invio
seo-description: Scopri come impostare l'ora di invio e migliorare la velocità di apertura dei messaggi.
page-status-flag: never-activated
uuid: c 2 c 13934-9819-4 e 18-b 5 c 7-60915 c 907 f 37
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: invio
content-type: riferimento
topic-tags: sheduling-messages
discoiquuid: 609355 f 6-9003-41 b 9-9981-ea 787419 fbf 5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Optimizing the sending time{#optimizing-the-sending-time}

Per migliorare la velocità di apertura dei messaggi, puoi definire manualmente un orario di invio per destinatario. Ogni profilo riceverà il messaggio nella data e all'ora specificate, se possibile.

La definizione di un'ora di invio può essere effettuata a livello di consegna o mediante un flusso di lavoro.

Per le e-mail, a seconda del carico del server e della quantità di tentativi, si consiglia di inviare il messaggio in base alla data e all'ora pianificate per ciascun destinatario.

* I tentativi dipendono dal provider Internet e dalla vostra reputazione. Il messaggio potrebbe non essere accettato al primo tentativo e possono essere eseguiti diversi tentativi. See [List of email channel parameters](../../administration/using/configuring-email-channel.md).
* I ritardi di ricezione dell'e-mail possono verificarsi a causa di una larghezza di banda insufficiente.

You can view when the message was sent to each recipient in the [sending logs](../../sending/using/monitoring-a-delivery.md#sending-logs).

Sono disponibili diverse opzioni:

* **[!UICONTROL No optimization]**: I messaggi vengono inviati a tempo dell'utente.

   For example, if your time zone is GMT+1 and if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field, a recipient located in the GMT+3 time zone will receive the message at 11:00 AM local time for that recipient.

* **[!UICONTROL Send at the recipient's time zone]**: Tutti i destinatari riceveranno il messaggio con il fuso orario considerato.

   For example, if you enter 9:00 AM in the **[!UICONTROL Start sending from]** field, a recipient located in the GMT+3 time zone will receive the message at 9:00 AM local time for that recipient.

   See [Sending messages at the recipient's time zone](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).

* **[!UICONTROL Send at a custom date defined by a formula]**: Ogni destinatario riceve il messaggio in base alla data e all'ora configurate dalla formula specificata.

   See [Computing the sending date](../../sending/using/computing-the-sending-date.md).

