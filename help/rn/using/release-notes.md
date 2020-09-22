---
title: Ultima versione
description: Questa pagina contiene dettagli sul contenuto dell’ultima versione Campaign Standard
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
source-git-commit: 893cd3a07063f8349dfeeae0f3274a6f54bf04f7
workflow-type: tm+mt
source-wordcount: '2441'
ht-degree: 4%

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
  <td> <p>È ora possibile utilizzare i gruppi <strong>di</strong> controllo per misurare l'impatto delle campagne escludendo una parte del pubblico. Potrete quindi confrontare il comportamento della popolazione di destinazione che ha ricevuto il messaggio con il comportamento dei contatti non mirati. In base ai registri di invio, puoi anche eseguire il targeting di un gruppo di controllo in campagne future.
</p>
<p>For more information refer to the <a href="../../sending/using/control-group.md">detailed documentation</a> and <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html">how-to video</a>.
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
  <td> <p> Adobe Campaign ora supporta OAuth per l'autenticazione nell'attività del flusso di lavoro API <strong></strong> esterna. Questa nuova funzionalità consente a questa attività di comunicare con i sistemi che richiedono il supporto OAuth.
</p>
<p>For more information refer to the <a href="../../automating/using/external-api.md">detailed documentation</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Integrazione dell'AI nel percorso</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Siamo entusiasti di annunciare Journey AI per tutti  clienti Adobe Campaign Standard.</p>
  <p>Journey AI utilizza l'apprendimento automatico avanzato (ML) per consentire alle aziende di ottimizzare la progettazione e la consegna dei viaggi dei clienti preannunciando le preferenze di coinvolgimento di ogni individuo.</p>
  <P>L'AI del viaggio è costituito da due caratteristiche ML:</p>
<ul> 
     <li> <strong>Predictive Engagement Scoring</strong> (Punteggio di coinvolgimento predittivo) - Identifica in modo intelligente il livello di coinvolgimento preferito dai clienti per mirare meglio e personalizzare i messaggi al fine di aumentare le conversioni e la fidelizzazione. Guardate il <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">video</a>su come.</li> 
     <li> <strong>Predictive Send Time Optimization</strong> - Prevede il momento migliore per inviare e-mail a ogni singolo in una campagna per massimizzare i tassi di coinvolgimento e migliorare il ROI delle campagne e-mail. Guardate il <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">video</a>su come.</li>
    </ul>
  <p>Per informazioni su come iniziare a utilizzare Journey AI, consulta la documentazione <a href="../../sending/using/predictive.md"></a> dettagliata e rivolgiti al tuo Account Executive. Anche se l'AI del viaggio è disponibile gratuitamente per i clienti di Campaign esistenti, il costo di implementazione è di circa 50 ore.</p>
    </td> 
</tr> 
</tbody> 
</table>

**Miglioramenti**

* **Gestione** della privacy: il campo **CCPA Opt-Out** , disponibile tramite l&#39;interfaccia Campaign e l&#39;API, ora è supportato anche tramite il servizio di base Privacy. Questo campo consente  utenti di Adobe Campaign di verificare se un consumatore ha rinunciato alla vendita di Dati Personali. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#ccpa)
* **Miglioramenti** nell’esecuzione del flusso di lavoro (versione beta): nel contesto di un&#39;iniziativa globale sui flussi di lavoro, sono stati sviluppati alcuni miglioramenti importanti per stabilizzare la gestione della memoria, ridurre la latenza e ottimizzare la memoria utilizzata dai flussi di lavoro durante l&#39;esecuzione. Questi miglioramenti sono attualmente in versione beta e sono disponibili solo per un gruppo di clienti. La disponibilità generale è prevista per l&#39;inizio del 2021.
* Per migliorare la sicurezza, Campaign utilizza ora un meccanismo **di** firma per il tracciamento dei collegamenti nelle e-mail.
* La configurazione dell&#39;app mobile è stata migliorata con messaggi **di errore** più chiari durante il caricamento di certificati iOS o chiavi Android.
* È ora disponibile una **nuova mappatura** di consegna (mapRtEventAppSubRcp) per i profili di targeting dei messaggi push transazionali. I registri di consegna, esclusione e tracciamento di queste consegne saranno ora disponibili nelle tabelle wideLogAppSubRcp, excludeLogAppSubRcp e trackingLogAppSubRcp. Questo risolve un problema che causava un errore di analisi del recapito durante l&#39;invio di un messaggio push transazionale tramite la dimensione di destinazione **Profilo** .
* **È stata migliorata la gestione** degli errori SMS per impedire l&#39;aggiunta di troppi profili all&#39;elenco di quarantena. Per impostazione predefinita, gli errori SMS ora sono configurati come errori software invece di errori rigidi. Consulta [questa pagina](https://helpx.adobe.com/it/campaign/kb/sms-connector-protocol-and-settings.html).

