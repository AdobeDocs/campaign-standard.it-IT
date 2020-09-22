---
title: Migliorare la tua reputazione con  Adobe Campaign Standard
description: Scopri come migliorare la tua reputazione con  Adobe Campaign Standard gestendo indirizzi e-mail e quarantena duplicati.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Crescita reputazione{#improving-reputation}

Per evitare di esaurire i destinatari, elimina gli indirizzi e-mail duplicati dalla destinazione. Questo passaggio protegge la tua reputazione di invio e assicura una buona gestione della quarantena.  Adobe Campaign offre gli strumenti necessari per attuare queste raccomandazioni ed evitare il rischio di essere aggiunti al elenco Bloccati dagli ISP.

Qui di seguito troverete informazioni sulla gestione dei duplicati e della quarantena.

## Duplicati {#duplicates}

La presenza di indirizzi e-mail duplicati può avere molteplici conseguenze:
* Lo stesso messaggio viene inviato più di una volta. Anche se Campaign esegue una procedura di deduplicazione per impostazione predefinita prima dell&#39;invio, non c&#39;è nulla che fermi l&#39;invio dello stesso messaggio da parte di azioni diverse con lo stesso contenuto quando una destinazione viene divisa.
* Richieste di annullamento sottoscrizione non rispettate. Se un destinatario annulla la sottoscrizione dopo aver ricevuto un messaggio, il profilo duplicato sarà comunque idoneo per i messaggi futuri.

Oltre a questa procedura di opt-in, questa situazione porterà probabilmente gli utenti a considerare i messaggi come spam e ad avviare una procedura di elenco Bloccati presso l&#39;ISP.

È necessario prestare particolare attenzione quando si eseguono operazioni sul database. Per evitare il più possibile duplicazioni, è necessario eseguire le azioni seguenti:
* **Le importazioni devono essere configurate meticolosamente.** Ciò è particolarmente importante nella scelta della chiave di riconciliazione.
* **Prestate attenzione quando modificate gli indirizzi e-mail.** Gli indirizzi e-mail modificati possono anche essere fonte di duplicati. In particolare, due indirizzi con domini diversi possono essere indirizzati alla stessa cassetta postale, ad esempio nel caso di una società che ha cambiato nome e che ha mantenuto il dominio precedente per un certo periodo di tempo: joe.doe@amce-co.com e joe.doe@acme-rebranded.com.
* **Prestate attenzione durante le importazioni automatiche.** Sia che si tratti di elenchi o di altre banche dati, essi sono elementi di cui tenere conto nella gestione dei profili. Cosa succede quando si elimina o si sposta un profilo in un&#39;altra partizione? Potrebbe essere ricreato nella partizione iniziale da un&#39;importazione automatica, ad esempio, quando viene inserito un ordine di acquisto.
* **I profili devono essere ordinati in diverse cartelle.**

Ci sono, comunque, casi in cui i duplicati tra le diverse partizioni sono normali. Ad esempio, quando si inviano dati per terze parti o entità aziendali diverse, è logico che la stessa persona sia un destinatario per diversi motivi. Tuttavia, raramente è normale trovare duplicati all&#39;interno della stessa partizione.

## Quarantena {#quarantines}

 Adobe Campaign gestisce un elenco di indirizzi in quarantena. I destinatari i cui indirizzi sono posti in quarantena sono esclusi per impostazione predefinita durante l&#39;analisi del recapito: non sono mirati.

La gestione della quarantena è dettagliata in [questa sezione](../../sending/using/understanding-quarantine-management.md).

Un indirizzo e-mail può essere messo in quarantena, ad esempio se la casella in entrata è piena o se l’indirizzo non esiste. In tutti i casi, la quarantena corrisponde alle regole specifiche presentate in [questa sezione](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).
