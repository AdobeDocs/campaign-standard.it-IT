---
solution: Campaign Standard
product: campaign
title: Note sulla versione 2020
description: In questa pagina sono elencate tutte le versioni del 2020 di Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: 36e0f6be4dc8c1a6e4b0d8878d190f2abce99fcd
workflow-type: tm+mt
source-wordcount: '5323'
ht-degree: 100%

---


# Note sulla versione 2020{#release-notes-2020}

[Pianificazione del rilascio](https://helpx.adobe.com/it/campaign/kb/acs-release-planning.html) | [Versioni del Pannello di controllo Campaign](https://docs.adobe.com/content/help/it-IT/control-panel/using/release-notes.html) | [Aggiornamenti alla documentazione](../../rn/using/documentation-updates.md) | [Note sulla versione precedenti](../../rn/using/release-notes-2019.md) | [Funzioni obsolete](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=it#)

![](assets/do-not-localize/cp-icon.png) **Nuova versione del Pannello di controllo Campaign di giugno** con monitoraggio dei profili attivi, audit del recapito messaggi del sottodominio e gestione delle chiavi GPG. [Ulteriori informazioni](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

![](assets/do-not-localize/cp-icon.png) **Rilascio di ottobre del nuovo Pannello di controllo Campaign** con configurazione dei domini tramite CNAME e nuove funzionalità di monitoraggio del database. [Ulteriori informazioni](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

## Versione 20.4 - ottobre 2020 {#release-20-4---october-2020}

**Novità?**

<table> 
<thead> 
<tr> 
<th> <strong>Gruppi di controllo</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Ora è possibile utilizzare i <strong>Gruppi di controllo</strong> per misurare l’impatto delle campagne escludendo parte delle relative audience. Puoi quindi confrontare il comportamento della popolazione di destinazione che ha ricevuto il messaggio con il comportamento dei contatti non mirati. In base ai registri di invio, puoi anche eseguire il targeting di un gruppo di controllo in campagne future.
</p>
<p>Per ulteriori informazioni consulta la <a href="../../sending/using/control-group.md">documentazione dettagliata</a> e il <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html?lang=it#communication-channels">video tutorial</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>API esterna - Supporto OAuth</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p> Adobe Campaign ora supporta OAuth per l’Authentication nell’attività del flusso di lavoro dell’<strong>API esterna</strong>. Questa nuova funzionalità consente a questa attività di comunicare con i sistemi che richiedono il supporto OAuth.
</p>
<p>Per ulteriori informazioni consulta la <a href="../../automating/using/external-api.md">documentazione dettagliata</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Integrazione Journey AI</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Siamo entusiasti di annunciare Journey AI per tutti i clienti Adobe Campaign Standard.</p>
  <p>Journey AI utilizza l’apprendimento automatico avanzato (ML) per consentire alle aziende di ottimizzare la progettazione e la consegna dei percorsi dei clienti prevedendo le preferenze di coinvolgimento di ognuno.</p>
  <P>Journey AI è costituito da due caratteristiche ML:</p>
<ul> 
     <li> <strong>Valutazione predittiva del coinvolgimento</strong>: identifica in modo intelligente il livello di coinvolgimento preferito dai clienti per eseguire meglio il targeting e personalizzare i messaggi, al fine di aumentare le conversioni e la fidelizzazione. Guarda il <a href="https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">video-tutorial</a>.</li> 
     <li> <strong>Ottimizzazione predittiva del momento di invio</strong>: prevede il momento migliore per inviare e-mail ai clienti in una campagna, in modo da massimizzare i tassi di coinvolgimento e migliorare il ROI delle campagne e-mail. Guarda il <a href="https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">video-tutorial</a>.</li>
    </ul>
  <p>Per informazioni su come iniziare a utilizzare Journey AI, consulta la <a href="../../sending/using/predictive.md">documentazione dettagliata</a> e rivolgiti al tuo Account Executive. Journey AI è disponibile gratuitamente per chi è già cliente di Campaign, tuttavia è previsto un costo di implementazione di circa 50 ore.</p>
    </td> 
</tr> 
</tbody> 
</table>

**Miglioramenti**

* **Gestione della privacy**: il campo **Rinuncia CCPA**, disponibile tramite l’interfaccia Campaign e l’API, ora è supportato anche tramite il servizio core Privacy. Questo campo consente agli utenti di Adobe Campaign di verificare se un cliente ha rinunciato alla vendita di Dati Personali. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#ccpa)
* **Miglioramenti dell’esecuzione del flusso di lavoro** (versione beta): nel contesto di un’iniziativa globale sui flussi di lavoro, sono stati sviluppati alcuni miglioramenti importanti per stabilizzare la gestione della memoria, ridurre la latenza e ottimizzare la memoria utilizzata dai flussi di lavoro durante l’esecuzione. Questi miglioramenti sono attualmente in versione beta e sono disponibili solo per alcuni clienti. La disponibilità generale è prevista per l’inizio del 2021.
* Per migliorare la sicurezza, ora Campaign utilizza un **meccanismo di firma** per tracciare i collegamenti nelle e-mail.
* La configurazione dell’app mobile è stata migliorata con **messaggi di errore più chiari** durante il caricamento di certificati iOS o di chiavi Android.
* È stata migliorata la **gestione degli errori SMS** per impedire l’aggiunta di troppi profili all’elenco di quarantena. Per impostazione predefinita, gli errori SMS ora sono configurati come errori soft invece di errori rigidi. Consulta [questa pagina](https://helpx.adobe.com/it/campaign/kb/sms-connector-protocol-and-settings.html).

**Miglioramenti di E-mail Designer**

* È stata migliorata l’esperienza di utilizzo in E-mail designer con la **nuova guida dinamica contestuale** che collega completamente l’interfaccia utente e la documentazione, permettendo di accedere facilmente ai contenuti più recenti della guida.
* È stato risolto un problema che causava la rimozione delle interruzioni di riga in un messaggio durante la modifica del testo. (CAMP-44483)
* È stato risolto un problema che impediva la generazione e la sincronizzazione automatica del testo normale di un modello HTML. (CAMP-44195)
* È stato risolto un problema che poteva verificarsi durante il ridimensionamento delle immagini. Una volta inviati i messaggi, le immagini non venivano visualizzate correttamente in Microsoft Outlook. (CAMP-44656)
* È stato risolto un problema che si verificava inserendo un pulsante e impostandone la larghezza su &quot;auto&quot;. Una volta inviato il messaggio, il contenuto del pulsante non veniva visualizzato completamente. (CAMP-44560)
* È stato risolto un problema che si verificava durante il caricamento del contenuto da un file HTML allegato. Una volta inviato il messaggio a un indirizzo Gmail, il CSS non veniva applicato, causando un problema di rendering. (CAMP-44085)
* È stato risolto un problema che impediva l’aggiornamento dei frammenti di contenuto utilizzati in precedenza in un messaggio in seguito alla loro modifica diretta nel modello di contenuto. (CAMP-43973)
* È stato risolto un problema relativo alla barra di ricerca **Frammenti** . Durante la ricerca di un frammento esistente, la barra di ricerca non mostrava alcun risultato. (CAMP-44223)
* È stato risolto un problema relativo alle barre di ricerca **Blocchi di contenuto** e **Frammenti**. Utilizzando una delle barre di ricerca, i risultati venivano visualizzati solo facendo clic su **Mostra più risultati**. (CAMP-44205)
* È stato risolto un problema che impediva la spaziatura tra testo e immagini in Microsoft Outlook. (CAMP-45370)
* È stato risolto un problema che si verificava con la duplicazione di un frammento. Dopo aver duplicato il frammento, in quello originale mancavano righe HTML. (CAMP-45207)
* È stato corretto un errore che causava problemi di rendering in Microsoft Outlook. (CAMP-44749)
* È stato corretto un errore che si verificava con la modifica della spaziatura di un **Componente struttura** in un modello di consegna. I tag CSS non riportavano le modifiche apportate alla spaziatura, causando un problema di rendering. (CAMP-45381)
* È stato risolto un problema che si verificava durante il caricamento di un’immagine. L’altezza dell’immagine veniva impostata automaticamente su 0, causando un problema di rendering. (CAMP-45366)

**Altre modifiche**

* Sono stati aggiunti meccanismi di esecuzione di nuovi tentativi in caso di errore durante il tentativo di importare un’audience di Experience Platform utilizzando un’attività **Read audience**. (CAMP-43947, CAMP-43366)
* Ora le unità organizzative vengono impostate automaticamente in modo che corrispondano all’unità organizzativa dell’utente che crea il profilo o l’entità. Le unità organizzative non possono più essere rimosse e lasciate vuote.
* Quando si pubblica una risorsa personalizzata, dopo la preparazione viene ora visualizzata una finestra di conferma a comparsa.
* Per una maggiore chiarezza, è stato migliorato il messaggio a comparsa visualizzato in caso di errore di una risorsa personalizzata.
* L’editor espressioni nei flussi di lavoro è stato migliorato per evitare errori di esecuzione. Sono disponibili [nuove funzioni](../../automating/using/customizing-workflow-external-parameters.md): queste possono essere utilizzate in tutte le attività che consentono di applicare variabili evento dopo la chiamata di un flusso di lavoro con parametri esterni. Inoltre, ora viene visualizzata una descrizione comandi nell’editor espressioni con la descrizione della relativa funzione.
* Sono stati aggiunti [nuovi filtri](../../channels/using/configuring-transactional-event.md#searching-transactional-events) all’elenco degli eventi transazionali. Questi consentono di filtrare le configurazioni dell’evento in base al loro stato, come pure in base all’ultima volta che è stato ricevuto un evento.
* I file di registro visualizzati durante l’esportazione dei pacchetti sono stati resi più specifici e dettagliati per quanto riguarda gli eventuali errori riscontrati.
* Dopo aver inviato un messaggio, ora puoi cercare, filtrare ed esportare l’elenco degli [URL tracciati](../../sending/using/tracking-messages.md).
* La [sincronizzazione automatica tra Launch e Campaign](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) ora è in versione GA ed è attivata per impostazione predefinita.
* La dimensione dei pacchetti di esportazione del flusso di lavoro è stata ottimizzata rimuovendo l’esportazione della prova di invio.
* È stato aggiunto un nuovo messaggio per visualizzare le dimensioni del file scaricato nell’attività di **trasferimento dei file**.
* Sono stati migliorati i messaggi di errore per token di sessione non validi.
* Un nuovo meccanismo ora impedisce l’aggiunta di proxy ai registri di tracciamento e al reporting.
* È stato aggiunto un nuovo messaggio di avviso per facilitare il debug delle attività di gestione dei dati connesse a un’attività di consegna.
* Sono state migliorate le etichette nell’area di lavoro di reporting.
* È stato aggiunto un nuovo passaggio di convalida per impedire l’eliminazione di oggetti tecnici nei messaggi transazionali.
* Nella scheda **Lista di esecuzione** dei messaggi transazionali è stato aggiunto un nuovo filtro per lo stato di consegna in modo da migliorare la risoluzione dei problemi.
* Per migliorare le prestazioni e ottimizzare i tempi di esecuzione, gli indici non utilizzati sono stati rimossi, in base agli stati di utilizzo delle tabelle identificati nelle analisi preliminari per più di 350 clienti. Le tabelle interessate sono: nmsaddressStatus, nmscam, nmsdelivery, nmsslandingpage, nmsprogram, nmsrecipients, nmsseedmember, nmsservice, nmssubstorcp, nmsaudience, xtkworkflow

**Patch**

* È stato risolto un problema che impediva l’utilizzo di un collegamento di destinazione per le notifiche push o per i messaggi in-app quando il tracciamento era abilitato.
* È stato risolto un problema che impediva il rispetto della priorità elevata nei messaggi transazionali in presenza di una grande quantità di consegne in massa.
* È stato risolto un problema che poteva impedire l’assegnazione di marchi a un’e-mail transazionale. Durante il passaggio della pubblicazione potrebbero essere visualizzati diversi messaggi di errore. (CAMP-44988)
* È stato risolto un problema nell’interfaccia utente del flusso di lavoro che poteva impedire il salvataggio delle informazioni nei campi che richiedevano valori numerici. (CAMP-44025)
* È stato risolto un problema per cui poteva essere visualizzato un messaggio di errore in caso di utilizzo di un’attività di **test** in un flusso di lavoro dei modelli di importazione. (CAMP-42910)
* È stato risolto un problema che si verificava durante l’utilizzo di un’attività **Read audience** contenente un campo di enumerazione e connessa alle attività **Unione** o **Arricchimento**. (CAMP-42795)
* È stato risolto un problema nei report dinamici che si verificava con l’utilizzo di segmenti preconfigurati per filtrare i dati nei report. (CAMP-42627)
* È stato risolto un problema che impediva di impostare un’attività **Pianificazione** alle ore 00:00. (CAMP-42674)
* È stato risolto un problema che poteva interrompere l’invio di messaggi SMS quando la connessione SMPP era instabile. (CAMP-42789)
* È stato risolto un problema che impediva la visualizzazione del pulsante **Interrompi preparazione** dopo l’aggiornamento della pagina. (CAMP-42721)
* È stato risolto un problema che impediva la visualizzazione delle percentuali dei rapporti sugli hot click durante l’importazione di contenuto da un URL. (CAMP-44468)
* È stato risolto un problema che, nel contesto di una sostituzione del profilo, poteva far visualizzare un errore di timeout in caso di selezione di un profilo da utilizzare. (CAMP-44746)
* È stato risolto un problema che poteva impedire il funzionamento delle istanze dopo la distribuzione di risorse personalizzate contenenti definizioni di collegamenti non corrette. (CAMP-44406)
* È stato risolto un problema che creava entità collegate vuote (tipologie, marchi, ecc.) dopo aver copiato e incollato una consegna in un modello della campagna. (CAMP-44765)
* È stato risolto un problema che impediva l’invio delle bozze a causa di una gestione non corretta delle tabelle di preparazione delle consegne in caso di arresto anomalo del database o di un semplice riavvio del database in Azure.
* È stato risolto un problema che poteva impedire l’eliminazione di collegamenti con contenuto Experience Manager in una consegna configurata con contenuto multilingue. (CAMP-44029)
* È stato risolto un problema nei report dinamici che poteva far visualizzare un messaggio di errore durante il tentativo di filtrare le dimensioni. (CAMP-43097)
* È stato risolto un problema che poteva far visualizzare una schermata vuota durante il tentativo di accedere ai profili in un’istanza configurata con risorse personalizzate contenenti specifiche definizioni di collegamenti. (CAMP-41009)
* È stato risolto un problema nei flussi di lavoro che poteva verificarsi durante un’attività **Arricchimento** con due attività di input, con entrambe le risorse di destinazione collegate tra loro. (CAMP-42133)
* È stato risolto un problema che causava il loop dei flussi di lavoro di importazione durante l’utilizzo di un’attività di **trasferimento dei file**. (CAMP-43754)
* È stato corretto un problema a causa del quale i duplicati non venivano presi in considerazione durante la creazione di un profilo con registri esportati. (CAMP-45031)
* È stato risolto un problema che causava discrepanze di dati tra i report in Adobe Campaign e quelli esportati in file PDF. (CAMP-43010)
* È stato corretto un errore che ostacolava il flusso di lavoro della consegna di direct mail in caso di utilizzo di campi di dati esistenti nelle funzioni. (CAMP-42737)
* È stato risolto un problema che si verificava con l’importazione di pacchetti comprendenti eventi transazionali e modelli di messaggi. Il processo di importazione si interrompeva al 5%. (CAMP-42544)
* È stato risolto un problema che causava un errore (TipoErrore non rilevato) dopo aver modificato l’attività di **Arricchimento** e inserito dati aggiuntivi in un flusso di lavoro. (CAMP-41877)
* È stato corretto un errore che impediva l’eliminazione dei flussi di lavoro. Per eliminare un flusso di lavoro, era necessario eliminare i registri. (CAMP-44144)
* È stato corretto un errore che si presentata con la creazione di una pagina di destinazione con codice HTML. Le caselle di controllo obbligatorie non venivano riconosciute in Campaign e non erano disponibili nella pagina di destinazione pubblicata. (CAMP-44181)
* È stato risolto un problema che causava il loop di flussi di lavoro durante l’utilizzo dell’attività **Attendi**. (CAMP-43981)
* È stato risolto un problema che si verificava con l’invio di messaggi transazionali a causa del quale diversi indirizzi e-mail venivano inseriti più volte come destinatari all’interno della stessa consegna. (CAMP-44202)
* È stato risolto un errore che si verificava con la sostituzione di un profilo con la personalizzazione targetData. (CAMP-44996)
* È stato risolto un problema che causava un errore nell’anteprima della consegna in caso di esportazione in un pacchetto di un modello di consegna. (CAMP-44084)
* È stato risolto un problema che impediva l’invio delle bozze ai profili di test in caso di utilizzo di mappature di destinazione personalizzate. (CAMP-43701)
* È stato corretto un errore che si verificava nei flussi di lavoro in caso di utilizzo dell’attività **Read audience** e di targeting di un’audience con una dimensione di targeting diversa da **Profilo**. (CAMP-41885)
* È stato risolto un problema che causava errori quando il flusso di lavoro tecnico **updateEventsStatus** impiegava troppo tempo per recuperare la cronologia degli eventi (quando il flusso di lavoro veniva interrotto). Per risolvere il problema, il campo aggregato &quot;sumQueueTime&quot; inutilizzato è stato rimosso dal flusso di lavoro. (CAMP-43920)
* È stato risolto un problema di memoria che avveniva durante la distribuzione di risorse personalizzate. (CAMP-42909)
* È stato risolto un problema nei messaggi transazionali quando nelle raccolte mancavano attributi. Ora tutti gli attributi mancanti sono definiti con un valore predefinito e inclusi nel payload. (CAMP-42882)
* È stato risolto un problema che poteva influire sulle prestazioni in caso di utilizzo di una query dei registri di consegna degli eventi in tempo reale. (CAMP-42759)
* È stato corretto un errore che si verificava durante l’utilizzo di estensioni di file in maiuscolo con risorse condivise. (CAMP-44159)
* È stato risolto un problema che causava la visualizzazione di un messaggio di errore durante il test di connessione a un account esterno prima che questo fosse creato. Il pulsante **Verifica connessione** ora viene visualizzato solo dopo la creazione dell’account esterno.
* È stato risolto un problema che causava la mancata visualizzazione dei messaggi in sospeso dopo il riavvio dell’MTA avanzata nelle istanze configurate con la condivisione.
* È stato risolto un problema che poteva causare una mancata corrispondenza tra il conteggio dei profili attivi con il numero effettivo di consegne inviate.
* È stato risolto un problema che poteva causare latenza durante la ricerca di risorse nell’editor delle query in un flusso di lavoro.
* È stato risolto un problema che si verificava selezionando l’opzione **Specifica i campi da tenere in considerazione nell’opzione di ricerca** in una risorsa personalizzata. Se l’elenco dei campi veniva lasciato vuoto, si verificava un errore nella pubblicazione delle risorse personalizzate.
* È stato risolto un problema di prestazioni durante la visualizzazione della panoramica delle risorse personalizzate con un grande volume di dati.
* È stato risolto un problema che impediva l’importazione di una consegna ricorrendo alla sostituzione di un profilo.
* È stato risolto un problema che impediva l’invio immediato delle bozze del profilo in caso di programmazione della consegna.
* È stato risolto un problema che si verificava durante il caricamento di una chiave Android per un’app mobile. Il messaggio visualizzato dopo il corretto caricamento della chiave mostrava il valore della chiave precedente.
* È stato risolto un problema che impediva la creazione di profili di test partendo dai messaggi transazionali dopo la creazione di una configurazione dell’evento con una raccolta senza attributi.
* È stato risolto un problema che poteva impedire la pubblicazione di risorse personalizzate dopo la creazione di un nuovo filtro tramite un’aggregato.
* È stato risolto un problema che, a causa del proxy immagine Gmail, rendeva errato il tasso di apertura del tracciamento.
* È stato risolto un problema che causava errori di memoria insufficiente in caso di importazione di un pacchetto.
* È stato risolto un problema che causava un errore dopo il tentativo di scollegare Experience Manager quando il suo contenuto includeva un percorso con un carattere &quot;%20&quot;.
* È stato corretto un errore sulle etichette durante la duplicazione delle attività del flusso di lavoro.
* È stato risolto un problema con il selettore di messaggi transazionali in una pagina di destinazione nel caso in cui fosse selezionata l’opzione **Avvia l’invio di messaggi**.
* È stato risolto un problema relativo ai messaggi transazionali o alle consegne ricorrenti che impediva l’inizializzazione dello stato di consegna con il valore predefinito corretto. Sono stati migliorati anche i registri di errore.
* È stato risolto un problema che si verificava durante l’estensione dello schema **Iscrizione a un’applicazione** (appSubscriptionRcp) con un collegamento di profilo, utilizzando un campo personalizzato. L’indice non veniva creato automaticamente, influendo sul tempo di invio push. (CAMP-41120)



## Versione 20.3 - maggio 2020 {#release-20-3---may-2020}

**Quali sono le novità?**

<table> 
<thead> 
<tr> 
<th> <strong>Legge tailandese sulla protezione dei dati personali (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>La legge tailandese sulla protezione dei dati personali (PDPA) è la nuova legge sulla privacy che armonizza e aggiorna i requisiti di protezione dei dati in Thailandia. Questo regolamento si applica ai clienti di Adobe Campaign che detengono i relativi dati dei soggetti residenti in questo paese.</p>
<p>Oltre alle funzionalità per la privacy già disponibili in Adobe Campaign (compresa la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), sono state incluse funzionalità aggiuntive per facilitare la tuo preparazione al PDPA:</p>
<ul>
<li>Diritto di accesso e Diritto di eliminazione: sono state sfruttate le funzionalità aggiunte del RGPD e del CCPA. <a href="https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#righttoaccess">Ulteriori informazioni</a> </li>
<li><p>Durante la creazione di una richiesta di accesso a dati personali, il tipo di regolamento PDPA è stato aggiunto al servizio core Privacy. Dovresti utilizzare questo metodo per tutte le richieste di accesso ed eliminazione. L’utilizzo dell’API e dell’interfaccia di Campaign per le richieste di accesso ed eliminazione è obsoleto. Consulta l’articolo <a href="../../rn/using/deprecated-features.md">Funzioni obsolete e rimosse</a>.</p></li>
</ul>
<p>Consulta il <a href="https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/privacy/privacy-overview.html">video tutorial</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Attività API esterna (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>L’attività <strong>External API</strong> è in fase di transizione dalla versione beta a GA. Questa versione offre ulteriore flessibilità al parser del corpo della risposta JSON. Ora puoi:</p>
<ul>
<li>analizzare un JSON nidificato con una profondità massima di 10 livelli; </li>
<li>analizzare le proprietà selezionate come nodi foglia da un JSON e uniformarle in una singola riga di tabella;</li>
<li>selezionare e utilizzare un oggetto array da un JSON senza dover denominare l’oggetto "data" o posizionarlo sul livello superiore.</li>
</ul>
<p><strong>Attenzione:</strong> i clienti devono <strong>sostituire tutte le attività API esterne in versione beta</strong> con attività API esterne GA nei relativi flussi di lavoro. I flussi di lavoro che utilizzano la versione beta dell’API esterna non funzionano più in 20.3.</p>
<p>Per ulteriori informazioni, consulta la <a href="../../automating/using/external-api.md">documentazione dettagliata</a> e il <a href="https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">video tutorial</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Funzionalità aggiuntive** (a partire dal 13 luglio)

* **Ottimizzazione dei tempi di invio e valutazione del profilo con tecnologia AI**: ora puoi ottimizzare la progettazione e la consegna dei percorsi dei clienti per prevedere le preferenze di coinvolgimento di ogni individuo. Basato sull’intelligenza artificiale Journey AI, Adobe Campaign può analizzare e prevedere i tassi di apertura, i tempi di invio ottimali e la probabilità di abbandono in base alle metriche di coinvolgimento storiche. [Ulteriori informazioni](../../sending/using/predictive.md)
* **Brasile: nuova normativa sulla privacy**: oltre alle funzionalità per la privacy già disponibili in Campaign, Adobe facilita la tua preparazione al Lei Geral de Proteçao de Datos (LGPD) del Brasile. Durante la creazione di una richiesta di accesso a dati personali, il tipo di regolamento LGPD è stato aggiunto al servizio core Privacy di Adobe. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/campaign-privacy-overview.html)

**Miglioramenti**

* Il numero dei caratteri utilizzabili nel campo **Prefix** per [verificare messaggi tramite i profili target](../../sending/using/testing-messages-using-target.md) è stato aumentato da 32 a 500 caratteri.
* Il numero massimo degli eventi in tempo reale pubblicabili su un’istanza è stato aumentato da 350 a 2000. (CAMP-41608)
* La sincronizzazione tra Adobe Launch e Campaign Standard è stata migliorata mediante il flusso di lavoro tecnico syncWithLaunch. Questo flusso di lavoro abilita l’importazione automatica di tutte le proprietà mobili di Adobe Launch in Adobe Campaign Standard. Per ulteriori informazioni, consulta [questa pagina](../../administration/using/technical-workflows.md).

   Devi inviare un ticket all’Assistenza cliente di Adobe (direttamente o tramite il contatto di Adobe) per far sì che il flusso di lavoro tecnico syncWithLaunch sia abilitato nell’istanza Campaign. (CAMP-40082)

**Miglioramenti di E-mail Designer**

* L’Email Designer può ora gestire una formattazione HTML più flessibile rispetto al rigido W3C. (CAMP-42529)
* È stato risolto un problema relativo alle [immagini cliccabili](../../designing/using/links.md#inserting-a-link) per impedire la visualizzazione di collegamenti accanto all’immagine nei blocchi di contenuto. (CAMP-41586)
* È stato risolto un problema che impediva il reindirizzamento a una pagina di destinazione quando l’[URL tracciato](../../designing/using/links.md#about-tracked-urls) aveva una categoria aggiunta nel modello. (CAMP-41537)
* È stato risolto un problema relativo alla spaziatura dei pulsanti in Outlook.
* È stato risolto un problema che causava la visualizzazione dei tag HTML nel testo normale.
* La ricerca per blocchi di contenuto visualizza ora i risultati della ricerca sul server e i risultati precaricati. (CAMP-41870)

**Altre modifiche**

* L’interfaccia di pubblicazione delle risorse personalizzate è stata migliorata con messaggi di errore più chiari.
* Le mappature di consegna non utilizzate sono state rimosse dall’interfaccia.
* I ruoli di amministratore non necessari sono stati rimossi dall’interfaccia.
* Le caselle di controllo possono ora diventare obbligatorie in una pagina di destinazione.
* È stato rimosso il limite di 200 righe durante il download del file CSV di un rapporto dinamico. Ora puoi includere ogni riga del rapporto. (CAMP-40810)
* È stata aggiunta la lingua ES-US nell’elenco delle lingue predefinite per le e-mail multilingue. (CAMP-42279)
* I file scaricati con un’attività Transfer file vengono ora eliminati dopo X giorni, dove X è determinato dal campo **History in days** nel menu **Execution** delle proprietà del flusso di lavoro. [Ulteriori informazioni](../../automating/using/managing-execution-options.md)

**Integrazioni con Experience Platform**

* L’attivazione di Adobe [Experience Platform Audiences](../../automating/using/aep-targeting-audiences.md)dall’attività **Read audience** è stata migliorata per fornire prestazioni e stabilità migliori. Inoltre, i log del flusso di lavoro sono stati resi più chiari e dettagliati per quanto riguarda i processi di attivazione, consentendo un monitoraggio e una risoluzione dei problemi più semplice durante la lettura dei tipi di pubblico in Adobe Experience Platform.

**Patch**

* È stato corretto un errore che causava la creazione di una risorsa fantasma durante il processo di pubblicazione di una risorsa personalizzata.
* È stato risolto un problema che poteva impedire la visualizzazione dello storico dei dati marketing dei profili se la risorsa Profile era stata estesa con una risorsa personalizzata. (CAMP-41009)
* È stato risolto un problema relativo ai modelli di pagine di destinazione preconfigurati che visualizzavano il contenuto in francese all’apertura dell’editor. (CAMP-41639)
* È stato risolto un problema nelle notifiche push con contenuto dinamico che poteva impedire la visualizzazione delle emoticon. (CAMP-40715)
* È stato risolto un problema nell’attività **Deduplication** che poteva causare l’assegnazione di un codice di segmento errato a una delle transizioni di complemento in uscita. (CAMP-41400)
* È stato corretto un errore che impediva l’eliminazione dei rapporti pianificati. (CAMP-41302)
* È stato risolto un problema che causava discrepanze tra il dashboard di consegna e il rapporto **Delivery Summary**. (CAMP-41145)
* È stato risolto un problema che causava un problema di visualizzazione di sovrapposizione dei caratteri nei rapporti scaricati.
* È stato risolto un problema che impediva il funzionamento dell’anteprima di una consegna per la sostituzione della bozza.
* È stato corretto un errore durante l’eliminazione dei campi di personalizzazione di una notifica locale in-app.
* È stato risolto un problema che impediva il funzionamento della funzione charIndex con un’attività **End** o **File transfer** in un flusso di lavoro.
* È stato risolto un problema nei flussi di lavoro che poteva verificarsi durante un’attività **Enrichment** con due attività di input, incluse le risorse target con un collegamento tra loro. (CAMP-42133)
* È stato risolto un problema che poteva impedire l’esecuzione di un flusso di lavoro durante l’utilizzo di funzioni sconosciute. (CAMP-41873)
* È stato risolto un problema nei flussi di lavoro che poteva verificarsi durante la creazione di tipi di pubblico utilizzando diverse attività **Save audience** con transizioni di complemento in uscita. (CAMP-39992)
* È stato risolto un problema che causava discrepanze di dati durante la personalizzazione nelle e-mail transazionali. (CAMP-41842)
* Sono stati risolti i problemi che si verificavano durante l’eliminazione dei campi di personalizzazione nelle consegne di notifiche push. (CAMP-37586)
* È stato corretto un errore che impediva agli utenti di apportare modifiche ai rapporti. (CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **Nuova versione di maggio del Pannello di controllo Campaign** con rinnovo del certificato per i sottodomini CNAME. [Ulteriori informazioni](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

## Versione 20.2 - Aprile 2020 {#release-20-2---april-2020}

**Quali sono le novità?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integrazione con Azure Blob</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Il connettore di archiviazione Azure Blob può ora essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un’attività di flusso di lavoro <strong>Trasferisci file</strong>. </p>
    <p>Per ulteriori informazioni, consulta la <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">documentazione dettagliata</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Verifica dei messaggi e-mail tramite profili di destinazione</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Oltre ai profili di test, ora puoi testare le e-mail su profili di destinazione reali. Ciò ti consente di ottenere una rappresentazione esatta del messaggio ricevuto dal profilo: campi personalizzati, informazioni dinamiche e personalizzate, compresi dati aggiuntivi dei flussi di lavoro, ecc. </p>
    <p>Per ulteriori informazioni, consulta la <a href="../../sending/using/testing-messages-using-target.md">documentazione dettagliata</a> e il <a href="https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">video tutorial</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Nuove funzionalità verranno rilasciate nel Pannello di controllo Campaign ad aprile, tra cui la gestione dei record TXT di Google, il monitoraggio dello spazio del database e l’avviso e-mail. Per ulteriori informazioni su queste funzioni, consulta le [Note sulla versione del Pannello di controllo Campaign](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

**Miglioramenti**

* La user experience dei messaggi transazionali e la coerenza dell’interfaccia sono state migliorate. [Ulteriori informazioni](../../channels/using/getting-started-with-transactional-msg.md)
* Campaign Standard ora ti consente di inviare bozze ai profili di test utilizzando dati aggiuntivi dei flussi di lavoro.
* I guardrail per l’attività External API sono stati aggiornati. [Ulteriori informazioni](../../automating/using/external-api.md)

**Miglioramenti di E-mail Designer**

* È stato risolto un problema che riguardava l’uscita quando si faceva clic più volte su un’immagine personalizzata.
* È stato risolto un problema che si verificava durante la duplicazione di componenti di testo dinamico che poteva causare la duplicazione della riga errata. (CAMP-41249)
* È stato risolto un problema relativo alla spaziatura in Outlook che si verificava durante la definizione della spaziatura a livello di tabella anziché a livello div.
* È stato risolto un problema che causava la modifica della larghezza di un’immagine quando si passava alla modalità HTML. (CAMP-41116)
* È stato risolto un problema che impediva al componente social media di essere accessibile quando si forniva testo alternativo alle icone. (CAMP-41345)
* È stato risolto un problema che causava la visualizzazione di tag `<br>` visibili durante l’utilizzo del comando Copia/Incolla in E-mail Designer.
* È stato risolto un problema che causava la visualizzazione di tag HTML nell’e-mail dopo il passaggio dal contenuto HTML al testo normale. (CAMP-41138)
* È stato risolto un problema che impediva il rendering dei pulsanti con un solo bordo definito.
* È stato risolto un problema nel rientro HTML che causava lo spostamento a sinistra del piè di pagina delle e-mail in Microsoft Outlook. (CAMP-40987)
* È stato risolto un problema che causava la copia dei campi di personalizzazione per un attributo di raccolta definito in HTML nel contenuto di testo normale quando si passava alla modalità di testo normale. (CAMP-40365)
* È stato risolto un problema che impediva l’inserimento di collegamenti in un segmento di testo selezionato. (CAMP-41406)
* È stato risolto un problema che causava la modifica della data durante la selezione di un fuso orario nell’editor delle query. (CAMP-38277)

**Altre modifiche**

* Il flusso di lavoro preconfigurato **Riconciliazione dei KPI con Adobe Analytics** viene ora eseguito fino alla data corrente, invece di essere eseguito per un singolo giorno.
* MCPNS non supporta l’aggiunta di APNS e APNS-SANDBOX come piattaforme in un’app. Dopo l’aggiunta del certificato in Adobe Campaign Standard, ora non è più possibile ripristinare le impostazioni perché è possibile aggiungere una sola piattaforma APNS (produzione o sandbox) all’app MCPNS.

**Integrazioni con Experience Platform**

>[!NOTE]
>
>Le funzionalità di Adobe Experience Platform in Campaign Standard sono attualmente in versione beta, e potrebbero essere soggette ad aggiornamenti frequenti senza preavviso. Consulta la documentazione dettagliata: [Connettore dati di Experience Platform](../../developing/using/aep-about-data-connector.md), [Audience Destinations](../../audiences/using/aep-about-audience-destinations-service.md)

* Nei registri del flusso di lavoro, Campaign ora visualizza ogni 10 minuti il numero di record già elaborati dal processo attualmente in esecuzione.
* È stato risolto un problema che poteva verificarsi durante l’importazione di un profilo Adobe Experience Platform eliminato dal database.
* È stato risolto un problema nei registri del flusso di lavoro che poteva visualizzare un risultato errato per il numero totale di record importati.

**Patch**

* È stato risolto un problema relativo all’attività del flusso di lavoro **Arricchimento** che poteva verificarsi quando si aggiungevano spazi nel campo **Alias** e creava un nuovo elemento riga. (CAMP-39229)
* È stato risolto un problema a causa del quale ogni profilo di test poteva essere oggetto di targeting durante l’invio di un messaggio di bozza.
* È stato risolto un problema che si verificava dopo l’annullamento della pubblicazione e l’eliminazione di una configurazione di evento. [Ulteriori informazioni](../../channels/using/publishing-transactional-event.md#deleting-an-event)
* È stato risolto un problema che causava la scomparsa del pulsante **Save** quando si apportavano modifiche ai flussi di lavoro.
* È stato risolto un problema che si verificava durante l’eliminazione manuale di una richiesta di accesso a dati personali in Campaign a seguito dell’elaborazione, a causa del quale i dati associati alla richiesta non potevano essere eliminati anche dopo la pulizia.
* È stato risolto un problema che poteva verificarsi durante l’anteprima o l’invio di messaggi che includevano caratteri speciali da Adobe Experience Manager.
* È stato risolto un problema che poteva verificarsi nei flussi di lavoro durante l’esecuzione di un’attività con diverse transizioni in entrata.
* È stato risolto un problema che impediva agli utenti standard di utilizzare “Abbonamenti a un’applicazione” come dimensione di destinazione in una query del flusso di lavoro o una consegna. (CAMP-37618)

## Versione 20.1.4 - Febbraio 2020 {#release-20-1-4---february-2020}

* È stato risolto un problema che si verificava all’apertura di un’attività **Read Audience** sui flussi di lavoro esistenti. (CAMP-41002)

## Versione 20.1.3 - Febbraio 2020 {#release-20-1-3---february-2020}

* È stato risolto un problema di regressione introdotto in 20.1 da CAMP-39273 per i clienti che utilizzano la scappatoia. CAMP-39273 è stato ripristinato.

## Versione 20.1.2 - Febbraio 2020 {#release-20-1-2---february-2020}

**Miglioramenti di E-mail Designer**

* È stato risolto un problema che causava l’aggiunta di un elemento tag HTML in un frammento obsoleto al momento dell’applicazione della patch e del salvataggio del contenuto. (CAMP-40685)
* È stato risolto un problema che aggiungeva uno spazio quando si utilizzava contenuto dinamico. (CAMP-40605)
* È stato risolto un problema durante la configurazione di un modello e-mail transazionale. (CAMP-40604)

## Versione 20.1 - Febbraio 2020 {#release-20-1---february-2020}

**Quali sono le novità?**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Connettore dati di Adobe Experience Platform (beta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Il Connettore dati di Adobe Experience Platform è ora integrato con Adobe Campaign Standard. Puoi rendere disponibili i dati di Campaign su Adobe Experience Platform mappando i dati XTK (dati acquisiti in Campaign) su Adobe Experience Platform Data Model (XDM). </p>
    <p>Questa funzionalità è disponibile solo per i clienti in hosting su Azure. Per ulteriori informazioni su questa funzionalità e sulle relative condizioni di attivazione, consulta la <a href="../../developing/using/aep-about-data-connector.md">documentazione dettagliata</a> e il <a href="https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">video di istruzioni</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Audience Destinations (beta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Audience Destinations ti consente di condividere segmenti da Adobe Experience Platform ad Adobe Campaign.</p>
    <p>Questa funzionalità è disponibile solo per i clienti in hosting su Azure. Per ulteriori informazioni su questa funzionalità e sulle relative condizioni di attivazione, consulta la <a href="../../audiences/using/aep-about-audience-destinations-service.md">documentazione dettagliata</a> e il <a href="https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">video di istruzioni</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Miglioramenti**

* Disponibilità globale dell’MTA avanzato: i messaggi (inclusi i messaggi transazionali) vengono ora inviati dall’MTA avanzato di Adobe Campaign, che fornisce un’infrastruttura di invio aggiornata che consente di migliorare la consegna, la velocità effettiva e la gestione delle mancate consegne. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/campaign-enhanced-mta.html)

* La gestione del fuso orario è stata migliorata. Ora puoi definire un [fuso orario specifico](../../automating/using/building-a-workflow.md) per un intero flusso di lavoro. Il fuso orario selezionato verrà applicato a tutte le attività del flusso di lavoro. Le informazioni sul fuso orario configurato per l’operatore o il server vengono ora visualizzate nell’interfaccia (nei registri e dopo aver selezionato un fuso orario). (CAMP-37672)

* Le API di Campaign Standard ti consentono ora di eseguire l’impaginazione quando utilizzi tabelle di grandi dimensioni, aggiungendo il parametro `_forcePagination=true` all’URL della chiamata. [Ulteriori informazioni](../../api/using/pagination.md)

* L’ID del registro di consegna (un identificatore univoco per ciascun registro) è ora disponibile nelle risorse Registri di consegna e Registri di tracciamento per tutte le dimensioni di targeting. Ciò consente ad esempio di identificare i registri di invio o di tracciamento durante l’esportazione. [Ulteriori informazioni](../../automating/using/exporting-logs.md)

**Miglioramenti di E-mail Designer**

* Sono state aggiunte istruzioni di testo obbligatorie mancanti durante la creazione di un pubblico.
* È stato risolto un problema che si verificava facendo clic sul pulsante **Change content** nella procedura guidata dell’editor e-mail legacy.
* È stato risolto un problema che impediva l’allineamento delle intestazioni con il contenuto del report Riepilogo del servizio. (CAMP-38103)
* È stato risolto un problema che impediva l’eliminazione delle varianti di contenuto dinamico senza influire sul resto dell’oggetto. (CAMP-40096)
* È stato risolto un problema di test A/B che si verificava quando si utilizzava la variante B nell’oggetto. (CAMP-40327)
* È stato risolto un problema che impediva il trascinamento e il rilascio di file durante l’utilizzo della funzione di importazione Carica HTML. (CAMP-39326)
* È stato risolto un problema che impediva di copiare e incollare testo da un editor di testo. (CAMP-39028)
* È stato risolto un problema che impediva la visualizzazione delle parole suggerite. (CAMP-38970)
* È stato risolto un problema che impediva agli utenti di salvare frammenti. (ATU-2447)
* È stato risolto un problema che impediva la duplicazione delle strutture dinamiche. (CAMP-38367)
* È stato risolto un problema che impediva il mantenimento delle condizioni del contenuto dinamico in caso di duplicazione. (CAMP-39051)

**Altre modifiche**

* Il filtro &quot;Consegne con preparazione non riuscita&quot; ora prende in considerazione la data di creazione delle consegne anziché l’ultima data di modifica.
* L’unità organizzativa del gruppo di protezione Amministratori non può più essere modificata.
* Quando si crea un profilo, è necessario compilare il campo Unità organizzativa.
* Ora è possibile eliminare un trigger di Experience Cloud solo se vengono eliminati sia l’evento sia il modello transazionale ad esso collegato.
* [!DNL Adobe Creative SDK] è stato disattivato. È ora obsoleto in Campaign Standard. Consulta la pagina [Funzioni obsolete e rimosse](../../rn/using/deprecated-features.md).


**Patch**

* È stato risolto un problema che impediva l’eliminazione dei dati utente nei registri di esclusione durante l’esecuzione di una richiesta di eliminazione di dati personali. (CAMP-39003)
* È stato risolto un problema che causava problemi di accessibilità durante il ridimensionamento del testo in un elemento contenitore.
* È stato risolto un problema che impediva agli utenti di chiudere il pop-up Calendario visualizzato al passaggio del mouse nelle attività di marketing.
* È stato risolto un problema nell’attività **[!UICONTROL External API]** che visualizzava il pulsante **[!UICONTROL Confirm]** anche quando non venivano modificati dati.
* È stato risolto un problema che si verificava durante l’utilizzo di un’attività **[!UICONTROL Union]** su query con dimensioni di destinazione diverse. I dati di transizione mostravano solo record della dimensione di targeting del set principale. (CAMP-36831)
* È stato risolto un problema che poteva causare un errore durante l’utilizzo di un’attività **[!UICONTROL Reconciliation]** in contesti specifici, ad esempio con due attività in entrata, una delle quali era un’attività di esclusione. (CAMP-37490)
* Sono stati risolti dei problemi di prestazioni che potevano verificarsi durante la selezione e l’aggiornamento dei profili di test. (CAMP-37976)
* È stato risolto un problema che poteva provocare la visualizzazione di pagine di errore durante l’abbonamento o l’annullamento dell’abbonamento tramite pagine di destinazione. (CAMP-37771)
* È stato risolto un problema che si verificava durante il caricamento di contenuto in formato zip, in cui l’estensione dei file PNG a cui si faceva riferimento nell’HTML era in lettere maiuscole. (CAMP-37913)
* È stato risolto un problema che impediva l’invio di messaggi in-app quando si aggiungeva un profilo di test alla consegna.
* È stato risolto un errore che impediva il funzionamento dell’attività del flusso di lavoro External API quando era collegata ad attività di arricchimento.
* È stato risolto un problema che poteva causare una visualizzazione errata dello stato dei messaggi SMS.
* È stato risolto un problema relativo alle risorse personalizzate che provocava la visualizzazione di voci duplicate in endpoint API diversi.
* È stato risolto un problema che rendeva non disponibili le pagine di destinazione dopo la pubblicazione. (CAMP-38695)
* È stato risolto un bug che si verificava durante la visualizzazione di dati da una transizione Intersezione proveniente da due risorse diverse. (CAMP-38974)
* È stato risolto un problema che causava l’impostazione errata del valore di enumerazione in un modello di consegna. (CAMP-38388)
* È stato risolto un errore riguardante le consegne di gruppo di e-mail che visualizzava lo stato delle consegne come In sospeso e lo stato Inviato come Completato. (CAMP-35355)
* È stato risolto un errore che causava la visualizzazione errata del dominio del mittente nel Reporting dinamico. (CAMP-33123)
* È stato risolto un problema che causava discrepanze nei conteggi di annullamento dell’abbonamento nel Reporting dinamico. (CAMP-39949)
* È stato risolto un problema che impediva la visualizzazione degli indirizzi nella schermata dei registri di invio durante l’invio di messaggi in-app.
* È stato risolto un problema che impediva l’aggiornamento dei registri di invio SMS con il numero corretto di mancate consegne. (CAMP-38395)
* Risolta una scappatoia che consentiva alle chiamate successive all’abbonamento a un’applicazione di aggiornare i token di notifica push. (CAMP-39273)