**Miglioramenti di E-mail Designer**

* È stata migliorata l&#39;esperienza utente in e-mail Designer con la **nuova guida** contestuale dinamica che collega completamente l&#39;interfaccia utente e la documentazione, fornendo un accesso semplice ai contenuti più recenti della guida.
* È stato risolto un problema che causava la rimozione delle interruzioni di riga in un messaggio durante la modifica della versione di testo del messaggio. (CAMP-44483)
* È stato risolto un problema che impediva la generazione e la sincronizzazione automatica della versione in testo normale di un modello HTML. (CAMP-44195)
* È stato risolto un problema che poteva verificarsi durante il ridimensionamento delle immagini. Una volta inviati i messaggi, le immagini non venivano visualizzate correttamente in Microsoft Outlook. (CAMP-44656)
* È stato risolto un problema che si verificava quando si inseriva un pulsante e si impostava la larghezza su &quot;auto&quot;. Una volta inviato il messaggio, il contenuto del pulsante non veniva visualizzato completamente. (CAMP-44560)
* È stato risolto un problema che si verificava durante il caricamento del contenuto da un file HTML allegato. Una volta inviato il messaggio a un indirizzo Gmail, il CSS non veniva applicato, causando un problema di rendering. (CAMP-44085)
* È stato risolto un problema che impediva l&#39;aggiornamento dei frammenti di contenuto utilizzati in precedenza in un messaggio in seguito alla loro modifica diretta nel modello di contenuto. (CAMP-43973)
* È stato risolto un problema relativo alla barra di ricerca **Frammenti** . Durante la ricerca di un frammento esistente, la barra di ricerca non mostrava alcun risultato. (CAMP-44223)
* È stato risolto un problema relativo alle barre di ricerca **Blocchi** di contenuto e **Frammenti** . Quando si utilizza una delle barre di ricerca, i risultati venivano visualizzati solo se si faceva clic su **Mostra più risultati...**. (CAMP-44205)
* È stato risolto un problema che impediva l&#39;applicazione in Microsoft Outlook della spaziatura tra testo e immagini. (CAMP-45370)
* È stato risolto un problema che si verificava durante la duplicazione di un frammento. Dopo aver duplicato il frammento, nel frammento originale mancavano righe HTML. (CAMP-45207)
* È stato corretto un errore che causava problemi di rendering in Microsoft Outlook. (CAMP-44749)
* È stato corretto un errore che si verificava durante la modifica della spaziatura del componente **** Struttura in un modello di consegna. I tag CSS non riportavano le modifiche apportate alla spaziatura che causavano un problema di rendering. (CAMP-45381)
* È stato risolto un problema durante il caricamento di un’immagine. L&#39;altezza dell&#39;immagine è stata impostata automaticamente su 0 causando un problema di rendering. (CAMP-45366)

**Altre modifiche**

