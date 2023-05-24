---
title: Riepilogo messaggi non recapitati
description: Con il rapporto predefinito Riepilogo delle e-mail non consegnate, scopri lo stato delle campagne inviate e gli errori che potrebbero aver riscontrato.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 03ea2f20-959c-497e-bd71-4e77132d712e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---

# Riepilogo messaggi non recapitati{#bounce-summary}

Questo rapporto descrive gli errori rigidi e morbidi riscontrati durante le consegne, nonché l’elaborazione automatica delle e-mail non consegnate (vedi [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)).

![](assets/campaign_reports_bounces.png)

Ogni tabella è rappresentata da numeri e grafici di riepilogo. Puoi modificare la modalità di visualizzazione dei dettagli nelle rispettive impostazioni di visualizzazione.

**Ripartizione flop 5** elenca le cinque consegne con il maggior numero di quarantene:

Il **Motivi di mancato recapito** La tabella contiene i dati disponibili per i tipi di errori che hanno causato mancati recapiti per ogni consegna:

* **[!UICONTROL User unknown]**: tipo di errore generato quando una consegna viene inviata a un indirizzo e-mail non valido.
* **[!UICONTROL Invalid domain]**: tipo di errore generato quando una consegna viene inviata a un indirizzo e-mail il cui dominio non è corretto o non esiste più.
* **[!UICONTROL Unreachable]**: tipo di errore riscontrato nella stringa di consegna del messaggio, ad esempio dominio temporaneamente non raggiungibile.
* **[!UICONTROL Account disabled]**: tipo di errore generato quando una consegna viene inviata a un indirizzo e-mail che non esiste più.
* **[!UICONTROL Mailbox full]**: tipo di errore generato quando la casella in entrata del destinatario è piena. Ci sono cinque tentativi di recapitare il messaggio prima che questo errore venga generato.
* **[!UICONTROL Not connected]**: tipo di errore generato quando il telefono cellulare del destinatario è spento o non è connesso a una rete al momento dell’invio del messaggio.

   >[!NOTE]
   >
   >Questo tipo di errore riguarda solo le consegne sui canali mobili.

* **[!UICONTROL Refused]**: tipo di errore generato quando un indirizzo viene rifiutato dal provider di servizi Internet (ISP). Ad esempio, quando una regola di sicurezza è stata applicata da un software antispam.

Il **Ripartizione del dominio** Nella tabella vengono visualizzati i problemi generali riscontrati durante le consegne in base al dominio del destinatario.
