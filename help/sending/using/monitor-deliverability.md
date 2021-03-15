---
solution: Campaign Standard
product: campaign
title: Monitoraggio del recapito messaggi in Adobe Campaign Standard
description: Utilizza gli strumenti offerti da Adobe Campaign Standard per monitorare il recapito messaggi della piattaforma.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Consegna
role: Professionista
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 7%

---


# Monitoraggio della consegna messaggi{#monitor-deliverability}

Di seguito sono riportati i dettagli del rapporto **[!UICONTROL Delivery throughput]** e i diversi strumenti di monitoraggio offerti da Adobe Campaign. Di seguito sono riportate alcune linee guida aggiuntive sul monitoraggio delle consegne:
* Controlla regolarmente il throughput di consegna per l’intera piattaforma per verificare se è coerente con la configurazione originale.
* Verifica che i nuovi tentativi siano configurati correttamente (30 minuti per il periodo dei nuovi tentativi e più di 20 tentativi) nei modelli di consegna.
* Verifica regolarmente che la cassetta postale non recapitata sia accessibile e che l&#39;account non stia per scadere.
* Controlla ogni throughput di consegna per assicurarti che sia coerente con la validità del contenuto di consegna (ad es. Le vendite flash devono essere consegnate in minuti, non in giorni).
* Quando utilizzi le onde, verifica che ogni onda abbia tempo sufficiente per terminare prima che venga attivata quella successiva.
* Verifica che il numero di errori e nuove quarantene siano coerenti con altre consegne.
* Consulta attentamente i registri di consegna per verificare il tipo di errori evidenziati (elenco Bloccati, problemi DNS, regole anti-spam, ecc.).

## Velocità effettiva di consegna {#delivery-throughput}

Questo rapporto contiene informazioni sulla velocità effettiva di consegna dell’intera piattaforma per un determinato periodo, al fine di misurare la velocità con cui vengono inviati i messaggi.

Per ulteriori informazioni, consulta [Velocità effettiva di consegna](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

Puoi configurare i valori visualizzati modificando la scala cronologica.

Sono disponibili altri rapporti, ad esempio **[!UICONTROL Delivery summary]** o **[!UICONTROL Non-deliverables and bounces]**. Per ulteriori informazioni, consulta [Rapporti dinamici](../../reporting/using/about-dynamic-reports.md).

## Monitoraggio delle consegne {#monitoring-deliveries}

Il dashboard dei messaggi ti consente di accedere ai registri di consegna: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** e **[!UICONTROL Tracked URLs]**. Mostrano i dettagli dell’invio, quale target è stato escluso e perché, nonché le informazioni di tracciamento come aperture e clic.

Per ulteriori informazioni, consulta [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## Ricezione degli avvisi {#receiving-alerts}

La funzione **[!UICONTROL Delivery alerting]** è un sistema di gestione degli avvisi che consente a un gruppo di utenti di ricevere automaticamente le notifiche contenenti informazioni sull’esecuzione delle consegne.

Per ulteriori informazioni, consulta [Ricezione degli avvisi in caso di errori](../../sending/using/receiving-alerts-when-failures-happen.md).

## Spam segnale {#signal-spam}

Signal Spam è un servizio francese che offre rapporti di retroazione anonimi per gli ISP francesi (Orange, SFR).

Questo servizio ti permette di seguire la reputazione degli ISP francesi e tenere traccia dell&#39;evoluzione dell&#39;attività dei clienti.

Segnale Spam fornisce anche reclami diretti che gli utenti finali effettuano il log attraverso un&#39;interfaccia dedicata. Tali reclami vengono quindi messi in quarantena dal database degli indirizzi e-mail.

## 250ok {#solution-250ok}

250ok è una soluzione di monitoraggio che fornisce  IP e di dominio, nonché indicatori di reputazione.

Le informazioni fornite sono in tempo reale, il che consente un&#39;assistenza proattiva. 250ok una soluzione complementare agli strumenti interni di consegna Adobe.
