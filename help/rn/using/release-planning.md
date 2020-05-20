---
title: Pianificazione della versione di Campaign Standard
description: In questa pagina sono elencate le prossime versioni di Adobe Campaign Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fb865ae08a4b0db42b71e58895976a973a2ed6b7
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 1%

---


# Pianificazione del rilascio {#release-planning}

Adobe migliora continuamente le proprie soluzioni aggiungendo nuove funzionalità, miglioramenti e correzioni.

Tutte le istanze di Adobe Campaign Standard vengono aggiornate con ogni nuova versione. Per effettuare l’aggiornamento non è richiesta alcuna azione.

Gli aggiornamenti vengono distribuiti in due fasi. In primo luogo, le istanze di Stage vengono aggiornate per consentire ai clienti di testare le nuove funzionalità e adattare la propria configurazione, se necessario. Le istanze di produzione vengono quindi aggiornate.

Tutte le date di rilascio sono soggette a modifica: consigliamo di visitare questa pagina regolarmente per verificare la disponibilità di aggiornamenti.

**NUOVO!** Iscriviti alle notifiche [di rilascio di](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) Campaign Standard per ottenere informazioni sulle prossime release direttamente nella casella in entrata.

## Release 20.3.1 - Rilascio di maggio {#release-20-3-may-release}

Gli aggiornamenti dell&#39;ambiente si verificano a ondate, nei tempi indicati di seguito. Informazioni dettagliate su questa versione sono disponibili nelle [Note](../../rn/using/release-notes.md)sulla versione. Per ulteriori domande, contatta l&#39;Assistenza clienti [Adobe](https://support.neolane.net/webApp/extranetLogin).

<table>
 <thead>
  <tr>
   <th> Ambiente<br /> </th>
   <th> Date<br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Stage<br /> </td>
   <td>26 - 27 maggio 2020<br /> </td>
  </tr>
  <tr>
   <td> Produzione<br /> </td>
   <td>28 maggio - 1 giugno 2020<br /> </td>
  </tr>
 </tbody>
</table>



## Domande e risposte {#questions-and-answers}

**D: Qual è l&#39;impatto?**

A: Le modifiche sono elencate nelle Note sulla [versione](../../rn/using/release-notes.md), compresi i collegamenti alla relativa documentazione. Adobe consiglia inoltre di consultare la pagina [Funzioni](https://helpx.adobe.com/it/campaign/kb/acs-deprecated-and-removed-features.html)obsolete e rimosse. Queste pagine sono disponibili per la nuova versione alla data di aggiornamento dell&#39;ambiente Stage.

**D: Qual è il processo di convalida?**

A: Con l&#39;aggiornamento dell&#39;istanza di staging, Adobe consiglia di convalidare i processi e i casi di utilizzo con questa nuova versione e di segnalare eventuali problemi ad [Adobe Client Care](https://support.neolane.net/webApp/extranetLogin).

**D: Sarà possibile accedere all&#39;istanza durante il processo di aggiornamento?**

A: No. Durante l&#39;aggiornamento dell&#39;istanza, il database potrebbe non essere accessibile in pochi minuti. Tutti i processi si riavviano automaticamente.

**D: I messaggi continueranno a essere inviati?**

A: No. I messaggi non verranno inviati nel giro di pochi minuti. Al termine dell&#39;aggiornamento, i processi vengono riavviati automaticamente.

**D: I flussi di lavoro continueranno a essere eseguiti e a inviare le consegne?**

A: No. Durante l&#39;aggiornamento della build, il server del flusso di lavoro e MTA vengono entrambi interrotti. Ciò significa che i flussi di lavoro non verranno eseguiti e che le consegne non verranno inviate nel giro di pochi minuti. Nessuna azione richiesta: i flussi di lavoro inizieranno nuovamente non appena l&#39;istanza viene aggiornata.

**D: I collegamenti di tracciamento nei messaggi continueranno a funzionare durante l&#39;aggiornamento?**

A: Sì, funzioneranno. Non è possibile inviare nuove e-mail durante l&#39;aggiornamento, ma i collegamenti di tracciamento inclusi nelle e-mail già inviate saranno operativi.

**D: Come posso sapere che l&#39;aggiornamento è stato completato?**

A: Quando accedete a Campaign, viene visualizzata una finestra a comparsa di notifica della versione, con l&#39;ultima versione.

Per qualsiasi altra domanda, contatta l&#39;Assistenza clienti [Adobe](https://support.neolane.net/webApp/extranetLogin).
