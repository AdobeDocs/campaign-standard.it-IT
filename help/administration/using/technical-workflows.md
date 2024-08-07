---
title: Flussi di lavoro tecnici
description: Ulteriori informazioni sui flussi di lavoro tecnici
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: da3a3af5-207a-4289-bd07-00a8c5d1cf57
source-git-commit: f87795ee2378a1e9e1b393c6cce002bcb70178b8
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 74%

---

# Flussi di lavoro tecnici{#technical-workflows}

I flussi di lavoro tecnici sono preconfigurati in Adobe Campaign. I flussi di lavoro tecnici sono operazioni o processi pianificati da eseguire regolarmente sul server.

Ti consentono di eseguire operazioni di manutenzione sul database, sfruttare le informazioni di tracciamento nelle consegne e aggiornare i processi provvisori relativi alle consegne.

Gli amministratori funzionali possono accedere ai flussi di lavoro tecnici dal menu **[!UICONTROL Administration > Application settings > Workflows]**.

>[!NOTE]
>
>In qualità di amministratore funzionale, puoi riavviare o mettere in pausa flussi di lavoro tecnici e modificarne proprietà e struttura.

![](assets/technical_workflows.png)

## Elenco dei flussi di lavoro tecnici {#list-of-technical-workflows}

I flussi di lavoro tecnici vengono utilizzati per gestire processi tecnici e di background con attivazione automatica in Adobe Campaign.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etichetta</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">A/B Testing</span> <br /> </td> 
   <td> <span class="uicontrol">abTesting</span> <br /> </td> 
   <td> Questo flusso di lavoro analizza log di tracciamento di ogni variante. Al termine del periodo di test A/B, calcola automaticamente la variante vincente. Per impostazione predefinita viene avviato ogni giorno.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Billing</span> <br /> </td> 
   <td> <span class="uicontrol">billing</span> <br /> </td> 
   <td> Questo flusso di lavoro invia il rapporto sull’attività del sistema all’utente di “fatturazione” tramite e-mail. Per impostazione predefinita viene avviato automaticamente ogni giorno all’1.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Copia intestazioni dai modelli di consegna</span> <br /> </td> 
   <td> <span class="uicontrol">smtpHeaderupdate</span> <br /> </td> 
   <td> Questo flusso di lavoro copia le intestazioni SMTP impostate per i modelli di consegna e-mail nelle consegne secondarie non basate su modelli corrispondenti. Solo le consegne di e-mail marketing vengono selezionate da questo flusso di lavoro. Le intestazioni SMTP non vengono copiate nelle consegne transazionali e nelle consegne di bozze. <br> Questo flusso di lavoro non viene eseguito periodicamente. Deve essere avviato dall’utente in base all’utilizzo. <!--So it'not really a technical workflow like all workflows on this page, because it's not run automatically - TBC--> <br> Se nell'istanza è presente un numero elevato di consegne, è possibile aggiornare l'opzione NmsCleanup_DeliveryPurgeDelay nelle <strong>Impostazioni applicazione</strong>. Se apporti una modifica nelle intestazioni SMTP di qualsiasi modello, devi eseguire nuovamente il flusso di lavoro dopo la modifica in modo che le intestazioni corrette vengano copiate nelle consegne non basate su modelli.<a href="data-retention.md#deliveries">Ulteriori informazioni</a>
   <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Database cleanup</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> Questo flusso di lavoro riguarda la manutenzione del database: esegue statistiche e processi diversi ed elimina dati obsoleti dal database in base alla configurazione definita. Per impostazione predefinita viene avviato automaticamente ogni giorno alle 4.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Import a shared audience</span> <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span> <br /> </td> 
   <td> Questo flusso di lavoro sincronizza i dati importati del pubblico di Adobe Experience Cloud in Adobe Campaign. Per impostazione predefinita viene avviato ogni ora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Instant Report Sharing</span> <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span> <br /> </td> 
   <td> Questo flusso di lavoro viene avviato dopo la pianificazione dell’invio di un rapporto. Converte il rapporto in un file pdf e lo invia tramite e-mail ai destinatari desiderati.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPIs reconciliation with Adobe Analytics</span> <br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span> <br /> </td> 
   <td> Questo flusso di lavoro recupera i KPI dal servizio Reporting una volta al giorno e li riconcilia con i dati di Adobe Analytics. Quindi, se necessario, appiana la differenza. Per impostazione predefinita viene avviato ogni giorno alle 4.20.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Message Center local archiving</span> <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span> <br /> </td> 
   <td> Questo flusso di lavoro archivia gli eventi in tempo reale in una tabella di cronologia. Per impostazione predefinita viene avviato ogni ora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Reporting aggregates</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> Questo flusso di lavoro aggiorna gli aggregati utilizzati nei rapporti. Per impostazione predefinita viene avviato automaticamente alle 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Share KPIs with Adobe Analytics</span> <br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span> <br /> </td> 
   <td> Questo flusso di lavoro invia i dati dei KPI (Key Performance Indicator) ogni 15 minuti da Adobe Campaign Standard in Adobe Analytics.<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">Sync with Launch</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> Questo flusso di lavoro sincronizza le proprietà dei tag mobili importate in Adobe Campaign Standard. Viene avviato ogni 15 minuti.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Registrazione del ripristino dei registri</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> Questo flusso di lavoro sincronizza le proprietà dei tag mobili importate in Adobe Campaign Standard. Viene avviato ogni 15 minuti.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Recupera registri di tracciamento</span> <br /> </td> 
   <td> <span class="uicontrol">trackingLogRecovery</span> <br /> </td> 
   <td> Questo flusso di lavoro ripristina i registri di tracciamento persi. Tieni presente che questo flusso di lavoro tecnico viene utilizzato in contesti specifici e limitato al solo uso interno Adobe. <br> Per impostazione predefinita viene avviato ogni 10 minuti.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Update delivery execution</span> <br/> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span> <br/> </td> 
   <td> Questo flusso di lavoro copia i registri di trasmissione e i registri di tracciamento nel database locale. Per impostazione predefinita viene avviato ogni 10 minuti.<br/> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Update delivery indicators</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span> <br /> </td> 
   <td> Questo flusso di lavoro aggiorna i KPI (indicatori chiave di prestazioni) della consegna. Per impostazione predefinita viene avviato ogni ora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Update event status</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> Questo flusso di lavoro ti consente di attribuire uno stato a un evento. Sono disponibili i seguenti stati dell’evento:<br /> <strong>Pending</strong>: l’evento è in coda. Non è ancora stato assegnato alcun modello di messaggio.<br /> <span class="uicontrol">Pending delivery</span>: l’evento è in coda, gli è stato assegnato un modello di messaggio e viene elaborato dalla consegna.<br /> <strong>Sent</strong>: questo stato viene copiato dai log di consegna. Significa che la consegna è stata inviata.<br /> <strong>Ignored by the delivery</strong>: questo stato viene copiato dai log di consegna. Significa che la consegna è stata ignorata.<br /> <strong>Delivery failed</strong>: questo stato viene copiato dai log di consegna. Significa che la consegna è non è andata a buon fine.<br /> <span class="uicontrol">Event not taken into account</span>: impossibile collegare l’evento a un modello di messaggio. L’evento non viene elaborato.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Update for deliverability</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> Questo flusso di lavoro ti consente di creare l’elenco delle regole di qualifica dei messaggi non recapitati, nonché l’elenco di domini e record MX nella piattaforma. Questo flusso di lavoro funziona solo se è aperto l’HTTPS. Per impostazione predefinita viene avviato automaticamente alle 2.<br /> </td> 
  </tr> 
 </tbody> 
</table>
