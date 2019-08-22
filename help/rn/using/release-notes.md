---
title: Note sulla versione
seo-title: Note sulla versione
description: Note sulla versione
seo-description: In questa pagina sono elencate tutte le versioni recenti di Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 1 cf 2 e 40 c-beca -43 db -8261-a 1820 ee 86 ad 3
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: riferimento
topic-tags: campaign-standard-release
discoiquuid: 5 c 7 bfb 74-4002-4 ffe -87 e 8-bddb 41 d 34 b 41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 725c9bf196988717f313bbf72448067fef8e8647

---


# Note sulla versione{#release-notes}

Stai cercando una versione specifica di Adobe Campaign Standard?

Ogni rilascio viene fornito con nuove funzionalità e patch. Fate clic su una versione per visualizzarne il contenuto. Consulta la [Pianificazione del rilascio](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) per scoprire quando verrà rilasciata la prossima release.

Visualizza gli ultimi aggiornamenti [della documentazione](../../rn/using/documentation-updates.md) per Adobe Campaign Standard. Se stai cercando una versione precedente, consulta le seguenti pagine: [Note sulla versione 2018](../../rn/using/release-notes-2018.md)- [Note sulla versione 2017](../../rn/using/release-notes-2017.md)- [Note sulla versione 2015-2016](../../rn/using/release-notes-2015-2016.md). Consultate anche l'elenco delle funzioni [obsolete e rimosse](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

## Aggiornamento del Pannello di controllo - Agosto 2019 {#controlpanel-update---august-2019}

### Novità {#what-s-new-4}

Abbiamo aggiunto nuove funzionalità agli utenti Admin per ricevere notifiche prima della scadenza dei certificati SSL relativi ai loro domini. Per ulteriori informazioni, consulta la documentazione [dettagliata](https://helpx.adobe.com/campaign/kb/control-panel-subdomains-certificates.html).

Inoltre, gli utenti Admin ora possono eliminare le chiavi SSH aggiunte per accedere ai server SFTP.

Tenete presente che il Pannello di controllo è disponibile per i clienti ospitati solo su AWS. Questi aggiornamenti saranno disponibili il 26 agosto.

## Rilascio 19.3 - Luglio 2019 {#release-19-3---july-2019}

### Novità {#what-s-new-3}

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
   <td> <p>Per una personalizzazione più approfondita, l'attività API esterna consente di portare dati da sistemi esterni in un flusso di lavoro tramite una chiamata REST API. Gli endpoint REST possono essere un sistema di gestione clienti, Adobe I/O Runtime o un endpoint REST di Adobe Experience Cloud (ad es. Piattaforma dati, Target, Analytics, Campaign).</p><p>Questa funzionalità è attualmente in versione beta pubblica.</p><p>Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/external-api.md">dettagliata</a> e il video <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">di istruzioni</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Rapporto sul segmento del flusso di lavoro<br /> </td> 
   <td> <p>Questa funzione consente agli esperti di marketing di suddividere le prestazioni di distribuzione in base al codice del segmento. Quando crei un flusso di lavoro e utilizzi un'attività di segmentazione per assegnare segmenti alla popolazione di consegna, questi segmenti possono ora entrare nella stessa consegna. Questo consente di visualizzare le statistiche di apertura/clic basate su più segmenti all'interno di una singola consegna.</p><p>Per ulteriori informazioni, consulta la documentazione <a href="../../reporting/using/creating-a-report-workflow-segment.md">dettagliata</a> e il video <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">di istruzioni</a>.</p></td>
  </tr> 
 </tbody> 
</table>

### Miglioramenti della sicurezza {#security-enhancements-2}

* Risolto un problema di sicurezza per evitare attacchi Denial of Service (DoS) su richieste non valide per ottenere immagini. (CAMP -33454)

### Miglioramenti di Designer Designer {#email-designer-enhancements-3}

* È stato risolto un problema che causava aggiunta di tag di stile HTML aggiuntivi a un modello HTML ogni volta che veniva aggiunto un componente, che poteva aumentare notevolmente le dimensioni del modello. (CAMP -34694)
* È stato risolto un problema che poteva impedire la disponibilità di alcune opzioni di menu della barra degli strumenti superiore destra. (CAMP -34577)
* È stato risolto un problema che si verificava quando il blocco di contenuto URL della pagina Speculare veniva inserito in un contenuto e-mail. (CAMP -34779)
* È stato risolto un problema che si verificava durante l'utilizzo del codice JPS in un messaggio e-mail, rendendo difficile la modifica del contenuto. (CAMP -34574)
* È stato risolto un problema che causava il troncamento delle immagini nella parte superiore quando vi veniva aggiunto un collegamento ipertestuale. (CAMP -34382)
* Risoluzione di un problema di visualizzazione durante l'utilizzo di E-mail Designer con Firefox. (CAMP -34364)
* Risolti diversi problemi che si verificavano nella modalità Avanzate durante la definizione del contenuto dinamico in un messaggio e-mail. (CAMP -34351, CAMP -34333, CAMP -34331)
* Risolti diversi problemi che si verificavano con l'editor di regole di contenuto dinamico (CAMP -34304, CAMP -34303).
* È stato risolto un problema che poteva impedire la visualizzazione del campo Collegamento nel riquadro Impostazioni di Designer e-mail (CAMP -33749).
* È stato risolto un problema relativo all'icona YouTube che era sovrapportata nelle e-mail inviate. (CAMP -33726)
* Risolto un problema di sicurezza che rendeva modificabile il contenuto della pagina speculare. (CAMP -33691)
* È stato risolto un problema che rispediva l'output HTML quando si utilizzava il simbolo maggiore di quello dinamico. (CAMP -33688)
* È stato risolto un problema che si verificava utilizzando l'opzione Annulla durante la modifica del testo in E-mail Designer. (CAMP -32565)
* È stato risolto un problema che causava altri tag durante l'annullamento degli stili invece di rimuoverli. (CAMP -32359)
* Ora potete definire se ogni componente utilizzato in un'e-mail verrà visualizzato solo sui dispositivi desktop o solo sui dispositivi mobili.
* Ora potete impostare la larghezza e l'altezza di un componente Contenuto social.
* È stato risolto un problema che impediva la rimozione del codice sorgente precedente del contenuto dinamico dopo l'eliminazione del contenuto dinamico.
* È stato risolto un problema che poteva impedire l'aggiornamento dell'oggetto di un'e-mail dopo la modifica.
* È stato risolto un problema che impediva a un n: La struttura delle colonne viene selezionata una volta rilasciata nell'area di lavoro.
* È stato risolto un problema che rendeva la miniatura del messaggio sfocata nel dashboard e-mail.
* È stato risolto un problema che impediva la corretta visualizzazione dello sfondo per le e-mail ricevute in Outlook.
* Risolti alcuni problemi di ordinamento nella home page di Designer di e-mail.
* È stato risolto un problema che si verificava durante la duplicazione di varianti quando si utilizzavano contenuti dinamici.
* Alcuni campi non desiderati sono stati rimossi dal riquadro Impostazioni di Designer di e-mail.

### Altri miglioramenti {#other-improvements-3}

* Grazie all'integrazione con Adobe Experience Platform Services Services, Adobe Campaign è ora compatibile con l'invio di messaggi di marketing basati sulla posizione agli abbonati all'applicazione mobile tramite l'SDK della piattaforma Experience Platform. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md).
* La funzione di reporting è stata migliorata per migliorare l'esperienza. Per utilizzare questa funzione, è necessario accettare il Contratto di utilizzo dei rapporti dinamici. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* Nei flussi di lavoro, è stata aggiunta una nuova opzione per l'anteprima delle dieci esecuzioni successive di un flusso di lavoro. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../automating/using/scheduler.md).
* Nell'attività Pianificatore, una nuova opzione consente di selezionare un giorno specifico di una settimana specifica per le consegne mensili. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../automating/using/scheduler.md).
* Quando si creano consegne ricorrenti senza periodi di aggregazione, il dashboard di consegna ora consente di confermare la conferma prima dell'invio della consegna. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../sending/using/confirming-the-send.md).
* Ora potete personalizzare l'etichetta di una distribuzione con variabili degli eventi dichiarate nell'attività del segnale esterno del flusso di lavoro. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../automating/using/calling-a-workflow-with-external-parameters.md).
* La query di eliminazione GDPR è stata migliorata per migliorare le prestazioni. (CAMP -33504)
* L'opzione "ftp" è stata rimossa dall'interfaccia di configurazione dell'account esterno. (CAMP -34472)
* Ora potete attivare e disattivare l'opzione Modalità di test SMTP per ogni messaggio e-mail. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP -34602)

