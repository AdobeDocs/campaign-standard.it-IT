---
title: Riepilogo rimbalzo
seo-title: Riepilogo rimbalzo
description: Riepilogo rimbalzo
seo-description: Con il riepilogo Riepilogo didascalia, scopri lo stato delle campagne e degli errori inviati.
page-status-flag: never-activated
uuid: 90087311-4236-4 df 9-ae 7 d -4 a 15 c 00 c 70 ab
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: reporting
content-type: riferimento
topic-tags: list-of-reports
discoiquuid: 5 ae 561 b 4-03 cf -4541-87 ff -47 f 1027 d 53 b 8
context-tags: Bouncereport, main; Campaigncirculationreport, main; Programcirculationreport, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Bounce summary{#bounce-summary}

Questo rapporto illustra gli errori complessivi e netti riscontrati durante le consegne nonché l'elaborazione automatica degli sbalzi.

![](assets/campaign_reports_bounces.png)

Ogni tabella è rappresentata da numeri di riepilogo e diagrammi. Puoi modificare il modo in cui i dettagli vengono visualizzati nelle rispettive impostazioni di visualizzazione.

**La ripartizione** flop 5 elenca le cinque consegne con il numero massimo di conversioni:

The **Bounce reasons** table contains the available data for the types of errors that caused bounces for each delivery:

* **[!UICONTROL User unknown]**: Il tipo di errore generato quando viene inviata una consegna a un indirizzo e-mail non valido.
* **[!UICONTROL Invalid domain]**: Il tipo di errore generato quando viene inviata una consegna a un indirizzo e-mail il cui dominio è errato o non esiste più.
* **[!UICONTROL Unreachable]**: Il tipo di errore riscontrato nella stringa di consegna messaggio. Ad esempio, l'incidente SMTP, il dominio temporaneamente non raggiungibile, ecc.
* **[!UICONTROL Account disabled]**: Il tipo di errore generato quando viene inviata una consegna a un indirizzo e-mail che non esiste più.
* **[!UICONTROL Mailbox full]**: Il tipo di errore generato quando la inbox del destinatario è piena. Esistono cinque tentativi di consegnare il messaggio prima che questo errore venga generato.
* **[!UICONTROL Not connected]**: Il tipo di errore generato quando il cellulare del destinatario è disattivato o non è connesso a una rete al momento dell'invio del messaggio.

   >[!NOTE]
   >
   >Questo tipo di errore riguarda solo le consegne sui canali mobili.

* **[!UICONTROL Refused]**: Il tipo di errore generato quando un indirizzo viene rifiutato dal provider di servizi Internet (ISP). Ad esempio, quando una regola di sicurezza è stata applicata dal software antispam.

The **Domain repartition** table displays the overall problems encountered during the deliveries according to the recipient domain.
