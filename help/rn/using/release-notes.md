---
title: Note sulla versione
seo-title: Note sulla versione
description: Note sulla versione
seo-description: In questa pagina sono elencate tutte le versioni recenti di Adobe Campaign Standard.
page-status-flag: mai attivato
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: release standard di campagna
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 637cddaa2fb29554f7e6c8b6ae2e4076515488de

---


# Note sulla versione{#release-notes}

Tutte le versioni 2019, con le relative nuove funzioni e patch, sono elencate in questa pagina. Sono inclusi anche gli aggiornamenti del Pannello di controllo.

Risorse aggiuntive:

* [Pianificazione rilascio campagna](https://helpx.adobe.com/campaign/kb/acs-release-planning.html)
* [Ultimi aggiornamenti della documentazione](../../rn/using/documentation-updates.md)
* [Funzioni obsolete e rimosse](https://helpx.adobe.com/campaign/kb/deprecated-and-removed-features.html)
* [Pannello di controllo](https://helpx.adobe.com/campaign/kb/control-panel.html)
* Note sulla versione precedente: [2018](../../rn/using/release-notes-2018.md), [2017](../../rn/using/release-notes-2017.md), [2015-2016](../../rn/using/release-notes-2015-2016.md)

## Rilascio 19.4 - ottobre 2019 {#release-19-4---october-2019}

### Cosa c'è di nuovo? {#what-s-new-5}

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> California Consumer Privacy Act (CCPA)<br /> </td> 
   <td> <p>CCPA è la nuova legge sulla privacy dello Stato californiano che armonizza e aggiorna i requisiti di protezione dei dati in vigore dal 1° gennaio 2020. CCPA si applica ai clienti di Adobe Campaign che detengono i dati per i soggetti dati residenti in California.</p>
   <p>Oltre alle funzionalità per la privacy già disponibili in Adobe Campaign (compresa la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), stiamo colgendo l'opportunità di includere funzionalità aggiuntive per facilitare la disponibilità dell'APP:</p>
   <ul>
    <li>Diritto di accesso e Diritto di eliminazione: stiamo sfruttando le funzionalità aggiunte per il GDPR. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">Ulteriori informazioni</a> </li>
    <li><p>Durante la creazione di una richiesta per la privacy, il tipo di regolamento (GDPR o CCPA) è stato aggiunto al Servizio di base per la privacy. Questo metodo è quello da utilizzare per tutte le richieste di accesso ed eliminazione. L'utilizzo dell'API e dell'interfaccia di Campaign per le richieste di accesso ed eliminazione è obsoleto. Tuttavia, se devi ancora utilizzare questi metodi nella versione 19.4, il tipo di regolamento è stato aggiunto nell'interfaccia e nell'API di Campaign ed è obbligatorio. Per l'interfaccia, il valore predefinito sarà impostato su GDPR. Per l'API, dovrete includere questo campo nel payload. Consultate la documentazione <a href="https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#privacy-management">sulle</a>API.</p></li>
    <li>Alla risorsa Profili è stato aggiunto un campo di rifiuto <strong></strong> CCPA per consentire agli utenti di Adobe Campaign di verificare se un consumatore ha rinunciato alla vendita di Informazioni personali. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#ccpa">Ulteriori</a>informazioni.</li>
  </ul>
    <p>Fate riferimento al <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">video</a>dimostrativo.</p>
</td> 
  </tr> 
  <tr> 
   <td> Integrazione di Microsoft Dynamics 365 (GA)<br /> </td> 
   <td> 
    <p>È ora disponibile l'integrazione tra Adobe Campaign Standard e Microsoft Dynamics 365. Potrai trasferire i tuoi record di contatti e entità personalizzati da Dynamics 365 a Campaign e recuperare i dati degli eventi e-mail da Campaign a Dynamics 365 per migliorare l'allineamento vendite/marketing.</p>
    <p>Fate riferimento alla documentazione <a href="https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html"></a> dettagliata per configurare questa integrazione e visualizzare il video <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/integrating/microsoft-dynamics365-connector/introduction.html"></a>dimostrativo.</p>
  </td>
  </tr> 
 </tbody> 
</table>

### Miglioramenti {#improvements-3}

* La finestra a comparsa di consenso per il reporting dinamico è stata aggiornata per includere l'integrazione di Adobe Campaign Standard e Microsoft Dynamics 365. Accettando i termini, i dati del profilo saranno inclusi quando si utilizzano l'integrazione Adobe Campaign Standard / Microsoft Dynamics 365 e i rapporti dinamici. [Leggi tutto](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* È stato risolto un problema che causava la visualizzazione di date di contatto errate durante la ricezione degli avvisi di consegna.
* Quando un evento messaggio transazionale viene inviato con un parametro di contesto sconosciuto, Campaign ora restituisce un messaggio di errore "400" invece di "500". (CAMP-28632)
* È stato aggiunto un nuovo segmento **Escludi prova** nel reporting dinamico. Questo segmento è ora selezionato per impostazione predefinita per filtrare i rapporti. [Leggi tutto](../../reporting/using/list-of-components-.md#segments)
* L'opzione **Scadenza** messaggio è stata aggiunta alla notifica push. Consente di specificare una data di scadenza in cui il messaggio non verrà più inviato da Apple (APNS) o Android (FCM). [Leggi tutto](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* Sono stati apportati miglioramenti all'attività del file **** Load: i registri del flusso di lavoro sono stati resi più chiari e dettagliati in merito all'errore che si verifica quando un file non viene caricato. La transizione in uscita generata durante l'attivazione dell'opzione **Mantieni i rifiuti in un file** è stata rinominata **Rifiuti**. [Leggi tutto](../../automating/using/load-file.md#load-files)
* Sono stati aggiunti registri multilingue ai file di registro di invio per comprendere meglio gli errori di invio dovuti alle lingue mancanti nei file CSV caricati.

### Miglioramenti della sicurezza {#security-enhancements-3}

* È stato risolto un problema che causava la rimozione di tutti i dati tranne l'indirizzo e-mail presente nell'elenco di quarantena durante l'eliminazione delle informazioni di un profilo in quarantena tramite una richiesta di privacy.
* È stata migliorata la protezione contro le iniezioni nelle intestazioni delle e-mail.
* È stata migliorata la protezione contro gli attacchi SSRF in cui è possibile utilizzare espressioni xtk (HTML per e-mail, contenuto di testo e oggetto, SMS e contenuto di notifica push).

### Miglioramenti di Email Designer {#email-designer-enhancements-4}

* Quando si modifica un collegamento utilizzando la finestra di progettazione e-mail, è ora possibile utilizzare l'opzione **Sottolineato collegamento** . Inoltre, è stata aggiunta una proprietà **Target** con il valore predefinito impostato su **Nessuno**. [Leggi tutto](../../designing/using/styles.md#about-styling-links)
* È stato risolto un problema di colore sui collegamenti in componenti di testo nel corpo di un messaggio e-mail. (CAMP-37330)
* È stato risolto un problema che impediva la rimozione dei collegamenti associati durante l'eliminazione di un'immagine. (CAMP-37234)
* È stato risolto un problema che impediva il salvataggio delle modifiche nelle impostazioni **Ordine** del contenuto dinamico in una condizione. (CAMP-36883)
* È stato risolto un problema durante la ricerca delle pagine di destinazione. La ricerca è stata estesa dalle 50 create per prime a tutto il database. (CAMP-36839)
* È stato risolto un problema che si verificava durante il salvataggio delle modifiche sul mittente dell’e-mail in **Da: Campo nome** . (CAMP-36606)
* L’avviso di compatibilità dei componenti carosello è stato modificato per riflettere i client e-mail supportati.
* È stato risolto un problema di visualizzazione su dispositivi mobili. L'attributo height ora è sempre impostato su "height: auto" quando si aggiunge o si carica una nuova immagine in un messaggio e-mail. (CAMP-35497)
* È stato risolto un problema che lasciava gli stili e i tag meta nell’HTML quando si eliminava un frammento da un componente struttura. (CAMP-35390)
* È stato risolto un problema relativo ai frammenti durante l'aggiornamento del contenuto riutilizzabile. (CAMP-35186)
* È stato risolto un problema che si verificava durante la visualizzazione nelle e-mail del contenuto condizionale solo per dispositivi mobili. (CAMP-35155)
* È stato corretto un problema a causa del quale venivano visualizzati in modo casuale gli spazi unificatori a larghezza zero. (CAMP-35116)
* È stato risolto un problema relativo alla posizione dei pulsanti nella finestra di dialogo **Salva come frammento** .
* È stato corretto un problema di anteprima quando si aggiungeva un tag HTML in un titolo immagine e testo alternativo.
* È stato risolto un problema che si verificava durante la modifica, nella finestra di progettazione e-mail, dei collegamenti creati nelle e-mail dall'editor legacy.
* È stato risolto un problema che lasciava nel contenuto dei tag di stile duplicati.
* È stato risolto un problema relativo al formato della data durante l'inserimento di un campo di personalizzazione in un messaggio e-mail.
* È stato corretto un problema di salvataggio quando si passava dalla modalità HTML al testo normale.
* È stato risolto un problema che si verificava quando si faceva clic sull'opzione Blocca e sblocca che aggiungeva i valori dei margini nel pannello delle proprietà dello stile in linea.
* È stato risolto un problema con la dimensione dell'anteprima mobile per migliorare il rendering.
* È stato risolto un problema relativo alla dimensione dei pulsanti nei modelli e nei frammenti.
* È stato risolto un problema relativo alla dimensione delle immagini quando queste venivano inserite in un componente pulsante.

### Altre modifiche {#other-changes-3}

* L'intervallo di tempo predefinito per il quale i dati vengono visualizzati nelle pagine KPI di consegna e nella pagina Generazione rapporti dinamica è stato allineato per evitare discrepanze nei risultati dei rapporti. (CAMP-35148)
* È stato aggiunto un messaggio di errore nei registri alla scadenza del certificato dell'applicazione.
* L'anteprima del calcolo del payload ora include la dimensione del campo personalizzato per evitare errori di notifica push. (CAMP-35303)
* Il nome del file **** Rifiuta nell'attività del file **** Carica ora può essere personalizzato nello stesso modo in cui si trovava nell'attività di esportazione **** File.
* Ora è possibile accedere a tutte le entità personalizzate che non sono collegate ad alcuna entità out-of-the-box tramite l'API.
* Sono state migliorate le prestazioni del database su risorse di grandi dimensioni.
* Le descrizioni di alcuni errori che si verificavano durante l'invio di messaggi SMS sono state rese più chiare. (CAMP-36558)
* Viene ora visualizzato un messaggio di errore durante l'esecuzione dell'attività **Scheduler** di un flusso di lavoro connessa a se stessa, direttamente o attraverso diverse attività, in quanto ciò potrebbe causare il blocco del server del flusso di lavoro dell'istanza.
* Sono stati apportati miglioramenti per risolvere eventuali problemi relativi ai messaggi transazionali: il collegamento "Dati" è stato rinominato "Ultimi eventi transazionali" nella schermata di configurazione dell’evento, e ora elenca gli eventi ricevuti ordinati in ordine decrescente. Inoltre, è stato creato un nuovo stato evento transazionale: "targetingFailed". Quando il modulo di messaggistica transazionale non riesce ad arricchire un collegamento utilizzato per il targeting dei messaggi, l'evento transazionale ora si troverà in questo nuovo stato (invece dello stato "routingFailed").
* Sono stati apportati miglioramenti all'interfaccia quando si limita l'accesso alla pagina di destinazione a unità geografiche o organizzative specifiche. Lo scopo è avvertire che la pagina di destinazione può essere soggetta a condizioni di visibilità: la selezione di un'unità geografica e organizzativa al momento della creazione di una pagina di destinazione è ora obbligatoria. Un banner con informazioni correlate ora viene visualizzato una volta selezionata un'unità. Il messaggio di errore visualizzato durante la verifica della pagina di destinazione è stato reso più chiaro.
* Nelle API Campaign Standard non è possibile modificare le chiavi personalizzate utilizzando un'operazione PATCH se il valore della chiave è diverso dalla chiave di origine o se si utilizza la chiave aziendale come URI anziché quella fornita da Adobe.
* La lingua "Albanese - Macedonia" è stata aggiunta all'elenco a discesa della lingua preferita. (CAMP-35396)

### Patch {#patches-4}

* È stato risolto un problema che impediva l'ordinamento o la ricerca dei report pianificati.
* È stato risolto un problema con le regole Triggers che causava la combinazione di regole AND e OR.
* È stato risolto un problema che causava la visualizzazione della proprietà Mobile come Eliminato in Launch. (CAMP-35382)
* È stato risolto un problema che impediva la sincronizzazione delle proprietà mobili di Adobe Launch in Adobe Campaign. (CAMP-35411, CAMP-35089, CAMP-35014, CAMP-35487)
* È stato risolto un problema che causava un errore nei messaggi push transazionali quando gli eventi venivano arricchiti con i dati del profilo. (CAMP-34385)
* È stato risolto un problema che impediva la sincronizzazione delle proprietà mobili su più ambienti. (CAMP-37060)
* È stato risolto un problema che si verificava quando, in una notifica push, veniva selezionato un modello utilizzando una formula per la data del contatto. (CAMP-35300)
* È stato risolto un problema che poteva causare l'arresto anomalo del servizio di invio dei messaggi. (CAMP-35287)
* È stato risolto un problema relativo alle e-mail dirette ricorrenti, tutte definite con la prima data dell'evento. (CAMP-35139)
* È stato risolto un problema con le risorse personalizzate **Profili** di nuova estensione che non erano disponibili per le query. (CAMP-35119)
* È stata corretta la modalità **Ripara struttura** del database per le istanze con la configurazione Shaccing attivata. (CAMP-35118)
* È stato risolto un problema che causava un errore del registro SQL durante l'aggiunta di dati aggregati nei log di trasmissione. (CAMP-35034)
* È stato risolto un problema relativo alle transizioni durante la creazione di un'attività di **segmentazione** . (CAMP-35033)
* È stato risolto un problema nell'attività **Query** che impediva alla funzione **Encryption_aescbcDecrypt** di decrittografare la funzione **Encryption_aescbcEncrypt** . (CAMP-34952)
* È stato risolto un problema che poteva impedire la visualizzazione dei log **di** tracciamento nelle consegne. (CAMP-34855)
* È stato risolto un problema che, quando si utilizzava una formula di data personalizzata per l'ottimizzazione dell'ora di **** invio, poteva impedire l'invio delle notifiche push a causa di errori con i dati aggiuntivi del flusso di lavoro. (CAMP-30336)
* È stato risolto un problema che poteva impedire la pubblicazione di risorse personalizzate. (CAMP-37425)
* È stato risolto un problema che impediva agli utenti Admin di modificare i pacchetti di importazione.  (CAMP-37176)
* È stato risolto un problema nei flussi di lavoro che impediva l'invio di prove, se l'attività di consegna era connessa a un'attività di audience **di** lettura vuota. (CAMP-37164)
* È stato risolto un problema che impediva l'importazione di risorse personalizzate in un nuovo ambiente. (CAMP-36506)
* È stato risolto un problema nei rapporti sul clic con il pulsante destro del mouse che poteva determinare la visualizzazione delle percentuali da parte delle immagini (CAMP-36407)
* È stato risolto un problema che si verificava durante il tentativo di esportazione di un campo di descrizione della consegna. (CAMP-35467)
* È stato risolto un problema che poteva lasciare lo stato di una consegna come "Inizio in sospeso" anche se la consegna era terminata. (CAMP-35355)
* È stato risolto un problema che impediva la visualizzazione dei registri del flusso di lavoro dopo l'attivazione e la disabilitazione dei registri SQL.

## Aggiornamento del Pannello di controllo - Agosto 2019 {#controlpanel-update---august-2019}

### Cosa c'è di nuovo? {#what-s-new-4}

Abbiamo aggiunto nuove funzionalità affinché gli utenti Admin ricevano notifiche prima della scadenza dei certificati SSL per i loro domini. Per ulteriori informazioni, consulta la documentazione [](https://helpx.adobe.com/campaign/kb/control-panel-subdomains-certificates.html)dettagliata.

Inoltre, gli utenti amministratore possono ora eliminare le chiavi SSH aggiunte per accedere ai server SFTP.

Il Pannello di controllo è disponibile solo per i clienti ospitati su AWS. Questi aggiornamenti saranno disponibili il 26 agosto.

## Rilascio 19.3 - luglio 2019 {#release-19-3---july-2019}

### Cosa c'è di nuovo? {#what-s-new-3}

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
   <td> <p>Per una personalizzazione più approfondita, Attività API esterna consente di portare dati da sistemi esterni in un flusso di lavoro tramite una chiamata REST API. Gli endpoint REST possono essere un sistema di gestione dei clienti, un runtime Adobe I/O o un endpoint REST di Adobe Experience Cloud (ad esempio, piattaforma dati, Target, Analytics, Campaign).</p><p>Questa funzionalità è attualmente nella versione beta pubblica.</p><p>Per ulteriori informazioni, consultate la documentazione <a href="../../automating/using/external-api.md"></a> dettagliata e il video <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">sulle</a>procedure.</p></td> 
  </tr> 
  <tr> 
   <td> Report sul segmento del flusso di lavoro<br /> </td> 
   <td> <p>Questa funzione consente agli esperti di marketing di suddividere le prestazioni di consegna per codice del segmento. Quando create un flusso di lavoro e utilizzate un'attività di segmentazione per assegnare segmenti alla popolazione di distribuzione, questi segmenti ora possono passare alla stessa distribuzione. Questo consente di visualizzare le statistiche di apertura/clic basate su più segmenti all'interno di una singola consegna.</p><p>Per ulteriori informazioni, consultate la documentazione <a href="../../reporting/using/creating-a-report-workflow-segment.md"></a> dettagliata e il video <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">sulle</a>procedure.</p></td>
  </tr> 
 </tbody> 
</table>

### Miglioramenti della sicurezza {#security-enhancements-2}

* È stato risolto un problema di sicurezza per impedire attacchi di tipo Denial of Service (DoS) a richieste non valide per ottenere immagini. (CAMP-33454)

### Miglioramenti di Email Designer {#email-designer-enhancements-3}

* È stato risolto un problema che causava l'aggiunta di tag di stile HTML aggiuntivi a un modello HTML ogni volta che veniva aggiunto un componente, con un conseguente aumento vertiginoso delle dimensioni del modello. (CAMP-34694)
* È stato risolto un problema che poteva impedire la disponibilità di alcune opzioni del menu della barra degli strumenti superiore destra. (CAMP-34577)
* È stato risolto un problema che si verificava quando il blocco contenuto URL pagina mirror veniva inserito in un contenuto e-mail. (CAMP-34779)
* È stato risolto un problema che si verificava quando si utilizzava il codice JSPP in un messaggio e-mail, rendendo difficile la modifica del contenuto. (CAMP-34574)
* È stato risolto un problema che causava il troncamento delle immagini in cima quando veniva loro aggiunto un collegamento ipertestuale. (CAMP-34382)
* È stato risolto un problema di visualizzazione che si verificava durante l'utilizzo di Email Designer con Firefox. (CAMP-34364)
* Sono stati risolti diversi problemi che si verificavano in modalità Avanzato durante la definizione del contenuto dinamico in un messaggio e-mail. (CAMP-34351, CAMP-34333, CAMP-34331)
* Sono stati corretti diversi problemi che si verificavano con l'editor della regola del contenuto dinamico (CAMP-34304, CAMP-34303).
* È stato risolto un problema che poteva impedire la visualizzazione del campo Collegamento nel riquadro Impostazioni di Designer e-mail (CAMP-33749).
* È stato risolto un problema relativo all'icona di YouTube che era sovrapposta nelle e-mail inviate. (CAMP-33726)
* È stato risolto un problema di sicurezza che rendeva modificabile il contenuto della pagina mirror. (CAMP-33691)
* È stato risolto un problema che causava l'interruzione dell'output HTML quando si utilizzava il simbolo maggiore di nel contenuto dinamico. (CAMP-33688)
* È stato risolto un problema che si verificava durante l'utilizzo dell'opzione Annulla durante la modifica del testo in Designer e-mail. (CAMP-32565)
* È stato risolto un problema che causava la creazione di tag aggiuntivi durante l'annullamento degli stili invece di rimuoverli. (CAMP-32359)
* Ora potete definire se ogni componente utilizzato in un messaggio e-mail verrà visualizzato solo sui dispositivi desktop o solo sui dispositivi mobili.
* Ora potete impostare la larghezza e l'altezza di un componente di contenuto Social.
* È stato risolto un problema che impediva la rimozione del vecchio codice sorgente del contenuto dinamico dopo l'eliminazione di tale contenuto dinamico.
* È stato risolto un problema che poteva impedire l’aggiornamento dell’oggetto di un messaggio e-mail dopo la modifica.
* È stato risolto un problema che impediva la selezione di una struttura di colonne n:n una volta rilasciata nell'area di lavoro.
* È stato risolto un problema che causava la visualizzazione sfocata della miniatura del messaggio nel dashboard e-mail.
* È stato risolto un problema che impediva la corretta visualizzazione dello sfondo per le e-mail ricevute in Outlook.
* Sono stati corretti alcuni problemi di ordinamento nella home page di Designer e-mail.
* È stato risolto un problema che si verificava durante la duplicazione delle varianti quando si utilizzava il contenuto dinamico.
* Alcuni campi indesiderati sono stati rimossi dal riquadro Impostazioni di Designer e-mail.

### Altri miglioramenti {#other-improvements-3}

* Grazie all'integrazione con Adobe Experience Platform Location Services, Adobe Campaign è ora compatibile con l'invio di messaggi di marketing basati sulla posizione agli abbonati dell'applicazione mobile tramite l'SDK di Experience Platform. Per ulteriori informazioni, consulta la documentazione [](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md)dettagliata.
* La funzione di reporting è stata migliorata per migliorare l'esperienza. Per utilizzare questa funzione, devi accettare il contratto di utilizzo di reporting dinamico. Per ulteriori informazioni, consulta la documentazione [](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)dettagliata.
* Nei flussi di lavoro è stata aggiunta una nuova opzione per visualizzare in anteprima le dieci esecuzioni successive di un flusso di lavoro. Per ulteriori informazioni, consulta la documentazione [](../../automating/using/scheduler.md)dettagliata.
* Nell'attività Scheduler, una nuova opzione consente di selezionare un giorno specifico di una settimana per le consegne mensili. Per ulteriori informazioni, consulta la documentazione [](../../automating/using/scheduler.md)dettagliata.
* Quando si creano consegne ricorrenti senza periodo di aggregazione, il dashboard di consegna ora consente di richiedere conferma prima dell'invio. Per ulteriori informazioni, consulta la documentazione [](../../sending/using/confirming-the-send.md)dettagliata.
* Ora puoi personalizzare l'etichetta di una consegna con le variabili evento dichiarate nell'attività del segnale esterno del flusso di lavoro. Per ulteriori informazioni, consulta la documentazione [](../../automating/using/calling-a-workflow-with-external-parameters.md)dettagliata.
* La query di eliminazione GDPR è stata migliorata per migliorare le prestazioni. (CAMP-33504)
* L'opzione "ftp" è stata rimossa dall'interfaccia di configurazione dell'account esterno. (CAMP-34472)
* Ora puoi attivare e disattivare l'opzione della modalità di prova SMTP per ogni messaggio e-mail. Per ulteriori informazioni, consulta la documentazione [](../../administration/using/configuring-email-channel.md#smtp-test-mode)dettagliata. (CAMP-34602)

### Altre modifiche {#other-changes-2}

* Nell'interfaccia delle proprietà di consegna è stato aggiunto un avviso. Specifica che le consegne sono preparate in base al periodo di aggregazione e il disgelo per chiamare il flusso di lavoro più volte al giorno, accertati che non abbiano un periodo. (CAMP-34393)
* Nelle schermate di configurazione delle risorse personalizzate è stato aggiunto un avviso. È consigliabile utilizzare un massimo di 30 caratteri per gli ID di risorse personalizzati. Questo vale anche per campi di risorse personalizzati, chiavi, indici e collegamenti.
* Ora viene visualizzato un messaggio quando si tenta di eliminare un messaggio transazionale utilizzato da una pagina di destinazione come messaggio di conferma.
* Nei registri dei flussi di lavoro viene ora visualizzato un avviso quando un'attività è in esecuzione da più di 6 ore. Ciò non si applica alle attività di notifica push, Consegna, Segnale, Inizio, Fine, Fork, E-joint, Pianificazione e Attesa.
* Nei registri dei flussi di lavoro viene ora visualizzato un avviso quando raggiungete il numero massimo di flussi di lavoro in esecuzione contemporaneamente.
* I flussi di lavoro in stato di pausa o di mancata riuscita per oltre 7 giorni vengono ora interrotti per ridurre lo spazio su disco. L’attività di pulizia viene visualizzata nei registri del flusso di lavoro.
* Quando si utilizza un'attività "Trasferisci file", ora viene registrato un errore se la dimensione del file supera lo spazio disponibile su disco.
* L'azione Reindirizza all'URL di destinazione non può più essere selezionata per il pulsante secondario nei messaggi in-app.

### Patch {#patches-3}

* È stato risolto un problema che poteva causare un errore nelle richieste di accesso GDPR.
* È stato risolto un problema che poteva causare la rimozione dei trigger quando venivano ricevuti più attivatori per un profilo univoco.
* È stato risolto un problema che poteva causare un errore di pubblicazione delle risorse personalizzato errato dopo l'accesso.
* È stato risolto un problema che causava la visualizzazione di una pagina vuota durante la creazione o l'estensione di una risorsa personalizzata.
* È stato risolto un problema che impediva a un'audience con appSubscriptionrcp come dimensione di targeting di essere disponibile per il targeting in una distribuzione mobile.
* È stato corretto un errore che impediva di mettere in quarantena gli indirizzi e-mail con rimbalzo fisso. (CAMP-24587)
* È stato risolto un problema che si verificava quando si aggiungeva una regola di tipo, quindi la si eliminava prima di salvare la tipologia. (CAMP-32789)
* È stato risolto un problema che poteva impedire la visualizzazione del contenuto della pagina di destinazione quando si disattivava il contenuto dinamico. (CAMP-32924)
* È stato risolto un problema con consegne ricorrenti che si verificava durante l'utilizzo della personalizzazione sugli attributi di una consegna master. (CAMP-32983)
* È stato risolto un problema nei flussi di lavoro che impediva la lettura dei risultati da una transizione contenente i dati dei messaggi SMS in arrivo. (CAMP-33134)
* È stato risolto un problema nei flussi di lavoro che si verificava durante la combinazione di fork ed attività di esclusione per creare audience. (CAMP-33401)
* È stato risolto un problema che impediva la visualizzazione del contenuto della pagina mirror e l'invio di messaggi di prova per consegne ricorrenti. (CAMP-33413)
* È stato risolto un problema che causava un errore durante l'utilizzo di un'attività dell'Unione tra profili e audience. Questo problema è stato causato da un'incompatibilità dei tasti di identificazione nelle transizioni di input. (CAMP-33713)
* È stato risolto un problema nelle attività Test che impediva all'espressione "recCount" di utilizzare la sintassi corretta quando si faceva doppio clic su di essa. (CAMP-33756)
* È stato risolto un problema che poteva causare un messaggio di errore all'apertura dei registri del flusso di lavoro tecnico di fatturazione. (CAMP-34313)
* È stato risolto un problema nelle pagine di destinazione che poteva verificarsi durante la configurazione dei campi casella di controllo con iscrizioni. (CAMP-34369)
* È stato risolto un problema che si verificava durante la configurazione di un elenco e l'aggiunta del campo "icona". (CAMP-34585)
* È stato risolto un problema che impediva l'utilizzo dei simboli "|" e "%" come separatori di data o ora nelle attività del flusso di lavoro del file di caricamento. (CAMP-34706)
* È stato risolto un problema che si verificava quando si utilizzavano le condizioni di visibilità con le caselle di controllo nelle pagine di destinazione. (CAMP-34802)
* È stato risolto un problema nell'attività di arricchimento che impediva la visualizzazione dei campi nella scheda "Dati aggiuntivi", se la dimensione di filtro era impostata sul tracciamento dei registri e la dimensione di destinazione sul profilo.
* È stato risolto un problema che causava un messaggio di errore durante l'esportazione di una risorsa "workflowTemplate".
* È stato risolto un problema durante la creazione di un nuovo profilo che impediva il salvataggio del campo "Codice paese/regione" se era stato selezionato dalla finestra di dialogo.
* Sono stati risolti diversi problemi che si verificavano durante l'utilizzo del modello di importazione Direct Mail (updateQuarantinesDeliveryLogsDirectMail).
* È stato risolto un problema relativo all'integrazione Assets on Demand.
* È stato risolto un problema che si verificava eseguendo lo zoom in nella visualizzazione Timeline. (CAMP-33628)
* È stato risolto un problema che impediva l'invio immediato delle prove per i messaggi e-mail con data e ora pianificata. (CAMP-33723)
* È stato risolto un problema relativo ai messaggi transazionali che generavano log degli errori quando un utente si disconnetteva. (CAMP-31698)
* È stato corretto un errore che poteva verificarsi in ambienti specifici durante la pianificazione di un messaggio e-mail.
* È stato risolto un problema che causava il fallimento del flusso di lavoro di esecuzione dell'aggiornamento.
* È stato risolto un problema di sicurezza che causava l'interruzione del contenuto dell'e-mail quando l'oggetto conteneva più righe.


## Rilascio 19.2.7 - luglio 2019 {#release-19-2-7---july-2019}

### Miglioramenti {#improvements-2}

* La query di eliminazione GDPR è stata migliorata per migliorare le prestazioni.
* È stato risolto un problema che poteva causare arresti Web dopo l'aggiornamento 19.2. (CAMP-34862)
* È stato risolto un problema che poteva impedire agli utenti non amministratori di salvare o pianificare i rapporti. (CAMP-31133)
* È stato risolto un problema che si verificava quando si utilizzava "|" come separatore di data nell'attività del flusso di lavoro del file di caricamento. (CAMP-34706)

## Rilascio 19.2.4 - giugno 2019 {#release-19-2-4---june-2019}

### Designer e-mail {#email-designer-2}

* È stato risolto un problema che impediva agli utenti di modificare i frammenti in caso di utilizzo di tag di stile vuoti nell'HTML. Questa è una correzione per CAMP-33778 in 19.2.3.

## Rilascio 19.2.3 - giugno 2019 {#release-19-2-3---june-2019}

### Designer e-mail {#email-designer-1}

È stata introdotta una serie di miglioramenti e correzioni per ottimizzare i frammenti nella release 19.2. I frammenti creati di recente funzioneranno perfettamente. I frammenti creati in precedenza sono stati disattivati e devono essere migrati nel nuovo formato. A tal fine, fare clic su ciascun frammento e convalidarne la migrazione nel nuovo formato. È consigliabile verificare alcuni frammenti prima di eseguire la migrazione di tutti.

* È stato risolto un problema che impediva agli utenti di modificare un frammento dopo averlo sbloccato. Questo problema interessava i frammenti esistenti durante l'aggiornamento a 19.2. (CAMP-33778)
* È stato risolto un problema durante l'utilizzo del contenuto dinamico. Nell’HTML sono stati aggiunti spazi aggiuntivi.

### Altri miglioramenti {#other-improvements-2}

* È stato risolto un problema che poteva impedire la ripresa dell'invio SMS dopo la disconnessione del connettore SMS.
* È stato risolto un problema che poteva chiudere le connessioni SMPP quando TLS era abilitato.
* È stato risolto un problema che poteva chiudere le connessioni SMPP quando TLS era abilitato.
* L'opzione "Launch_URL_Campaign" è stata aggiunta in Campaign per gestire le proprietà delle applicazioni mobili create con l'SDK di Adobe Experience Platform Mobile.
* È stato corretto un errore a causa del quale l'opzione di ambiente sandbox veniva deselezionata dopo il caricamento del certificato di una proprietà mobile appena creata e l'uscita dalla pagina delle proprietà dell'applicazione mobile.
* È stato risolto un problema che impediva di arricchire un contenuto di messaggi transazionali con informazioni provenienti dalla risorsa Servizio. (CAMP-33707)
* È stato risolto un problema nelle pagine di destinazione Blacklist che si verificava durante il tentativo di annullare la sottoscrizione di profili da un servizio.

## Rilascio 19.2 - maggio 2019 {#release-19-2---may-2019}

### Cosa c'è di nuovo? {#what-s-new-}

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
   <td> <p>Per migliorare l'efficienza del lavoro di amministratore, puoi monitorare facilmente la capacità e gestire le impostazioni delle tue istanze (a partire dalla gestione dei server SFTP).</p><p>Per ulteriori informazioni, consultate la documentazione <a href="https://helpx.adobe.com/campaign/kb/control-panel.html"></a> dettagliata e il video <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-control-panel-video-use.html">sulle</a>procedure.</p></td> 
  </tr> 
  <tr> 
   <td> Notifiche locali<br /> </td> 
   <td> <p>I messaggi di notifica locale consentono di informare gli utenti quando nuovi dati diventano disponibili nelle applicazioni mobili, anche senza avere accesso a Internet o all’applicazione mobile in esecuzione in primo piano. Le notifiche locali vengono attivate da un'applicazione mobile in un momento particolare e in base a un evento.</p><p>Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type"></a>dettagliata.</p></td> 
  </tr> 
  <tr> 
   <td> Miglioramento del flusso di lavoro - Aggiunta di un payload all'attività del segnale esterno<br /> </td> 
   <td> <p>Avviate un flusso di lavoro con un payload quando determinate condizioni vengono soddisfatte da un altro flusso di lavoro o da una chiamata REST API per l'integrazione con i sistemi esterni. Questo include anche una nuova attività di <strong>test</strong> in cui è possibile eseguire test su questa funzionalità.</p><p>Per ulteriori informazioni, consultate la documentazione <a href="../../automating/using/calling-a-workflow-with-external-parameters.md"></a> dettagliata e il video <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-external-signal-activity-feature-video-use.html">sulle</a>procedure.</p></td> 
  </tr> 
  <tr> 
   <td> Miglioramento delle pagine di destinazione - Google reCAPTCHA<br /> </td> 
   <td> <p>Sfruttate Google reCAPTCHA per evitare spam sulle pagine di destinazione senza richiedere alcuna azione da parte dei clienti.</p><p>Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/designing-a-landing-page.md#setting-google-recaptcha"></a>dettagliata.</p></td> 
  </tr> 
 </tbody> 
</table>

### Miglioramenti della sicurezza {#security-enhancements}

* È stato risolto un potenziale problema di sicurezza del clickjacking nell'area di lavoro di reporting.

### Miglioramenti di Email Designer {#email-designer-enhancements}

* È stato risolto un problema che si verificava durante la duplicazione dei frammenti e il tentativo di utilizzarli in Designer e-mail. (CAMP-33193)
* È stato risolto un problema che creava spazi indesiderati quando si utilizzavano elementi in linea nell'interfaccia di Email Designer. (CAMP-32163)
* È stato risolto un problema che causava l'eliminazione di alcuni attributi di tag HTML aggiuntivi aggiunti dall'utente dopo il salvataggio del contenuto dell'e-mail in Designer e-mail. (CAMP-32162)
* È stato risolto un problema che causava la visualizzazione di un tag di Microsoft Office in modalità HTML di E-mail Designer anche dopo la sua rimozione. (CAMP-32141)
* Se un'e-mail è stata creata con una versione precedente di Designer e-mail, all'apertura del contenuto dell'e-mail verrà visualizzata una finestra a comparsa in cui viene richiesto all'utente di eseguire l'aggiornamento alla versione più recente. (CAMP-31529)
* È stato risolto un problema che poteva distorcere le immagini di un'e-mail creata con Designer e-mail quando venivano distribuite ad alcuni client di messaggistica. (CAMP-31407)
* È stato risolto un problema che impediva ad alcuni elementi come elenchi o pulsanti di essere visualizzati correttamente in modalità di testo normale durante la creazione in modalità HTML. (CAMP-32582, CAMP-32542)
* È stato risolto un problema che impediva la visualizzazione di più di 50 unità organizzative in un modello di contenuto o nelle proprietà del frammento. (CAMP-32932)
* È stato risolto un problema relativo al colore di sfondo della finestra di visualizzazione durante la ricezione di un'e-mail creata con Designer e-mail in Outlook. (CAMP-31402)
* È stato risolto un problema che poteva impedire che il contenuto delle e-mail create con Designer e-mail fosse reattivo quando aperto in Outlook. (CAMP-31400)
* È stato risolto un problema che impediva il corretto funzionamento del contenuto dinamico utilizzato in un oggetto e-mail. (CAMP-32837)
* È stato risolto un problema relativo all'oggetto dell'e-mail che non risultava con la corretta escape.
* È stato risolto un problema che impediva il caricamento dei frammenti nella palette a sinistra di Designer e-mail.
* È stato risolto un problema che impediva la visualizzazione dei frammenti creati durante l'edizione del contenuto dell'e-mail nella palette a sinistra di Designer e-mail durante l'aggiornamento dell'elenco dei frammenti.
* Sono stati corretti diversi problemi che si verificavano durante l'utilizzo del contenuto dinamico in un'e-mail.
* È stato risolto un problema che si verificava con il selettore colore durante il tentativo di definire un colore utilizzando i valori RGB.
* È stato risolto un problema che impediva alla pagina mirror di essere reattiva durante la ricezione dell'e-mail su un dispositivo mobile.

### Miglioramenti dei messaggi transazionali {#transactional-messaging-enhancements}

Diversi miglioramenti sono stati aggiunti al canale di messaggistica transazionale per ottimizzare il funzionamento e le prestazioni.

* La durata dei messaggi transazionali è stata estesa per garantire che tutti i messaggi vengano inviati prima della scadenza, in particolare quando vengono eseguiti dei tentativi.
* Le prestazioni dei messaggi transazionali sono state incrementate distribuendo il carico sui diversi thread di invio.
* Il processo di messaggistica transazionale è stato ottimizzato per poter iniziare in parallelo più analisi dello stesso messaggio.
* È stato risolto un problema che poteva causare un throughput e una latenza incoerenti per le notifiche push transazionali.
* È stato risolto un problema che causava la visualizzazione di un'audience di destinazione non corretta per le consegne di esecuzione dei messaggi transazionali.
* È stato risolto un problema che si verificava durante l'importazione di un pacchetto con una configurazione di evento e il messaggio transazionale associato. Per ulteriori informazioni, consulta la documentazione [](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages)dettagliata.
* È stato risolto un problema che eliminava i dati di raccolta dai profili di test creati per un messaggio transazionale contenente gli elenchi di prodotti.

### Altre modifiche {#other-changes}

* È stata aggiunta una nuova opzione all'account esterno di SMS. Consente di limitare il numero massimo di processi MTA che inviano SMS per controllare meglio il numero di connessioni parallele. Per ulteriori informazioni, consultare la nota tecnica relativa al protocollo e alle impostazioni [del connettore](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html) SMS.
* Quando si pubblica una risorsa con estensione API, se l'API è già stata pubblicata, ora viene aggiornata automaticamente ogni volta che viene pubblicata di nuovo. In precedenza questa azione era manuale e l'aggiornamento dell'API non riusciva a interrompere la risorsa del profilo o del servizio di questa API. Per ulteriori informazioni, consulta la documentazione [](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)dettagliata.
* La dimensione del codice ZIP è stata rimossa da Generazione rapporti dinamica. È consigliabile utilizzare le dimensioni Città, Paese e Stato.
* Il trigger dell'evento "Primo avvio" del ciclo di vita per i messaggi in-app è stato rimosso.
* Quando si esporta un pacchetto con gruppi di protezione, ora contiene i ruoli assegnati a ciascun gruppo. (CAMP-32960)
* Nell'attività Carica file, una nuova opzione consente di verificare che le colonne del file che state caricando corrispondano alla definizione della colonna. Per ulteriori informazioni, consulta la documentazione [](../../automating/using/load-file.md)dettagliata. (CAMP-32229)
* I flussi di lavoro possono ora essere avviati con un payload, consentendo di utilizzare e condividere parametri esterni tra le attività all'interno del flusso di lavoro. Per ulteriori informazioni, consulta la documentazione [](../../automating/using/calling-a-workflow-with-external-parameters.md)dettagliata. (CAMP-29412 e CAMP-29413)
* Le API Campaign Standard ora ti consentono di aggiornare le unità geografiche e organizzative dei profili utilizzando un payload. Per ulteriori informazioni, consulta la documentazione [](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)dettagliata.
* I messaggi di errore quando un oggetto del database non è accessibile sono stati resi più chiari.
* Nell'attività del file Extract, le funzionalità Javascript sono state aggiornate quando si definisce il nome di un file da esportare. Nel campo Output è ora disponibile solo la funzione formatDate. Per ulteriori informazioni, consulta la documentazione [](../../automating/using/extract-file.md)dettagliata.
* È stata migliorata la generazione automatica degli ID di sequenza per le risorse personalizzate. Per impostazione predefinita, le chiavi primarie per le nuove risorse personalizzate sono ora a 64 bit.
* È stata migliorata la modalità di test della pubblicazione delle risorse personalizzata. Ora agli utenti viene visualizzato un messaggio di avviso se l'ultima pubblicazione di risorse personalizzata non è riuscita e non è fissa. Dopo un errore di pubblicazione di una risorsa personalizzata, è possibile ripristinare l'ultima versione di lavoro. Per ulteriori informazioni, consulta la documentazione [](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)dettagliata.
* È stata aggiunta una nuova opzione nell'attività del file di trasferimento. Consente di ordinare i file quando si utilizza l’azione di download dei file in modalità SFTP. Per ulteriori informazioni, consulta la documentazione [](../../automating/using/transfer-file.md)dettagliata. (CAMP-33109)

### Patch {#patches}

* È stato risolto un problema che poteva causare una perdita di memoria all'MTA quando le impostazioni SMS venivano ricaricate.
* È stato risolto un problema che poteva impedire la pubblicazione degli aggiornamenti del database in modalità di ripristino.
* È stato risolto un problema che causava discrepanze tra Adobe Analytics Reports e Adobe Campaign Dynamic Reporting. (CAMP-25393)
* È stato risolto un errore che causava un errore nel flusso di lavoro di condivisione dei report.
* È stato corretto un errore che impediva agli utenti di inviare messaggi in-app con un semplice URL multimediale.
* È stato risolto un problema che causava la visualizzazione di un'app mobile anche se il relativo certificato non era caricato nell'istanza.
* È stato corretto un errore che impediva il funzionamento dei campi di personalizzazione quando si utilizza **Target per tutti gli utenti di un modello di app** Mobile.
* È stato eseguito il provisioning delle nuove istanze Campaign Standard. (CAMP-32635 E CAMP-32344)
* È stato corretto un errore che impediva la personalizzazione della formula della data in un flusso di lavoro. (CAMP-30336)
* È stato risolto un problema che si verificava durante la definizione di una formula di data personalizzata che poteva impedire la disponibilità dei campi "Dati aggiuntivi" e "Codice segmento" nell'elenco a discesa. (CAMP-32383)
* È stato risolto un problema che poteva impedire alle attività "Trasferisci file" e "Estrai file" di trovare i file rifiutati se erano crittografati. (CAMP-32377)
* È stato risolto un problema nelle API che poteva impedire al filtro lineCount di eseguire il rendering del conteggio totale esatto. (CAMP-31424)
* È stato risolto un problema nelle pagine di destinazione che poteva impedire ai campi di input di visualizzare il valore aggiornato una volta che era stato modificato. (CAMP-31401)
* È stato risolto un problema che poteva provocare un'attivazione inattesa dell'attività del segnale.
* È stato risolto un problema che poteva impedire la visualizzazione dell'anteprima e-mail quando il pubblico era vuoto.
* È stato risolto un problema nell'attività "Estrai file" che poteva generare un file mentre l'opzione "Non generare un file se la transizione in entrata è vuota" era attivata.
* È stato risolto un problema che causava la disattivazione del flusso di lavoro di recapito se il completamento non andava a buon fine.
* È stato risolto un problema che poteva impedire agli utenti di salvare o pianificare i rapporti. (CAMP-31133)

## Rilascio 19.1.3 - marzo 2019 {#release-19-1-3---march-2019}

### Miglioramenti di Email Designer {#email-designer-enhancements-1}

* È stato risolto un problema che impediva la modifica di un modello dopo il salvataggio.
* Sono stati risolti diversi problemi durante l'utilizzo di un modello creato in precedenza in un'e-mail.
* È stato risolto un problema che impediva ai componenti di essere nascosti nei modelli importati.

### Altri miglioramenti {#other-improvements}

* È stato corretto un errore durante la visualizzazione delle regole di tipologia. (CAMP-32059 E CAMP-31849)
* È stato risolto un problema che impediva la modifica delle regole di tipologia. (CAMP-31750)
* È stato risolto un problema con il processo inMail che poteva arrestarsi in modo imprevisto. (CAMP-31238)

## Rilascio 19.1 - febbraio 2019 {#release-19-1---february-2019}

### Cosa c'è di nuovo? {#what-s-new--1}

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Miglioramenti per i rapporti sui canali push<br /> </td> 
   <td> <p>Sono stati aggiunti diversi miglioramenti alla generazione di rapporti sui canali push per consentirvi di misurare il coinvolgimento degli utenti in modo più intuitivo. Con questa versione, stiamo espandendo l'elenco delle metriche dei canali push in tre diverse metriche: Impressioni, clic, aperture (App Open) per misurare e analizzare in modo più efficace l'interazione degli utenti con le notifiche push. Inoltre, stiamo standardizzando la definizione e l'implementazione di queste metriche. Il rapporto integrato della notifica push è stato migliorato anche con visualizzazioni e metriche comunemente utilizzate.</p><p> Per ulteriori informazioni, consulta la documentazione <a href="../../reporting/using/push-notification-report.md"></a>dettagliata.</p> </td> 
  </tr> 
  <tr> 
   <td> Integrazione di Launch per l'app mobile<br /> </td> 
   <td> <p>Questa release contiene l'integrazione di Adobe Campaign con le versioni GA delle estensioni Android e iOS per Adobe Campaign Standard in Adobe Experience Platform Launch e Mobile SDK. Queste estensioni supportano la messaggistica push, la messaggistica in-app e gli aggiornamenti del profilo delle app per dispositivi mobili.</p><p> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/about-typology-rules.md#typology-rules"></a>dettagliata.</p> </td> 
  </tr> 
  <tr> 
   <td> Messaggistica in-app mobile<br /> </td> 
   <td> <p>Questa release contiene la versione GA del canale in-app in Campaign. Da un punto di vista funzionale, le aggiunte più importanti alla versione beta sono i report dinamici per il canale in-app e la stretta di mano sicura tra Mobile SDK e MCIAS (Marketing Cloud In-App Messaging Service che fornisce le regole in-app all'SDK). La stretta di mano sicura garantisce che i dati PII degli utenti non cadano in mani malevoli e consente di mantenere la privacy degli utenti su un dispositivo condiviso, cancellando la cache dei messaggi ogni volta che l'utente si disconnette.</p><p>Per ulteriori informazioni, consultate la documentazione <a href="../../channels/using/about-in-app-messaging.md"></a> dettagliata e l'esercitazione <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-in-app-message-tutorial.html"></a>in-app dedicata.</p> </td> 
  </tr> 
  <tr> 
   <td> Miglioramenti del flusso di lavoro<br /> </td> 
   <td> <p>Sono state aggiunte le seguenti funzionalità del flusso di lavoro:</p> 
    <ul> 
     <li> Ora puoi copiare e incollare le attività all'interno di un flusso di lavoro o di un altro flusso di lavoro dalla stessa istanza Campaign. In questo modo, potete duplicare facilmente un intero flusso di lavoro o attività specifiche e mantenere le impostazioni inizialmente definite. Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities"></a>dettagliata. (CAMP-2014) </li> 
     <li> Quando si utilizza l'attività <strong>Carica file</strong> , ora è possibile aggiungere una marca temporale al nome del file contenente i record rifiutati. Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/load-file.md#configuration"></a>dettagliata. </li> 
     <li> <strong>Le attività di query</strong> e <strong>segmentazione</strong> ora consentono di abilitare una transizione in uscita se le attività non recuperano dati. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Miglioramenti della sicurezza {#security-enhancements-1}

* Il codice HTML generato della pagina di destinazione è stato aggiornato per impedire l’indicizzazione del motore di ricerca.

### Miglioramenti di Email Designer {#email-designer-enhancements-2}

* È ora disponibile un set di quattro modelli di e-mail reattiva all’avanguardia, progettati dagli artisti di Behance.

   Per ulteriori informazioni, consulta la documentazione [](../../designing/using/using-reusable-content.md#content-templates)dettagliata.

* La nuova esperienza di registrazione vi consentirà di avviare la creazione di e-mail in modo più rapido e di accedere più facilmente alla documentazione e alle esercitazioni.

   Per ulteriori informazioni, consulta la documentazione [](../../designing/using/overview.md#email-designer-home-page)dettagliata.

* Ora puoi configurare il numero di colonne e la larghezza in base alle tue esigenze.

   Per ulteriori informazioni, consulta la documentazione [](../../designing/using/designing-from-scratch.md#defining-the-email-structure)dettagliata.

* Quando effettuate modifiche in visualizzazione mobile, potete nascondere alcuni componenti solo nella visualizzazione mobile per un utilizzo efficace dello spazio.

   Per ulteriori informazioni, consulta la documentazione [](../../designing/using/styles.md#switching-to-mobile-view)dettagliata.

* Ora potete aggiungere canali social personalizzati al modello e-mail sopra a quelli già disponibili.
* È stato risolto un problema che impediva lo scorrimento verso il basso del menu della struttura quando si utilizzavano più di 18 strutture. (CAMP-31173)
* È stato risolto un problema che causava la visualizzazione della preintestazione sopra il contenuto durante l'inoltro di un'e-mail contenente un preheader inviato con Adobe Campaign. (CAMP-30736)
* È stato risolto un problema che impediva l’aggiornamento dell’oggetto quando si faceva clic sull’opzione **Aggiorna contenuto** AEM dopo la modifica dell’oggetto in Adobe Experience Manager. (CAMP-29984)
* Sono stati risolti diversi problemi che impedivano l'utilizzo di immagini dinamiche da Adobe Target.
* È stato risolto un problema che impediva l'aggiornamento dell'anteprima durante il recupero del contenuto in fase di preparazione, se il contenuto era stato precedentemente importato da un URL.
* L'icona YouTube è stata aggiunta al componente di contenuto **Social** .
* La visualizzazione **Elenco** è stata aggiunta per i componenti di contenuto e i frammenti visualizzati nella palette Designer e-mail.

### Altri miglioramenti {#other-improvements-1}

* Adobe Campaign è ora completamente conforme allo standard FCM sia per le app SDK V4 che per le app SDK AEP.
* Adobe Campaign supporta le notifiche push sul sistema operativo Wear di Android e anche watchOS di Apple.
* I messaggi di avviso e di errore che possono essere visualizzati durante la navigazione nell'interfaccia sono stati resi più chiari e facili da comprendere.
* È ora possibile aggiungere all'elenco dei profili le colonne relative ai campi opt-in e opt-out ("Non contattare più...").
* L’elenco a discesa Fuso orario nella schermata di creazione del profilo è stato spostato dalla sezione Indirizzo alla sezione superiore dell’interfaccia.
* È ora possibile aggiungere separatori durante la configurazione delle schermate delle risorse personalizzate, per organizzare i campi in categorie.

   Per ulteriori informazioni, consulta la documentazione [](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration)dettagliata.

### Altre modifiche {#other-changes-1}

* Adobe Campaign e Adobe Experience Cloud non supporteranno più Microsoft Internet Explorer 11 a partire dalla release Primavera 2019 e Campaign Standard 19.2. Passate a Microsoft Edge o a un altro browser supportato. Consultate [Pagina delle funzioni](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html) obsolete e rimosse.
* Il campo del codice **del** paese dalla risorsa Profilo è stato rinominato in codice **del** paese/regione.

### Patch {#patches-1}

* È stato risolto un problema che impediva l'invio del messaggio durante l'aggiunta di un profilo di test a un messaggio di transazione e-mail. (CAMP-29854)
* È stato risolto un problema che rallentava l'invio di messaggi da altri canali se l'invio era limitato per un canale quando l'invio di messaggi da tutti i canali veniva attivato contemporaneamente.
* È stato risolto un problema che causava l'avvio dell'MTA per l'invio di messaggi SMS quando la connessione dell'account esterno non era ancora stabilita.
* È stato risolto un problema che si verificava con la frequenza e l'ora di inizio dell'esecuzione dell'attività dell'Utilità di pianificazione. (CAMP-30745)
* È stato risolto un problema che poteva verificarsi con la generazione PKEY quando si utilizzavano risorse di profilo estese. (CAMP-30285)
* È stato risolto un problema che poteva verificarsi con le regole di Fatigue basate su un giorno di calendario. (CAMP-30136)
* È stato risolto un problema che poteva verificarsi quando si tentava di accedere a risorse personalizzate con nomi che terminavano con "Base". (CAMP-30109)
* È stato risolto un problema che impediva l’utilizzo di una chiamata PATCH per sottoscrivere un profilo a un servizio. (CAMP-29728)
* È stato risolto un problema che poteva danneggiare un flusso di lavoro durante l'importazione di un file XML tramite l'attività Carica file. (CAMP-29208 e CAMP-28205)
* È stato risolto un problema che impediva la generazione di collegamenti di cardinalità inversa durante il collegamento di risorse personalizzate. (CAMP-30476)
* È stato risolto un problema che impediva di estendere i log di consegna solo quando si utilizzava il codice del segmento.
* È stato risolto un problema che poteva duplicare le righe quando si utilizzava l'attività di trasferimento file nei flussi di lavoro.
* È stato risolto un problema che impediva l'invio dei rapporti pianificati al momento scelto.
* È stato risolto un problema che causava una discrepanza tra i KPI "Per distribuire" e "Inviato" per una consegna in-app in un flusso di lavoro.
* È stato risolto un problema che impediva il monitoraggio per un messaggio in-app creato con un HTML personalizzato.
* È stato risolto un problema che impediva il salvataggio del contenuto per la distribuzione in-app quando veniva utilizzato in un flusso di lavoro.
* È stato risolto un problema che impediva la visualizzazione delle applicazioni mobili per gli amministratori.
* È stato risolto un problema che causava il fallimento del flusso di lavoro tecnico di aggiornamento della conformità. (CAMP-26387)
* È stato risolto un problema che causava discrepanza tra i profili di destinazione durante la creazione di una consegna in-app e quelli visualizzati nel dashboard di distribuzione. (CAMP-28722)
* È stato risolto un problema con l'integrazione del servizio core Campaign e Assets che poteva impedire la selezione di una risorsa condivisa in un messaggio e-mail.

## Rilascio 19.0 - gennaio 2019 {#release-19-0---january-2019}

### Cosa c'è di nuovo? {#what-s-new--2}

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
   <td> Disponibilità generale di Email Designer<br /> </td> 
   <td> <p>Il nuovo intuitivo e-mail Designer (precedentemente noto come Creative Designer) è stato spostato in GA. Ora supporta tutte le funzionalità dell'editor di contenuti legacy, tra cui:</p> 
    <ul> 
     <li> Utilizzo di immagini <a href="../../integrating/using/adding-target-dynamic-content.md">dinamiche da Adobe Target</a> </li> 
     <li> Possibilità di <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">recuperare automaticamente i contenuti da un URL al momento della preparazione</a> </li> 
     <li> Modelli <a href="../../designing/using/using-reusable-content.md#content-templates">di contenuto</a>out-of-the-box completamente conformi. </li> 
    </ul> 
    <p>Per ulteriori informazioni, consultate la documentazione <a href="../../designing/using/overview.md"></a> dettagliata e il video <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html">sulle</a>procedure. Miglioramenti e correzioni sono elencati di seguito.</p><p>Di conseguenza, l'editor del contenuto delle e-mail legacy ora è obsoleto. Per ulteriori informazioni, consultare questa <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">pagina</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Elenco prodotti nelle e-mail transazionali<br /> </td> 
   <td> <p>Ora potete fare riferimento a una o più raccolte di prodotti in un messaggio e-mail transazionale. Ad esempio, puoi inviare automaticamente un messaggio e-mail di abbandono del carrello in cui sono elencati tutti i prodotti inclusi nel carrello dell'utente con un'immagine, un prezzo e un collegamento a ciascun prodotto.</p><p>Per ulteriori informazioni, consultate la documentazione <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message"></a> dettagliata e il video <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html">sulle</a>procedure.</p> </td> 
  </tr> 
  <tr> 
   <td> Visualizzazione mobile in Designer e-mail<br /> </td> 
   <td> <p>È ora possibile passare a una visualizzazione mobile dedicata durante la modifica del contenuto delle e-mail. Questo consente di ottimizzare il design reattivo di un’e-mail modificando separatamente tutte le opzioni di stile per la visualizzazione mobile, ad esempio adattando i margini, le dimensioni dei font più piccole, i diversi colori di sfondo e così via.</p><p> Per ulteriori informazioni, consulta la documentazione <a href="../../designing/using/styles.md#switching-to-mobile-view"></a>dettagliata.</p> </td> 
  </tr> 
  <tr> 
   <td> Miglioramenti della versione beta della messaggistica in-app<br /> </td> 
   <td> <p>La funzione Beta Messaggistica in-app è stata migliorata con le seguenti funzionalità:</p> 
    <ul> 
     <li> Il canale Beta in-app è compatibile con GDPR </li> 
     <li> Integrazione con le API di Analytics per la compilazione dei menu a discesa Triggers </li> 
     <li> Aspetto intuitivo e descrizione dei modelli di consegna </li> 
     <li> Miglioramenti all’interfaccia di authoring dal punto di vista dell’usabilità </li> 
    </ul> <p>Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-in-app-messaging.md"></a>dettagliata.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Miglioramenti {#improvements}

* Una nuova opzione nell'attività di caricamento dei dati ora consente di applicare una fase di post-elaborazione al file contenente i record rifiutati (ad esempio. Compressione formato ZIP). (CAMP-24521)
* Una nuova opzione nell'attività di aggiornamento dei dati ora consente di configurare la dimensione batch massima per i dati da caricare. (CAMP-28400)
* È stata migliorata la selezione dello stato dell'indirizzo dei profili. Quando si seleziona un paese, l'elenco a discesa "Stato" ora viene aggiornato automaticamente con i valori degli stati pertinenti. (CAMP-28874)
* Una nuova opzione nell'attività del file Extract ora impedisce la generazione di un file se la transizione in entrata è vuota. In questo modo si evita di creare e caricare file vuoti sui server SFTP.
* Il rapporto di riepilogo sulla distribuzione è stato migliorato.
* L'elenco dei paesi disponibili per la definizione dell'indirizzo di un profilo è stato arricchito. (CAMP-26707)
* Viene ora visualizzato un messaggio di errore quando si tenta di importare un flusso di lavoro integrato.

### Designer e-mail {#email-designer}

* È stato risolto un problema che consentiva la funzionalità dell'unità geografica su un modello e-mail o un frammento di contenuto creato con Designer e-mail, anche se questa funzionalità era disabilitata in Adobe Campaign, rendendo il modello o il frammento non disponibile quando si tentava di accedervi nuovamente. (CAMP-28174)
* È stato risolto un problema che impediva il salvataggio delle condizioni di contenuto dinamico durante la modifica del contenuto con Designer e-mail. (CAMP-27905)
* È stato risolto un problema che rimuoveva la versione HTML dal contenuto dell'e-mail dopo la modifica della versione di testo normale di un messaggio e l'interruzione della sincronizzazione HTML in Designer e-mail. (CAMP-28507)
* È stato risolto un problema che impediva l'apertura dell'interfaccia di Email Designer quando si utilizzava Internet Explorer 11. (CAMP-28273)
* È stato risolto un problema che causava una distorsione del rendering delle impostazioni di stile applicate ai pulsanti con Designer e-mail.
* È stato risolto un problema in Designer e-mail che rendeva modificabile un URL da un frammento di contenuto utilizzato in un messaggio e-mail, che non era previsto in quanto il frammento era bloccato per impostazione predefinita.
* È stato risolto un problema che impediva la visualizzazione in Microsoft Office del componente divisore di Email Designer.
* È stato risolto un problema che causava il blocco delle pagine su alcuni browser Internet quando si visualizzava un contenuto sincronizzato da AEM tramite l’editor dei contenuti e-mail legacy. (CAMP-29068)
* È stato corretto un errore che si verificava quando si faceva clic su un’immagine in un messaggio e-mail con l’editor di contenuti e-mail legacy. (CAMP-30424)
* È stato risolto un problema che impediva la visualizzazione dei frammenti appena creati durante la modifica di un'e-mail con Designer e-mail. (CAMP-29928)
* È stato risolto un problema che impediva la corretta visualizzazione del testo del pulsante nelle e-mail create con Designer e ricevute utilizzando il client di posta elettronica di Outlook.
* È ora possibile creare messaggi transazionali di profilo utilizzando e-mail Designer. (CAMP-28900)
* È stato corretto un errore in Designer e-mail che rendeva modificabile il contenuto durante il recupero automatico del contenuto da un URL al momento della preparazione, mentre doveva essere bloccato.

### Patch {#patches-2}

* È stato risolto un problema che causava la visualizzazione di log di consegna non corretti nel reporting dinamico. (CAMP-23446)
* È stato risolto un problema che poteva interessare i numeri nel rapporto Riepilogo rimbalzo (CAMP-28703)
* È stato risolto un problema con l'integrazione del servizio core Campaign and Assets che poteva impedire la visualizzazione delle risorse durante la selezione **[!UICONTROL Image shared from Adobe Experience Cloud]** in un messaggio e-mail (CAMP-28732).
* È stato risolto un problema che impediva l'invio di messaggi SMS contenenti il carattere "uno" anche se la traslitterazione era autorizzata nell'account esterno SMPP. (CAMP-29041)
* È stato risolto un problema che poteva visualizzare record duplicati quando si utilizzava un'attività di segmentazione nei flussi di lavoro. (CAMP-28743)
* È stato risolto un problema che impediva l'eliminazione di una delle mappature dei valori su una colonna in un'attività del flusso di lavoro. (CAMP-28708)
* È stato risolto un problema nell'attività di trasferimento file, quando si utilizzavano caratteri jolly con l'opzione "Verifica dell'esistenza del file". (CAMP-28977)
* È stato risolto un problema nell'attività di trasferimento file che poteva verificarsi durante l'aggiornamento delle impostazioni dell'account esterno. (CAMP-28894)
* È stato risolto un problema relativo ai filtri personalizzati nell'editor di query quando si utilizzava la condizione "E-mail non vuota". (CAMP-28741)
* È stato risolto un problema che poteva verificarsi durante l'esportazione di tabelle di risorse personalizzate con più di 100 k record. (CAMP-28150)
* È stato risolto un problema che impediva l'eliminazione di messaggi transazionali collegati ai trigger. (CAMP-28385)
* Sono state rimosse le password che venivano visualizzate in modo invisibile in alcuni log SMS.
* È stato risolto un problema che causava un errore nelle connessioni al simulatore SMPP a causa di una password vuota inviata da Adobe Campaign.
* È stato risolto un problema che impediva l'invio di campagne in caso di connessioni SMS instabili.
* È stato risolto un problema che causava la visualizzazione di invii eliminati nel reporting dinamico.
* È stato risolto un problema che poteva impedire il recupero di dati aggiuntivi dai registri di consegna, dai registri di tracciamento e dall'esclusione delle tabelle dei registri, quando si utilizzava un'attività di arricchimento in un flusso di lavoro.
* È stato risolto un problema con le richieste di eliminazione GDPR che poteva verificarsi quando si utilizzava un tipo di collegamento "N collegamento raccolta cardinalità" e l'opzione "Eliminazione del record di destinazione implica l'eliminazione dei riferimenti ai record tramite il collegamento".
* È stato risolto un problema di condivisione dei report.
* È stato risolto un problema che poteva causare problemi di throughput durante l'invio di una notifica push.
* È stato risolto un problema relativo ai file di output per posta diretta che causavano la mancanza di campi.
* È stato risolto un problema che consentiva agli utenti di modificare i flussi di lavoro integrati.
* È stato risolto un problema durante la creazione di una campagna basata su un modello di campagna che includeva un flusso di lavoro con un'attività estratta configurata. (CAMP-29198)
* È stato risolto un problema relativo all'attività di estrazione dei file che impediva l'utilizzo della stessa espressione per più elementi. (CAMP-29182)
* È stato risolto un problema, nell'editor di query, che causava la condizione di unione tra il registro di trasmissione e il registro di tracciamento per rtEvent. (CAMP-28780)
* È stato risolto un problema che impediva il salvataggio delle modifiche all'opzione "Azione specifica" della pagina di destinazione. (CAMP-29422)
* È stato risolto un problema che impediva l'esportazione del payload di un evento in un flusso di lavoro. (CAMP-29029)
* È stato risolto un problema che impediva l'esclusione dei numeri SMS in blacklist in un messaggio SMS. (CAMP-28898)
* È stato risolto un problema che poteva impedire ai fornitori SMPP di ricevere notifiche in caso di errore durante l'elaborazione dei messaggi in arrivo. (CAMP-29804)
* È stato risolto un problema che consentiva l'eliminazione di account esterni con consegne associate. (CAMP-29738)
* Il throughput di invio è stato migliorato e stabilizzato per i messaggi SMS.
* È stato risolto un problema che impediva l'utilizzo del carattere "~" in un messaggio SMS. (CAMP-29172)
* È stato risolto un problema nelle consegne con l’opzione di ottimizzazione Invia ora. (CAMP-29231)