### Altre modifiche {#other-changes-2}

* Nell'interfaccia delle proprietà di consegna è stato aggiunto un avviso. Specifica che le consegne vengono preparate in base al loro periodo di aggregazione e ti permettono di chiamare il flusso di lavoro più volte al giorno, accertandoti che non abbiano alcun punto. (CAMP -34393)
* È stato aggiunto un avviso nelle schermate di configurazione delle risorse personalizzate. Consigliamo di utilizzare massimo 30 caratteri per ID risorsa personalizzati. Ciò si applica anche a campi di risorse, chiavi, indici e collegamenti personalizzati.
* Viene visualizzato un messaggio quando si tenta di eliminare un messaggio transazionale utilizzato da una pagina di destinazione come messaggio di conferma.
* Un avviso ora viene visualizzato nei registri dei flussi di lavoro quando un'attività è in esecuzione da oltre 6 ore. Questo non vale per le attività di notifica push, consegna, segnale, avvio, fine, fine, fork, pianificazione e attesa.
* Un avviso ora viene visualizzato nei registri dei flussi di lavoro quando raggiungete il numero massimo di flussi di lavoro in esecuzione contemporaneamente.
* I flussi di lavoro che sono stati in pausa o in stato non riuscito per oltre 7 giorni vengono ora interrotti per poter utilizzare meno spazio su disco. L'attività di pulizia viene visualizzata nei registri di workflow.
* Quando si utilizza un'attività «Trasferimento file», ora viene registrato un errore se la dimensione del file supera lo spazio disponibile su disco.
* L'azione Reindirizza all'URL di destinazione non può più essere selezionata per il pulsante secondario nei messaggi in-app.

### Patch {#patches-3}

