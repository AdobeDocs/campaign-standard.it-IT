---
solution: Campaign Standard
product: campaign
title: Raggruppamento per domini
description: Con il rapporto predefinito Suddivisione per domini , scopri i dati sulle prestazioni delle consegne a seconda del dominio di ciascun cliente.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
feature: Generazione rapporti
role: Leader
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%

---


# Raggruppamento per domini{#breakdown-by-domains}

Questo rapporto contiene i dati sulle prestazioni per ogni dominio rappresentato nel pubblico per una consegna e-mail. Se si tratta di un rapporto di campagna o di programma, i dati sulle prestazioni sono disponibili per più tipi di pubblico. Questi dati ti consentono di analizzare il comportamento di ciascun dominio in risposta a eventi specifici. Ad esempio, visualizzazione del collegamento, URL al elenco Bloccati, ecc.

![](assets/delivery_reports_6.png)

La tabella **Statistiche di trasmissione** contiene i dati disponibili per eventuali errori riscontrati in ciascun dominio, ad esempio:

* **Elaborato/inviato**: Numero di e-mail inviate.
* **Consegnato**: Il numero di e-mail consegnate.
* **Rimbalzi + errori**: Numero di messaggi che non è stato possibile recapitare.
* **Rimbalzo** rigido: Numero totale di errori permanenti, ad esempio un indirizzo e-mail errato.
* **Rimbalzo** morbido: Numero totale di errori temporanei, ad esempio una casella in entrata completa.

La seconda tabella, **Statistiche di tracciamento**, contiene i dati disponibili per la reattività del destinatario alla consegna, ad esempio:

* **Consegnato**: Il numero di e-mail consegnate
* **Apri**: Il numero di volte in cui un messaggio è stato aperto in una consegna.
* **Fai clic su**: Numero di volte in cui è stato fatto clic sul contenuto in una consegna.
* **Annulla sottoscrizione**: Il numero di clic sul collegamento di abbonamento.
* **Pagina** speculare: Il numero di clic sul collegamento della pagina speculare.
* **A elenco Bloccati**: Il numero di destinatari che hanno dichiarato un’e-mail come spam o posta indesiderata. [Ulteriori informazioni](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

