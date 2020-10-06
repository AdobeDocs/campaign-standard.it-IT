---
title: Ultima versione
description: Questa pagina presenta dettagli sul contenuto dell’ultima versione Campaign Standard
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: vignes
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7168162baa26c960475d8c9c613989d0338f95c2
workflow-type: tm+mt
source-wordcount: '2387'
ht-degree: 99%

---


# Ultima versione{#latest-release}

[Pianificazione del rilascio](../../rn/using/release-planning.md) | [Versioni del Pannello di controllo Campaign](https://docs.adobe.com/content/help/it-IT/control-panel/using/release-notes.html) | [Aggiornamenti alla documentazione](../../rn/using/documentation-updates.md) | [Note sulla versione precedenti](../../rn/using/release-notes-2020.md) | [Funzioni obsolete](../../rn/using/deprecated-features.md)

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
<p>Per ulteriori informazioni consulta la <a href="../../sending/using/control-group.md">documentazione dettagliata</a> e il <a href="https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html">video tutorial</a>.
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
* [Sono stati aggiunti nuovi filtri all’elenco degli eventi transazionali. ](../../administration/using/configuring-transactional-messaging.md#searching-transactional-events) Questi consentono di filtrare le configurazioni dell’evento in base al loro stato, come pure in base all’ultima volta che è stato ricevuto un evento.
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
* È stato risolto un problema che impediva il rispetto della priorità elevata nei messaggi transazionali in caso di consegna in massa significativa.
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