* È stato risolto un problema che potrebbe causare errori di accesso al GDPR.
* È stato risolto un problema che poteva causare la cancellazione di attivatori quando venivano ricevuti più attivatori per un profilo univoco.
* È stato risolto un problema che poteva causare un errore errato di pubblicazione delle risorse personalizzato dopo l'accesso.
* È stato risolto un problema che visualizzava una pagina vuota durante la creazione o l'estensione di una risorsa personalizzata.
* È stato risolto un problema che impediva a un pubblico con appsubscriptionrcp di essere disponibile come dimensione di targeting per il targeting in una distribuzione mobile.
* È stato corretto un errore a causa del quale gli indirizzi e-mail netti non venivano inseriti in quarantena. (CAMP -24587)
* È stato risolto un problema che si verificava quando si aggiungeva una regola di tipo typology e quindi si eliminava prima di salvare il testo. (CAMP -32789)
* È stato risolto un problema che poteva impedire la visualizzazione del contenuto della pagina di destinazione durante la disabilitazione del contenuto dinamico. (CAMP -32924)
* È stato risolto un problema relativo alle consegne ricorrenti che si verificavano quando si utilizzava la personalizzazione negli attributi di una consegna principale. (CAMP -32983)
* È stato risolto un problema in flussi di lavoro che impediva di leggere i risultati di una transizione contenente dati di messaggi SMS in arrivo. (CAMP -33134)
* È stato risolto un problema nei flussi di lavoro che si verificava durante la combinazione di attività di foratura e di esclusione per creare audience. (CAMP -33401)
* È stato risolto un problema che poteva impedire la visualizzazione del contenuto della pagina speculare e l'invio di messaggi per le consegne ricorrenti. (CAMP -33413)
* Risolto un problema che causava un errore quando si utilizzava un'attività Unione tra profili e audience. Questo problema è stato causato da un'incompatibilità delle chiavi di identificazione nelle transizioni di input. (CAMP -33713)
* Risolto un problema nelle attività di test che impediva all'espressione "reccount" di utilizzare la sintassi corretta quando si faceva doppio clic su di essa. (CAMP -33756)
* È stato risolto un problema che poteva causare un messaggio di errore all'apertura dei registri di workflow tecnica Fatturazione. (CAMP -34313)
* È stato risolto un problema nelle pagine di destinazione che poteva verificarsi durante la configurazione dei campi caselle di controllo con iscrizioni. (CAMP -34369)
* È stato risolto un problema che si verificava durante la configurazione di un elenco e l'aggiunta del campo «icona». (CAMP -34585)
* È stato risolto un problema che impediva l'utilizzo di "|" e " %" come separatori di data o ora nelle attività del flusso di lavoro di caricamento dei file. (CAMP -34706)
* È stato risolto un problema che si verificava quando si utilizzavano condizioni di visibilità con caselle di controllo nelle pagine di destinazione. (CAMP -34802)
* È stato risolto un problema nell'attività Arricchimento che impediva la visualizzazione dei campi nella scheda «Additional data» (Dati aggiuntivi), se la dimensione di filtro era impostata su di tracciamento e la dimensione di destinazione al profilo.
* È stato risolto un problema che causava un messaggio di errore durante l'esportazione di una risorsa "workflowtemplate".
* È stato risolto un problema che si verificava durante la creazione di un nuovo profilo, che impediva il salvataggio del campo «Codice Paese/Regione», se selezionato dalla finestra di dialogo.
* Risolti diversi problemi che si verificavano quando si utilizzava il modello di importazione Direct Mail (updatequarantinesdeliverylogsdirectmail).
* È stato risolto un problema relativo all'integrazione Risorse on Demand.
* È stato risolto un problema che si verificava durante lo zoom nella visualizzazione Timeline. (CAMP -33628)
* È stato risolto un problema che impediva l'invio immediato delle prove per i messaggi e-mail con data e ora pianificate. (CAMP -33723)
* È stato risolto un problema relativo ai messaggi transazionali generati dai registri di errore quando un utente si disconnetteva. (CAMP -31698)
* È stato corretto un errore che poteva verificarsi in ambienti specifici durante la pianificazione di un messaggio e-mail.
* È stato risolto un problema a causa del quale il flusso di lavoro di prestazioni per la distribuzione aggiornata non andava a buon fine.
* È stato risolto un problema di sicurezza che causava il blocco del contenuto dell'e-mail quando l'oggetto conteneva più righe.


## Rilascio 19.2.7 - Luglio 2019 {#release-19-2-7---july-2019}

### Miglioramenti {#improvements-2}

* La query di eliminazione GDPR è stata migliorata per migliorare le prestazioni.
* È stato risolto un problema che poteva causare arresti anomali Web dopo l'aggiornamento del 19.2. (CAMP -34862)
* È stato risolto un problema che poteva impedire agli utenti non amministratori di salvare o pianificare i rapporti. (CAMP -31133)
* Risolto un problema quando si utilizzava "|" come separatore della data nell'attività del flusso di lavoro di caricamento. (CAMP -34706)

## Rilascio 19.2.4 - Giugno 2019 {#release-19-2-4---june-2019}

### Email Designer {#email-designer-2}

* È stato risolto un problema che impediva agli utenti di modificare i frammenti quando venivano usati tag stile vuoti nel codice HTML. Si tratta di una correzione di follow-up per CAMP -33778 nella 19.2.3.

## Rilascio 19.2.3 - Giugno 2019 {#release-19-2-3---june-2019}

### Email Designer {#email-designer-1}

È stata introdotta una serie di miglioramenti e correzioni per ottimizzare i frammenti nella release 19.2. I frammenti creati di recente funzionano direttamente. I frammenti creati in precedenza sono disabilitati e devono essere migrati nel nuovo formato. A questo scopo, fare clic su ciascun frammento e convalidarne la migrazione al nuovo formato. È consigliabile sottoporre a test alcuni frammenti prima di eseguirne la migrazione tutti.

* È stato risolto un problema che impediva agli utenti di modificare un frammento dopo averlo sbloccato. Ciò interessava i frammenti esistenti durante l'aggiornamento a 19.2. (CAMP -33778)
* Risolto un problema durante l'utilizzo del contenuto dinamico. Nell'HTML sono stati aggiunti spazi aggiuntivi.

### Altri miglioramenti {#other-improvements-2}

* È stato risolto un problema che poteva impedire l'invio SMS dopo la disconnessione del connettore SMS.
* È stato risolto un problema che poteva chiudere le connessioni SMPP quando TLS era abilitato.
* È stato risolto un problema che poteva chiudere le connessioni SMPP quando TLS era abilitato.
* L'opzione «Launch_ URL_ Campaign» è stata aggiunta in Campaign per gestire le proprietà delle applicazioni mobili create con l'SDK di Adobe Experience Platform Mobile.
* Risoluzione di un errore che causava la deselezione dell'opzione dell'ambiente sandbox dopo il caricamento del certificato di una nuova proprietà mobile creata e la chiusura della pagina delle proprietà dell'applicazione mobile.
* È stato risolto un problema che impediva di arricchire un contenuto di messaggi transazionali con informazioni provenienti dalla risorsa Servizio. (CAMP -33707)
* È stato risolto un problema nelle pagine di destinazione Blacklist che si verificava durante l'annullamento della sottoscrizione dei profili da un servizio.

## Release 19.2 - Maggio 2019 {#release-19-2---may-2019}

### Novità {#what-s-new-}

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
   <td> <p>Per migliorare l'efficienza del lavoro come utente amministratore, potete monitorare facilmente la capacità e gestire le impostazioni delle istanze (a partire dalla gestione dei server SFTP).</p><p>Per ulteriori informazioni, consulta la documentazione <a href="https://helpx.adobe.com/campaign/kb/control-panel.html">dettagliata</a> e il video <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-control-panel-video-use.html">di istruzioni</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Notifiche locali<br /> </td> 
   <td> <p>I messaggi di notifica locale consentono di informare gli utenti quando nuovi dati diventano disponibili all'interno delle applicazioni mobili, anche senza avere accesso a Internet o all'applicazione mobile in esecuzione in primo piano. Le notifiche locali vengono attivate da un'applicazione mobile in un determinato momento e a seconda di un evento.</p><p>Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">dettagliata</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Miglioramento del flusso di lavoro - Aggiunta di un payload all'attività segnale esterno<br /> </td> 
   <td> <p>Avviate un flusso di lavoro con un payload quando le condizioni definite vengono soddisfatte correttamente da un altro flusso di lavoro o una chiamata REST API per l'integrazione con i sistemi esterni. Ciò include anche una nuova <strong>attività di test</strong> in cui potete eseguire test su questa funzionalità.</p><p>Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">dettagliata</a> e il video <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-external-signal-activity-feature-video-use.html">di istruzioni</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Miglioramento delle pagine di destinazione - Google recaptcha<br /> </td> 
   <td> <p>Sfrutta Google recaptcha per impedire la spam sulle pagine di destinazione senza che venga richiesto di eseguire operazioni da parte dei clienti.</p><p>Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/designing-a-landing-page.md#setting-google-recaptcha">dettagliata</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

