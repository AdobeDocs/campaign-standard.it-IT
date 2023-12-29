---
title: Note sulla versione 2019
description: In questa pagina sono elencate tutte le versioni di Adobe Campaign Standard del 2019.
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 6a53e6f5-9b69-4068-ab7d-10e22e266277
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '7674'
ht-degree: 8%

---

# Note sulla versione 2019{#release-notes-2019}

## Versione 19.4 - dicembre 2019 {#release-19-4---october-2019}

**Novità**

<table> 
 <thead> 
  <tr> 
   <th> <strong>California Consumer Privacy Act (CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>CCPA è la nuova legge sulla privacy dello Stato della California che armonizza e modernizza i requisiti di protezione dei dati, in vigore dal 1° gennaio 2020. Il CCPA si applica ai clienti di Adobe Campaign che detengono i dati per i soggetti residenti in California.</p>
   <p>Oltre alle funzionalità per la privacy già disponibili in Adobe Campaign (tra cui la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), vogliamo sfruttare l’opportunità di includere funzionalità aggiuntive per agevolare la conformità a CCPA:</p>
   <ul>
    <li>Diritto di accesso e diritto alla cancellazione: stiamo sfruttando le funzionalità aggiunte per il RGPD. <a href="https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#righttoaccess">Ulteriori informazioni</a> </li>
    <li><p>Durante la creazione di una richiesta di accesso a dati personali, il tipo di regolamento (RGPD o CCPA) è stato aggiunto al servizio core per la privacy. Dovresti utilizzare questo metodo per tutte le richieste di accesso ed eliminazione. L’utilizzo dell’API e dell’interfaccia di Campaign per le richieste di accesso ed eliminazione è obsoleto. Consulta l’articolo <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=it#">Funzioni obsolete e rimosse</a>.</p></li>
    <li>A <strong>Rinuncia CCPA</strong> Questo campo è stato aggiunto alla risorsa Profili per consentire agli utenti di Adobe Campaign di verificare se un consumatore ha rinunciato alla vendita di Informazioni personali. <a href="https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#ccpa">Ulteriori informazioni</a>.</li>
  </ul>
    <p>Consulta il <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">video tutorial</a>.</p>
</td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integrazione con Microsoft Dynamics 365 (GA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 
    <p>È ora disponibile l’integrazione tra Adobe Campaign Standard e Microsoft Dynamics 365. Potrai trasferire i tuoi record di contatti ed entità personalizzate da Dynamics 365 a Campaign e recuperare i dati degli eventi e-mail da Campaign a Dynamics 365 per un migliore allineamento vendite/marketing.</p>
    <p>Consulta la sezione <a href="../../integrating/using/d365-acs-get-started.md">documentazione dettagliata</a> per configurare questa integrazione.</p>
  </td>
  </tr> 
 </tbody> 
</table>

**Miglioramenti**

* La finestra a comparsa relativa al consenso per il reporting dinamico è stata aggiornata per includere l’integrazione con Adobe Campaign Standard e Microsoft Dynamics 365. Accettando i termini, i dati del profilo verranno inclusi quando si utilizzano l’integrazione Adobe Campaign Standard/Microsoft Dynamics 365 e il reporting dinamico. [Ulteriori informazioni](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* È stato risolto un problema che causava la visualizzazione di date di contatto errate durante la ricezione di avvisi di consegna.
* Quando un evento di messaggio transazionale viene inviato con un parametro di contesto sconosciuto, Campaign ora restituisce un messaggio di errore &quot;400&quot; invece di &quot;500&quot;. (CAMP-28632)
* Una nuova **Escludi bozza** Il segmento è stato aggiunto nel reporting dinamico. Questo segmento ora è selezionato per impostazione predefinita per filtrare i rapporti. [Ulteriori informazioni](../../reporting/using/list-of-components-.md#segments)
* Il **Scadenza messaggio** l&#39;opzione è stata aggiunta alla notifica push. Consente di specificare una data di scadenza in cui il messaggio non verrà più inviato da Apple (APNS) o Android (FCM). [Ulteriori informazioni](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* Sono stati apportati miglioramenti alla **Carica file** attività: i registri del flusso di lavoro sono stati resi più chiari e dettagliati in merito all’errore che si verifica quando un file non viene caricato. La transizione in uscita generata durante l’attivazione di **Mantieni i rifiuti in un file** l&#39;opzione è stata rinominata **Rifiuti**. [Ulteriori informazioni](../../automating/using/load-file.md)
* Sono stati aggiunti registri multilingue correlati ai registri di invio per comprendere meglio gli errori di invio dovuti alla mancanza di lingue nei file CSV caricati.

**Miglioramenti di sicurezza**

* È stato risolto un problema che si verificava durante l’eliminazione di informazioni di un profilo in quarantena tramite una richiesta di privacy, causando la rimozione di tutti i dati eccetto l’indirizzo e-mail nell’elenco di quarantena.
* È stata migliorata la sicurezza per la protezione contro iniezioni nelle intestazioni delle e-mail.
* È stata migliorata la sicurezza per la protezione contro gli attacchi SSRF in cui è possibile utilizzare espressioni xtk (e-mail HTML, contenuto di testo e oggetto, SMS e contenuti di notifiche push).

**Miglioramenti di E-mail Designer**

* È stato risolto un problema che impediva il tracciamento dell’annullamento dell’abbonamento, dei collegamenti di abbonamento e della pagina di destinazione quando venivano inseriti in un’e-mail. (CAMP-37809)
* È stato risolto un problema che poteva causare errori durante la creazione di una nuova e-mail e la selezione di un modello. (CAMP-38000)
* Quando modifichi un collegamento tramite E-mail designer, ora puoi utilizzare **Sottolinea collegamento** opzione. Inoltre, un **Target** è stata aggiunta con il valore predefinito impostato su **Nessuno**. [Ulteriori informazioni](../../designing/using/styles.md#about-styling-links)
* È stato risolto un problema relativo ai colori dei collegamenti nei componenti di testo nel corpo di un messaggio e-mail. (CAMP-37330)
* È stato risolto un problema che impediva la rimozione dei collegamenti associati durante l’eliminazione di un’immagine. (CAMP-37234)
* È stato risolto un problema che impediva il salvataggio delle modifiche su **Ordine** impostazioni di contenuto dinamico in una condizione. (CAMP-36883)
* È stato risolto un problema che si verificava durante la ricerca di pagine di destinazione. La ricerca è stata estesa dalle prime 50 create a tutto il database. (CAMP-36839)
* È stato risolto un problema che si verificava durante il salvataggio delle modifiche sul mittente dell’e-mail in **Da: Nome** campo. (CAMP-36606)
* L’avviso di compatibilità del componente carosello è stato modificato per riflettere i client e-mail supportati.
* È stato risolto un problema di visualizzazione su dispositivi mobili. L’attributo height è ora sempre impostato su &quot;height: auto&quot; (altezza: automatica) quando si aggiunge o si carica una nuova immagine in un messaggio e-mail. (CAMP-35497)
* È stato risolto un problema che causava la perdita di tag di stile e metadati nel HTML durante l’eliminazione di un frammento da un componente struttura. (CAMP-35390)
* È stato risolto un problema relativo ai frammenti durante l’aggiornamento del contenuto riutilizzabile. (CAMP-35186)
* È stato risolto un problema che si verificava durante la visualizzazione del contenuto condizionale solo per dispositivi mobili nelle e-mail. (CAMP-35155)
* È stato risolto un problema che causava la visualizzazione casuale di spazi unificatori di larghezza zero. (CAMP-35116)
* È stato risolto un problema relativo alla posizione dei pulsanti nella **Salva come frammento** .
* È stato risolto un problema di anteprima che si verificava con l’aggiunta di un tag HTML in un titolo immagine e in un testo alternativo.
* È stato risolto un problema che si verificava durante la modifica, nella finestra di E-mail designer, dei collegamenti creati nelle e-mail dall’editor legacy.
* È stato risolto un problema che lasciava tag di stile duplicati nel contenuto.
* È stato risolto un problema relativo al formato della data che si verificava durante l’inserimento di un campo di personalizzazione in un messaggio e-mail.
* È stato risolto un problema di salvataggio che si verificava passando dalla modalità HTML al testo normale.
* È stato risolto un problema che si verificava facendo clic sull’opzione blocca e sblocca, che aggiungeva valori di margine nel pannello delle proprietà di stile in linea.
* È stato risolto un problema relativo alle dimensioni dell’anteprima mobile per un migliore rendering.
* È stato risolto un problema relativo alle dimensioni dei pulsanti nei modelli e nei frammenti.
* È stato risolto un problema relativo alle dimensioni delle immagini quando venivano inserite in un componente pulsante.

**Altre modifiche**

* L’intervallo di tempo predefinito per il quale i dati vengono visualizzati nelle pagine dei KPI di consegna e nella pagina Reporting dinamico è stato allineato per evitare discrepanze nei risultati di reporting. (CAMP-35148)
* Nei registri è stato aggiunto un messaggio di errore alla scadenza del certificato dell’applicazione.
* L’anteprima del calcolo del payload ora include dimensioni del campo personalizzato per evitare errori di notifica push. (CAMP-35303)
* Il nome del **Rifiuta file** nel **Carica file** L&#39;attività ora può essere personalizzata nello stesso modo in cui nella **Esportazione file** attività.
* Ora è possibile accedere tramite l’API a tutte le entità personalizzate non collegate a alcuna entità predefinita.
* Prestazioni del database migliorate su risorse di grandi dimensioni.
* Sono state rese più chiare le descrizioni di alcuni errori che si verificavano durante l’invio di messaggi SMS. (CAMP-36558)
* Ora viene visualizzato un messaggio di errore durante l’esecuzione del di un flusso di lavoro **Scheduler** l’attività che è connessa a se stessa, direttamente o tramite diverse attività, in quanto ciò potrebbe causare il blocco del server del flusso di lavoro dell’istanza.
* Sono stati apportati miglioramenti per facilitare la risoluzione dei problemi dei messaggi transazionali: il collegamento &quot;Dati&quot; è stato rinominato &quot;Ultimi eventi transazionali&quot; nella schermata di configurazione dell’evento, ora elenca gli eventi ricevuti ordinati in ordine decrescente. Inoltre, è stato creato un nuovo stato di evento transazionale: &quot;targetingFailed&quot;. Quando il modulo di messaggistica transazionale non riesce ad arricchire un collegamento utilizzato per il targeting dei messaggi, l’evento transazionale ora si trova in questo nuovo stato (invece dello stato &quot;routingFailed&quot;).
* Sono stati apportati miglioramenti all’interfaccia per limitare l’accesso alle pagine di destinazione a specifiche unità geografiche o organizzative. Lo scopo è quello di avvisare che la pagina di destinazione può essere soggetta a condizioni di visibilità: la selezione di un’unità geografica e organizzativa durante la creazione di una pagina di destinazione è ora obbligatoria. Una volta selezionata un&#39;unità, ora viene visualizzato un banner con le relative informazioni. Il messaggio di errore visualizzato durante il test della pagina di destinazione è stato reso più chiaro.
* Nelle API Campaign Standard, le chiavi personalizzate non possono essere modificate utilizzando un’operazione PATCH se il valore della chiave è diverso dalla chiave di origine o se si utilizza come URI la propria chiave aziendale invece di quella fornita da Adobe.
* La lingua &quot;albanese - Macedonia&quot; è stata aggiunta all’elenco a discesa delle lingue preferite. (CAMP-35396)

**Patch**

* È stato risolto un problema che impediva l’ordinamento o la ricerca dei rapporti pianificati.
* È stato risolto un problema relativo alle regole Triggers che causava la confusione tra le regole AND e OR.
* È stato risolto un problema a causa del quale la proprietà Mobile veniva visualizzata come Eliminata in Launch. (CAMP-35382)
* È stato risolto un problema che impediva la sincronizzazione delle proprietà dei dispositivi mobili Adobe Launch in Adobe Campaign. (CAMP-35411, CAMP-35089, CAMP-35014, CAMP-35487)
* È stato risolto un problema a causa del quale i messaggi push transazionali non riuscivano quando gli eventi venivano arricchiti con i dati di profilo. (CAMP-34385)
* È stato risolto un problema che impediva la sincronizzazione delle proprietà mobili in più ambienti. (CAMP-37060)
* È stato risolto un problema che si verificava selezionando, in una notifica push, un modello utilizzando una formula di data di contatto. (CAMP-35300)
* È stato risolto un problema che poteva causare l’arresto anomalo del servizio di invio del messaggio. (CAMP-35287)
* È stato risolto un problema relativo alle direct mailing ricorrenti, tutti definiti con la data del primo evento. (CAMP-35139)
* È stato risolto un problema relativo alla nuova estensione di **Profili** risorse personalizzate non disponibili per le query. (CAMP-35119)
* È stato corretto il **Ripristina struttura database** modalità per le istanze con la configurazione Condivisione attivata. (CAMP-35118)
* È stato risolto un problema che causava un errore di registro SQL durante l’aggiunta di dati aggregati nei broadLog. (CAMP-35034)
* È stato risolto un problema relativo alle transizioni durante la creazione di un’ **Segmentazione** attività. (CAMP-35033)
* È stato risolto un problema in **Query** attività che ha impedito **encryption_aescbcDecrypt** dalla decrittografia del **encryption_aescbcEncrypt** funzione. (CAMP-34952)
* È stato risolto un problema che poteva impedire il **Registri di tracciamento** da mostrare nelle consegne. (CAMP-34855)
* È stato risolto un problema che si verificava con l’utilizzo di una **Ottimizzazione del tempo di invio** formula di data personalizzata, che poteva impedire l’invio di notifiche push a causa di errori con i dati aggiuntivi del flusso di lavoro. (CAMP-30336)
* È stato risolto un problema che poteva impedire la pubblicazione di risorse personalizzate. (CAMP-37425)
* È stato risolto un problema che impediva agli utenti amministratori di modificare i pacchetti di importazione.  (CAMP-37176)
* È stato risolto un problema nei flussi di lavoro che impediva l’invio delle bozze, se l’attività di consegna era connessa a un elemento vuoto **Read audience** attività. (CAMP-37164)
* È stato risolto un problema che impediva l’importazione di risorse personalizzate in un nuovo ambiente. (CAMP-36506)
* È stato risolto un problema nei rapporti sugli hot click che poteva causare la mancata visualizzazione delle percentuali da parte delle immagini (CAMP-36407)
* È stato risolto un problema che si verificava durante il tentativo di esportazione di un campo di descrizione della consegna. (CAMP-35467)
* È stato risolto un problema che poteva lasciare lo stato di una consegna come &quot;Inizio in sospeso&quot; anche se la consegna era terminata. (CAMP-35355)
* È stato risolto un problema che impediva la visualizzazione dei registri del flusso di lavoro dopo l’abilitazione di, quindi la disabilitazione dei registri SQL.

## Versione 19.3 - Luglio 2019 {#release-19-3---july-2019}

**Novità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Attività API esterna (versione beta pubblica)<br /> </td> 
   <td> <p>Per una personalizzazione più approfondita, l’attività API esterna consente di inserire dati da sistemi esterni in un flusso di lavoro tramite una chiamata API REST. Gli endpoint REST possono essere un sistema di gestione clienti, un endpoint REST Adobe I/O Runtime o Adobe Experience Cloud (ad esempio Data Platform, Target, Analytics, Campaign).</p><p>Questa funzionalità è attualmente in versione beta pubblica.</p><p>Per ulteriori informazioni, consulta la <a href="../../automating/using/external-api.md">documentazione dettagliata</a> e il <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">video tutorial</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Rapporto sul segmento del flusso di lavoro<br /> </td> 
   <td> <p>Questa funzione consente agli addetti al marketing di suddividere le prestazioni di consegna per codice di segmento. Quando crei un flusso di lavoro e utilizzi un’attività di segmentazione per assegnare segmenti al pubblico a cui verrà consegnata l’attività, questi segmenti possono ora essere inseriti nella stessa consegna. Questo consente di visualizzare le statistiche di apertura e clic basate su più segmenti all’interno di una singola consegna.</p><p>Per ulteriori informazioni, consulta la <a href="../../reporting/using/creating-a-report-workflow-segment.md">documentazione dettagliata</a> e il <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">video tutorial</a>.</p></td>
  </tr> 
 </tbody> 
</table>

**Miglioramenti di sicurezza**

* È stato risolto un problema di sicurezza per impedire attacchi Denial of Service (DoS) su richieste non valide per ottenere immagini. (CAMP-33454)

**Miglioramenti di E-mail Designer**

* È stato risolto un problema che aggiungeva tag di stile HTML aggiuntivi a un modello HTML ogni volta che veniva aggiunto un componente, il che poteva aumentare notevolmente le dimensioni del modello. (CAMP-34694)
* È stato risolto un problema che poteva impedire la disponibilità di alcune opzioni di menu della barra degli strumenti superiore destra. (CAMP-34577)
* È stato risolto un problema che si verificava quando il blocco di contenuto URL della pagina mirror veniva inserito in un contenuto e-mail. (CAMP-34779)
* È stato risolto un problema che si verificava durante l’utilizzo del codice JSPP in un’e-mail, rendendo difficile la modifica del contenuto. (CAMP-34574)
* È stato risolto un problema che causava il troncamento delle immagini in primo piano quando veniva aggiunto loro un collegamento ipertestuale. (CAMP-34382)
* È stato risolto un problema di visualizzazione che si verificava con l’utilizzo di E-mail Designer con Firefox. (CAMP-34364)
* Sono stati risolti diversi problemi che si verificavano con la modalità Avanzata durante la definizione del contenuto dinamico in un messaggio e-mail. (CAMP-34351, CAMP-34333, CAMP-34331)
* Sono stati risolti diversi problemi che si verificavano con l’editor di regole per contenuti dinamici (CAMP-34304, CAMP-34303).
* È stato risolto un problema che poteva impedire la visualizzazione del campo Collegamento nel riquadro Impostazioni di E-mail Designer (CAMP-33749).
* È stato risolto un problema relativo all’icona YouTube di dimensioni eccessive nelle e-mail inviate. (CAMP-33726)
* È stato risolto un problema di sicurezza che rendeva modificabile il contenuto della pagina speculare. (CAMP-33691)
* È stato risolto un problema che causava l’interruzione dell’output HTML quando si utilizzava il simbolo maggiore di nel contenuto dinamico. (CAMP-33688)
* È stato risolto un problema che si verificava durante l’utilizzo dell’opzione Annulla durante la modifica del testo in E-mail Designer. (CAMP-32565)
* È stato risolto un problema che causava la creazione di tag aggiuntivi durante l’annullamento degli stili invece di rimuoverli. (CAMP-32359)
* Ora puoi definire se ogni componente utilizzato in un’e-mail verrà visualizzato solo sui dispositivi desktop o solo sui dispositivi mobili.
* Ora puoi impostare la larghezza e l’altezza di un componente di contenuto Social.
* È stato risolto un problema che impediva la rimozione del vecchio codice sorgente del contenuto dinamico dopo l’eliminazione di tale contenuto dinamico.
* È stato risolto un problema che poteva impedire l’aggiornamento dell’oggetto di un’e-mail dopo la sua modifica.
* È stato risolto un problema che impediva la selezione di una struttura di colonne n:n una volta rilasciata nell’area di lavoro.
* È stato risolto un problema a causa del quale la miniatura del messaggio risultava sfocata nel dashboard e-mail.
* È stato risolto un problema che impediva la corretta visualizzazione dello sfondo per le e-mail ricevute in Outlook.
* Sono stati risolti alcuni problemi di ordinamento nella pagina Home di E-mail Designer.
* È stato risolto un problema che si verificava durante la duplicazione di varianti quando si utilizzava contenuto dinamico.
* Alcuni campi indesiderati sono stati rimossi dal riquadro Impostazioni di E-mail Designer.

**Altri miglioramenti**

* Grazie all’integrazione con Adobe Experience Platform Location Services, Adobe Campaign è ora compatibile per inviare messaggi di marketing basati sulla posizione agli abbonati alla tua app mobile tramite l’SDK di Experience Platform. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md).
* La funzione di reporting è stata migliorata per offrire un’esperienza migliore. Per utilizzare questa funzione, devi accettare il contratto di utilizzo per Reporting dinamico. Per ulteriori informazioni, consulta [documentazione dettagliata](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* Nei flussi di lavoro è stata aggiunta una nuova opzione per visualizzare in anteprima le prossime dieci esecuzioni di un flusso di lavoro. Per ulteriori informazioni, consulta [documentazione dettagliata](../../automating/using/scheduler.md).
* Nell’attività Scheduler, una nuova opzione consente di selezionare un giorno specifico di una settimana specifica per le consegne mensili. Per ulteriori informazioni, consulta [documentazione dettagliata](../../automating/using/scheduler.md).
* Durante la creazione di consegne ricorrenti senza periodo di aggregazione, il dashboard di consegna ora consente di richiedere una conferma prima dell’invio della consegna. Per ulteriori informazioni, consulta [documentazione dettagliata](../../sending/using/confirming-the-send.md).
* Ora puoi personalizzare l’etichetta di una consegna con le variabili evento dichiarate nell’attività del segnale esterno del flusso di lavoro. Per ulteriori informazioni, consulta [documentazione dettagliata](../../automating/using/calling-a-workflow-with-external-parameters.md).
* La query di eliminazione RGPD è stata migliorata per migliorare le prestazioni. (CAMP-33504)
* L’opzione &quot;ftp&quot; è stata rimossa dall’interfaccia di configurazione dell’account esterno. (CAMP-34472)
* Ora puoi abilitare e disabilitare l’opzione della modalità di test SMTP per ogni messaggio e-mail. Per ulteriori informazioni, consulta [documentazione dettagliata](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**Altre modifiche**

* È stato aggiunto un avviso nell’interfaccia delle proprietà di consegna. Specifica che le consegne vengono preparate in base al loro periodo di aggregazione e scongelate per chiamare il flusso di lavoro più volte al giorno, è necessario assicurarsi che non abbiano alcun periodo. (CAMP-34393)
* È stato aggiunto un avviso nelle schermate di configurazione delle risorse personalizzate. È consigliabile utilizzare un massimo di 30 caratteri per gli ID di risorse personalizzati. Questo vale anche per campi di risorse personalizzati, chiavi, indici e collegamenti.
* Ora viene visualizzato un messaggio quando si tenta di eliminare un messaggio transazionale utilizzato da una pagina di destinazione come messaggio di conferma.
* Ora viene visualizzato un avviso nei registri dei flussi di lavoro quando un’attività è in esecuzione da più di 6 ore. Questo non si applica alle attività Push notification, Delivery, Signal, Start, End, Fork , AND-joint, Schedule e Wait.
* Ora nei registri dei flussi di lavoro viene visualizzato un avviso quando si raggiunge il numero massimo di flussi di lavoro in esecuzione simultanea.
* I flussi di lavoro che si trovano nello stato di pausa o errore per più di 7 giorni ora vengono interrotti per ridurre lo spazio su disco. L’attività di pulizia viene visualizzata nei registri del flusso di lavoro.
* Quando si utilizza un’attività &quot;Transfer file&quot;, ora viene registrato un errore se la dimensione del file supera lo spazio disponibile su disco.
* L’azione Reindirizza all’URL di destinazione non può più essere selezionata per il pulsante secondario nei messaggi in-app.

**Patch**

* È stato risolto un problema che poteva causare un errore nelle richieste di accesso RGPD.
* È stato risolto un problema che poteva causare l’eliminazione dei trigger quando venivano ricevuti più trigger per un profilo univoco.
* È stato risolto un problema che poteva causare un messaggio di errore di pubblicazione delle risorse personalizzate errato dopo l’accesso.
* È stato risolto un problema che causava la visualizzazione di una pagina vuota durante la creazione o l’estensione di una risorsa personalizzata.
* È stato risolto un problema che impediva a un pubblico con appSubscriptionrcp come dimensione di targeting di essere disponibile per il targeting in una consegna mobile.
* È stato corretto un errore che impediva la quarantena degli indirizzi e-mail non recapitati. (CAMP-24587)
* È stato risolto un problema che si verificava durante l’aggiunta di una regola di tipologia, eliminandola quindi prima di salvare la tipologia. (CAMP-32789)
* È stato risolto un problema che poteva impedire la visualizzazione del contenuto della pagina di destinazione durante la disattivazione del contenuto dinamico. (CAMP-32924)
* È stato risolto un problema relativo alle consegne ricorrenti che si verificava durante l’utilizzo della personalizzazione sugli attributi di una consegna principale. (CAMP-32983)
* È stato risolto un problema nei flussi di lavoro che impediva la lettura dei risultati di una transizione contenente i dati dei messaggi SMS in arrivo. (CAMP-33134)
* È stato risolto un problema nei flussi di lavoro che si verificava quando si combinavano attività di fork e di esclusione per creare tipi di pubblico. (CAMP-33401)
* È stato risolto un problema che poteva impedire la visualizzazione del contenuto di una pagina speculare e l’invio di messaggi di prova per consegne ricorrenti. (CAMP-33413)
* È stato risolto un problema che causava un errore durante l’utilizzo di un’attività di unione tra profili e pubblico. Questo problema era causato da un’incompatibilità delle chiavi di identificazione nelle transizioni di input. (CAMP-33713)
* È stato risolto un problema nelle attività Test che impediva all’espressione &quot;recCount&quot; di utilizzare la sintassi corretta quando si faceva doppio clic su di essa. (CAMP-33756)
* È stato risolto un problema che poteva causare un messaggio di errore durante l’apertura dei registri del flusso di lavoro tecnico Fatturazione. (CAMP-34313)
* È stato risolto un problema nelle pagine di destinazione che poteva verificarsi durante la configurazione dei campi casella di controllo con le sottoscrizioni. (CAMP-34369)
* È stato risolto un problema che si verificava durante la configurazione di un elenco e l’aggiunta del campo &quot;icon&quot;. (CAMP-34585)
* È stato risolto un problema che impediva l’utilizzo dei simboli &quot;|&quot; e &quot;%&quot; come separatori di data e ora nelle attività del flusso di lavoro Load file. (CAMP-34706)
* È stato risolto un problema che si verificava durante l’utilizzo delle condizioni di visibilità con le caselle di controllo nelle pagine di destinazione. (CAMP-34802)
* È stato risolto un problema nell’attività Enrichment che impediva la visualizzazione dei campi nella scheda &quot;Dati aggiuntivi&quot;, se la dimensione di filtro era impostata su tracking logs e la dimensione di destinazione su profile.
* È stato risolto un problema che causava un messaggio di errore durante l’esportazione di una risorsa &quot;workflowTemplate&quot;.
* È stato risolto un problema che impediva il salvataggio del campo &quot;Codice paese&quot; se era stato selezionato dalla finestra di dialogo durante la creazione di un nuovo profilo.
* Sono stati risolti diversi problemi che si verificavano durante l’utilizzo del modello di importazione Direct Mail (updateQuarantinesDeliveryLogsDirectMail).
* È stato risolto un problema relativo all’integrazione di Assets on Demand.
* È stato risolto un problema che si verificava durante l’ingrandimento della visualizzazione Timeline. (CAMP-33628)
* È stato risolto un problema che impediva l’invio immediato delle bozze per i messaggi e-mail con data e ora pianificate. (CAMP-33723)
* È stato risolto un problema relativo alla messaggistica transazionale che generava registri di errore alla disconnessione di un utente. (CAMP-31698)
* È stato corretto un errore che poteva verificarsi in ambienti specifici durante la pianificazione di un messaggio e-mail.
* È stato risolto un problema che causava un errore nel flusso di lavoro di esecuzione Aggiorna consegna.
* È stato risolto un problema di sicurezza che causava l’interruzione del contenuto dell’e-mail se l’oggetto conteneva più righe.


## Versione 19.2.7 - Luglio 2019 {#release-19-2-7---july-2019}

**Miglioramenti**

* La query di eliminazione RGPD è stata migliorata per migliorare le prestazioni.
* È stato risolto un problema che poteva causare arresti anomali del web dopo l’aggiornamento 19.2. (CAMP-34862)
* È stato risolto un problema che poteva impedire agli utenti non amministratori di salvare o pianificare i rapporti. (CAMP-31133)
* È stato risolto un problema che si verificava con l’utilizzo di &quot;|&quot; come separatore di data nell’attività del flusso di lavoro Load file. (CAMP-34706)

## Versione 19.2.4 - Giugno 2019 {#release-19-2-4---june-2019}

**E-mail Designer**

* È stato risolto un problema che impediva agli utenti di modificare frammenti quando nel HTML venivano utilizzati tag di stile vuoti. Questa è una correzione di follow-up per CAMP-33778 nella versione 19.2.3.

## Versione 19.2.3 - Giugno 2019 {#release-19-2-3---june-2019}

**E-mail Designer**

Nella versione 19.2 è stata introdotta una serie di miglioramenti e correzioni per ottimizzare i frammenti. I nuovi frammenti creati funzioneranno senza problemi. I frammenti creati in precedenza sono stati disattivati e devono essere migrati al nuovo formato. A questo scopo, fai clic su ciascun frammento e ne convalida la migrazione al nuovo formato. È consigliabile eseguire il test di alcuni frammenti prima di eseguirne la migrazione di tutti.

* È stato risolto un problema che impediva agli utenti di modificare un frammento dopo averlo sbloccato. Questo influenzava i frammenti esistenti durante l’aggiornamento alla versione 19.2. (CAMP-33778)
* È stato risolto un problema che si verificava con l’utilizzo di contenuto dinamico. Nel HTML sono stati aggiunti degli spazi aggiuntivi.

**Altri miglioramenti**

* È stato risolto un problema che poteva impedire la ripresa dell’invio SMS dopo una disconnessione del connettore SMS.
* È stato risolto un problema che poteva chiudere le connessioni SMPP quando TLS era abilitato.
* È stato risolto un problema che poteva chiudere le connessioni SMPP quando TLS era abilitato.
* L’opzione &quot;Launch_URL_Campaign&quot; è stata aggiunta in Campaign per gestire le proprietà delle applicazioni mobili create con l’SDK di Adobe Experience Platform Mobile.
* È stato corretto un errore a causa del quale l’opzione dell’ambiente Sandbox veniva deselezionata dopo il caricamento del certificato di una proprietà mobile appena creata e l’uscita dalla pagina delle proprietà dell’app mobile.
* È stato risolto un problema che impediva l’arricchimento del contenuto di un messaggio transazionale con le informazioni provenienti dalla risorsa Servizio. (CAMP-33707)
* È stato risolto un problema nel elenco Bloccati di pagine di destinazione del che si verificava quando si tentava di annullare l’abbonamento di profili da un servizio.

## Versione 19.2 - Maggio 2019 {#release-19-2---may-2019}

**Novità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Pannello di controllo<br /> </td> 
   <td> <p>Per migliorare l’efficienza del lavoro come utente amministratore, puoi monitorare facilmente la capacità e gestire le impostazioni delle istanze (a partire dalla gestione dei server SFTP).</p><p>Per ulteriori informazioni, consulta la <a href="https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it">documentazione dettagliata</a> e il <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/control-panel-overview.html?lang=it">video tutorial</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Notifiche locali<br /> </td> 
   <td> <p>I messaggi di notifica locale consentono di informare gli utenti quando nuovi dati diventano disponibili nelle applicazioni mobili, anche senza avere accesso a Internet o all'applicazione mobile in esecuzione in primo piano. Le notifiche locali vengono attivate da un’app mobile in un determinato momento e a seconda di un evento.</p><p>Per ulteriori informazioni, consulta la <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">documentazione dettagliata</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Miglioramento del flusso di lavoro - Aggiunta di un payload all’attività del segnale esterno<br /> </td> 
   <td> <p>Avvia un flusso di lavoro con un payload quando le condizioni definite vengono soddisfatte correttamente da un altro flusso di lavoro o una chiamata API REST per l’integrazione con i sistemi esterni. Questo include anche un nuovo <strong>test</strong> attività in cui è possibile eseguire test su questa funzionalità.</p><p>Per ulteriori informazioni, consulta la <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">documentazione dettagliata</a> e il <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">video tutorial</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Miglioramento delle pagine di destinazione - Google reCAPTCHA<br /> </td> 
   <td> <p>Sfrutta Google reCAPTCHA per evitare spam sulle pagine di destinazione senza richiedere alcuna azione da parte dei clienti.</p><p>Per ulteriori informazioni, consulta la <a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">documentazione dettagliata</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

**Miglioramenti di sicurezza**

* È stato risolto un potenziale problema di sicurezza relativo al clickjacking nell’area di lavoro di reporting.

**Miglioramenti di E-mail Designer**

* È stato risolto un problema che si verificava durante la duplicazione di frammenti e il tentativo di utilizzarli in E-mail Designer. (CAMP-33193)
* È stato risolto un problema che causava la creazione di spazi indesiderati durante l’utilizzo di elementi in linea nell’interfaccia di E-mail Designer. (CAMP-32163)
* È stato risolto un problema che eliminava alcuni attributi di tag HTML aggiuntivi aggiunti dall’utente dopo il salvataggio del contenuto dell’e-mail in E-mail Designer. (CAMP-32162)
* È stato risolto un problema che causava la visualizzazione di un tag di Microsoft Office in modalità HTML di E-mail Designer anche dopo la sua rimozione. (CAMP-32141)
* Se hai creato un messaggio e-mail utilizzando una versione precedente di E-mail Designer, all’apertura di questo contenuto viene visualizzata una finestra a comparsa in cui viene richiesto all’utente di eseguire l’aggiornamento alla versione più recente. (CAMP-31529)
* È stato risolto un problema che poteva distorcere le immagini provenienti da un’e-mail creata con E-mail Designer quando distribuita ad alcuni client di messaggistica. (CAMP-31407)
* È stato risolto un problema che impediva la corretta visualizzazione di alcuni elementi come elenchi o pulsanti in modalità testo normale durante la creazione in modalità HTML. (CAMP-32582, CAMP-32542)
* È stato risolto un problema che impediva la visualizzazione di più di 50 unità organizzative in un modello di contenuto o in proprietà di frammenti. (CAMP-32932)
* È stato risolto un problema relativo al colore di sfondo del riquadro di visualizzazione che si verificava durante la ricezione di un messaggio e-mail creato con E-mail Designer in Outlook. (CAMP-31402)
* È stato risolto un problema che poteva impedire la reattività del contenuto delle e-mail create con E-mail Designer quando veniva aperto in Outlook. (CAMP-31400)
* È stato risolto un problema che impediva il corretto funzionamento del contenuto dinamico se utilizzato in un oggetto e-mail. (CAMP-32837)
* È stato risolto un problema relativo all’oggetto e-mail che non presentava un escape corretto.
* È stato risolto un problema che impediva il caricamento dei frammenti nella palette a sinistra di E-mail Designer.
* È stato risolto un problema che impediva la visualizzazione dei frammenti creati durante l’edizione del contenuto dell’e-mail nella palette a sinistra di E-mail Designer durante l’aggiornamento dell’elenco di frammenti.
* Sono stati risolti diversi problemi che si verificavano durante l’utilizzo di contenuto dinamico in un’e-mail.
* È stato risolto un problema che si verificava con il selettore colore durante il tentativo di definire un colore utilizzando i valori RGB.
* È stato risolto un problema che impediva alla pagina speculare di essere reattiva durante la ricezione dell’e-mail su un dispositivo mobile.

**Miglioramenti alla messaggistica transazionale**

Sono stati aggiunti diversi miglioramenti al canale di messaggistica transazionale per ottimizzare il funzionamento e le prestazioni.

* La durata dei messaggi transazionali è stata estesa per garantire che tutti i messaggi vengano inviati prima della scadenza, soprattutto quando vengono eseguiti nuovi tentativi.
* Le prestazioni della messaggistica transazionale sono state migliorate distribuendo il carico su diversi thread di invio.
* Il processo di messaggistica transazionale è stato ottimizzato per poter iniziare in parallelo l’analisi multipla dello stesso messaggio.
* È stato risolto un problema che poteva causare velocità effettiva e latenza incoerenti per le notifiche push transazionali.
* È stato risolto un problema che causava la visualizzazione di un pubblico di destinazione errato per le consegne di esecuzione dei messaggi transazionali.
* È stato risolto un problema che si verificava durante l’importazione di un pacchetto con una configurazione dell’evento e il relativo messaggio transazionale. Per ulteriori informazioni, consulta [documentazione dettagliata](../../channels/using/getting-started-with-transactional-msg.md#exporting-and-importing-transactional-messages).
* È stato risolto un problema che eliminava i dati della raccolta dai profili di test creati per un messaggio transazionale contenente gli elenchi di prodotti.

**Altre modifiche**

* È stata aggiunta una nuova opzione all’account esterno SMS. Consente di limitare il numero massimo di processi MTA che inviano SMS per controllare meglio il numero di connessioni parallele. Per ulteriori informazioni, consulta [Protocollo e impostazioni del connettore SMS](https://helpx.adobe.com/it/campaign/kb/sms-connector-protocol-and-settings.html) nota tecnica.
* Quando si pubblica una risorsa con estensione API, se l’API è già stata pubblicata, ora viene aggiornata automaticamente a ogni nuova pubblicazione. In precedenza, questa azione era manuale e il mancato aggiornamento dell’API poteva interrompere il profilo o la risorsa del servizio di questa API. Per ulteriori informazioni, consulta [documentazione dettagliata](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* La dimensione Codice postale è stata rimossa da Reporting dinamico. È invece consigliabile utilizzare le dimensioni Città, Paese e Stato.
* Il trigger dell’evento del ciclo di vita &quot;Primo avvio&quot; per i messaggi in-app è stato rimosso.
* Durante l’esportazione di un pacchetto con gruppi di sicurezza, ora questo contiene i ruoli assegnati a ciascun gruppo. (CAMP-32960)
* Nell’attività Load file, una nuova opzione ti consente di verificare che le colonne del file che stai caricando corrispondano alla definizione della colonna. Per ulteriori informazioni, consulta [documentazione dettagliata](../../automating/using/load-file.md). (CAMP-32229)
* Ora è possibile avviare i flussi di lavoro con un payload, che consente di utilizzare e condividere parametri esterni tra le attività all’interno del flusso di lavoro. Per ulteriori informazioni, consulta [documentazione dettagliata](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP-29412 E CAMP-29413)
* Le API di Campaign Standard ora consentono di aggiornare le unità geografiche e organizzative dei profili utilizzando un payload. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../api/using/get-started-apis.md).
* I messaggi di errore quando un oggetto del database non è accessibile sono stati resi più chiari.
* Nell’attività Extract file, le funzionalità JavaScript sono state aggiornate durante la definizione del nome di un file da esportare. Solo la funzione formatDate è ora disponibile per l&#39;utilizzo nel campo Output. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../automating/using/extract-file.md).
* La generazione automatica dell’ID di sequenza è stata migliorata per le risorse personalizzate. Le chiavi primarie per le nuove risorse personalizzate ora sono in 64 bit per impostazione predefinita.
* È stata migliorata la modalità di test per la pubblicazione delle risorse personalizzate. Se l’ultima pubblicazione delle risorse personalizzate non è riuscita e non è stata corretta, ora viene visualizzato un messaggio di avviso per gli utenti. Dopo un errore di pubblicazione di una risorsa personalizzata, puoi eseguire il rollback all’ultima versione di lavoro. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* È stata aggiunta una nuova opzione nell’attività Trasferisci file. Ti consente di ordinare i file quando utilizzi l’azione Scarica file, in modalità SFTP. Per ulteriori informazioni, consulta [documentazione dettagliata](../../automating/using/transfer-file.md). (CAMP-33109)

**Patch**

* È stato risolto un problema che poteva causare una perdita di memoria nell’MTA in seguito al ricaricamento delle impostazioni SMS.
* È stato risolto un problema che poteva impedire la pubblicazione degli aggiornamenti del database in modalità di ripristino.
* È stato risolto un problema che causava discrepanze tra i rapporti di Adobe Analytics e Adobe Campaign Dynamic Reporting. (CAMP-25393)
* È stato corretto un errore che impediva il corretto funzionamento del flusso di lavoro di condivisione dei rapporti.
* È stato corretto un errore che impediva agli utenti di inviare messaggi in-app con il solo URL del file multimediale.
* È stato risolto un problema che causava la visualizzazione di un’app mobile anche se il relativo certificato non era stato caricato nell’istanza.
* È stato corretto un errore che impediva il funzionamento dei campi di personalizzazione durante l’utilizzo di **Eseguire il targeting per tutti gli utenti di un’app mobile** modello.
* È stato eseguito il provisioning di nuove istanze di Campaign Standard. (CAMP-32635 E CAMP-32344)
* È stato corretto un errore che impediva la personalizzazione della formula della data in un flusso di lavoro. (CAMP-30336)
* È stato risolto un problema che si verificava durante la definizione di una formula di data personalizzata che poteva impedire la disponibilità dei campi &quot;Dati aggiuntivi&quot; e &quot;Codice segmento&quot; nell’elenco a discesa. (CAMP-32383)
* È stato risolto un problema che poteva impedire alle attività &quot;Transfer file&quot; (Trasferisci file) e &quot;Extract file&quot; (Estrai file) di trovare i file rifiutati se crittografati. (CAMP-32377)
* È stato risolto un problema nelle API che poteva impedire al filtro lineCount di eseguire il rendering del conteggio totale esatto. (CAMP-31424)
* È stato risolto un problema nelle pagine di destinazione che poteva impedire ai campi di input di visualizzare il valore aggiornato dopo la sua modifica. (CAMP-31401)
* È stato risolto un problema che poteva causare l’attivazione imprevista di un’attività di segnale.
* È stato risolto un problema che poteva impedire la visualizzazione dell’anteprima e-mail quando il pubblico era vuoto.
* È stato risolto un problema nell’attività &quot;Extract file&quot; (Estrai file) che poteva generare un file mentre l’opzione &quot;Do not generate a file if the inbound transition is empty&quot; (Non generare un file se la transizione in entrata è vuota) era attivata.
* È stato risolto un problema che causava la disattivazione del flusso di lavoro Deliverability in caso di mancato completamento.
* È stato risolto un problema che poteva impedire agli utenti di salvare o pianificare i rapporti. (CAMP-31133)

## Versione 19.1.3 - marzo 2019 {#release-19-1-3---march-2019}

**Miglioramenti di E-mail Designer**

* È stato risolto un problema che impediva la modifica di un modello dopo averlo salvato.
* Sono stati risolti diversi problemi che si verificavano con l’utilizzo di un modello creato in precedenza in un messaggio e-mail.
* È stato risolto un problema che impediva ai componenti di essere nascosti nei modelli importati.

**Altri miglioramenti**

* È stato corretto un errore che si verificava durante la visualizzazione delle regole di tipologia. (CAMP-32059 E CAMP-31849)
* È stato risolto un problema che impediva la modifica delle regole di tipologia. (CAMP-31750)
* È stato risolto un problema con il processo inMail che poteva interrompersi in modo imprevisto. (CAMP-31238)

## Versione 19.1 - Febbraio 2019 {#release-19-1---february-2019}

**Novità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Miglioramenti al reporting dei canali push<br /> </td> 
   <td> <p>Sono stati aggiunti diversi miglioramenti al reporting dei canali push per consentire di misurare il coinvolgimento degli utenti in modo più intuitivo. Con questa versione, stiamo espandendo l’elenco delle metriche del canale push a tre diverse metriche: Impression, Clic, Aperture (Apertura app) per aiutarti a misurare e analizzare l’interazione degli utenti con le notifiche push in modo più efficace. Inoltre, stiamo standardizzando la definizione e l’implementazione di queste metriche. Anche il rapporto integrato sulle notifiche push è stato migliorato con visualizzazioni e metriche di uso comune.</p><p> Per ulteriori informazioni, consulta la <a href="../../reporting/using/push-notification-report.md">documentazione dettagliata</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Integrazione di Launch per l’app mobile<br /> </td> 
   <td> <p>Questa versione contiene l’integrazione di Adobe Campaign con le versioni GA delle estensioni Android e iOS per Adobe Campaign Standard in Adobe Experience Platform Launch e Mobile SDK. Queste estensioni supportano la messaggistica push, in-app e gli aggiornamenti dei profili delle app mobili.</p><p> Per ulteriori informazioni, consulta la <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html?lang=it">documentazione dettagliata</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Messaggistica in-app mobile<br /> </td> 
   <td> <p>Questa versione contiene la versione GA del canale in-app in Campaign. Dal punto di vista funzionale, le aggiunte più importanti alla versione beta sono i rapporti dinamici per il canale in-app e l’handshake sicuro tra Mobile SDK e MCIAS (Marketing Cloud In-App Messaging Service che funge da criterio in-app per l’SDK). Secure Handshake garantisce che i dati PII degli utenti non cadano in mani maligne e consente di mantenere la privacy degli utenti su un dispositivo condiviso cancellando la cache dei messaggi ogni volta che l’utente si disconnette.</p><p>Per ulteriori informazioni, consulta <a href="../../channels/using/about-in-app-messaging.md">documentazione dettagliata</a> e l'apposito <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">Tutorial in-app</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Miglioramenti al flusso di lavoro<br /> </td> 
   <td> <p>Sono state aggiunte le seguenti funzionalità del flusso di lavoro:</p> 
    <ul> 
     <li> Ora puoi copiare e incollare le attività all’interno di un flusso di lavoro o di un altro flusso di lavoro dalla stessa istanza di Campaign. In questo modo, puoi duplicare facilmente un intero flusso di lavoro o attività specifiche e mantenere le impostazioni inizialmente definite. Per ulteriori informazioni, consulta <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">documentazione dettagliata</a>. (CAMP-20014) </li> 
     <li> Quando si utilizza <strong>Carica file</strong> attività, è ora possibile aggiungere una marca temporale al nome del file contenente i record rifiutati. Per ulteriori informazioni, consulta la <a href="../../automating/using/load-file.md#configuration">documentazione dettagliata</a>. </li> 
     <li> <strong>Query</strong> e <strong>Segmentazione</strong> Le attività ora consentono di abilitare una transizione in uscita se non recuperano dati. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Miglioramenti di sicurezza**

* Il codice HTML della pagina di destinazione generata è stato aggiornato per impedire l’indicizzazione del motore di ricerca.

**Miglioramenti di E-mail Designer**

* È ora disponibile un set di quattro modelli di e-mail reattive all’avanguardia progettati da artisti di Behance.

  Per ulteriori informazioni, consulta la [documentazione dettagliata](../../designing/using/using-reusable-content.md#content-templates).

* La nostra nuova esperienza di onboarding ti aiuta ad avviare più rapidamente la creazione di e-mail e a fornire un accesso più semplice alla documentazione e ai tutorial.

  Per ulteriori informazioni, consulta la [documentazione dettagliata](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page).

* Ora puoi configurare il numero di colonne e la larghezza in base alle tue esigenze.

  Per ulteriori informazioni, consulta la [documentazione dettagliata](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

* Quando esegui la modifica in visualizzazione mobile, puoi nascondere alcuni componenti solo in visualizzazione mobile per un utilizzo efficace dello spazio.

  Per ulteriori informazioni, consulta la [documentazione dettagliata](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

* Ora puoi aggiungere canali social personalizzati al modello e-mail oltre a quelli già disponibili.
* È stato risolto un problema che impediva lo scorrimento verso il basso del menu struttura quando si utilizzavano più di 18 strutture. (CAMP-31173)
* È stato risolto un problema che causava la visualizzazione del preheader sopra il contenuto durante l’inoltro di un’e-mail contenente un preheader inviato con Adobe Campaign. (CAMP-30736)
* È stato risolto un problema che impediva l’aggiornamento della riga dell’oggetto quando si faceva clic su **Aggiorna contenuti AEM** dopo aver modificato l’oggetto in Adobe Experience Manager. (CAMP-29984)
* Sono stati risolti diversi problemi che impedivano l’utilizzo di immagini dinamiche da Adobe Target.
* È stato risolto un problema che impediva l’aggiornamento dell’anteprima durante il recupero del contenuto in fase di preparazione se il contenuto era stato precedentemente importato da un URL.
* L’icona YouTube è stata aggiunta al **Social** componente contenuto.
* Il **Elenco** È stata aggiunta una vista per i componenti di contenuto e i frammenti visualizzati nella palette di E-mail Designer.

**Altri miglioramenti**

* Adobe Campaign è ora completamente conforme a FCM sia per le app SDK V4 che per quelle SDK AEP.
* Adobe Campaign supporta le notifiche push su Wear OS tramite Android e watchOS tramite Apple.
* I messaggi di avviso e di errore che possono apparire durante la navigazione nell’interfaccia sono stati resi più chiari e comprensibili.
* Ora puoi aggiungere all’elenco dei profili colonne relative ai campi di consenso e rinuncia (&quot;Non contattare più ...&quot;).
* L’elenco a discesa Fuso orario nella schermata di creazione del profilo è stato spostato dalla sezione Indirizzo alla sezione superiore dell’interfaccia.
* È ora possibile aggiungere separatori durante la configurazione delle schermate delle risorse personalizzate, consentendo di organizzare i campi in categorie.

  Per ulteriori informazioni, consulta la [documentazione dettagliata](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

**Altre modifiche**

* Adobe Campaign e Adobe Experience Cloud abbandoneranno il supporto per Microsoft Internet Explorer 11 a partire dalla primavera 2019 e dalla versione Campaign Standard 19.2. Passa a Microsoft Edge o a un altro browser supportato. Consulta [Funzioni obsolete e rimosse](../../rn/using/deprecated-features.md) pagina.
* Il **Codice paese** dal profilo è stato rinominato in **Codice paese**.

**Patch**

* È stato risolto un problema che impediva l’invio del messaggio quando si aggiungeva un profilo di test a un messaggio transazionale e-mail. (CAMP-29854)
* È stato risolto un problema che rallentava l’invio di messaggi da altri canali se l’invio era basso per un canale quando l’invio di messaggi da tutti i canali veniva attivato simultaneamente.
* È stato risolto un problema che causava l’avvio dell’invio di messaggi SMS da parte dell’MTA quando la connessione all’account esterno non era ancora stata stabilita.
* È stato risolto un problema che si verificava con la frequenza di esecuzione dell’attività di pianificazione e l’ora di inizio. (CAMP-30745)
* È stato risolto un problema che poteva verificarsi con la generazione di PKEY quando si utilizzavano risorse di profilo estese. (CAMP-30285)
* È stato risolto un problema che poteva verificarsi con le regole di affaticamento basate su giorni di calendario. (CAMP-30136)
* È stato risolto un problema che poteva verificarsi quando si tentava di accedere a risorse personalizzate con nomi che terminavano con &quot;Base&quot;. (CAMP-30109)
* È stato risolto un problema che impediva l’utilizzo di una chiamata PATCH per abbonare un profilo a un servizio. (CAMP-29728)
* È stato risolto un problema che poteva danneggiare un flusso di lavoro durante l’importazione di un file XML tramite l’attività Load File. (CAMP-29208 e CAMP-28205)
* È stato risolto un problema che si verificava durante il collegamento di risorse personalizzate che poteva impedire la generazione di collegamenti a cardinalità inversa. (CAMP-30476)
* È stato risolto un problema che impediva l’estensione dei registri di consegna quando si utilizzava solo il codice di segmento.
* È stato risolto un problema che poteva duplicare le righe durante l’utilizzo dell’attività di trasferimento dei file nei flussi di lavoro.
* È stato risolto un problema che impediva l’invio dei rapporti pianificati al momento scelto.
* È stato risolto un problema che causava discrepanze tra i KPI &quot;To deliver&quot; e &quot;Sent&quot; per una consegna in-app in un flusso di lavoro.
* È stato risolto un problema che impediva il funzionamento del tracciamento per un messaggio in-app creato con un HTML personalizzato.
* È stato risolto un problema che impediva il salvataggio del contenuto di consegna in-app se utilizzato in un flusso di lavoro.
* È stato risolto un problema che impediva agli amministratori di visualizzare le app mobili.
* È stato risolto un problema che causava un errore nel flusso di lavoro tecnico Aggiornamento del recapito messaggi. (CAMP-26387)
* È stato risolto un problema che causava discrepanze tra i profili target durante la creazione di una consegna in-app e quelli visualizzati nel dashboard di consegna. (CAMP-28722)
* È stato risolto un problema relativo all’integrazione del servizio core Campaign e Assets che poteva impedire la selezione di una risorsa condivisa in un messaggio e-mail.

## Versione 19.0 - Gennaio 2019 {#release-19-0---january-2019}

**Novità**

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Disponibilità generale di E-mail Designer<br /> </td> 
   <td> <p>Il nuovo e-mail designer intuitivo (precedentemente noto come Creative Designer) è stato spostato in GA. Ora supporta tutte le funzioni dell’editor di contenuti legacy, tra cui:</p> 
    <ul> 
     <li> L'uso di <a href="../../integrating/using/adding-target-dynamic-content.md">immagini dinamiche da Adobe Target</a> </li> 
     <li> La capacità di <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">recuperare automaticamente il contenuto da un URL al momento della preparazione</a> </li> 
     <li> Completamente conforme <a href="../../designing/using/using-reusable-content.md#content-templates">modelli di contenuto predefiniti</a>. </li> 
    </ul> 
    <p>Per ulteriori informazioni, consulta <a href="../../designing/using/designing-content-in-adobe-campaign.md">documentazione dettagliata</a> e <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">video tutorial</a>. Miglioramenti e correzioni sono elencati di seguito.</p><p>Di conseguenza, l’editor di contenuti e-mail legacy è ora obsoleto. Per ulteriori informazioni, consulta questa <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=it#">pagina</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Elenco prodotti nei messaggi e-mail sulle transazioni<br /> </td> 
   <td> <p>Ora puoi fare riferimento a una o più raccolte di prodotti in un messaggio e-mail transazionale. Ad esempio, puoi inviare automaticamente un’e-mail di abbandono carrello elencando tutti i prodotti presenti nel carrello dell’utente con un’immagine, un prezzo e un collegamento a ciascun prodotto.</p><p>Per ulteriori informazioni, consulta la <a href="../../designing/using/using-product-listings.md">documentazione dettagliata</a> e il <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">video tutorial</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Visualizzazione mobile in E-mail Designer<br /> </td> 
   <td> <p>È ora possibile passare a una visualizzazione mobile dedicata durante la modifica del contenuto delle e-mail. Questo consente di mettere a punto la progettazione reattiva di un’e-mail modificando separatamente tutte le opzioni di stile per la visualizzazione mobile, ad esempio per adattare i margini, ridurre le dimensioni del font, usare colori di sfondo diversi e così via.</p><p> Per ulteriori informazioni, consulta la <a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">documentazione dettagliata</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Miglioramenti della versione beta della messaggistica in-app<br /> </td> 
   <td> <p>La funzione Messaggistica in-app Beta è stata migliorata con le seguenti funzionalità:</p> 
    <ul> 
     <li> Il canale Beta in-app è conforme ai requisiti RGPD </li> 
     <li> Integrazione con le API di Analytics per popolare i menu a discesa Triggers </li> 
     <li> Descrizione intuitiva dei modelli di consegna </li> 
     <li> Miglioramenti all’interfaccia di authoring dal punto di vista dell’usabilità </li> 
    </ul> <p>Per ulteriori informazioni, consulta la <a href="../../channels/using/about-in-app-messaging.md">documentazione dettagliata</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

**Miglioramenti**

* Una nuova opzione nell’attività Load data ora consente di applicare una fase di post-elaborazione al file contenente i record rifiutati (ad esempio, la compressione del formato ZIP). (CAMP-24521)
* Una nuova opzione nell’attività Aggiornare dati ora consente di configurare la dimensione batch massima per i dati da caricare. (CAMP-28400)
* È stata migliorata la selezione dello stato dell’indirizzo dei profili. Quando si seleziona un paese, l’elenco a discesa &quot;Stato&quot; viene ora aggiornato automaticamente con i valori degli stati rilevanti. (CAMP-28874)
* Una nuova opzione nell’attività Extract file ora impedisce la generazione di un file se la transizione in entrata è vuota. Questo evita di creare e caricare file vuoti sui server SFTP.
* Il rapporto di riepilogo Consegna è stato migliorato.
* L’elenco dei paesi disponibili durante la definizione dell’indirizzo di un profilo è stato arricchito. (CAMP-26707)
* Ora viene visualizzato un messaggio di errore quando si tenta di importare un flusso di lavoro integrato.

**E-mail Designer**

* È stato risolto un problema che attivava la funzionalità unità geografica in un modello e-mail o in un frammento di contenuto creato con E-mail Designer, anche se questa funzionalità era disabilitata in Adobe Campaign, rendendo il modello o il frammento non disponibile quando si tentava di accedervi di nuovo. (CAMP-28174)
* È stato risolto un problema che impediva il salvataggio delle condizioni di contenuto dinamico durante la modifica del contenuto con E-mail Designer. (CAMP-27905)
* È stato risolto un problema che causava la rimozione della versione di HTML dal contenuto dell’e-mail dopo la modifica della versione in testo normale di un messaggio e l’interruzione della sincronizzazione di HTML in E-mail Designer. (CAMP-28507)
* È stato risolto un problema che impediva l’apertura dell’interfaccia di E-mail Designer durante l’utilizzo di Internet Explorer 11. (CAMP-28273)
* È stato risolto un problema che distorceva il rendering in Microsoft Outlook delle impostazioni di stile applicate ai pulsanti con E-mail Designer.
* È stato risolto un problema in E-mail Designer che rendeva modificabile un URL da un frammento di contenuto utilizzato in un messaggio e-mail. Ciò non era previsto in quanto il frammento è bloccato per impostazione predefinita.
* È stato risolto un problema che impediva la visualizzazione del componente divisore di E-mail Designer in Microsoft Office.
* È stato risolto un problema che causava il blocco della pagina in alcuni browser Internet durante la visualizzazione di un contenuto sincronizzato dall’AEM utilizzando l’editor di contenuti e-mail legacy. (CAMP-29068)
* È stato corretto un errore che si verificava facendo clic su un’immagine in un messaggio e-mail quando si utilizzava l’editor di contenuti e-mail legacy. (CAMP-30424)
* È stato risolto un problema che impediva la visualizzazione dei nuovi frammenti creati durante la modifica di un’e-mail con E-mail Designer. (CAMP-29928)
* È stato risolto un problema che impediva la corretta visualizzazione del testo del pulsante nelle e-mail create con E-mail Designer e ricevute utilizzando il client Outlook WebMail.
* È ora possibile creare messaggi transazionali di profilo utilizzando E-mail Designer. (CAMP-28900)
* È stato corretto un errore in E-mail Designer a causa del quale il contenuto diventava modificabile durante il recupero automatico del contenuto da un URL in fase di preparazione, mentre doveva essere bloccato.

**Patch**

* È stato risolto un problema che causava la visualizzazione di registri di consegna errati nel reporting dinamico. (CAMP-23446)
* È stato risolto un problema che poteva interessare i numeri nel rapporto Riepilogo mancate consegne (CAMP-28703)
* È stato risolto un problema relativo all’integrazione di Campaign con il servizio core Assets che poteva impedire la visualizzazione delle risorse durante la selezione **[!UICONTROL Image shared from Adobe Experience Cloud]** in un messaggio e-mail (CAMP-28732).
* È stato risolto un problema che impediva l’invio di messaggi SMS contenenti il carattere &quot;oe&quot; anche se la traslitterazione era autorizzata nell’account esterno SMPP. (CAMP-29041)
* È stato risolto un problema che poteva mostrare record duplicati durante l’utilizzo di un’attività Segmentation nei flussi di lavoro. (CAMP-28743)
* È stato risolto un problema che impediva l’eliminazione di una delle mappature di valore su una colonna in un’attività del flusso di lavoro. (CAMP-28708)
* È stato risolto un problema nell’attività di trasferimento dei file, quando si utilizzavano caratteri jolly con l’opzione &quot;Test per verificare se il file esiste&quot;. (CAMP-28977)
* È stato risolto un problema nell’attività File Transfer che poteva verificarsi durante l’aggiornamento delle impostazioni dell’account esterno. (CAMP-28894)
* È stato risolto un problema relativo ai filtri personalizzati nell’editor delle query quando si utilizzava la condizione &quot;E-mail non è vuota&quot;. (CAMP-28741)
* È stato risolto un problema che poteva verificarsi durante l’esportazione di tabelle di risorse personalizzate con più di 100.000 record. (CAMP-28150)
* È stato risolto un problema che impediva l’eliminazione dei messaggi transazionali collegati ai trigger. (CAMP-28385)
* Sono state rimosse le password che venivano visualizzate in modo insicuro in alcuni registri SMS.
* È stato risolto un problema che impediva le connessioni al simulatore SMPP a causa di una password vuota inviata da Adobe Campaign.
* È stato risolto un problema che impediva l’invio di campagne quando le connessioni SMS erano instabili.
* È stato risolto un problema che causava la visualizzazione di consegne eliminate in Reporting dinamico.
* È stato risolto un problema che poteva impedire il recupero di dati aggiuntivi dai registri di consegna, dai registri di tracciamento e dalle tabelle dei registri di esclusione durante l’utilizzo di un’attività Enrichment in un flusso di lavoro.
* È stato risolto un problema relativo alle richieste di eliminazione del RGPD che poteva verificarsi quando si utilizzava un tipo di collegamento &quot;Collegamento raccolta con cardinalità N&quot; e l’opzione &quot;L’eliminazione del record di destinazione comporta l’eliminazione dei riferimenti ai record tramite il collegamento&quot;.
* È stato risolto un problema relativo alla condivisione dei report.
* È stato risolto un problema che poteva causare problemi di velocità effettiva durante l’invio di una notifica push.
* È stato risolto un problema a causa del quale nei file di output della direct mailing mancavano dei campi.
* È stato risolto un problema che consentiva agli utenti di modificare i flussi di lavoro incorporati.
* È stato risolto un problema che si verificava durante la creazione di una campagna basata su un modello di campagna comprensivo di un flusso di lavoro con un’attività di estrazione configurata. (CAMP-29198)
* È stato risolto un problema relativo all’attività di estrazione File che impediva l’utilizzo della stessa espressione per diversi elementi. (CAMP-29182)
* È stato risolto un problema, nell’editor delle query, relativo alla condizione di unione tra broadlog e il registro di tracciamento per rtEvent. (CAMP-28780)
* È stato risolto un problema che impediva il salvataggio delle modifiche all’opzione della pagina di destinazione &quot;Azione specifica&quot;. (CAMP-29422)
* È stato risolto un problema che impediva l’esportazione del payload di un evento in un flusso di lavoro. (CAMP-29029)
* È stato risolto un problema che impediva l’esclusione di numeri SMS sul inserisco nell&#39;elenco Bloccati di in un messaggio SMS. (CAMP-28898)
* È stato risolto un problema che poteva impedire ai provider SMPP di ricevere una notifica in caso di errore durante l’elaborazione dei messaggi in arrivo. (CAMP-29804)
* È stato risolto un problema che consentiva l’eliminazione di account esterni con consegne associate. (CAMP-29738)
* La velocità effettiva di invio è stata migliorata e stabilizzata per i messaggi SMS.
* È stato risolto un problema che impediva l’utilizzo del carattere &quot;~&quot; in un messaggio SMS. (CAMP-29172)
* È stato risolto un problema nelle consegne con l’opzione di ottimizzazione dell’ora di invio. (CAMP-29231)
