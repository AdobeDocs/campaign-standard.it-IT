---
title: Flussi di lavoro tecnici
description: I flussi di lavoro tecnici sono flussi di lavoro preconfigurati e progettati per gestire processi tecnici in background in Adobe Campaign, garantendo il corretto funzionamento della piattaforma.
page-status-flag: never-activated
uuid: 6e763dc1-e1d3-4d94-bc0b-ef5b1703d8e5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: e9f147bd-6a5b-4b82-b9bb-311e38e22c62
internal: n
snippet: y
translation-type: ht
source-git-commit: b4cbc56973a57cde8af6cefa9ff89c7d29ab7b79
workflow-type: ht
source-wordcount: '678'
ht-degree: 100%

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
   <td> <span class="uicontrol">Database cleanup</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> Questo flusso di lavoro riguarda la manutenzione del database: esegue statistiche e processi diversi ed elimina dati obsoleti dal database in base alla configurazione definita. Per impostazione predefinita viene avviato automaticamente ogni giorno alle 4.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Forecasting</span> <br /> </td> 
   <td> <span class="uicontrol">forecasting</span> <br /> </td> 
   <td> Questo flusso di lavoro esegue l’analisi delle consegne archiviate nelle previsioni provvisorie (creazione dei log provvisori). Per impostazione predefinita viene avviato ogni giorno all’1. <br /> </td> 
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
   <td> <span class="uicontrol">Managing NMAC opt-outs</span> <br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMgt</span> <br /> </td> 
   <td> Questo flusso di lavoro aggiorna gli annullamenti dell’abbonamento alle notifiche sui dispositivi mobili. Per impostazione predefinita viene avviato ogni 6 ore tra l’1 e mezzanotte.<br /> </td> 
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
   <td> Questo flusso di lavoro sincronizza le proprietà importate dei dispositivi mobili di Adobe Launch in Adobe Campaign Standard. Viene avviato ogni 15 minuti.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Update delivery execution</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span> <br /> </td> 
   <td> Questo flusso di lavoro aggiorna il tracciamento della consegna. Per impostazione predefinita viene avviato ogni 10 minuti.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Update delivery indicators</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span> <br /> </td> 
   <td> Questo flusso di lavoro aggiorna i KPI (Key Performance Indicator) della consegna. Per impostazione predefinita viene avviato ogni ora.<br /> </td> 
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