### Miglioramenti della sicurezza {#security-enhancements}

* È stato corretto un potenziale problema di sicurezza clickjacking nell'area di lavoro per il reporting.

### Miglioramenti di Designer Designer {#email-designer-enhancements}

* È stato risolto un problema che si verificava duplicando i frammenti e tentando di utilizzarli in E-mail Designer. (CAMP -33193)
* È stato risolto un problema che causava spazi indesiderati quando si utilizzavano elementi in linea nell'interfaccia di Designer Designer. (CAMP -32163)
* È stato risolto un problema che eliminava alcuni attributi aggiuntivi di tag HTML aggiunti dall'utente dopo il salvataggio del contenuto e-mail in Email Designer. (CAMP -32162)
* È stato risolto un problema che visualizzava un tag di Microsoft Office nella modalità HTML di Designer di e-mail anche dopo la rimozione. (CAMP -32141)
* Se si è creata un'e-mail utilizzando una versione precedente di E-mail Designer, all'apertura del contenuto dell'e-mail viene visualizzata una finestra a comparsa che richiede all'utente di effettuare l'aggiornamento alla versione più recente. (CAMP -31529)
* È stato risolto un problema che poteva distorcere le immagini da un'e-mail creata con E-mail Designer quando veniva inviata ad alcuni client di messaggistica. (CAMP -31407)
* È stato risolto un problema che impediva la corretta visualizzazione di alcuni elementi come elenchi o pulsanti in modalità testo normale in modalità HTML. (CAMP -32582, CAMP -32542)
* È stato risolto un problema che impediva la visualizzazione di più di 50 unità organizzative in un modello di contenuto o proprietà frammento. (CAMP -32932)
* È stato risolto un problema relativo al colore dello sfondo della visualizzazione durante la ricezione di un'e-mail creata con E-mail Designer in Outlook. (CAMP -31402)
* È stato risolto un problema che poteva impedire il reinvio dei contenuti e-mail creati con E-mail Designer in Outlook. (CAMP -31400)
* È stato risolto un problema che impediva il corretto funzionamento del contenuto dinamico se utilizzato in un oggetto e-mail. (CAMP -32837)
* È stato risolto un problema relativo all'oggetto dell'e-mail che non veniva in sequenza corretta.
* È stato risolto un problema che impediva il caricamento dei frammenti nella palette a sinistra di Designer.
* È stato risolto un problema che impediva la visualizzazione dei frammenti creati durante l'edizione del contenuto e-mail nella palette a sinistra di Designer e all'aggiornamento dell'elenco dei frammenti.
* Risolti diversi problemi che si verificavano durante l'utilizzo del contenuto dinamico in un messaggio e-mail.
* È stato risolto un problema che si verificava con il selettore colore quando si tentava di definire un colore utilizzando i valori RGB.
* È stato risolto un problema che impediva la reinvio della pagina speculare quando si riceveva l'e-mail su un dispositivo mobile.

### Miglioramenti dei messaggi transazionali {#transactional-messaging-enhancements}

Sono stati aggiunti diversi miglioramenti al canale di messaggistica Transazionali per ottimizzare l'operazione e le prestazioni.

* La durata del messaggio transazionali è stata estesa per essere certi che tutti i messaggi vengano inviati prima della scadenza, soprattutto quando vengono eseguiti tentativi.
* Le prestazioni di messaggistica transazionali sono state incrementate distribuendo il carico su thread di invio diversi.
* Il processo di messaggistica transazionali è stato ottimizzato per poter iniziare in parallelo con un'analisi multipla dello stesso messaggio.
* È stato risolto un problema che poteva causare la continuità e la latenza non coerenti per le notifiche push transazionali.
* È stato risolto un problema che causava un pubblico di destinazione errato per le consegne di esecuzione dei messaggi transazionali.
* È stato risolto un problema che si verificava durante l'importazione di un pacchetto con una configurazione evento e il messaggio transazionali associato. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages).
* È stato risolto un problema che eliminava i dati della raccolta dai profili di test creati per un messaggio transazionale contenente gli elenchi dei prodotti.

### Altre modifiche {#other-changes}

* All'account esterno SMS è stata aggiunta una nuova opzione. Consente di limitare il numero massimo di processi MTA che inviano SMS per controllare meglio il numero di connessioni parallele. Per ulteriori informazioni, fare riferimento al [protocollo di connettore SMS e alle impostazioni](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html) tecniche.
* Quando si pubblica una risorsa con estensione API, se l'API è già stata pubblicata, ora viene aggiornata automaticamente ogni volta che viene nuovamente pubblicata. In precedenza questa azione era manuale e l'aggiornamento dell'API poteva interrompere la risorsa di profilo o servizio dell'API. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* La dimensione del codice ZIP è stata rimossa da Reporting dinamico. Consigliamo di utilizzare invece le dimensioni Città, Paese, Stato.
* L'attivatore dell'evento "Primo avvio" per i messaggi in-app è stato rimosso.
* Quando si esporta un pacchetto con gruppi di protezione, ora contiene i ruoli assegnati a ciascun gruppo. (CAMP -32960)
* Nell'attività Carica file, una nuova opzione consente di verificare che le colonne del file che state caricando corrispondano alla definizione della colonna. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../automating/using/load-file.md). (CAMP -32229)
* Adesso, i flussi di lavoro possono essere avviati con un payload, consentendo di utilizzare e condividere parametri esterni tra attività all'interno del flusso di lavoro. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP -29412 e CAMP -29413)
* Le API Campaign Standard ora consentono di aggiornare le unità geografiche e organizzative con un payload. Per ulteriori informazioni, consulta la documentazione [dettagliata](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).
* I messaggi di errore quando un oggetto del database non è accessibile sono stati resi più chiari da comprendere.
* Nell'attività Estrai file, le funzionalità Javascript sono state aggiornate quando si definisce il nome di un file da esportare. È possibile utilizzare solo la funzione formatdate per l'uso nel campo Output. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../automating/using/extract-file.md).
* È stata migliorata la generazione ID della sequenza automatica per le risorse personalizzate. Le chiavi principali per le nuove risorse personalizzate sono ora a 64 bit per impostazione predefinita.
* La modalità di test della pubblicazione delle risorse personalizzata è stata migliorata. Un messaggio di avviso ora viene presentato agli utenti se l'ultima pubblicazione personalizzata non è riuscita e non è fissa. Dopo un errore di pubblicazione delle risorse personalizzate, potete tornare all'ultima versione di lavoro. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* Nell'attività del file di trasferimento è stata aggiunta una nuova opzione. Consente di ordinare i file quando si utilizza l'azione di download File, in modalità SFTP. Per ulteriori informazioni, consulta la documentazione [dettagliata](../../automating/using/transfer-file.md). (CAMP -33109)

