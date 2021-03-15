---
solution: Campaign Standard
product: campaign
title: Linee guida per il monitoraggio
description: Questa sezione presenta le linee guida generali per il monitoraggio di Campaign Standard.
audience: production
content-type: reference
topic-tags: introduction
index: y
feature: Gestione degli accessi
role: Amministratore
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 9%

---


# Linee guida per il monitoraggio {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Monitoraggio del sistema</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Monitoraggio dei flussi di lavoro</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Monitoraggio delle consegne</a></p></td></tr>
</table>

Campaign Standard offre diversi modi per monitorare le istanze in modo da garantire che il sistema sia integro e risolvere eventuali problemi che possono verificarsi durante la configurazione dei flussi di lavoro, l’invio di consegne, ecc.

## Monitoraggio del sistema {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Notifiche**
di sistemaL’interfaccia di Campaign Standard fornisce un riquadro di notifica che ti consente di essere informato su ciò che sta accadendo nel sistema: stati degli eventi, aggiornamenti del sistema, azione richiesta, ecc. [Leggi tutto](../../start/using/interface-description.md#top-bar)


**Flussi di**
lavoro tecniciI flussi di lavoro tecnici sono operazioni o lavori pianificati da eseguire regolarmente sul server. Per garantire che l’istanza sia sana e funzioni correttamente, è necessario assicurarsi che sia sempre in esecuzione. [Leggi tutto](../../administration/using/technical-workflows.md)

**Pannello**
di controlloIl Pannello di controllo Campaign consente di gestire diverse impostazioni dell&#39;istanza: Autorizzazioni URL, controlla i dettagli dell’istanza come le versioni di build dei server, monitora l’utilizzo dei profili attivi, ecc. Consente inoltre di monitorare lo spazio disponibile sui server SFTP collegati all’istanza. [Leggi tutto](https://docs.adobe.com/content/help/it-IT/control-panel/using/control-panel-home.html).

>[!NOTE]
>
>Il Pannello di controllo Campaign è accessibile solo agli utenti amministratori e disponibile per tutti i clienti che utilizzano Adobe Managed Services.

**Oggetti tecniciIl**
  **[!UICONTROL Diagnosis]** menu è uno strumento chiave per monitorare e analizzare i diversi oggetti tecnici generati dall&#39;applicazione: schemi di dati, pagine web, processi batch, ecc. [Leggi tutto](../../developing/using/monitoring-data-model-changes.md)

**Audit**
di esportazioneI controlli di esportazione consentono di monitorare le esportazioni eseguite sulle istanze: file caricati da flussi di lavoro, esportazioni di elenchi e file scaricati da messaggi di direct mailing.
[Leggi tutto](../../administration/using/auditing-export-logs.md)

****
LicenzeCon il  **[!UICONTROL Licenses]** menu , monitora le informazioni sulle istanze: licenze installate, versioni della build e accettazioni dei termini del contratto.
[Leggi tutto](../../administration/using/licenses.md)

## Monitoraggio dei flussi di lavoro {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Procedure consigliate e**
risoluzione dei problemiLe best practice e le linee guida per la risoluzione dei problemi nell’utilizzo dei flussi di lavoro consentono di migliorare le prestazioni.
[Leggi tutto](../../automating/using/best-practices-workflows.md)

**Registri e**
attivitàIl monitoraggio dei registri del flusso di lavoro è un passaggio chiave per analizzare i flussi di lavoro e assicurarsi che siano in esecuzione correttamente.
[Leggi tutto](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

****
NotificationsCampaign Standard consente di inviare notifiche alle autorità di vigilanza per monitorare l’esecuzione dei flussi di lavoro e verificare se vi è un errore che richiede la tua attenzione.
[Leggi tutto](../../automating/using/monitoring-workflow-execution.md#error-management)

## Monitoraggio delle consegne {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

****
DeliverabilityCampaign Standard fornisce diversi strumenti di recapito per aiutarti a migliorare il numero di messaggi consegnati correttamente: rapporti sulla velocità effettiva di consegna, ottimizzazione del tempo di invio, anteprima dei messaggi, rendering delle e-mail, gestione della quarantena, ecc.
[Leggi tutto](../../sending/using/about-deliverability.md)

****
ConsegneUna volta inviati i messaggi, i registri dettagliati ti consentono di monitorare le consegne e misurare il successo della campagna, nonché di tenere traccia del comportamento dei destinatari dei messaggi.
[Leggi tutto](../../sending/using/monitoring-a-delivery.md)

**Avvisi di consegnaCon la funzione Avvisi di consegna è possibile impostare avvisi che verranno inviati automaticamente a un gruppo di utenti per quanto riguarda l’esecuzione delle consegne:**
 invio o preparazione non riusciti, rapporto non recapitato errato, throughput ridotto, ecc.
[Leggi tutto](../../sending/using/receiving-alerts-when-failures-happen.md)

**Reporting dinamicoIl reporting dinamico fornisce vari report per consentirti di essere informato sulle prestazioni delle consegne:**
 mancati recapiti, consegne più visualizzate per destinatari, throughput delle consegne, ecc.
[Leggi tutto](../../reporting/using/about-dynamic-reports.md)
