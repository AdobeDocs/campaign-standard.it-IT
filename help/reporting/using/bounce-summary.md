---
title: Riepilogo messaggi non recapitati
description: Con il rapporto di riepilogo non recapitato, scopri lo stato delle campagne inviate e gli eventuali errori riscontrati.
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

Questo rapporto descrive gli errori rigidi e morbidi riscontrati durante le consegne e l’elaborazione automatica dei mancati recapiti (vedi [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)).

![](assets/campaign_reports_bounces.png)

Ogni tabella è rappresentata da numeri di riepilogo e grafici. Puoi modificare il modo in cui i dettagli vengono visualizzati nelle rispettive impostazioni di visualizzazione.

**Partizione flop 5** elenca le cinque consegne con il numero più alto di quarantene:

La **Motivi di mancato recapito** La tabella contiene i dati disponibili per i tipi di errori che hanno causato mancati recapiti per ogni consegna:

* **[!UICONTROL User unknown]**: Tipo di errore generato quando una consegna viene inviata a un indirizzo e-mail non valido.
* **[!UICONTROL Invalid domain]**: Tipo di errore generato quando una consegna viene inviata a un indirizzo e-mail il cui dominio è errato o non esiste più.
* **[!UICONTROL Unreachable]**: Tipo di errore rilevato nella stringa di consegna del messaggio, ad esempio dominio temporaneamente non raggiungibile.
* **[!UICONTROL Account disabled]**: Il tipo di errore generato quando una consegna viene inviata a un indirizzo e-mail che non esiste più.
* **[!UICONTROL Mailbox full]**: Il tipo di errore generato quando la casella in entrata del destinatario è piena. Ci sono cinque tentativi per consegnare il messaggio prima che questo errore venga generato.
* **[!UICONTROL Not connected]**: Tipo di errore generato quando il telefono cellulare del destinatario è spento o non è connesso a una rete al momento dell&#39;invio del messaggio.

   >[!NOTE]
   >
   >Questo tipo di errore riguarda solo le consegne sui canali mobili.

* **[!UICONTROL Refused]**: Tipo di errore generato quando un indirizzo viene rifiutato dal provider di servizi Internet (ISP). Ad esempio, quando una regola di sicurezza è stata applicata dal software anti-Spam.

La **Partizione del dominio** nella tabella vengono visualizzati i problemi generali riscontrati durante le consegne in base al dominio destinatario.
