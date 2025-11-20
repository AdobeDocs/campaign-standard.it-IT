---
title: Pianificazione del rilascio di Campaign Standard
description: In questa pagina sono elencate le prossime versioni di Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
feature: Overview
role: User
level: Beginner
exl-id: 1f48d4da-5622-4fab-af87-fcce0e40ade1
source-git-commit: d69dfd5cb214f1655563fc4a255b1f8aba834848
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 100%

---

# Pianificazione del rilascio {#release-planning}

Adobe migliora continuamente le proprie soluzioni aggiungendo nuove funzionalità, miglioramenti e correzioni.

Tutte le istanze di Adobe Campaign Standard vengono aggiornate con ogni nuova versione. Per effettuare l’aggiornamento non è richiesta alcuna azione.

Gli aggiornamenti vengono implementati in due fasi. In primo luogo, le istanze nell’ambiente di staging vengono aggiornate per consentire ai clienti di testare le nuove funzionalità e adattare la propria configurazione, se necessario. Vengono quindi aggiornate le istanze di produzione.

Tutte le date di rilascio sono soggette a modifica: visita questa pagina regolarmente per verificare la disponibilità di aggiornamenti. Gli aggiornamenti degli ambienti avvengono gradualmente, negli archi temporali indicati di seguito. Le date esatte vengono comunicate per e-mail a ciascun cliente.

## Versione 25.2 - Estate 2025 {#release-25-2-release}

Informazioni dettagliate su questa versione sono disponibili nelle [Note sulla versione](release-notes.md) all’avvio degli aggiornamenti dell’ambiente di staging.

<table>
 <thead>
  <tr>
   <th> Ambienti </th>
   <th> Date</th>
   <!--th> General Availability </th-->
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Fase </td>
   <td>Agosto </td>
   <!--td>2025 - Dates to be confirmed</td-->
  </tr>
  <tr>
   <td>Produzione </td>
   <td>Settembre </td>
   <!--td>2025 - Dates to be confirmed</td-->
  </tr>
 </tbody>
</table>

## Domande e risposte {#questions-and-answers}

**D: Che impatto hanno gli aggiornamenti?**

R: Le modifiche sono elencate nelle [Note sulla versione](../../rn/using/release-notes.md), compresi i collegamenti alla relativa documentazione. Adobe consiglia inoltre di consultare la [pagina Funzioni obsolete e rimosse](../../rn/using/deprecated-features.md). Queste pagine sono disponibili per la nuova versione nella data di aggiornamento dell’ambiente di staging.

**D: Qual è il processo di convalida?**

R: Con l’aggiornamento dell’istanza di gestione temporanea, Adobe consiglia di verificare che i processi e i casi di utilizzo funzionino correttamente con questa nuova versione e di segnalare eventuali problemi all’[Assistenza clienti di Adobe](https://helpx.adobe.com/it/enterprise/using/support-for-experience-cloud.html).

**D: Sarà possibile accedere all’istanza durante il processo di aggiornamento?**

R: No. Durante l’aggiornamento dell’istanza il database potrebbe non essere accessibile per qualche minuto. Tutti i processi vengono riavviati automaticamente.

**D: I messaggi continueranno a essere inviati?**

R: No. I messaggi non verranno inviati per qualche minuto. Al termine dell’aggiornamento, i processi vengono riavviati automaticamente.

**D: I flussi di lavoro continueranno a essere eseguiti e a inviare le consegne?**

R: No. Durante l’aggiornamento della build, il server del flusso di lavoro e l’MTA vengono entrambi interrotti. Ciò significa che i flussi di lavoro non verranno eseguiti e le consegne non verranno inviate per qualche minuto. Non è richiesta alcuna azione: i flussi di lavoro verranno avviati nuovamente non appena l’istanza sarà stata aggiornata.

**D: I collegamenti di tracciamento nei messaggi continueranno a funzionare durante l’aggiornamento?**

R: Sì, funzioneranno. Non è possibile inviare nuove e-mail durante l’aggiornamento, ma i collegamenti di tracciamento inclusi nelle e-mail già inviate saranno operativi.

**D: Come posso sapere se l’aggiornamento è stato completato?**

R: Quando accedi a Campaign, viene visualizzato un pop-up di notifica della versione, con la versione più recente.

Per eventuali altre domande, contatta l’[Assistenza clienti di Adobe](https://helpx.adobe.com/it/enterprise/using/support-for-experience-cloud.html).