* Sono stati aggiunti meccanismi di prova in caso di errore durante il tentativo di importare un pubblico di Experienci Platform  utilizzando un&#39;attività di audience **** di lettura. (CAMP-43947, CAMP-43366)
* Le unità organizzative vengono ora automaticamente impostate in modo che corrispondano all&#39;unità organizzativa dell&#39;utente che crea il profilo o l&#39;entità. Le unità organizzative non possono più essere rimosse e lasciate vuote.
* Quando si pubblica una risorsa personalizzata, dopo la preparazione viene ora visualizzata una finestra a comparsa di conferma.
* È stato migliorato il messaggio a comparsa visualizzato in caso di errore di una risorsa personalizzata, per una maggiore chiarezza.
* L&#39;editor di espressioni nei flussi di lavoro è stato migliorato per evitare errori di esecuzione. [Sono disponibili nuove funzioni](../../automating/using/customizing-workflow-external-parameters.md) : possono essere utilizzati in tutte le attività che consentono di utilizzare le variabili evento dopo aver chiamato un flusso di lavoro con parametri esterni. Inoltre, ora viene visualizzata una descrizione comandi nell&#39;editor di espressioni con la descrizione della funzione.
* Sono stati aggiunti nuovi filtri all&#39;elenco degli eventi transazionali. Consentono di filtrare le configurazioni dell’evento in base al loro stato, nonché l’ultima volta che un evento è stato ricevuto.
* I file di registro visualizzati durante l&#39;esportazione dei pacchetti sono stati resi più specifici e dettagliati sugli errori riscontrati in caso di errore.
* Dopo aver inviato un messaggio, ora puoi cercare, filtrare ed esportare l’elenco degli URL [tracciati](../../sending/using/tracking-messages.md).
* La [sincronizzazione automatica tra Launch e Campaign](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) ora è in GA e attivata per impostazione predefinita.
* I messaggi transazionali possono essere inviati con priorità elevata anche in caso di un carico di lavoro di consegna in massa significativo.
* La dimensione dei pacchetti di esportazione del flusso di lavoro è stata ottimizzata rimuovendo l&#39;esportazione della prova di invio.
* È stato aggiunto un nuovo messaggio per visualizzare le dimensioni del file scaricato nell&#39;attività di trasferimento **dei** file.
* Sono stati migliorati i messaggi di errore per token di sessione non validi.
* Un nuovo meccanismo ora impedisce l&#39;aggiunta di proxy agli eventi di tracciamento ai registri e ai report.
* È stato aggiunto un nuovo messaggio di avviso per facilitare il debug delle attività di gestione dei dati connesse a un&#39;attività di consegna.
* Sono state migliorate le etichette nell&#39;area di lavoro di reporting.
* È stato aggiunto un nuovo passaggio di convalida per impedire l&#39;eliminazione di oggetti tecnici nei messaggi transazionali.
* Un nuovo filtro per lo stato di consegna è stato aggiunto nella scheda Elenco **di** esecuzione di un messaggio transazionale per migliorare la risoluzione dei problemi.
* Per migliorare le prestazioni e ottimizzare i tempi di esecuzione, gli indici non utilizzati sono stati rimossi, in base agli stati di utilizzo delle tabelle identificati nelle analisi preliminari per più di 350 clienti. Le tabelle interessate sono: nmsaddressStatus, nmscam, nmsdelivery, nmsslandingpage, nmsprogram, nmsRecipients, nmsseedMember, nmsservice, nmssubstorcp, nmsaudience, xtkworkflow

**Patch**

