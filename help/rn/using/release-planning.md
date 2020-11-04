---
title: Pianificazione del rilascio di Campaign Standard
description: In questa pagina sono elencate le prossime versioni di Adobe Campaign Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
discoiquuid: null
translation-type: tm+mt
source-git-commit: e57fb3ad898be580828fbe031faf0bc3664246eb
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 98%

---


# Pianificazione del rilascio {#release-planning}

Adobe migliora continuamente le proprie soluzioni aggiungendo nuove funzionalità, miglioramenti e correzioni.

Tutte le istanze di Adobe Campaign Standard vengono aggiornate con ogni nuova versione. Per effettuare l’aggiornamento non è richiesta alcuna azione.

Gli aggiornamenti vengono distribuiti in due fasi. In primo luogo, le istanze di stage vengono aggiornate per consentire ai clienti di testare le nuove funzionalità e adattare la propria configurazione, se necessario. Vengono quindi aggiornate le istanze di produzione.

Tutte le date di rilascio sono soggette a modifica: si consiglia di visitare questa pagina regolarmente per verificare la disponibilità di aggiornamenti.

**NOVITÀ!** Abbonati alle [notifiche di rilascio di Campaign Standard](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) per ottenere informazioni sulle prossime versioni direttamente nella tua casella in entrata.

## Release 21.1 - Rilascio di gennaio {#release-21-1-release}

Gli aggiornamenti degli ambienti avvengono gradualmente, nei tempi indicati di seguito. Informazioni dettagliate su questa versione sono disponibili nelle [Note sulla versione](../../rn/using/release-notes.md). Per ulteriori domande, contatta l’[Assistenza clienti di Adobe](https://helpx.adobe.com/it/enterprise/using/support-for-experience-cloud.html).

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
   <td>11-12 gennaio 2021<br /> </td>
  </tr>
  <tr>
   <td> Produzione<br /> </td>
   <td>18 - 25 gennaio 2021<br /> </td>
  </tr>
 </tbody>
</table>

## Domande e risposte {#questions-and-answers}

**D: Che impatto hanno gli aggiornamenti?**

R: Le modifiche sono elencate nelle [Note sulla versione](../../rn/using/release-notes.md), compresi i collegamenti alla relativa documentazione. Adobe consiglia inoltre di consultare la [pagina Funzioni obsolete e rimosse](https://helpx.adobe.com/it/campaign/kb/acs-deprecated-and-removed-features.html). Queste pagine sono disponibili per la nuova versione nella data di aggiornamento dell’ambiente di stage.

**D: Qual è il processo di convalida?**

R: Con l’aggiornamento dell’istanza di gestione temporanea, Adobe consiglia di verificare che i processi e i casi di utilizzo funzionino correttamente con questa nuova versione e di segnalare eventuali problemi all’[Assistenza clienti di Adobe](https://helpx.adobe.com/it/enterprise/using/support-for-experience-cloud.html).

**D: Sarà possibile accedere all’istanza durante il processo di aggiornamento?**

R: No. Durante l’aggiornamento dell’istanza il database potrebbe non essere accessibile per qualche minuto. Tutti i processi vengono riavviati automaticamente.

**D: I messaggi continueranno a essere inviati?**

R: No. I messaggi non verranno inviati per qualche minuto. Al termine dell’aggiornamento, i processi vengono riavviati automaticamente.

**D: I flussi di lavoro continueranno a essere eseguiti e a inviare le consegne?**

R: No. Durante l’aggiornamento della build, il server del flusso di lavoro e l’MTA vengono entrambi arrestati. Ciò significa che i flussi di lavoro non verranno eseguiti e che le consegne non verranno inviate per qualche minuto. Nessuna azione è richiesta: i flussi di lavoro verranno avviati nuovamente non appena l’istanza è aggiornata.

**D: I collegamenti di tracciamento nei messaggi continueranno a funzionare durante l’aggiornamento?**

R: Sì, funzioneranno. Non è possibile inviare nuove e-mail durante l’aggiornamento, ma i collegamenti di tracciamento inclusi nelle e-mail già inviate saranno operativi.

**D: Come posso sapere che l’aggiornamento è stato completato?**

R: Quando accedi a Campaign, viene visualizzato un pop-up di notifica della versione, con la versione più recente.

Per eventuali altre domande, contatta l’[Assistenza clienti di Adobe](https://helpx.adobe.com/it/enterprise/using/support-for-experience-cloud.html).
