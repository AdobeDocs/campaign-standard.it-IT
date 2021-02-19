---
solution: Campaign Standard
product: campaign
title: Linee guida per il monitoraggio
description: Questa sezione presenta le linee guida generali per il monitoraggio Campaign Standard.
audience: production
content-type: reference
topic-tags: introduction
index: y
translation-type: tm+mt
source-git-commit: 4b87ebc2585b87f918bbd688c5858394d8d4a742
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 9%

---


# Linee guida per il monitoraggio {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Monitoraggio del sistema</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Monitoraggio dei flussi di lavoro</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Monitoraggio delle consegne</a></p></td></tr>
</table>

Campaign Standard offre diversi modi di monitorare le istanze per garantire che il sistema sia sano e alla fine risolvere eventuali problemi che possono verificarsi durante la configurazione dei flussi di lavoro, l&#39;invio di consegne, ecc.

## Monitoraggio del sistema {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Notifiche**
di sistemaL&#39;interfaccia Campaign Standard fornisce un riquadro di notifica che consente di essere informati su quanto sta accadendo nel sistema: stati degli eventi, aggiornamenti del sistema, azioni richieste, ecc. [Leggi tutto](../../start/using/interface-description.md#top-bar)


**Flussi di**
lavoro tecniciI flussi di lavoro tecnici sono operazioni o processi pianificati per essere eseguiti regolarmente sul server. Per garantire che l&#39;istanza sia sana e funzioni correttamente, è necessario assicurarsi che siano sempre in funzione. [Leggi tutto](../../administration/using/technical-workflows.md)

**Pannello**
di controlloIl Pannello di controllo Campaign consente di gestire diverse impostazioni dell’istanza: autorizzazioni URL, controllo dei dettagli dell&#39;istanza come le versioni di build dei server, controllo dell&#39;utilizzo dei profili attivi, ecc. Consente inoltre di monitorare lo spazio disponibile sui server SFTP collegati all’istanza. [Leggi tutto](https://docs.adobe.com/content/help/it-IT/control-panel/using/control-panel-home.html).

>[!NOTE]
>
>Il Pannello di controllo Campaign è accessibile solo agli utenti Admin e disponibile per tutti i clienti che utilizzano i servizi gestiti Adobe.

**Oggetti**
tecniciIl  **[!UICONTROL Diagnosis]** menu è uno strumento fondamentale per monitorare e analizzare i diversi oggetti tecnici generati dall&#39;applicazione: schemi di dati, pagine Web, processi batch ecc. [Leggi tutto](../../developing/using/monitoring-data-model-changes.md)

**Esportazione di**
controlliI controlli di esportazione consentono di monitorare le esportazioni eseguite sulle istanze: file caricati da flussi di lavoro, esportazioni di elenchi e file scaricati da messaggi di posta diretta.
[Leggi tutto](../../administration/using/auditing-export-logs.md)

****
LicenzeNel  **[!UICONTROL Licenses]** menu, controllate le informazioni relative alle vostre istanze: licenze installate, versioni build e accettazioni dei termini.
[Leggi tutto](../../administration/using/licenses.md)

## Monitoraggio dei flussi di lavoro {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Procedure ottimali e**
risoluzione dei problemiLe best practice e le linee guida per la risoluzione dei problemi nell&#39;utilizzo dei flussi di lavoro consentono di migliorare le prestazioni.
[Leggi tutto](../../automating/using/best-practices-workflows.md)

**Registri e**
attivitàIl monitoraggio dei registri dei flussi di lavoro è un passaggio chiave per analizzare i flussi di lavoro e verificare che siano in esecuzione correttamente.
[Leggi tutto](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

****
NotificationsCampaign Standard consente di inviare notifiche ai supervisori per monitorare l&#39;esecuzione dei flussi di lavoro e verificare se vi sono errori che richiedono la vostra attenzione.
[Leggi tutto](../../automating/using/monitoring-workflow-execution.md#error-management)

## Monitoraggio delle consegne {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

****
DeliverabilityCampaign Standard offre diversi strumenti di recapito che consentono di migliorare il numero di messaggi recapitati correttamente: rapporti sul throughput di consegna, ottimizzazione del tempo di invio, anteprima dei messaggi, rendering delle e-mail, gestione della quarantena, ecc.
[Leggi tutto](../../sending/using/about-deliverability.md)

**Consegne**
Una volta inviati i messaggi, i registri dettagliati consentono di monitorare le consegne e misurare il successo della campagna, nonché di monitorare il comportamento dei destinatari dei messaggi.
[Leggi tutto](../../sending/using/monitoring-a-delivery.md)

**Avvisi**
di consegnaCon la funzione Avvisi di consegna potete impostare avvisi che verranno inviati automaticamente a un gruppo di utenti per quanto riguarda l’esecuzione delle consegne: invio o preparazione non riusciti, rapporto di rimbalzo errato, basso throughput, ecc.
[Leggi tutto](../../sending/using/receiving-alerts-when-failures-happen.md)

**Generazione**
di rapporti dinamicaLa generazione di rapporti dinamica fornisce vari rapporti che consentono di essere informati sulle prestazioni delle consegne: rimbalzi, la maggior parte delle consegne visualizzate dai destinatari, il throughput delle consegne, ecc.
[Leggi tutto](../../reporting/using/about-dynamic-reports.md)
