---
title: Raggruppamento per domini
description: Con il rapporto predefinito Suddivisione per domini , scopri i dati sulle prestazioni delle consegne a seconda del dominio di ciascun cliente.
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

Questo rapporto contiene i dati sulle prestazioni per ogni dominio rappresentato nel pubblico per una consegna e-mail. Se si tratta di un rapporto di campagna o di programma, i dati sulle prestazioni sono disponibili per più tipi di pubblico. Questi dati ti consentono di analizzare il comportamento di ciascun dominio in risposta a eventi specifici. Ad esempio, visualizzazione del collegamento, URL al elenco Bloccati, ecc.

![](assets/delivery_reports_6.png)

La tabella **Statistiche broadcast** contiene i dati disponibili per eventuali errori riscontrati in ciascun dominio, ad esempio:

* **Elaborato/inviato**: Numero di e-mail inviate.
* **Consegnato**: Il numero di e-mail consegnate.
* **Rimbalzi + errori**: Numero di messaggi che non è stato possibile recapitare.
* **Rimbalzo duro**: Numero totale di errori permanenti, ad esempio un indirizzo e-mail errato.
* **Rimbalzo morbido**: Numero totale di errori temporanei, ad esempio una casella in entrata completa.

la seconda tabella, **Tracking delle statistiche**, contiene i dati disponibili per la reattività del destinatario alla consegna, ad esempio:

* **Consegnato**: Il numero di e-mail consegnate
* **Apri**: Il numero di volte in cui un messaggio è stato aperto in una consegna.
* **Fai clic su**: Numero di volte in cui è stato fatto clic sul contenuto in una consegna.
* **Annulla sottoscrizione**: Il numero di clic sul collegamento di abbonamento.
* **Pagina speculare**: Il numero di clic sul collegamento della pagina speculare.
* **A elenco Bloccati**: Il numero di destinatari che hanno dichiarato un’e-mail come spam o posta indesiderata. [Ulteriori informazioni](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
