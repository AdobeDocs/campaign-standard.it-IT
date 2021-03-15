---
solution: Campaign Standard
product: campaign
title: Migliorare la reputazione con Adobe Campaign Standard
description: Scopri come migliorare la tua reputazione con Adobe Campaign Standard gestendo indirizzi e-mail e quarantena duplicati.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Consegna
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 2%

---


# Crescita reputazione{#improving-reputation}

Per evitare di esaurire i destinatari, elimina gli indirizzi e-mail duplicati dal target. Questo passaggio protegge la reputazione dell’invio e assicura una buona gestione della quarantena. Adobe Campaign offre gli strumenti necessari per implementare queste raccomandazioni ed evitare il rischio di essere aggiunti al elenco Bloccati dagli ISP.

Di seguito trovi i dettagli sulla gestione della quarantena e della duplicazione.

## Duplicati {#duplicates}

Avere indirizzi e-mail duplicati può avere più conseguenze:
* Lo stesso messaggio viene inviato più di una volta. Anche se Campaign esegue una procedura di deduplicazione per impostazione predefinita prima dell’invio, non c’è nulla che impedisca l’invio dello stesso messaggio da parte di azioni diverse con lo stesso contenuto quando una destinazione viene divisa.
* Richieste di annullamento dell’abbonamento non rispettate. Se un destinatario annulla l’abbonamento dopo aver ricevuto un messaggio, il suo profilo duplicato sarà comunque idoneo per i messaggi futuri.

Oltre a questa fase secondaria delle procedure di consenso, questa situazione porterà probabilmente gli utenti a considerare i messaggi come spam e ad attivare una procedura di elenco Bloccati presso l&#39;ISP.

È necessario prestare particolare attenzione quando si eseguono operazioni sul database. Per evitare duplicati il più possibile, è necessario eseguire le azioni seguenti:
* **Le importazioni devono essere configurate meticolosamente.** Ciò è particolarmente importante quando si sceglie la chiave di riconciliazione.
* **Presta attenzione quando modifichi gli indirizzi e-mail.** Gli indirizzi e-mail modificati possono anche essere una fonte di duplicati. In particolare, due indirizzi con domini diversi possono essere indirizzati alla stessa cassetta postale, ad esempio nel caso di una società che ha cambiato nome e che ha mantenuto il dominio precedente per un certo periodo di tempo: joe.doe@amce-co.com e joe.doe@acme-rebranded.com.
* **Presta attenzione durante le importazioni automatiche.** Sia che si tratti di elenchi o di altri database, sono elementi da prendere in considerazione nella gestione dei profili. Cosa succede quando si elimina o si sposta un profilo in un&#39;altra partizione? Potrebbe essere ricreato nella partizione iniziale da un&#39;importazione automatica, ad esempio, quando viene inserito un ordine di acquisto.
* **I profili devono essere ordinati in cartelle diverse.**

Ci sono, comunque, casi in cui i duplicati tra le diverse partizioni sono normali. Ad esempio, quando invii a terzi o a entità aziendali diverse, è logico che la stessa persona sia un destinatario per motivi diversi. Tuttavia, raramente è normale trovare duplicati all’interno della stessa partizione.

## Quarantena {#quarantines}

 Adobe Campaign gestisce un elenco di indirizzi in quarantena. I destinatari i cui indirizzi sono messi in quarantena sono esclusi per impostazione predefinita durante l’analisi della consegna: non sono mirati.

La gestione della quarantena è descritta in [questa sezione](../../sending/using/understanding-quarantine-management.md).

È possibile mettere in quarantena un indirizzo e-mail, ad esempio se la casella in entrata è piena o se l’indirizzo non esiste. In tutti i casi, la quarantena corrisponde alle regole specifiche presentate in [questa sezione](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).
