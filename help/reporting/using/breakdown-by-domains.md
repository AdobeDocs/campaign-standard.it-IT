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
TQID: 'https://experienceleague.adobe.com/25Ci4GFEJHIO3Ed2BTBF2qUmD4LKh3jwUC56K8JZgzA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '238'
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
