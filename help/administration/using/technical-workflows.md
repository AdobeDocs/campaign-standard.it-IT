---
title: Flussi di lavoro tecnici
description: I flussi di lavoro tecnici sono flussi di lavoro standard progettati per gestire i processi tecnici in background in Adobe Campaign, garantendo il corretto funzionamento della piattaforma.
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
translation-type: tm+mt
source-git-commit: b4cbc56973a57cde8af6cefa9ff89c7d29ab7b79

---


# Flussi di lavoro tecnici{#technical-workflows}

I flussi di lavoro tecnici vengono forniti con Adobe Campaign. I flussi di lavoro tecnici sono operazioni o processi pianificati per essere eseguiti regolarmente sul server.

Consentono di eseguire operazioni di manutenzione sul database, sfruttare le informazioni di tracciamento nelle consegne e aggiornare i processi provvisori relativi alle consegne.

Gli amministratori funzionali possono accedere ai flussi di lavoro tecnici dal **[!UICONTROL Administration > Application settings > Workflows]** menu.

>[!NOTE]
>
>In qualità di amministratore funzionale, potete riavviare o mettere in pausa i flussi di lavoro tecnici e modificarne le proprietà e la struttura.

![](assets/technical_workflows.png)

## Elenco dei flussi di lavoro tecnici {#list-of-technical-workflows}

I flussi di lavoro tecnici vengono utilizzati per gestire i processi tecnici e di background con attivazione automatica in Adobe Campaign.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etichetta</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Test</span> A/B <br /> </td> 
   <td> <span class="uicontrol">abTesting</span><br /> </td> 
   <td> Questo flusso di lavoro analizza i registri di tracciamento di ogni variante. Al termine del periodo di test A/B, calcola automaticamente la variante vincente. Per impostazione predefinita, viene avviata ogni giorno.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Fatturazione</span><br /> </td> 
   <td> <span class="uicontrol">fatturazione</span><br /> </td> 
   <td> Questo flusso di lavoro invia il rapporto sull'attività del sistema all'utente di fatturazione tramite e-mail. Per impostazione predefinita, viene avviato automaticamente ogni giorno alle 1.00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Pulizia</span> del database <br /> </td> 
   <td> <span class="uicontrol">pulizia</span><br /> </td> 
   <td> Questo flusso di lavoro è il flusso di lavoro di manutenzione del database: esegue statistiche e processi diversi ed elimina i dati obsoleti dal database in base alla configurazione definita. Per impostazione predefinita, viene avviata automaticamente ogni giorno 4.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Previsione</span><br /> </td> 
   <td> <span class="uicontrol">previsione</span><br /> </td> 
   <td> Questo flusso di lavoro esegue l'analisi delle consegne memorizzate nelle previsioni provvisorie (creazione dei registri provvisori). Per impostazione predefinita, viene avviata ogni giorno alle 1 del mattino. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Importare un'audience</span> condivisa <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span><br /> </td> 
   <td> Questo flusso di lavoro sincronizza i dati di audience di Adobe Experience Cloud importati in Adobe Campaign. Per impostazione predefinita, viene avviata ogni ora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Condivisione</span> istantanea dei report <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span><br /> </td> 
   <td> Questo flusso di lavoro viene avviato non appena è pianificato l'invio di un rapporto. Converte il rapporto in un file pdf e lo invia tramite e-mail ai destinatari desiderati.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Riconciliazione dei KPI con Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">kpiRealing</span><br /> </td> 
   <td> Questo flusso di lavoro recupera i KPI dal servizio Reporting una volta al giorno e li riconcilia con i dati di Adobe Analytics. Quindi, se necessario, spinge la differenza. Per impostazione predefinita, viene avviata ogni giorno alle 4.20.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Gestione delle opzioni di rifiuto</span> NMAC <br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMgt</span><br /> </td> 
   <td> Questo flusso di lavoro aggiorna le sottoscrizioni alle notifiche sui dispositivi mobili. Per impostazione predefinita, viene avviata ogni 6 ore tra l’1 e la mezzanotte.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Archiviazione</span> locale del centro messaggi <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span><br /> </td> 
   <td> Questo flusso di lavoro consente di archiviare gli eventi in tempo reale in una tabella storica. Per impostazione predefinita, viene avviata ogni ora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Aggregati</span> di segnalazione <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span><br /> </td> 
   <td> Questo flusso di lavoro aggiorna gli aggregati utilizzati nei report. Per impostazione predefinita, viene avviato automaticamente alle 2 del mattino.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Condivisione di KPI con Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span><br /> </td> 
   <td> Questo flusso di lavoro invia i dati KPI ogni 15 minuti da Adobe Campaign Standard ad Adobe Analytics.<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">Sincronizza con Launch</span><br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span><br /> </td> 
   <td> Questo flusso di lavoro sincronizza le proprietà dei dispositivi mobili Adobe Launch importate in Adobe Campaign Standard. Viene avviato ogni 15 minuti.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Aggiornamento dell'esecuzione</span> del recapito <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span><br /> </td> 
   <td> Questo flusso di lavoro aggiorna il tracciamento della consegna. Per impostazione predefinita, viene avviata ogni 10 minuti.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Aggiorna indicatori</span> di consegna <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span><br /> </td> 
   <td> Questo flusso di lavoro aggiorna i KPI della consegna (Indicatore prestazioni chiave). Per impostazione predefinita, viene avviata ogni ora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Aggiorna stato</span> evento <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span><br /> </td> 
   <td> Questo flusso di lavoro consente di attribuire uno stato a un evento. Sono disponibili i seguenti stati dell'evento:<br /> <strong>In sospeso</strong>: L'evento è in coda. Non è ancora stato assegnato alcun modello di messaggio.<br /> Consegna <span class="uicontrol">in sospeso</span> : L'evento è nella coda, gli è stato assegnato un modello di messaggio e viene elaborato dal recapito.<br /> <strong>Inviato</strong>: Questo stato viene copiato dai registri di consegna. Significa che la consegna è stata inviata.<br /> <strong>Ignorato dalla consegna</strong>: Questo stato viene copiato dai registri di consegna. Significa che la consegna è stata ignorata.<br /> <strong>Consegna non riuscita</strong>: Questo stato viene copiato dai registri di consegna. Significa che la consegna non è riuscita.<br /> <span class="uicontrol">Evento non preso in considerazione</span> : Impossibile collegare l'evento a un modello di messaggio. L'evento non verrà elaborato.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Aggiornamento per recapito</span><br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span><br /> </td> 
   <td> Questo flusso di lavoro consente di creare l'elenco delle regole di qualificazione delle regole di rimbalzo, nonché l'elenco dei domini e MX nella piattaforma. Questo flusso di lavoro funziona solo se è aperto HTTPS. Per impostazione predefinita, viene avviato automaticamente alle 2 del mattino.<br /> </td> 
  </tr> 
 </tbody> 
</table>

