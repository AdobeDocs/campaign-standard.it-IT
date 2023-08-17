---
title: Raggruppamento per domini
description: Con il rapporto predefinito Raggruppamento per domini, scopri i dati sulle prestazioni delle consegne in base a ciascun dominio del cliente.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 513d74ae-10c0-4d41-a7d1-8ed655e1a2d1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# Raggruppamento per domini{#breakdown-by-domains}

Questo rapporto contiene i dati sulle prestazioni per ogni dominio rappresentato nel pubblico per una consegna e-mail. Se si tratta di un rapporto di una campagna o di un programma, i dati sulle prestazioni sono disponibili per più tipi di pubblico. Questi dati ti consentono di analizzare il comportamento di ciascun dominio in reazione a eventi specifici. Ad esempio, visualizzazione di collegamenti, URL sul inserisco nell&#39;elenco Bloccati del collegamento, ecc.

![](assets/delivery_reports_6.png)

Tabella **Statistiche di trasmissione** contiene i dati disponibili per i possibili errori riscontrati con ciascun dominio, ad esempio:

* **Elaborato/inviato**: numero di e-mail inviate.
* **Consegnato**: numero di e-mail consegnate.
* **Mancati recapiti + errori**: numero di messaggi che non è stato possibile recapitare.
* **Mancato recapito permanente**: numero totale di errori permanenti, ad esempio un indirizzo e-mail errato.
* **Mancato recapito non permanente**: numero totale di errori temporanei, ad esempio una casella in entrata completa.

La seconda tabella, **Statistiche di tracciamento**, contiene i dati disponibili per la reattività del destinatario alla consegna, ad esempio:

* **Consegnato**: numero di e-mail consegnate
* **Apri**: numero di volte in cui un messaggio è stato aperto in una consegna.
* **Clic**: il numero di volte in cui è stato fatto clic sul contenuto in una consegna.
* **Annullamento iscrizione**: numero di clic sul collegamento di abbonamento.
* **Pagina mirror**: numero di clic sul collegamento della pagina speculare.
* **Inserire nell&#39;elenco Bloccati Il**: numero di destinatari che hanno dichiarato un’e-mail come spam o posta indesiderata. [Ulteriori informazioni](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
