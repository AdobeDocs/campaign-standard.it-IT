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

Questo rapporto contiene i dati sulle prestazioni per ogni dominio rappresentato nel pubblico per una consegna e-mail. Se si tratta di un rapporto di una campagna o di un programma, i dati sulle prestazioni sono disponibili per più tipi di pubblico. Questi dati ti consentono di analizzare il comportamento di ciascun dominio in reazione a eventi specifici. Ad esempio, visualizzazione di collegamenti, URL nella inserisce nell&#39;elenco Bloccati di accesso a un sito web (informazioni in lingua inglese), ecc.

![](assets/delivery_reports_6.png)

La tabella **Statistiche trasmissione** contiene i dati disponibili per i possibili errori riscontrati in ciascun dominio, ad esempio:

* **Elaborati/inviati**: numero di messaggi di posta elettronica inviati.
* **Recapitato**: numero di e-mail consegnate.
* **Messaggi non recapitati + Errori**: numero di messaggi che non è stato possibile recapitare.
* **Notifica di mancato recapito**: numero totale di errori permanenti, ad esempio un indirizzo e-mail errato.
* **Mancato recapito non permanente**: numero totale di errori temporanei, ad esempio una casella in entrata completa.

La seconda tabella, **Statistiche di tracciamento**, contiene i dati disponibili per la reattività del destinatario alla consegna, ad esempio:

* **Recapitato**: numero di e-mail consegnate
* **Apri**: il numero di volte in cui un messaggio è stato aperto in una consegna.
* **Clic**: il numero di volte in cui è stato fatto clic sul contenuto in una consegna.
* **Annullamento dell&#39;abbonamento**: numero di clic sul collegamento dell&#39;abbonamento.
* **Pagina mirror**: numero di clic sul collegamento della pagina mirror.
* **In caso di inserita nell&#39;elenco Bloccati di un&#39;e-mail in corso**: numero di destinatari che hanno dichiarato un&#39;e-mail come posta indesiderata o indesiderata. [Ulteriori informazioni](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
