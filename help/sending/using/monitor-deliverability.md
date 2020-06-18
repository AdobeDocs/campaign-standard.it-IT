---
title: Monitoraggio dell'operabilità nel  Adobe Campaign Standard
description: Utilizzate gli strumenti offerti  Adobe Campaign Standard per monitorare l'affidabilità della piattaforma.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c89973e2c733d9c0b1c4434e77ef51103ccde0fa
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 0%

---


# Monitoraggio del recapito messaggi{#monitor-deliverability}

Qui di seguito troverete dettagli sulla **[!UICONTROL Delivery throughput]** relazione e sui diversi strumenti di monitoraggio offerti dal Adobe Campaign . Seguono alcune linee guida aggiuntive sul monitoraggio della recapito:
* Controllate regolarmente la velocità di consegna per l&#39;intera piattaforma per verificare se è coerente con la configurazione originale.
* Verificate che i tentativi siano impostati correttamente (30 minuti per il periodo di tentativi e più di 20 tentativi) nei modelli di consegna.
* Verificare regolarmente che la casella di posta non riuscita sia accessibile e che l&#39;account non stia per scadere.
* Controllate ogni throughput di distribuzione per assicurarvi che sia coerente con la validità del contenuto di distribuzione (ad es. Le vendite flash devono essere consegnate in minuti, non in giorni).
* Quando si utilizzano le onde, verificare che ogni onda disponga di tempo sufficiente per terminare prima che venga attivata la successiva.
* Verificate che il numero di errori e di nuove quarantena siano coerenti con altre consegne.
* Consultate attentamente i registri di consegna per verificare il tipo di errori evidenziati (elenchi di blocchi, problemi DNS, regole anti-spam, ecc.).

## Velocità effettiva di consegna {#delivery-throughput}

Questo rapporto contiene informazioni sulla velocità di consegna dell&#39;intera piattaforma per un determinato periodo, per misurare la velocità di consegna dei messaggi.

Per ulteriori informazioni, consulta [Distribuzione effettiva](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

Potete configurare i valori visualizzati modificando la scala cronologica.

Sono disponibili altri rapporti, ad esempio **[!UICONTROL Delivery summary]** o **[!UICONTROL Non-deliverables and bounces]**. Per ulteriori informazioni, consulta Report [](../../reporting/using/about-dynamic-reports.md)dinamici.

## Monitoraggio delle consegne {#monitoring-deliveries}

Il dashboard dei messaggi consente di accedere ai registri di distribuzione: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** e **[!UICONTROL Tracked URLs]**. Mostra i dettagli dell’invio, quale destinazione è stata esclusa e perché, nonché le informazioni di tracciamento come aperture e clic.

Per ulteriori informazioni, consulta [Monitoraggio della distribuzione](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## Ricezione degli avvisi {#receiving-alerts}

La **[!UICONTROL Delivery alerting]** funzione è un sistema di gestione degli avvisi che consente a un gruppo di utenti di ricevere automaticamente le notifiche contenenti informazioni sull’esecuzione delle loro consegne.

Per ulteriori informazioni, vedere [Ricevere avvisi in caso di errori](../../sending/using/receiving-alerts-when-failures-happen.md).

## Spam segnale {#signal-spam}

Signal Spam è un servizio francese che offre un report anonimo sul loop di feedback per gli ISP francesi (Orange, SFR).

Questo servizio consente di seguire la reputazione degli ISP francesi e di monitorare l&#39;evoluzione dell&#39;attività dei clienti.

Il segnale Spam fornisce inoltre reclami diretti che gli utenti finali accedono attraverso un&#39;interfaccia dedicata. Tali reclami vengono quindi messi in quarantena dal database degli indirizzi e-mail.

## 250 ok {#solution-250ok}

250ok è una soluzione di monitoraggio che fornisce elenchi di blocchi IP e di dominio, nonché indicatori di reputazione.

Le informazioni fornite sono in tempo reale, il che consente un&#39;assistenza proattiva. 250ok una soluzione complementare agli strumenti interni di recapito Adobe.
