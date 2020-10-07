---
title: Tracciare e monitorare i messaggi
seo-title: Tracciare e monitorare i messaggi
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 3%

---


# Monitoraggio e monitoraggio {#track-and-monitor}

Hai fatto clic sul pulsante Invia? Vediamo cosa succede. Una volta inviata la consegna,  Adobe Campaign consente di tenere traccia dei messaggi inviati e di scoprire in che modo i destinatari reagiscono alla consegna. In questo modo potrai migliorare l’invio futuro e ottimizzare le campagne successive.

## Monitoraggio delle consegne {#monitoring-deliveries}

Per controllare le campagne, devi accertarti che il messaggio sia stato effettivamente recapitato ai destinatari.

**Suggerimenti**

* Puoi controllare lo stato dei messaggi nei registri di consegna.

* Per tenere traccia dei successi o degli errori di consegna,  Adobe Campaign fornisce un sistema di avvisi e-mail che invia notifiche per informare gli utenti di importanti attività del sistema.

* Dal dashboard dei messaggi, puoi accedere a diversi rapporti per questo messaggio specifico.

Per ulteriori informazioni, vedere [Monitoraggio di una distribuzione](../../sending/using/monitoring-a-delivery.md).

## Tracking {#tracking-deliveries}

Per conoscere meglio il comportamento dei profili di destinazione, puoi tenere traccia di come reagiscono a una consegna: ricezione, apertura, clic su collegamenti, annullamento sottoscrizioni, ecc. Fare riferimento alla scheda Registri **di** tracciamento della consegna.

**Suggerimento**: Il tracciamento dei messaggi è abilitato per impostazione predefinita. Per configurare gli URL, selezionate l’opzione Visualizza URL nella sezione inferiore della procedura guidata di consegna. Per ciascun URL del messaggio, potete scegliere se attivare il tracciamento.

Per ulteriori informazioni, consulta la sezione Messaggi [di](../../sending/using/tracking-messages.md) tracciamento e la descrizione degli indicatori [di](../../reporting/using/tracking-indicators.md) tracciamento.

## Report dinamici {#dyn-reports}

I rapporti dinamici consentono di creare rapporti completamente personalizzabili e in tempo reale per monitorare le campagne. Dimension, metriche e visualizzazioni consentono di misurare l&#39;impatto e il successo delle campagne sui destinatari.

**Suggerimento** : i rapporti incorporati sono disponibili per il monitoraggio delle campagne, ma possono essere personalizzati anche trascinando nel rapporto eventuali metriche o dimensioni.

For more on this, refer to the [Reporting guide](../../reporting/using/about-dynamic-reports.md).

## Hot click

Il rapporto sui clic attivi presenta il contenuto del messaggio (HTML e/o testo) con la percentuale di clic su ciascun collegamento. Visualizzando la percentuale di clic su ciascun contenuto dinamico, potete misurare il contenuto per il quale i destinatari sono maggiormente invitati.

Per ulteriori informazioni, consulta il rapporto [Clic](../../reporting/using/hot-clicks.md).

## Suggerimenti sulle prestazioni di distribuzione {#performance-tips}

* Non mantenere le consegne in stato di errore nell&#39;istanza, in quanto questo mantiene le tabelle temporanee e influisce sulle prestazioni.

* Rimuovete dal database i recapiti non più necessari e i destinatari inattivi per mantenere la qualità degli indirizzi.

* Non provare a pianificare insieme consegne di grandi dimensioni. Si prega di notare che possono essere necessari da 5 a 10 minuti per distribuire uniformemente il carico sul sistema.

**Argomenti correlati:**

* [Ricezione degli avvisi in caso di errori](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporti](../../reporting/using/about-dynamic-reports.md)
