---
title: Monitoraggio del recapito messaggi in Adobe Campaign Standard
description: Utilizza gli strumenti offerti da Adobe Campaign Standard per monitorare il recapito messaggi della piattaforma.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 683341fb-fef5-4aa1-8606-9526d9ae6290
source-git-commit: 449187bba167f9ce00e644d44a124b36030ba001
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 9%

---

# Monitoraggio del recapito messaggi{#monitor-deliverability}

Di seguito sono riportati i dettagli sul report **[!UICONTROL Delivery throughput]** e sui diversi strumenti di monitoraggio offerti da Adobe Campaign. Di seguito sono riportate alcune linee guida aggiuntive sul monitoraggio della consegna dei messaggi:

* Verifica regolarmente la velocità effettiva di consegna per l’intera piattaforma per verificarne la coerenza con la configurazione originale.
* Verifica che i nuovi tentativi siano configurati correttamente nei modelli di consegna (30 minuti per il periodo di esecuzione dei nuovi tentativi e più di 20 tentativi).
* Verifica regolarmente che la cassetta postale di mancato recapito sia accessibile e che l’account non stia per scadere.
* Controlla ogni velocità effettiva di consegna per assicurarti che sia coerente con la validità del contenuto della consegna (ad esempio, le &quot;vendite flash&quot; devono essere consegnate in minuti, non in giorni).
* Verifica che il numero di errori e le nuove quarantene siano coerenti con le altre consegne.
* Consulta attentamente i registri di consegna in dettaglio per verificare il tipo di errori evidenziati (inserisce nell&#39;elenco Bloccati di, problemi DNS, regole anti-spam, ecc.).

## Velocità di consegna {#delivery-throughput}

Questo rapporto contiene informazioni sulla velocità effettiva di consegna dell’intera piattaforma per un determinato periodo di tempo, al fine di misurare la velocità a cui vengono consegnati i messaggi.

Per ulteriori informazioni, consulta [Velocità effettiva di consegna](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

È possibile configurare i valori visualizzati modificando la scala cronologica.

Sono disponibili altri report, ad esempio **[!UICONTROL Delivery summary]** o **[!UICONTROL Non-deliverables and bounces]**. Per ulteriori informazioni, consulta [Rapporti dinamici](../../reporting/using/about-dynamic-reports.md).

## Monitoraggio delle consegne {#monitoring-deliveries}

Il dashboard dei messaggi consente di accedere ai registri di consegna: **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** e **[!UICONTROL Tracked URLs]**. Mostrano i dettagli dell’invio, quale target è stato escluso e perché, nonché le informazioni di tracciamento come aperture e clic.

Per ulteriori informazioni, consulta [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## Ricezione degli avvisi {#receiving-alerts}

La funzionalità **[!UICONTROL Delivery alerting]** è un sistema di gestione degli avvisi che consente a un gruppo di utenti di ricevere automaticamente notifiche contenenti informazioni sull&#39;esecuzione delle consegne.

Per ulteriori informazioni, consulta [Ricezione degli avvisi in caso di errori](../../sending/using/receiving-alerts-when-failures-happen.md).

<!--## External tools (#external-tools)

### Signal Spam {#signal-spam}

Signal Spam is a French service which offers anonymized feedback loop reporting for French ISPs (Orange, SFR).

This service allows you to follow the reputation of the French ISPs and track customers' activity evolution.

Signal Spam also provides direct complaints that end users log through a dedicated interface. Those complaints are then quarantined from the email address database.

### 250ok {#solution-250ok}

250ok is a monitoring solution which provides IP and domain denylists, as well as reputation indicators.

The information provided is real-time, which allows for a pro-active assistance. 250ok a complementary solution to the Adobe deliverability internal tools.-->
