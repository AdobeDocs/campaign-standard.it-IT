---
title: Linee guida per il monitoraggio
description: Questa sezione presenta le linee guida generali per il monitoraggio di Campaign Standard.
page-status-flag: never-activated
uuid: cf0d782d-47bf-40ae-ab6f-d1d47fa15792
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: production
content-type: reference
topic-tags: introduction
discoiquuid: 8b33e6af-15c3-4b30-8ad6-d76a1f33be21
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4bac585ec25340d1f1d047f9a1f8dcd8e243821
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 6%

---


# Linee guida per il monitoraggio {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Monitoraggio del sistema</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Flussi di lavoro di monitoraggio</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Monitoraggio delle consegne</a></p></td></tr>
</table>

Campaign Standard offre diversi metodi per monitorare le istanze in modo da garantire che il sistema sia sano e, in ultima istanza, per risolvere eventuali problemi che possono verificarsi durante la configurazione dei flussi di lavoro, l&#39;invio di consegne ecc.

## Monitoraggio del sistema {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**L&#39;interfaccia** Campaign Standard delle notifiche di sistema fornisce un riquadro di notifica che consente di essere informati di ciò che sta accadendo nel sistema: stati degli eventi, aggiornamenti del sistema, azioni richieste, ecc. [Leggi tutto](../../start/using/interface-description.md#top-bar)


**Flussi di lavoro** tecnici I flussi di lavoro tecnici sono operazioni o processi pianificati per essere eseguiti regolarmente sul server. Per garantire che l&#39;istanza sia sana e funzioni correttamente, è necessario assicurarsi che siano sempre in funzione. [Leggi tutto](../../administration/using/technical-workflows.md)

**Pannello di controllo Campaign** Il Pannello di controllo Campaign consente di gestire diverse impostazioni dell’istanza: autorizzazioni URL, controllo dei dettagli dell&#39;istanza come le versioni di build dei server, controllo dell&#39;utilizzo dei profili attivi, ecc. Consente inoltre di monitorare lo spazio disponibile sui server SFTP collegati all’istanza. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/control-panel/using/control-panel-home.html).

>[!NOTE]
>
>Il Pannello di controllo Campaign è accessibile solo agli utenti Admin e disponibile per tutti i clienti che utilizzano  Adobi Managed Services.

**Oggetti** tecnici Il **[!UICONTROL Diagnosis]** menu è uno strumento fondamentale per monitorare e analizzare i diversi oggetti tecnici generati dall&#39;applicazione: schemi di dati, pagine Web, processi batch ecc. [Leggi tutto](../../developing/using/monitoring-data-model-changes.md)

**Audit**di esportazione I controlli di esportazione consentono di monitorare le esportazioni eseguite sulle istanze: file caricati da flussi di lavoro, esportazioni di elenchi e file scaricati da messaggi di posta diretta.
[Leggi tutto](../../administration/using/auditing-export-logs.md)

**Licenze** Il **[!UICONTROL Licenses]** menu consente di monitorare le informazioni relative alle istanze: licenze installate, versioni build e accettazioni dei termini.
[Leggi tutto](../../administration/using/licenses.md)

## Flussi di lavoro di monitoraggio {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Procedure ottimali e risoluzione dei problemi**Seguite le best practice e le linee guida per la risoluzione dei problemi durante l&#39;utilizzo dei flussi di lavoro per migliorare le prestazioni.
[Leggi tutto](../../automating/using/best-practices-workflows.md)

**Registri e attività**Il monitoraggio dei registri di lavoro è un passo fondamentale per analizzare i flussi di lavoro e verificare che siano in esecuzione correttamente.
[Leggi tutto](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Notifiche**Campaign Standard consente di inviare notifiche alle autorità di vigilanza per monitorare l&#39;esecuzione dei flussi di lavoro e verificare se vi sono errori che richiedono la vostra attenzione.
[Leggi tutto](../../automating/using/monitoring-workflow-execution.md#error-management)

## Monitoraggio delle consegne {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**La funzionalità di recapito**Campaign Standard offre diversi strumenti per migliorare il numero di messaggi recapitati correttamente: report di analisi dei tempi di consegna, ottimizzazione dei tempi di invio, anteprima dei messaggi, rendering delle e-mail, gestione della quarantena, ecc.
[Leggi tutto](../../sending/using/about-deliverability.md)

**Consegne**Una volta inviati i messaggi, i registri dettagliati consentono di monitorare le consegne e misurare il successo della campagna, nonché di monitorare il comportamento dei destinatari dei messaggi.
[Leggi tutto](../../sending/using/monitoring-a-delivery.md)

**Avvisi sulla distribuzione**Con la funzione Avvisi sulla consegna, puoi impostare avvisi che verranno inviati automaticamente a un gruppo di utenti per quanto riguarda l’esecuzione delle consegne: invio o preparazione non riusciti, rapporto di rimbalzo errato, basso throughput, ecc.
[Leggi tutto](../../sending/using/receiving-alerts-when-failures-happen.md)

**Generazione di rapporti**dinamica I rapporti dinamici forniscono vari rapporti che consentono di essere informati sulle prestazioni delle consegne: rimbalzi, la maggior parte dei invii visualizzati dai destinatari, il throughput delle consegne, ecc.
[Leggi tutto](../../reporting/using/about-dynamic-reports.md)
