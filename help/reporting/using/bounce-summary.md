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
TQID: https://experienceleague.adobe.com/ggB-q-6kJyPF4GgJJzJGtsOqg6-7MeBhEfiGVY0M7sQ
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 282
ht-degree: 1%

---

# Riepilogo messaggi non recapitati{#bounce-summary}

Questo report descrive gli errori rigidi e morbidi riscontrati durante le consegne, nonché l&#39;elaborazione automatica dei mancati recapiti (vedi [Informazioni sugli errori di consegna](../../sending/using/understanding-delivery-failures.md)).

![](assets/campaign_reports_bounces.png)

Ogni tabella è rappresentata da numeri e grafici di riepilogo. Puoi modificare la modalità di visualizzazione dei dettagli nelle rispettive impostazioni di visualizzazione.

**Partizione flop 5** elenca le cinque consegne con il maggior numero di quarantene:

La tabella **Motivi di mancato recapito** contiene i dati disponibili per i tipi di errori che hanno causato mancati recapiti per ogni consegna:

* **[!UICONTROL User unknown]**: tipo di errore generato quando una consegna viene inviata a un indirizzo e-mail non valido.
* **[!UICONTROL Invalid domain]**: tipo di errore generato quando una consegna viene inviata a un indirizzo e-mail il cui dominio non è corretto o non esiste più.
* **[!UICONTROL Unreachable]**: tipo di errore rilevato nella stringa di consegna del messaggio, ad esempio dominio temporaneamente non raggiungibile.
* **[!UICONTROL Account disabled]**: tipo di errore generato quando una consegna viene inviata a un indirizzo e-mail che non esiste più.
* **[!UICONTROL Mailbox full]**: tipo di errore generato quando la casella in entrata del destinatario è piena. Ci sono cinque tentativi di recapitare il messaggio prima che questo errore venga generato.
* **[!UICONTROL Not connected]**: tipo di errore generato quando il telefono cellulare del destinatario è spento o non è connesso a una rete al momento dell&#39;invio del messaggio.

  >[!NOTE]
  >
  >Questo tipo di errore riguarda solo le consegne sui canali mobili.

* **[!UICONTROL Refused]**: tipo di errore generato quando un indirizzo viene rifiutato dal provider di servizi Internet (ISP). Ad esempio, quando una regola di sicurezza è stata applicata da un software antispam.

Nella tabella **Partizione di dominio** vengono visualizzati i problemi generali riscontrati durante le consegne in base al dominio del destinatario.
