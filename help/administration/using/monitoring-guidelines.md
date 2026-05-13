---
title: Linee guida per il monitoraggio
description: Questa pagina presenta le linee guida generali per il monitoraggio di Campaign Standard
audience: production
feature: Access Management
role: Admin
level: Experienced
exl-id: 5f25f2b2-ca41-4baf-ade2-42bbafb4790d
TQID: https://experienceleague.adobe.com/4hy5-pubF9F2FDQGaC7GF-BfMHqMDykC4mtypRc-zsk
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c309ee4e-82e4-4f7e-b608-ef345678c34e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 512
ht-degree: 18%

---

# Linee guida per il monitoraggio {#monitoring-guidelines}

<table>
<tr><td><img src="assets/do-not-localize/icon_system.svg" width="60px"><p><a href="#monitoring-system">Monitoraggio del sistema</a></p></td>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#moniroting-workflows">Monitoraggio dei flussi di lavoro</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#monitoring-deliveries">Monitoraggio delle consegne</a></p></td></tr>
</table>

Campaign Standard offre diversi modi per monitorare le istanze per garantire che il sistema sia integro e, infine, risolvere i problemi che possono verificarsi durante la configurazione dei flussi di lavoro, l’invio di consegne, ecc.

## Monitoraggio del sistema {#monitoring-system}

<img src="assets/do-not-localize/icon_system.svg" width="60px">

**Notifiche di sistema**

L&#39;interfaccia di Campaign Standard fornisce un riquadro di notifica che consente di essere tenuti informati su ciò che accade nel sistema: stati degli eventi, aggiornamenti del sistema, azione richiesta, ecc. [Ulteriori informazioni](../../start/using/interface-description.md#top-bar)


**Flussi di lavoro tecnici**

I flussi di lavoro tecnici sono operazioni o processi pianificati da eseguire regolarmente sul server. Per garantire che l’istanza sia integra e funzioni correttamente, è necessario assicurarsi che sia sempre operativa. [Ulteriori informazioni](../../administration/using/technical-workflows.md)

**Pannello di controllo**

Il Pannello di controllo Campaign ti consente di gestire diverse impostazioni dell’istanza: autorizzazioni URL, verifica i dettagli dell’istanza come le versioni di build dei server, monitoraggio dell’utilizzo dei profili attivi, ecc. Consente inoltre di monitorare lo spazio disponibile sui server SFTP connessi all’istanza. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it).

>[!NOTE]
>
>Il Pannello di controllo è accessibile a tutti gli utenti amministratori. I passaggi per concedere a un utente l’accesso come amministratore sono descritti in[questa pagina](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/managing-permissions.html?lang=it#discover-control-panel).

**Oggetti tecnici**

Il menu **[!UICONTROL Diagnosis]** è uno strumento chiave per monitorare e analizzare i diversi oggetti tecnici generati dall&#39;applicazione: schemi di dati, pagine Web, processi batch, ecc. [Ulteriori informazioni](../../developing/using/monitoring-data-model-changes.md)

**Esporta controlli**

I controlli di esportazione ti consentono di monitorare le esportazioni eseguite sulle istanze: file caricati dai flussi di lavoro, esportazioni di elenchi e file scaricati dai messaggi di direct mailing.
[Ulteriori informazioni](../../administration/using/auditing-export-logs.md)

**Licenze**

Con il menu **[!UICONTROL Licenses]**, monitora le informazioni sulle istanze: licenze installate, versioni di build e termini accettati dall&#39;accordo.
[Ulteriori informazioni](../../administration/using/licenses.md)

## Monitoraggio dei flussi di lavoro {#monitoring-workflows}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

**Procedure consigliate e risoluzione dei problemi**

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

Campaign Standard fornisce diversi strumenti di recapito dei messaggi per aiutarti a migliorare il numero di messaggi consegnati correttamente: rapporti sulla velocità effettiva di consegna, ottimizzazione del tempo di invio, anteprima dei messaggi, rendering delle e-mail, gestione della quarantena, ecc.
[Ulteriori informazioni](../../sending/using/about-deliverability.md)

**Consegne**

Una volta inviati i messaggi, i registri dettagliati ti consentono di monitorare le consegne e misurare il successo della campagna, nonché di tenere traccia del comportamento dei destinatari dei messaggi.
[Ulteriori informazioni](../../sending/using/monitoring-a-delivery.md)

**Avvisi di consegna**

Con la funzione di avviso sulla consegna, puoi impostare avvisi che verranno inviati automaticamente a un gruppo di utenti per quanto riguarda l’esecuzione delle consegne: invio o preparazione non riusciti, rapporto mancati recapiti non riusciti, throughput basso, ecc.
[Ulteriori informazioni](../../sending/using/receiving-alerts-when-failures-happen.md)

**Reporting dinamico**

Il reporting dinamico fornisce vari rapporti per mantenerti informato sulle prestazioni delle consegne: mancati recapiti, il maggior numero di consegne visualizzate dai destinatari, la velocità effettiva delle consegne, ecc.
[Ulteriori informazioni](../../reporting/using/about-dynamic-reports.md)