### Patch {#patches}

* È stato risolto un problema che causava la perdita di memoria per MTA quando le impostazioni SMS venivano ricaricate.
* È stato risolto un problema che poteva impedire la pubblicazione di aggiornamenti di database in modalità riparazione.
* È stato risolto un problema che causava discrepanze tra rapporti Adobe Analytics e Adobe Campaign Dynamic Reporting. (CAMP -25393)
* È stato corretto un errore a causa del quale il flusso di lavoro di condivisione report non andava a buon fine.
* È stato corretto un errore che impediva agli utenti di inviare messaggi in-app con sufficiente URL multimediale.
* È stato risolto un problema che visualizzava un'app mobile anche se il certificato non veniva caricato nell'istanza.
* Risoluzione di un errore che impediva l'utilizzo dei campi di personalizzazione quando si utilizzava **il Target tutti gli utenti di un modello app** Mobile.
* Sono state fornite nuove istanze di Campaign Standard. (CAMP -32635 e CAMP -32344)
* Risolto un errore che impediva la personalizzazione della formula data in un flusso di lavoro. (CAMP -30336)
* Risolto un problema durante la definizione di una formula di data personalizzata che poteva impedire la disponibilità dei campi "Additional data" (Dati aggiuntivi) e "Segment code" (Codice segmento) nell'elenco a discesa. (CAMP -32383)
* È stato risolto un problema che impediva la ricerca dei file da parte delle attività "Trasferimento del file" e "Extract file" (Estrai file) in caso di cifratura. (CAMP -32377)
* È stato risolto un problema nelle API che poteva impedire al filtro linecount di eseguire il rendering del conteggio totale totale. (CAMP -31424)
* È stato risolto un problema nelle pagine di destinazione che poteva impedire che i campi di input mostrassero il valore aggiornato dopo la modifica. (CAMP -31401)
* È stato risolto un problema che poteva indurre l'attivazione imprevista di un'attività del segnale.
* È stato risolto un problema che poteva impedire la visualizzazione dell'anteprima e-mail quando l'audience era vuota.
* È stato risolto un problema nell'attività "Extract file" (Estrai file) che generava un file mentre l'opzione «Non generare un file se la transizione in entrata è vuota» è stata attivata.
* Risolto un problema che causava la disattivazione del flusso di lavoro di Deliverability in caso contrario.
* È stato risolto un problema che impediva agli utenti di salvare o pianificare i rapporti. (CAMP -31133)

## Rilascio 19.1.3 - Marzo 2019 {#release-19-1-3---march-2019}

### Miglioramenti di Designer Designer {#email-designer-enhancements-1}

* È stato risolto un problema che impediva l'modifica di un modello dopo averlo salvato.
* Risolti diversi problemi quando si utilizzava un modello creato in precedenza in un messaggio e-mail.
* È stato risolto un problema che impediva l'occultamento dei componenti nei modelli importati.

### Altri miglioramenti {#other-improvements}

* Risolto un errore durante la visualizzazione delle regole di tipologia. (CAMP -32059 e CAMP -31849)
* È stato risolto un problema che impediva la modifica delle regole di tipologie. (CAMP -31750)
* È stato risolto un problema relativo al processo inmail che poteva arrestarsi in modo imprevisto. (CAMP -31238)

## Rilascio 19.1 - Febbraio 2019 {#release-19-1---february-2019}

