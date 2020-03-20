---
title: Riepilogo messaggi non recapitati
description: Il rapporto di riepilogo Bounce fornisce informazioni sullo stato delle campagne inviate e sugli eventuali errori riscontrati.
page-status-flag: never-activated
uuid: 90087311-4236-4df9-ae7d-4a15c00c70ab
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: 5ae561b4-03cf-4541-87ff-47f1027d53b8
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bee7ea0f1728da2a96c1f225b91b13a7903be660

---


# Riepilogo messaggi non recapitati{#bounce-summary}

Questo rapporto descrive gli errori rigidi e morbidi riscontrati durante le consegne e l&#39;elaborazione automatica dei rimbalzi.

![](assets/campaign_reports_bounces.png)

Ogni tabella è rappresentata da numeri e grafici di riepilogo. Puoi modificare la modalità di visualizzazione dei dettagli nelle rispettive impostazioni di visualizzazione.

**La partizione** flop 5 elenca le cinque consegne con il numero più elevato di quarantena:

La tabella Motivi **** rimbalzi contiene i dati disponibili per i tipi di errori che hanno causato dei rimbalzi per ogni consegna:

* **[!UICONTROL User unknown]**: Il tipo di errore generato quando una consegna viene inviata a un indirizzo e-mail non valido.
* **[!UICONTROL Invalid domain]**: Tipo di errore generato quando un recapito viene inviato a un indirizzo e-mail il cui dominio è errato o non esiste più.
* **[!UICONTROL Unreachable]**: Tipo di errore rilevato nella stringa di consegna del messaggio, ad esempio dominio temporaneamente irraggiungibile.
* **[!UICONTROL Account disabled]**: Il tipo di errore generato quando una consegna viene inviata a un indirizzo e-mail che non esiste più.
* **[!UICONTROL Mailbox full]**: Tipo di errore generato quando la inbox del destinatario è piena. Prima di generare l&#39;errore, è possibile inviare il messaggio in cinque tentativi.
* **[!UICONTROL Not connected]**: Tipo di errore generato quando il telefono cellulare del destinatario è spento o non è connesso a una rete al momento dell&#39;invio del messaggio.

   >[!NOTE]
   >
   >Questo tipo di errore riguarda solo le consegne sui canali mobili.

* **[!UICONTROL Refused]**: Tipo di errore generato quando un indirizzo viene rifiutato dal provider di servizi Internet (ISP). Ad esempio, quando una regola di sicurezza è stata applicata dal software anti-Spam.

Nella tabella relativa alla partizione del **dominio** sono visualizzati i problemi generali riscontrati durante le consegne in base al dominio destinatario.