* È stato risolto un problema che impediva l&#39;utilizzo di un collegamento di destinazione per le notifiche push o i messaggi in-app quando il tracciamento era abilitato.
* È stato risolto un problema che poteva impedire l&#39;assegnazione di marchi a un&#39;e-mail transazionale. Durante il passaggio della pubblicazione potrebbero essere visualizzati diversi messaggi di errore. (CAMP-44988)
* È stato risolto un problema nell&#39;interfaccia utente del flusso di lavoro che poteva impedire il salvataggio delle informazioni nei campi che richiedevano valori numerici. (CAMP-44025)
* È stato risolto un problema che poteva visualizzare un messaggio di errore durante l&#39;utilizzo di un&#39;attività di **test** in un flusso di lavoro modello di importazione. (CAMP-42910)
* È stato risolto un problema che si verificava durante l&#39;utilizzo di un&#39;attività di **lettura dell&#39;audience** contenente un campo del tipo di enumerazione e connessa alle attività **di unione** o **arricchimento** . (CAMP-42795)
* È stato risolto un problema nei report dinamici che si verificava quando si utilizzavano i segmenti out-of-the-box per filtrare i dati nei report. (CAMP-42627)
* È stato risolto un problema che impediva di impostare un&#39;attività **Scheduler** su 12 AM. (CAMP-42674)
* È stato risolto un problema che poteva interrompere l&#39;invio di messaggi SMS quando la connessione SMPP era instabile. (CAMP-42789)
* È stato risolto un problema che impediva la visualizzazione del pulsante **Interrompi preparazione** dopo l&#39;aggiornamento della pagina. (CAMP-42721)
* È stato risolto un problema che impediva la visualizzazione delle percentuali dei rapporti sul clic con il pulsante di scelta rapida durante l&#39;importazione di contenuto da un URL. (CAMP-44468)
* È stato risolto un problema che poteva visualizzare un errore di timeout durante la selezione di un profilo da utilizzare nel contesto della sostituzione del profilo. (CAMP-44746)
* È stato risolto un problema che poteva impedire il funzionamento delle istanze dopo la distribuzione di risorse personalizzate contenenti definizioni di collegamenti non corrette. (CAMP-44406)
* È stato risolto un problema che creava entità collegate vuote (tipologie, marchi, ecc.) dopo aver copiato e incollato una distribuzione in un modello di campagna. (CAMP-44765)
* È stato risolto un problema che impediva l&#39;invio delle prove di stampa a causa di una gestione non corretta delle tabelle di preparazione del recapito in caso di arresto anomalo del database o di un semplice riavvio del database in Azure.
* È stato risolto un problema che poteva impedire l&#39;eliminazione di collegamenti con  contenuto Experience Manager in una distribuzione configurata con contenuto multilingue. (CAMP-44029)
* È stato risolto un problema nei report dinamici che poteva visualizzare un messaggio di errore durante il tentativo di filtrare le dimensioni.  (CAMP-43097)
* È stato risolto un problema che poteva visualizzare una schermata vuota quando si tentava di accedere ai profili in un&#39;istanza configurata con risorse personalizzate contenenti definizioni di collegamenti specifiche. (CAMP-41009)
* È stato risolto un problema nei flussi di lavoro che poteva verificarsi quando si utilizzava un&#39;attività di **arricchimento** con due attività di input con entrambe le risorse di destinazione collegate tra loro. (CAMP-42133)
* È stato risolto un problema che causava il loop dei flussi di lavoro di importazione quando si utilizzava un&#39;attività di trasferimento **di** file. (CAMP-43754)
* È stato corretto un problema a causa del quale i duplicati non venivano presi in considerazione durante la creazione di un profilo con registri esportati. (CAMP-45031)
* È stato risolto un problema che causava discrepanze di dati tra i report in  Adobe Campaign e i report esportati in file PDF. (CAMP-43010)
* È stato corretto un errore che causava un errore nel flusso di lavoro di consegna diretta tramite posta quando si utilizzavano campi di dati esistenti nelle funzioni. (CAMP-42737)
* È stato risolto un problema durante l&#39;importazione di pacchetti che includeva eventi transazionali e modelli di messaggi. Il processo di importazione è stato interrotto al 5%. (CAMP-42544)
* È stato risolto un problema che causava un errore (TipoErrore non rilevato) dopo la modifica dell&#39;attività di **arricchimento** e l&#39;aggiunta di dati aggiuntivi in un flusso di lavoro. (CAMP-41877)
* È stato corretto un errore che impediva l&#39;eliminazione del flusso di lavoro. Per eliminare il flusso di lavoro, era necessario eliminare i registri. (CAMP-44144)
* È stato corretto un errore durante la creazione di una pagina di destinazione con codice HTML. Le caselle di controllo obbligatorie non venivano riconosciute in Campaign e non erano disponibili nella pagina di destinazione pubblicata. (CAMP-44181)
* È stato risolto un problema che causava il loop di flussi di lavoro quando si utilizzava l&#39;attività **Wait** . (CAMP-43981)
* È stato risolto un problema che si verificava durante l&#39;invio di messaggi transazionali a causa del quale diversi indirizzi e-mail venivano mirati più volte nello stesso invio. (CAMP-44202)
* È stato risolto un errore che si verificava durante l&#39;utilizzo della sostituzione del profilo con la personalizzazione targetData. (CAMP-44996)
* È stato risolto un problema che causava un errore nell&#39;anteprima del recapito durante l&#39;esportazione di un modello di consegna in un pacchetto. (CAMP-44084)
* È stato risolto un problema che impediva l&#39;invio delle prove di stampa ai profili di test quando si utilizzavano mappature di destinazione personalizzate. (CAMP-43701)
* È stato corretto un errore che si verificava nei flussi di lavoro quando si utilizzava l&#39;attività **Leggi pubblico** e si utilizzava come destinazione un&#39;audience configurata con una dimensione di targeting diversa da **Profilo**.  (CAMP-41885)
* È stato risolto un problema che causava errori quando il flusso di lavoro tecnico **updateEventsStatus** impiegava troppo tempo per recuperare la cronologia degli eventi (quando il flusso di lavoro veniva interrotto). Il campo aggregato &quot;sumQueueTime&quot; non utilizzato è stato rimosso dal flusso di lavoro per risolvere il problema. (CAMP-43920)
* È stato risolto un problema di memoria durante la distribuzione di risorse personalizzate. (CAMP-42909)
* È stato risolto un problema nei messaggi transazionali quando gli attributi mancavano nelle raccolte. Ora tutti gli attributi mancanti sono definiti con un valore predefinito e inclusi nel payload. (CAMP-42882)
* È stato risolto un problema che poteva influire sulle prestazioni durante la query dei registri di consegna degli eventi in tempo reale. (CAMP-42759)
* È stato corretto un errore che si verificava durante l&#39;utilizzo di estensioni di file maiuscole con risorse condivise. (CAMP-44159)
* È stato risolto un problema che causava la visualizzazione di un messaggio di errore durante il test della connessione a un account esterno prima della creazione. Il pulsante **Verifica connessione** ora viene visualizzato solo dopo la creazione dell&#39;account esterno.
* È stato risolto un problema che causava la mancata visualizzazione dei messaggi in sospeso dopo il riavvio dell&#39;MTA avanzata nelle istanze configurate con la condivisione.
* È stato risolto un problema che poteva portare il conteggio dei profili attivi a una mancata corrispondenza del numero effettivo di consegne inviate.
* È stato risolto un problema che poteva causare latenza durante la ricerca di risorse nell&#39;editor di query in un flusso di lavoro.
* È stato risolto un problema che si verificava quando si selezionava **Specificare i campi da tenere in considerazione nell&#39;opzione di ricerca** del testo in una risorsa personalizzata. Se l&#39;elenco dei campi era lasciato vuoto, la pubblicazione delle risorse personalizzate non riusciva.
* È stato risolto un problema di prestazioni durante la visualizzazione della panoramica delle risorse personalizzate con un grande volume di dati.
* È stato risolto un problema che impediva l&#39;importazione di una consegna utilizzando sostituzioni di profilo.
* È stato risolto un problema che impediva l&#39;invio immediato delle prove di sostituzione del profilo in caso di programmazione della consegna.
* È stato risolto un problema che si verificava durante il caricamento di una chiave Android per un&#39;applicazione mobile. Il messaggio visualizzato dopo il corretto caricamento della chiave visualizzava il valore della chiave precedente.
* È stato risolto un problema che impediva la creazione di profili di test dai messaggi transazionali dopo la creazione di una configurazione dell&#39;evento con una raccolta senza attributo.
* È stato risolto un problema che poteva impedire la pubblicazione di risorse personalizzate dopo la creazione di un nuovo filtro tramite un&#39;aggregazione.
* È stato risolto un problema che causava una frequenza di apertura di tracciamento non corretta per i destinatari Gmail causata dal proxy immagine Gmail.
* È stato risolto un problema che causava errori di memoria insufficiente durante l&#39;importazione di un pacchetto.
* È stato risolto un problema che causava un errore nell&#39;azione di scollegamento del Experience Manager  quando il contenuto del Experience Manager  includeva un percorso con un carattere &quot;%20&quot;.
* È stato corretto un errore sulle etichette durante la duplicazione delle attività del flusso di lavoro.
* È stato risolto un problema con il selettore messaggi transazionali in una pagina di destinazione quando era selezionata l&#39;opzione **Avvia messaggio** di invio.
* È stato risolto un problema relativo ai messaggi transazionali o alle consegne ricorrenti che impediva l&#39;inizializzazione dello stato di consegna con il valore predefinito corretto. Sono stati migliorati anche i registri di errore.
* È stato risolto un problema che si verificava durante l&#39;estensione dell&#39; **iscrizione a uno schema di applicazione** (appSubscriptionRcp) con un collegamento di profilo utilizzando un campo personalizzato. L&#39;indice non è stato creato automaticamente e potrebbe influire sul tempo di invio push. (CAMP-41120)

