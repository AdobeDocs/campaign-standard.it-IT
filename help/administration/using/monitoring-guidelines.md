---
title: Linee guida per il monitoraggio
description: Questa pagina presenta le linee guida generali per il monitoraggio di Campaign Standard
audience: production
feature: Access Management
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 21%

---

# Linee guida per il monitoraggio {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Monitoraggio del sistema</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Monitoraggio dei flussi di lavoro</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Monitoraggio delle consegne</a></p></td></tr>
</table>

Campaign Standard offre diversi modi per monitorare le istanze per garantire che il sistema sia integro e, infine, per risolvere eventuali problemi che possono verificarsi durante la configurazione di flussi di lavoro, l’invio di consegne, ecc.

## Monitoraggio del sistema {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Notifiche di sistema**

L’interfaccia di Campaign Standard fornisce un riquadro di notifica che consente di essere tenuti informati su ciò che accade nel sistema: stati degli eventi, aggiornamenti del sistema, azioni necessarie, ecc. [Ulteriori informazioni](../../start/using/interface-description.md#top-bar)


**Flussi di lavoro tecnici**

I flussi di lavoro tecnici sono operazioni o processi pianificati da eseguire regolarmente sul server. Per garantire che l’istanza sia integra e funzioni correttamente, è necessario assicurarsi che sia sempre operativa. [Ulteriori informazioni](../../administration/using/technical-workflows.md)

**Pannello di controllo**

Il Pannello di controllo Campaign ti consente di gestire diverse impostazioni dell’istanza: autorizzazioni URL, verifica i dettagli dell’istanza come le versioni di build dei server, monitoraggio dell’utilizzo dei profili attivi, ecc. Consente inoltre di monitorare lo spazio disponibile sui server SFTP connessi all’istanza. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it).

>[!NOTE]
>
>Il Pannello di controllo è accessibile a tutti gli utenti amministratori. I passaggi per concedere a un utente l’accesso come amministratore sono descritti in[questa pagina](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=it#discover-control-panel).

**Oggetti tecnici**

Il **[!UICONTROL Diagnosis]** Il menu è uno strumento chiave per monitorare e analizzare i diversi oggetti tecnici generati dall’applicazione: schemi di dati, pagine web, processi batch, ecc. [Ulteriori informazioni](../../developing/using/monitoring-data-model-changes.md)

**Controlli sulle esportazioni**

I controlli di esportazione ti consentono di monitorare le esportazioni eseguite sulle istanze: file caricati dai flussi di lavoro, esportazioni di elenchi e file scaricati dai messaggi di direct mailing.
[Ulteriori informazioni](../../administration/using/auditing-export-logs.md)

**Licenze**

Con il **[!UICONTROL Licenses]** monitora le informazioni sulle istanze: licenze installate, versioni della build e termini accettati dall’accordo.
[Ulteriori informazioni](../../administration/using/licenses.md)

## Monitoraggio dei flussi di lavoro {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Best practice e risoluzione dei problemi**

Seguire le best practice e le linee guida per la risoluzione dei problemi durante l’utilizzo dei flussi di lavoro può contribuire a migliorare le prestazioni.
[Ulteriori informazioni](../../automating/using/best-practices-workflows.md)

**Registri e attività**

Il monitoraggio dei registri dei flussi di lavoro è un passaggio chiave per analizzare i flussi di lavoro e assicurarti che vengano eseguiti correttamente.
[Ulteriori informazioni](../../automating/using/monitoring-workflow-execution.md#workflow-log-and-tasks)

**Notifiche**

Campaign Standard ti consente di inviare notifiche ai supervisori per monitorare l’esecuzione dei flussi di lavoro e verificare se si verificano errori che richiedono la tua attenzione.
[Ulteriori informazioni](../../automating/using/monitoring-workflow-execution.md#error-management)

## Monitoraggio delle consegne {#monitoring-deliveries}

<img src="assets/do-not-localize/icon_send.svg" width="60px">

**Deliverability**

Campaign Standard fornisce diversi strumenti di recapito messaggi per aiutarti a migliorare il numero di messaggi consegnati correttamente: rapporti sulla velocità effettiva di consegna, ottimizzazione del tempo di invio, anteprima dei messaggi, rendering delle e-mail, gestione della quarantena, ecc.
[Ulteriori informazioni](../../sending/using/about-deliverability.md)

**Consegne**

Una volta inviati i messaggi, i registri dettagliati ti consentono di monitorare le consegne e misurare il successo della campagna, nonché di tenere traccia del comportamento dei destinatari dei messaggi.
[Ulteriori informazioni](../../sending/using/monitoring-a-delivery.md)

**Avvisi sulla consegna**

Con la funzione di avviso sulla consegna, puoi impostare avvisi che verranno inviati automaticamente a un gruppo di utenti per quanto riguarda l’esecuzione delle consegne: invio o preparazione non riusciti, rapporto mancati recapiti non riusciti, throughput basso, ecc.
[Ulteriori informazioni](../../sending/using/receiving-alerts-when-failures-happen.md)

**Reporting dinamico**

Il reporting dinamico fornisce vari rapporti per mantenerti informato sulle prestazioni delle consegne: mancati recapiti, il maggior numero di consegne visualizzate dai destinatari, la velocità effettiva delle consegne, ecc.
[Ulteriori informazioni](../../reporting/using/about-dynamic-reports.md)
