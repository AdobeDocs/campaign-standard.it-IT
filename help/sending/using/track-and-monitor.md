---
title: Tracciare e monitorare i messaggi
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Scopri come Adobe Campaign ti consente di tenere traccia dei messaggi inviati e scoprire come i destinatari reagiscono alla consegna
feature: Deliverability
role: User
level: Intermediate
exl-id: dd3bd672-fb9d-4e82-bdf3-d319f372baaa
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 3%

---

# Tracciamento e monitoraggio {#track-and-monitor}

Hai fatto clic sul pulsante Invia? Vediamo cosa succede. Una volta inviata la consegna, Adobe Campaign ti consente di tenere traccia dei messaggi inviati e scoprire come i destinatari reagiscono alla consegna. Questo ti consente di migliorare l’invio futuro e di ottimizzare le campagne successive.

## Monitoraggio delle consegne {#monitoring-deliveries}

Per controllare le campagne, devi assicurarti che il messaggio sia stato effettivamente recapitato ai destinatari.

**Suggerimenti**

* Puoi controllare lo stato dei messaggi nei registri di consegna.

* Per tenere traccia dei successi o degli errori di consegna, Adobe Campaign fornisce un sistema di avvisi e-mail che invia notifiche per informare gli utenti di importanti attività del sistema.

* Puoi accedere a diversi rapporti per questo messaggio specifico dal dashboard dei messaggi.

Per ulteriori informazioni, consulta [Monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md).

## Tracciamento {#tracking-deliveries}

Per conoscere meglio il comportamento dei profili target, puoi tracciare come reagiscono a una consegna: ricezione, apertura, clic su collegamenti, annullamenti di abbonamenti, ecc. Consulta la sezione **Registri di tracciamento** della consegna.

**Suggerimento**: il tracciamento dei messaggi è abilitato per impostazione predefinita. Per configurare gli URL, seleziona l’opzione Visualizza URL nella sezione inferiore della procedura guidata di consegna. Per ogni URL del messaggio, puoi scegliere se attivare il tracciamento.

Per ulteriori informazioni, consulta [Tracciamento dei messaggi](../../sending/using/tracking-messages.md) sezione e [Indicatori di tracciamento](../../reporting/using/tracking-indicators.md) descrizione.

## Rapporti dinamici {#dyn-reports}

I rapporti dinamici ti consentono di creare rapporti completamente personalizzabili e in tempo reale per monitorare le campagne. Dimension, metriche e visualizzazioni ti consentono di misurare l’impatto e il successo delle campagne sui destinatari.

**Suggerimento** - Sono disponibili rapporti incorporati per il monitoraggio delle campagne, ma possono anche essere personalizzati trascinando eventuali metriche o dimensioni nel rapporto.

Per ulteriori informazioni, consulta [Guida al reporting](../../reporting/using/about-dynamic-reports.md).

## Hot click

Il rapporto Hot clicks presenta il contenuto del messaggio (HTML e/o testo) con la percentuale di clic su ciascun collegamento. Visualizzando la percentuale di clic su ciascun contenuto dinamico, puoi misurare quale contenuto attrae maggiormente i destinatari.

Per ulteriori informazioni, consulta [Rapporto Hot click](../../reporting/using/hot-clicks.md).

## Suggerimenti sulle prestazioni della consegna {#performance-tips}

* Non mantenere le consegne in stato di errore nell’istanza, in quanto questa operazione mantiene le tabelle temporanee e influisce sulle prestazioni.

* Rimuovi dal database le consegne che non sono più necessarie e i destinatari inattivi per mantenere la qualità degli indirizzi.

* Non provare a pianificare insieme consegne di grandi dimensioni. Si prega di notare che possono essere necessari da 5 a 10 minuti per distribuire il carico uniformemente sul sistema.

**Argomenti correlati:**

* [Ricezione degli avvisi in caso di errori](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapporti](../../reporting/using/about-dynamic-reports.md)
