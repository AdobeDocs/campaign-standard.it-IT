---
solution: Campaign Standard
product: campaign
title: Tracciare e monitorare i messaggi
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Scopri come Adobe Campaign ti consente di tenere traccia dei messaggi inviati e scoprire come reagiscono i destinatari alla consegna
feature: Deliverability
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 4%

---


# Tracciare e monitorare {#track-and-monitor}

Hai fatto clic sul pulsante Invia? Vediamo cosa succede. Una volta inviata la consegna, Adobe Campaign ti consente di tenere traccia dei messaggi inviati e scoprire come reagiscono i destinatari alla consegna. In questo modo potrai migliorare l’invio futuro e ottimizzare le campagne successive.

## Monitoraggio delle consegne {#monitoring-deliveries}

Per controllare le campagne, assicurati che il messaggio sia stato effettivamente consegnato ai destinatari.

**Suggerimenti**

* Puoi controllare lo stato dei messaggi nei registri di consegna.

* Per tenere traccia dei successi o degli errori di consegna, Adobe Campaign fornisce un sistema di avvisi e-mail che invia notifiche per informare gli utenti di importanti attività del sistema.

* Dal dashboard messaggi, puoi accedere a diversi rapporti per questo messaggio specifico.

Per ulteriori informazioni, consulta [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md).

## Tracking {#tracking-deliveries}

Per conoscere meglio il comportamento dei profili di destinazione, puoi tenere traccia della loro reazione a una consegna: ricezione, apertura, clic su collegamenti, annullamenti di abbonamenti, ecc. Fai riferimento alla scheda **Registri di tracciamento** della consegna.

**Suggerimento**: Il tracciamento dei messaggi è abilitato per impostazione predefinita. Per configurare gli URL, seleziona l’opzione Visualizza URL nella sezione inferiore della procedura guidata di consegna. Per ogni URL del messaggio, puoi scegliere se attivare il tracciamento.

Per ulteriori informazioni, consulta la sezione [Messaggi di tracciamento](../../sending/using/tracking-messages.md) e la descrizione [Indicatori di tracciamento](../../reporting/using/tracking-indicators.md) .

## Rapporti dinamici {#dyn-reports}

I rapporti dinamici ti consentono di creare rapporti completamente personalizzabili e in tempo reale per monitorare le campagne. Dimension, metriche e visualizzazioni consentono di misurare l’impatto e il successo delle campagne sui destinatari.

**Suggerimento** : i rapporti incorporati sono disponibili per il monitoraggio delle campagne, ma puoi anche personalizzare tali rapporti trascinando nel rapporto eventuali metriche o dimensioni.

Per ulteriori informazioni, consulta la [Guida ai rapporti](../../reporting/using/about-dynamic-reports.md).

## Hot click

Il rapporto Hot click presenta il contenuto del messaggio (HTML e/o testo) con la percentuale di clic su ciascun collegamento. Visualizzando la percentuale di clic su ciascun contenuto dinamico, puoi misurare quale contenuto richiede maggiormente i destinatari.

Per ulteriori informazioni, consulta il [Rapporto con clic caldo](../../reporting/using/hot-clicks.md).

## Suggerimenti sulle prestazioni di consegna {#performance-tips}

* Non mantenere le consegne nello stato non riuscito sull’istanza, in quanto questo mantiene tabelle temporanee e influisce sulle prestazioni.

* Rimuovi dal database le consegne non più necessarie e inattive per mantenere la qualità degli indirizzi.

* Non provare a pianificare insieme consegne di grandi dimensioni. Si prega di notare che possono essere necessari da 5 a 10 minuti per distribuire uniformemente il carico sul sistema.

**Argomenti correlati:**

* [Ricezione degli avvisi in caso di errori](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporti](../../reporting/using/about-dynamic-reports.md)
