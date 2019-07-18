---
title: Suddivisione per domini
seo-title: Suddivisione per domini
description: Suddivisione per domini
seo-description: Con la suddivisione in base al dominio out-of-the-box, scopri i dati sulle prestazioni delle tue consegne a seconda di ciascun dominio del cliente.
page-status-flag: never-activated
uuid: 75 a 64 c 81-325 b -422 f-b 6 ef-deb 06 eec 7 f 7 b
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: reporting
content-type: riferimento
topic-tags: list-of-reports
discoiquuid: 2 ce 174 f 9-5 d 7 d -48 b 9-9235-6 bf 3 e 238 ff 37
context-tags: Deliverydomainbreakdownreport, main; Campaigndomainbreakdownreport, main; Programdomainbreakdownreport, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Breakdown by domains{#breakdown-by-domains}

Questo rapporto contiene i dati sulle prestazioni per ogni dominio rappresentato nell'audience per un'e-mail di consegna. Se si tratta di una campagna o di un rapporto di programma, i dati sulle prestazioni sono disponibili per più audience. Questi dati consentono di analizzare il comportamento di ogni dominio in risposta a eventi specifici. Ad esempio, visualizzazione dei collegamenti, blacklist URL ecc.

![](assets/delivery_reports_6.png)

The table **Broadcast statistics** contains the available data for possible errors encountered with each domain, such as:

* **Elaborato/inviato**: Numero di messaggi e-mail inviati.
* **Consegnato**: Numero di e-mail distribuite.
* **Bounce + Errors**: Numero di messaggi che non è stato possibile distribuire.
* **Rimbalzi rigidi**: Il numero totale di errori permanenti, ad esempio un indirizzo e-mail errato.
* **Rimbalza leggero**: Il numero totale di errori temporanei, ad esempio una casella completa.

The second table, **Tracking statistics**, contains the available data for recipient reactivity to delivery, such as:

* **Consegnato**: Numero di messaggi e-mail consegnati
* **Apri**: Numero di volte in cui un messaggio è stato aperto in una consegna.
* **Fate clic** su: Il numero di volte in cui è stato fatto clic sul contenuto in una consegna.
* **Annullato**: Numero di clic sul collegamento di iscrizione.
* **Pagina speculare**: Numero di clic sul collegamento della pagina speculare.
* **In lista nera**: Numero di destinatari che hanno dichiarato un messaggio e-mail come spam o incrinatura (consultate [Gestione della blacklist in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).

