---
title: Flussi di lavoro tecnici
seo-title: Flussi di lavoro tecnici
description: Flussi di lavoro tecnici
seo-description: I flussi di lavoro tecnici sono flussi di lavoro integrati per gestire i processi tecnici in background in Adobe Campaign, garantendo il corretto comportamento della piattaforma.
page-status-flag: never-activated
uuid: 6 e 763 dc 1-e 1 d 3-4 d 94-bc 0 b-ef 5 b 1703 d 8 e 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: riferimento
topic-tags: application-settings
discoiquuid: e 9 f 147 bd -6 a 5 b -4 b 82-b 9 bb -311 e 38 e 22 c 62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2541b6dadd005c74d6bb737a0e3692e63a5b85db

---


# Technical workflows{#technical-workflows}

I flussi di lavoro tecnici vengono forniti con Adobe Campaign. I flussi di lavoro tecnici sono operazioni o processi pianificati su base regolare sul server.

Consentono di eseguire operazioni di manutenzione sul database, di sfruttare le informazioni di tracciamento contenute nelle consegne e di aggiornare i processi provvisori sulle consegne.

Functional administrators can access technical workflows under the **[!UICONTROL Administration > Application settings > Workflows]** menu.

>[!NOTE]
>
>In qualità di amministratore funzionale, potete riavviare o mettere in pausa i flussi di lavoro tecnici e modificarne le proprietà e la struttura.

![](assets/technical_workflows.png)

## List of technical workflows {#list-of-technical-workflows}

I flussi di lavoro tecnici vengono utilizzati per gestire in Adobe Campaign i processi di sfondo e tecnici autoattivati.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etichetta</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>Descrizione</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Test A/B</span><br /> </td> 
   <td> <span class="uicontrol">Abtest</span><br /> </td> 
   <td> Questo flusso di lavoro analizza i registri di tracciamento di ciascuna variante. Alla fine del periodo di test A/B, calcola automaticamente la variante vincente. By default, it is started every day.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Fatturazione</span><br /> </td> 
   <td> <span class="uicontrol">fatturazione</span><br /> </td> 
   <td> Questo flusso di lavoro invia tramite e-mail il rapporto sull'attività del sistema all'utente "fatturazione". By default, it is automatically started every day at 1am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Pulizia del database</span><br /> </td> 
   <td> <span class="uicontrol">pulizia</span><br /> </td> 
   <td> Questo flusso di lavoro è il flusso di lavoro di manutenzione del database: esegue statistiche e processi diversi ed elimina i dati obsoleti dal database in base alla configurazione definita. By default, it is automatically started every day 4am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Previsioni</span><br /> </td> 
   <td> <span class="uicontrol">previsioni</span><br /> </td> 
   <td> Questo flusso di lavoro esegue l'analisi delle consegne memorizzate nelle previsioni provvisorie (creazione dei registri provvisori). By default, it is started every day at 1am. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Importazione di un pubblico condiviso</span><br /> </td> 
   <td> <span class="uicontrol">Importsharedaudience</span><br /> </td> 
   <td> Questo flusso di lavoro sincronizza i dati del pubblico di Adobe Experience Cloud importati in Adobe Campaign. By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Condivisione istantanea dei report</span><br /> </td> 
   <td> <span class="uicontrol">Reportsendingnow</span><br /> </td> 
   <td> Questo flusso di lavoro viene avviato non appena un rapporto viene pianificato. It converts your report into a pdf file then sends it in an email to the targeted recipients.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">KPI riconciliazione con Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">Kpiriconciliazione</span><br /> </td> 
   <td> Questo flusso di lavoro recupera i KPI dal servizio Reporting una volta al giorno e li unisce ai dati provenienti da Adobe Analytics. Quindi invia la differenza se necessario. By default, it is started every day at 4.20am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Gestione rinunce NMAC</span><br /> </td> 
   <td> <span class="uicontrol">Mobileelseptoutmgt</span><br /> </td> 
   <td> Questo flusso di lavoro aggiorna le sottoscrizioni alle notifiche sui dispositivi mobili. By default, it is started every 6 hours between 1am and midnight.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Archiviazione locale del messaggio</span><br /> </td> 
   <td> <span class="uicontrol">Mcsynch_ local</span><br /> </td> 
   <td> Questo flusso di lavoro archivia gli eventi in tempo reale in una tabella storica. By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Aggregazione di rapporti</span><br /> </td> 
   <td> <span class="uicontrol">Reportingaggregates</span><br /> </td> 
   <td> Questo flusso di lavoro aggiorna gli aggregati utilizzati nei rapporti. By default, it is automatically started at 2am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Condivisione di KPI con Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">Kpisharing</span><br /> </td> 
   <td> This workflow pushes KPI data every 15 minutes from Adobe Campaign Standard to Adobe Analytics.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Aggiornare l'esecuzione della consegna</span><br /> </td> 
   <td> <span class="uicontrol">Updatedeliveryexecinfo</span><br /> </td> 
   <td> Questo flusso di lavoro aggiorna il tracciamento della distribuzione. By default, it is started every 10 minutes.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Indicatori di consegna degli aggiornamenti</span><br /> </td> 
   <td> <span class="uicontrol">Updatedeliveryindicator</span><br /> </td> 
   <td> Questo flusso di lavoro aggiorna i KPI della distribuzione (Indicatori prestazioni chiave). By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Aggiornare lo stato dell'evento</span><br /> </td> 
   <td> <span class="uicontrol">Updateeventsstatus</span><br /> </td> 
   <td> Questo flusso di lavoro consente di attribuire uno stato a un evento. The following event statuses are available:<br /> <strong>Pending</strong>: The event is in a queue. Non è stato ancora assegnato alcun modello di messaggio.<br /><span class="uicontrol">Consegna</span> in sospeso: L'evento è in coda, un modello di messaggio è stato assegnato ad esso e lo sta elaborando.<br /><strong>Inviato</strong>: Questo stato viene copiato dai registri di consegna. Indica che la consegna è stata inviata.<br /><strong>Ignorato dalla distribuzione</strong>: Questo stato viene copiato dai registri di consegna. Ciò significa che la distribuzione è stata ignorata.<br /><strong>Consegna non riuscita</strong>: Questo stato viene copiato dai registri di consegna. Indica che la consegna non è riuscita.<br /><span class="uicontrol">L'evento non è considerato</span> : L'evento non è stato collegato a un modello di messaggio. The event will not be processed.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Aggiornamento per il recapito</span><br /> </td> 
   <td> <span class="uicontrol">Deliverabilityupdate</span><br /> </td> 
   <td> Questo flusso di lavoro consente di creare l'elenco delle regole di qualifica delle regole di rimbalzo, nonché l'elenco dei domini e MX nella piattaforma. Questa funzione funziona solo se l'HTTPS è aperto. By default, it is automatically started at 2am.<br /> </td> 
  </tr> 
 </tbody> 
</table>