### Novità {#what-s-new--1}

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Miglioramenti ai rapporti sui canali push<br /> </td> 
   <td> <p>Sono stati aggiunti diversi miglioramenti al reporting dei canali push per consentire di misurare il coinvolgimento degli utenti in modo più intuitivo. Con questa release, stiamo espandendo l'elenco delle metriche Canale push a tre metriche diverse: Impression, Clic, Aperture (Apri app) per misurare e analizzare l'interazione degli utenti con le notifiche push in modo più efficace. Inoltre, stiamo standardizzando la definizione e l'implementazione di queste metriche. Anche il rapporto incorporato sulla notifica push è stato migliorato con visualizzazioni e metriche comunemente utilizzate.</p><p> Per ulteriori informazioni, consulta la documentazione <a href="../../reporting/using/push-notification-report.md">dettagliata</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Integrazione lancio per app mobile<br /> </td> 
   <td> <p>Questa release contiene l'integrazione di Adobe Campaign con le versioni GA di estensioni Android e iOS per Adobe Campaign Standard negli SDK di Adobe Experience Platform Launch e Mobile. Queste estensioni supportano i messaggi push, i messaggi in-app e gli aggiornamenti di profilo app mobili.</p><p> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/about-typology-rules.md#typology-rules">dettagliata</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Messaggistica in-app per dispositivi mobili<br /> </td> 
   <td> <p>Questa release contiene la versione GA del canale In-app in Campaign. Da un punto di vista funzionale, le aggiunte più importanti alla versione beta sono rapporti dinamici per il canale in-app e handshake protetto tra Mobile SDK e MCIAS (Servizio Messaggistica in-app di Marketing Cloud che fornisce le regole in-app all'SDK). L'handshake protetto assicura che i dati PII degli utenti non siano in mani dannose e di mantenere la privacy degli utenti su un dispositivo condiviso cancellando la cache dei messaggi ogni volta che l'utente esce.</p><p>Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-in-app-messaging.md">dettagliata</a> e l'esercitazione <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-in-app-message-tutorial.html">dedicata in-app</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Miglioramenti al flusso di lavoro<br /> </td> 
   <td> <p>Sono state aggiunte le seguenti funzionalità del flusso di lavoro:</p> 
    <ul> 
     <li> Ora potete copiare-paste attività all'interno di un flusso di lavoro o di un altro flusso di lavoro dalla stessa istanza Campaign. In questo modo, potete duplicare facilmente un intero flusso di lavoro o attività specifiche e mantenere le impostazioni definite inizialmente. Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">dettagliata</a>. (CAMP -20014) </li> 
     <li> Quando si utilizza l'attività <strong>Carica file</strong> , ora è possibile aggiungere una marca temporale al nome del file contenente i record rifiutati. Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/load-file.md#configuration">dettagliata</a>. </li> 
     <li> <strong>Le attività di query</strong> e <strong>segmentazione</strong> ora consentono di abilitare una transizione in uscita se le attività non recuperano alcun dato. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Miglioramenti della sicurezza {#security-enhancements-1}

* Il codice HTML della pagina di destinazione generato è stato aggiornato per impedire l'indicizzazione del motore di ricerca.

### Miglioramenti di Designer Designer {#email-designer-enhancements-2}

* È ora disponibile un set di quattro modelli e-mail reattivi, progettati dagli artisti Behance.

   Per ulteriori informazioni, consulta la documentazione [dettagliata](../../start/using/about-templates.md#content-templates).

* La nuova esperienza di registrazione vi consentirà di avviare più rapidamente la creazione e-mail e di accedere più facilmente alla documentazione ed esercitazioni.

   Per ulteriori informazioni, consulta la documentazione [dettagliata](../../designing/using/about-email-content-design.md#email-designer-home-page).

* Ora è possibile configurare il numero di colonne e di larghezza in base alle esigenze.

   Per ulteriori informazioni, consulta la documentazione [dettagliata](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

* Quando si modifica in visualizzazione mobile, è possibile nascondere alcuni componenti solo in visualizzazione mobile per un utilizzo effettivo dello spazio.

   Per ulteriori informazioni, consulta la documentazione [dettagliata](../../designing/using/about-email-content-design.md#switching-to-mobile-view).

* Ora potete aggiungere canali social personalizzati al modello e-mail sopra quelli già disponibili.
* È stato risolto un problema che impediva di scorrere il menu struttura quando si utilizzavano più di 18 strutture. (CAMP -31173)
* È stato risolto un problema che visualizzava la preintestazione sulla parte superiore del contenuto quando si inoltrava un messaggio e-mail contenente una preintestazione inviata con Adobe Campaign. (CAMP -30736)
* È stato risolto un problema che non consentiva di aggiornare l'oggetto quando si faceva clic sull'opzione **Aggiorna contenuto** AEM dopo aver modificato l'oggetto in Adobe Experience Manager. (CAMP -29984)
* Sono stati corretti diversi problemi che impedivano l'utilizzo di immagini dinamiche da Adobe Target.
* È stato risolto un problema che impediva l'aggiornamento dell'anteprima durante il recupero del contenuto in fase di preparazione se il contenuto era stato precedentemente importato da un URL.
* L'icona YouTube è stata aggiunta al **componente** Contenuto social.
* The **List** view has been added for content components and fragments displayed in the Email Designer palette.

### Altri miglioramenti {#other-improvements-1}

* Adobe Campaign è ora completamente conforme con FCM per le app SDK V 4 e AEP SDK.
* Adobe Campaign supporta le notifiche push su Inserisci OS da Android e watchos da Apple.
* I messaggi di avviso e di errore che possono essere visualizzati durante la navigazione nell'interfaccia sono stati resi più chiari e facili da comprendere.
* Ora puoi aggiungere alle colonne dell'elenco dei profili le colonne relative alla rinuncia e alla rinuncia ("No più contact…").
* L'elenco a discesa Fuso orario nella schermata di creazione profilo è stato spostato dalla sezione Indirizzo alla sezione superiore dell'interfaccia.
* È ora possibile aggiungere separatori durante la configurazione delle schermate delle risorse personalizzate, in modo da organizzare i campi in categorie.

   Per ulteriori informazioni, consulta la documentazione [dettagliata](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

### Altre modifiche {#other-changes-1}

* Adobe Campaign e Adobe Experience Cloud cesseranno il supporto per Microsoft Internet Explorer 11 avvio primavera 2019 e Campaign Standard 19.2. Passate a Microsoft Edge o a un altro browser supportato. Consulta [Pagina delle funzioni](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html) obsoleta e rimossa.
* Il **campo del codice** Paese della risorsa Profilo è stato rinominato nel codice **Paese/Regione**.

### Patch {#patches-1}

* È stato risolto un problema che impediva l'invio del messaggio quando si aggiungeva un profilo di prova a un messaggio di transazione e-mail. (CAMP -29854)
* È stato risolto un problema che rallentava il messaggio inviato da altri canali se l'invio risultava basso per un canale quando l'invio da tutti i canali veniva attivato contemporaneamente.
* È stato risolto un problema a causa del quale il MTA iniziava a inviare messaggi SMS quando la connessione dell'account esterno non era ancora definita.
* È stato risolto un problema che si verificava con la frequenza di esecuzione dell'attività Pianificatore e l'ora di inizio. (CAMP -30745)
* È stato risolto un problema che poteva verificarsi con la generazione PKEY quando si utilizzano risorse di profilo estese. (CAMP -30285)
* È stato risolto un problema che poteva verificarsi con le regole Fatigue basate sul giorno del calendario. (CAMP -30136)
* È stato risolto un problema che poteva verificarsi quando si tentavano di accedere alle risorse personalizzate con nomi che terminavano con "Base". (CAMP -30109)
* È stato risolto un problema che impediva di utilizzare una chiamata PATCH per iscrivere un profilo a un servizio. (CAMP -29728)
* È stato risolto un problema che poteva danneggiare un flusso di lavoro durante l'importazione di un file XML tramite l'attività Carica file. (CAMP -29208 e CAMP -28205)
* È stato risolto un problema durante il collegamento di risorse personalizzate che potevano impedire la generazione di collegamenti di sottolineatura inversa. (CAMP -30476)
* È stato risolto un problema che impediva l'estensione di registri di consegna quando si utilizzava solo il codice del segmento.
* È stato risolto un problema che poteva duplicare le righe quando si utilizzava l'attività di trasferimento File nei flussi di lavoro.
* È stato risolto un problema che impediva l'invio dei rapporti pianificati nel momento scelto.
* È stato risolto un problema che causava discrepanze tra i KPI di consegna e Invio per una consegna in-app in un flusso di lavoro.
* È stato risolto un problema che impediva il tracciamento del tracciamento per un messaggio in-app creato con un HTML personalizzato.
* È stato risolto un problema che impediva il salvataggio del contenuto della distribuzione in-app quando utilizzato in un flusso di lavoro.
* È stato risolto un problema che impediva la visualizzazione delle applicazioni mobili per gli amministratori.
* È stato corretto un problema a causa del quale il flusso di lavoro Aggiornamento tecnico non riusciva a fallire. (CAMP -26387)
* È stato risolto un problema che causava discrepanze tra i profili mirati durante la creazione di una distribuzione in-app e quelle visualizzate nel dashboard di distribuzione. (CAMP -28722)
* È stato risolto un problema con l'integrazione del servizio di base Campaign (Campagna) e Assets (Servizi) che impediva la selezione di una risorsa condivisa in un messaggio e-mail.

## Rilascio 19.0 - Gennaio 2019 {#release-19-0---january-2019}

### Novità {#what-s-new--2}

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
   <td> Disponibilità generale di Designer Designer<br /> </td> 
   <td> <p>Il nuovo intuitivo Designer Designer (precedentemente denominato Creative Designer) è stato spostato in GA. Ora supporta tutte le funzioni dell'editor di contenuto legacy, tra cui:</p> 
    <ul> 
     <li> Utilizzo di immagini <a href="../../integrating/using/adding-target-dynamic-content.md">dinamiche da Adobe Target</a> </li> 
     <li> Possibilità di <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">recuperare automaticamente il contenuto da un URL in fase di preparazione</a> </li> 
     <li> Modelli di contenuto <a href="../../start/using/about-templates.md#content-templates">box completamente conformi</a>. </li> 
    </ul> 
    <p>Per ulteriori informazioni, consulta la documentazione <a href="../../designing/using/about-email-content-design.md">dettagliata</a> e il video <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html">di istruzioni</a>. I miglioramenti e le correzioni sono elencati di seguito.</p><p>Pertanto, l'editor di contenuto e-mail legacy è diventato obsoleto. Per ulteriori informazioni, consultate questa <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">pagina</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Elenchi di prodotti nelle e-mail transazionali<br /> </td> 
   <td> <p>Ora potete fare riferimento a una o più raccolte di prodotti in un messaggio e-mail transazionali. Ad esempio, potete inviare automaticamente un'e-mail di abbandono del carrello per tutti i prodotti che si trovavano nel carrello dell'utente con un'immagine, un prezzo e un collegamento a ciascun prodotto.</p><p>Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message">dettagliata</a> e il video <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html">di istruzioni</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Visualizzazione mobile in E-mail Designer<br /> </td> 
   <td> <p>Ora puoi passare a una visualizzazione mobile dedicata durante la modifica del contenuto delle e-mail. Questo consente di regolare la progettazione reattiva di un'e-mail modificando separatamente tutte le opzioni di stile per la visualizzazione mobile, ad esempio adattamento dei margini, dimensioni di font più piccole, colore di sfondo e così via.</p><p> Per ulteriori informazioni, consulta la documentazione <a href="../../designing/using/about-email-content-design.md#switching-to-mobile-view">dettagliata</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Miglioramenti in termini di messaggistica in-app<br /> </td> 
   <td> <p>La funzione Beta messaggistica in-app è stata migliorata con le seguenti funzionalità:</p> 
    <ul> 
     <li> Il canale beta in-app è conforme allo standard GDPR </li> 
     <li> Integrazione con le API di Analytics per compilare gli elenchi a discesa Attivatori </li> 
     <li> Aspetto intuitivo e descrizione dei modelli di consegna </li> 
     <li> Miglioramenti all'interfaccia di authoring dal punto di vista della fruibilità </li> 
    </ul> <p>Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-in-app-messaging.md">dettagliata</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Miglioramenti {#improvements}

* Una nuova opzione nell'attività Carica dati ora consente di applicare un passaggio di post-elaborazione al file contenente i record rifiutati (ex. Compressione formato ZIP). (CAMP -24521)
* Una nuova opzione nell'attività Dati Aggiorna ora consente di configurare la dimensione massima batch per i dati da caricare. (CAMP -28400)
* Selezione dello stato dell'indirizzo dei profili migliorata. Quando si seleziona un paese, l'elenco a discesa «Stato» ora viene aggiornato automaticamente con i valori degli stati pertinenti. (CAMP -28874)
* Una nuova opzione nell'attività del file Extract ora impedisce la generazione di un file se la transizione in entrata è vuota. Ciò evita la creazione e il caricamento di file vuoti sui server Sftp.
* Il rapporto Riepilogo sulla distribuzione è stato migliorato.
* L'elenco dei paesi disponibili durante la definizione dell'indirizzo di un profilo è stato arricchito. (CAMP -26707)
* Quando si tenta di importare un flusso di lavoro integrato viene visualizzato un messaggio di errore.

### Email Designer {#email-designer}

* È stato risolto un problema che attivava la funzionalità di unità geografica su un modello e-mail o un frammento di contenuto creato con E-mail Designer, anche se questa funzionalità era stata disabilitata in Adobe Campaign, il che rendeva il modello o il frammento non disponibile quando si tentava di accedervi di nuovo. (CAMP -28174)
* È stato risolto un problema che impediva il salvataggio delle condizioni di contenuto dinamico durante la modifica del contenuto con E-mail Designer. (CAMP -27905)
* È stato risolto un problema che rimuoveva la versione HTML dal contenuto dell'e-mail dopo la modifica della versione di testo normale di un messaggio e la suddivisione della sincronizzazione HTML in Email Designer. (CAMP -28507)
* È stato risolto un problema che impediva l'apertura dell'interfaccia di Designer di e-mail in Internet Explorer 11. (CAMP -28273)
* È stato risolto un problema che causava la distorsione del rendering Microsoft Outlook delle impostazioni di stile applicate ai pulsanti con E-mail Designer.
* È stato risolto un problema in Designer e-mail che rendeva modificabile un URL da un frammento di contenuto utilizzato in un'e-mail, che non era previsto come frammento per impostazione predefinita.
* È stato risolto un problema che impediva la visualizzazione del componente di divisione di Adobe Livecycle Designer in Microsoft Office.
* È stato risolto un problema che causava il blocco di una pagina su determinati browser Internet quando si visualizzava un contenuto sincronizzato da AEM con l'editor di contenuto e-mail legacy. (CAMP -29068)
* È stato corretto un errore che si verificava quando si faceva clic su un'immagine in un'e-mail quando si utilizzava l'editor di contenuto e-mail legacy. (CAMP -30424)
* È stato risolto un problema che impediva la visualizzazione dei frammenti appena creati durante la modifica di un'e-mail con Email Designer. (CAMP -29928)
* È stato risolto un problema che impediva la corretta visualizzazione del testo del pulsante nelle e-mail create con E-mail Designer e ricevuta utilizzando Client Webmail client.
* È ora possibile creare messaggi transazionali di profilo utilizzando l'e-mail Designer. (CAMP -28900)
* È stato risolto un errore in E-mail Designer che rendeva il contenuto modificabile quando si recuperava il contenuto automaticamente da un URL in fase di preparazione, in quanto dovrebbe essere bloccato.

### Patch {#patches-2}

* È stato risolto un problema che mostrava registri di consegna errati nel reporting dinamico. (CAMP -23446)
* È stato risolto un problema che poteva influenzare i numeri sul rapporto di riepilogo di rimbalzi (CAMP -28703)
* È stato risolto un problema con l'integrazione del servizio di base Campaign (Campagna) e Assets (Servizi) che impediva la visualizzazione delle risorse durante la selezione **[!UICONTROL Image shared from Adobe Experience Cloud]** in un'e-mail (CAMP -28732).
* È stato risolto un problema che impediva l'invio di messaggi SMS contenenti il carattere "contenuto" anche se la traslittura era autorizzata nell'account esterno SMPP. (CAMP -29041)
* È stato risolto un problema che poteva visualizzare record duplicati quando si utilizzava un'attività Segmentazione nei flussi di lavoro. (CAMP -28743)
* È stato risolto un problema che impediva l'eliminazione di una delle mappature valore in una colonna in un'attività del flusso di lavoro. (CAMP -28708)
* Risolto un problema nell'attività di trasferimento File, quando si utilizzavano caratteri jolly con l'opzione "Test per vedere se esiste". (CAMP -28977)
* È stato risolto un problema nell'attività di trasferimento file che poteva verificarsi durante l'aggiornamento delle impostazioni dell'account esterno. (CAMP -28894)
* È stato risolto un problema relativo ai filtri personalizzati nell'editor query quando si utilizzava la condizione "E-mail non vuota". (CAMP -28741)
* È stato risolto un problema che poteva verificarsi durante l'esportazione di tabelle di risorse personalizzate con oltre 100 record. (CAMP -28150)
* È stato risolto un problema che impediva l'eliminazione di messaggi transazionali collegati alle attivazioni. (CAMP -28385)
* Sono state rimosse password che venivano visualizzate in modo sicuro in alcuni registri SMS.
* È stato risolto un problema che causava errori nel simulatore SMPP a causa di password vuota inviata da Adobe Campaign.
* È stato risolto un problema che impediva l'invio di campagne quando le connessioni SMS sono instabilità.
* È stato risolto un problema che visualizzava le consegne eliminate nel reporting dinamico.
* È stato risolto un problema che impediva il recupero di dati aggiuntivi dai registri di consegna, i registri di tracciamento ed escludendo le tabelle dei registri quando si utilizzava un'attività di arricchimento in un flusso di lavoro.
* È stato risolto un problema con le richieste di eliminazione GDPR che potevano verificarsi quando si utilizzava un tipo di collegamento «Collegamento alla raccolta n cardinalità» e «Deleting the target record implies deleting record references by the link».
* È stato corretto un problema di condivisione dei rapporti.
* È stato risolto un problema che poteva causare problemi di velocità durante l'invio di una notifica push.
* È stato risolto un problema relativo ai file di output di posta diretta che mancano campi.
* È stato risolto un problema che consentiva agli utenti di modificare i flussi di lavoro incorporati.
* Risolto un problema durante la creazione di una campagna basata su un modello di campagna, incluso un flusso di lavoro con un'attività di estrazione configurata. (CAMP -29198)
* È stato risolto un problema relativo all'attività di estrazione File che impediva l'utilizzo della stessa espressione per più elementi. (CAMP -29182)
* È stato risolto un problema, nell'editor query, con la condizione di partecipazione tra il registro esteso e il registro di tracciamento per rtevent. (CAMP -28780)
* È stato risolto un problema che impediva il salvataggio delle modifiche all'opzione di pagina «Specifico azione». (CAMP -29422)
* È stato risolto un problema che impediva l'esportazione del payload di un evento in un flusso di lavoro. (CAMP -29029)
* È stato risolto un problema che impediva l'esclusione dei numeri SMS in blacklist in un messaggio SMS. (CAMP -28898)
* È stato risolto un problema che poteva impedire ai fornitori SMPP di ricevere notifiche in caso di errore durante l'elaborazione dei messaggi in arrivo. (CAMP -29804)
* Risolto un problema che consentiva l'eliminazione di account esterni con le consegne associate. (CAMP -29738)
* L'invio è stato migliorato e stabilizzato per i messaggi SMS.
* È stato risolto un problema che impediva l'utilizzo del carattere " ~" in un messaggio SMS. (CAMP -29172)
* È stato risolto un problema nelle consegne con l'opzione di ottimizzazione Ora di invio. (CAMP -29231)

