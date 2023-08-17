---
title: Note sulla versione 2021
description: In questa pagina sono elencate tutte le versioni del 2021 di Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: 225c65cc-2964-4b71-84a9-30fcd22d75bf
source-git-commit: 1a2b2ab8b6d23ca021d196909dc3ebdc02fe4e9e
workflow-type: tm+mt
source-wordcount: '4569'
ht-degree: 100%

---

# Note sulla versione 2021{#release-notes-2021}

## Versione 21.3 - Settembre 2021 {#release-21-3---sept-2021}

Di seguito sono elencati le nuove funzioni, i miglioramenti e le correzioni inclusi nell’ultima versione di Campaign Standard.

**Novità**

<table> 
<thead> 
<tr> 
<th> <strong>Interfaccia unificata di Experience Cloud</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>La barra dell’intestazione di Adobe Campaign è stata modificata per offrirti un’esperienza migliore e unificata in tutti i prodotti e i servizi Experience Cloud. Queste modifiche sono state progettate per rendere il lavoro più facile e includono:</p>
<ul>
<li>Passaggio più semplice da un’organizzazione all’altra o a un’altra applicazione.</li>
<li>Guida utente migliorata: Experience League è ora accessibile direttamente dal prodotto e i risultati delle ricerche includono anche i forum della community e altri contenuti video, per consentirti di accedere più facilmente a più contenuti e aiutarti a trarre il massimo dall’applicazione. Inoltre, è stato aggiunto un meccanismo di feedback nel menu Help, per agevolare la segnalazione di problemi e la condivisione di idee.</li>
<li>Notifiche migliorate: il menu a discesa Notifications ora include due schede, una per le notifiche sui tuoi prodotti e una per gli annunci globali sui prodotti.</li>
</ul>
<p>Per ulteriori informazioni consulta la <a href="../../start/using/interface-description.md#top-bar">documentazione dettagliata</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Audit Trail</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>La nuova funzione Audit Trail acquisisce in tempo reale un elenco completo delle azioni e degli eventi che si verificano in Adobe Campaign. Permette di accedere in autonomia alla cronologia dei dati per poter rispondere a domande quali:</p>
<ul>
<li>Cos’è successo a un dato flusso di lavoro e chi l’ha aggiornato per ultimo?</li>
<li>Chi ha effettuato gli ultimi cambiamenti?</li>
<li>Qual era lo stato precedente?</li>
</ul>
<p>Adobe Campaign ora controlla le azioni di creazione, modifica ed eliminazione per: flussi di lavoro, opzioni, risorse personalizzate. Vengono inoltre tracciate le modifiche di tali elementi.</p>
<p>Per ulteriori informazioni, consulta la <a href="../../administration/using/audit.md">documentazione dettagliata</a>.</p>
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>Modalità diagnostica per i flussi di lavoro</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Ora puoi eseguire i flussi di lavoro Campaign in modalità diagnostica. Questa modalità registra le informazioni utili per risolvere eventuali problemi di esecuzione. L’intero piano di esecuzione viene registrato se una query del flusso di lavoro richiede, per impostazione predefinita, più di un minuto.</p>
<p>Per ulteriori informazioni consulta la <a href="../../automating/using/managing-execution-options.md">documentazione dettagliata</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Miglioramenti della sicurezza**

* È stata migliorata la sicurezza per la protezione contro gli attacchi SSRF. (CAMP-47836)
* L’elenco degli utenti è ora limitato ai soli amministratori. (CAMP-47260)
* Le variabili di ambiente non possono più essere utilizzate come parte dell’espansione dei parametri in un URL. (CAMP-47268)

**Miglioramenti**

* Durante la creazione di una consegna ricorrente in un flusso di lavoro, collegata a un contenuto Adobe Experience Manager, ora lo stato di approvazione del contenuto viene controllato prima dell’invio.
* Il limite di connessione al database è ora allineato con il pacchetto Campaign per evitare errori di connessione.
* Una nuova verifica di coerenza nella pubblicazione delle risorse personalizzate impedisce agli utenti di creare indici duplicati, che causano errori di pubblicazione. Se necessario, un messaggio di errore migliorato chiede all’utente di rinominare l’indice. [Ulteriori informazioni](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)

**Altre modifiche**

* Il servizio Connettore dati e Destinazioni pubblico di Adobe Experience Platform è ora obsoleto con Campaign Standard. Se utilizzi queste funzionalità, devi passare ad origini e destinazioni di Adobe e adattare la tua implementazione. [Ulteriori informazioni](../../integrating/using/get-started-sources-destinations.md)
* Le funzioni obsolete e rimosse sono elencate in [questa pagina](deprecated-features.md).
* È stata introdotta una nuova funzione di aggregazione “StringAgg” per concatenare i valori di una colonna di tipo stringa. (CAMP-47077) [Ulteriori informazioni](../../automating/using/list-of-functions.md#aggregates)
* Il flusso di lavoro tecnico **Aggiorna indicatori di consegna** (updateDeliveryIndicators) è stato migliorato per potenziarne le prestazioni.
* I modelli di messaggistica in-app sono ora disponibili per tutte le lingue supportate in Campaign Standard.
* I tempi di preparazione della consegna sono stati ottimizzati per i messaggi transazionali riducendo il numero di chiamate al server di tracciamento durante l’analisi della consegna.
* Un nuovo messaggio di avviso informa gli utenti di un elevato tasso di mancato recapito.
* Sono stati migliorati i messaggi di errore del registro e gli avvisi per facilitare il debug quando i registri di tracciamento non sono stati recuperati correttamente. (CAMP-48939, CAMP-47360)
* Ora puoi personalizzare completamente gli URL, incluso il nome di dominio. [Ulteriori informazioni](../../designing/using/personalization.md#personalizing-urls)
* I profili trappola e di test ora sono stati esclusi dal calcolo delle prestazioni di consegna nei rapporti dinamici. (CAMP-47338)

**Patch**

* È stato corretto un errore di timeout che si verificava durante l’importazione di contenuti e-mail da un URL. (CAMP-49054)
* È stato corretto un errore (-69) causato dalla fine della sessione, quando si accede a un URL contrassegnato con segnalibro o si aggiorna una pagina dal browser. (CAMP-49003, CAMP-48930, CAMP-48894)
* È stato risolto un problema che si verificava durante la sincronizzazione delle regole dal server di recapito messaggi precedente al nuovo server di recapito messaggi. (CAMP-48923)
* È stato risolto un problema che si verificava durante il caricamento di un modello e-mail con tag HTML in Email Designer. (CAMP-48243)
* È stato corretto un errore a causa del quale il contenuto di Adobe Experience Manager non veniva caricato durante la creazione di messaggi transazionali con Email Designer. (CAMP-49075)
* È stato risolto un problema nell’interfaccia a causa del quale veniva aggiunta troppa spaziatura tra la barra superiore e il contenuto.
* È stato risolto un problema relativo ai messaggi transazionali che poteva causare un errore di pubblicazione durante l’utilizzo dei blocchi di contenuto Campaign in contenuti Adobe Experience Manager. (CAMP-49233)
* È stato risolto un problema che poteva causare un messaggio di errore in caso di autenticazione non riuscita. L’utente viene ora reindirizzato alla pagina di accesso.
* È stato risolto un problema di visualizzazione del token che poteva impedire agli utenti di modificare o condividere un rapporto.
* È stato risolto un problema riscontrato durante la pubblicazione di una risorsa personalizzata che utilizzava un’espressione di filtro con relazioni di tabella 1-n. (CAMP-48740)
* È stato risolto un problema di formattazione della data che impediva il recupero delle date di contatto di consegna nelle transizioni del flusso di lavoro. (CAMP-48871)
* È stato risolto un problema che impediva l’estensione dei registri di invio durante la creazione di una dimensione di profilo personalizzata.
* È stato risolto un problema che poteva causare un errore nelle consegne con più varianti di lingua. D’ora in poi, se si elimina la variante di lingua predefinita, prima di creare copie per lingue si deve impostare come predefinita un’altra variante di lingua. (CAMP-48235)
* È stato risolto un problema che causava la visualizzazione di spazi vuoti aggiuntivi nei messaggi e-mail in Outlook se l’utente aveva selezionato l’opzione **Mostra solo su dispositivi mobili** durante la progettazione del messaggio. (CAMP-48902)
* È stato risolto un problema che causava la mancanza dell’ultima data di esecuzione del campo dell’attività di query incrementale dalla scheda **Dati elaborati** dopo l’esecuzione del flusso di lavoro di query incrementale. (CAMP-48879)
* È stato risolto un problema che impediva la corretta definizione di un codice di segmento dinamico nell’attività del flusso di lavoro **Segmentazione**. (CAMP-48727)
* È stato corretto un errore che si verificava in modo casuale durante il tentativo di salvare un flusso di lavoro dopo averlo modificato. (CAMP-48695)
* È stato risolto un problema che impediva la pubblicazione di risorse personalizzate a causa della persistenza di uno schema di dati del trigger anche dopo l’eliminazione di quest’ultimo. (CAMP-48523)
* È stato risolto un problema che impediva il rispetto delle richieste del ciclo di feedback, perché il processo InMail non era in grado di recuperare i registri di consegna da aggiornare. (CAMP-48705)
* È stato risolto un problema che impediva la corretta definizione delle opzioni di esclusione nell’attività del flusso di lavoro **Esclusione**.(CAMP-48355)
* È stato risolto un problema che si verificava quando le attività di arricchimento nei flussi di lavoro includevano abbonamenti o annullamenti di abbonamenti da un servizio. Questo problema causava l’arresto dell’applicazione.
* È stato risolto un problema che poteva impedire l’esecuzione dei flussi di lavoro.
* È stato risolto un problema che poteva impedire agli utenti di rinominare o eliminare i gruppi di sicurezza predefiniti dall’interfaccia utente.
* È stato risolto un problema che poteva impedire agli utenti di eliminare un processo di pubblicazione evento incompleto.
* È stato risolto un problema che causava un errore nel flusso di lavoro di pulizia del database. (CAMP-49097)


## Versione 21.2 - Giugno 2021 {#release-21-2---june-2021}

Di seguito sono elencati le nuove funzioni, i miglioramenti e le correzioni inclusi nella prossima versione di Campaign Standard. Di seguito sono elencate nuove funzioni, miglioramenti e correzioni inclusi in questa versione di Campaign Standard.

**Miglioramenti**

* Durante la progettazione di una pagina di destinazione, è ora possibile aggiungere una casella di controllo obbligatoria che i profili devono selezionare prima di inviare il modulo. Per ulteriori informazioni consulta la [documentazione dettagliata](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox).

* Per l’integrazione con gli Attivatori, è stato migliorato il messaggio di errore visualizzato quando non sono presenti dati di riconciliazione in arrivo nel payload dell’attivatore: “Alias data missing from payload”.

* Sono state migliorate le prestazioni per il recupero delle notifiche push dalla coda.

**Altre modifiche**

* Il meccanismo di firma URL per i collegamenti di tracciamento è stato disattivato per evitare un problema che causava il blocco errato di alcuni collegamenti di tracciamento validi e firmati dopo la modifica da parte di strumenti di sicurezza di terze parti.

* Nelle consegne con più varianti, gli utenti non possono più creare copie per lingua se la variante predefinita è stata eliminata. Durante la creazione della copia in lingua viene ora visualizzato un messaggio. (CAMP-48235)

* Il processo di eliminazione del profilo in due fasi (obsoleto a partire da Campaign 19.4) ora è disattivato per impostazione predefinita. In precedenza era necessario disattivarlo manualmente dall’interfaccia di Campaign prima di utilizzare il servizio core Privacy. In caso contrario, lo stato delle richieste di cancellazione rimane in sospeso senza arrivare al termine.

* Nei rapporti dinamici, è stato rimosso il segmento **Exclude Proof**. (CAMP-46161)

* È stato aggiunto un nuovo messaggio di avvertenza per informare l’utente quando viene caricato nell’applicazione Campaign un certificato iOS senza il valore platformPrincipal.

* La dimensione massima di un messaggio e-mail ora è impostata su 100 MB per impostazione predefinita. Questo limite consente di evitare eventuali errori che potrebbero aumentare indefinitamente le dimensioni di un’e-mail e causare un arresto anomalo del sistema. (CAMP-47445) [Ulteriori informazioni](../../sending/using/design-and-personalize.md#email-size)

* L’integrazione del servizio core Assets con Email Designer può ora essere utilizzata dagli utenti Standard.

* È stato aggiunto un nuovo messaggio per confermare la riuscita della migrazione da un’applicazione push v4 a un’applicazione push v5.

* Durante la creazione di token JSONWeb per l’autenticazione nell’API Campaign Standard, ora vengono **considerati** i profili di prodotto. Ciò significa che le unità organizzative e i ruoli assegnati al gruppo di sicurezza (che corrispondono al profilo prodotto su AdobeIO) verranno applicati all’account tecnico IMS necessario per le chiamate API Rest di Campaign Standard. (CAMP-47479)

**Patch**

* È stato risolto un problema che impediva l’applicazione dell’opzione di scadenza per la tabella di registro del processo batch (**xtkjoblog**). Ciò impediva la corretta eliminazione della tabella.

* È stato risolto un problema che impediva la modifica dell’ordine dei filtri in un’attività del flusso di lavoro **Segmentation**. (CAMP-48357)

* È stata corretta una regressione dalla versione 20.4 che poteva causare un errore di consegne con un valore null. (CAMP-48591)

* È stato risolto un problema che impediva l’invio di un rapporto tramite il menu **Share** > **Send Report Now** o **Send Report on Schedule**. (CAMP-47798)

* È stata corretta una regressione che poteva causare tassi di apertura errati per Gmail a causa del filtraggio degli eventi di tracciamento ricevuti dagli account Gmail. (CAMP-46504)

* Sono stati risolti diversi problemi che causavano discrepanze di dati tra i rapporti in Adobe Campaign Standard e Adobe Analytics. (CAMP-47671, CAMP-47296)

* È stato risolto un problema che impediva l’accesso ai registri di consegna in seguito alla preparazione non riuscita. (CAMP-48296)

* È stato risolto un problema a causa del quale poteva comparire un messaggio di errore durante il tentativo di modificare, eliminare o inviare un rapporto personalizzato. (CAMP-47789, CAMP-47798)

* È stato risolto un problema che causava il mancato funzionamento delle chiamate API durante la creazione di una nuova risorsa personalizzata e l’abilitazione dell’opzione **Do not synchronize**. (CAMP-48014)

* È stato risolto un problema a causa del quale le risorse personalizzate abilitate con l’opzione **Do not synchronize** potevano fare riferimento a uno schema rielaborato o eliminato. Questo problema causava un errore durante la pubblicazione delle risorse personalizzate.

* È stato risolto un problema di rinuncia SMS quando si utilizzano più codici brevi sullo stesso account esterno.

* È stato risolto un problema che impediva l’accesso a un nuovo criterio di avviso sulla consegna (“la risorsa a cui si sta tentando di accedere non è raggiungibile”) dopo la pubblicazione del database. (CAMP-48221)

* È stato risolto un problema che causava l’assenza di registri di tracciamento in alcune istanze di Campaign con reporting dinamico. È stato aggiunto un nuovo [flusso di lavoro tecnico](../../administration/using/technical-workflows.md) per ripristinare questi registri di tracciamento. (CAMP-47885)

* È stato risolto un problema a causa del quale nei rapporti dinamici non venivano visualizzati dati di consegna. I rapporti venivano impostati su 0. (CAMP-47480)

* È stato risolto un problema che impediva al client HTTP JavaScript del server di connettersi all’URL esterno.

* È stato risolto un problema a causa del quale un’attività **Incremental query** veniva ripristinata in seguito alla modifica del nome interno del flusso di lavoro. Ciò si verificava quando un campo data veniva utilizzato come modalità incrementale. (CAMP-47674)

* È stato risolto un problema che impediva la visualizzazione della miniatura di anteprima nel riepilogo della consegna durante la creazione di un messaggio e-mail multilingue con l’integrazione di Adobe Experience Manager. Questo problema si verificava quando si utilizzava il pulsante per la **creazione copia in lingua** per creare le varianti dell’e-mail. (CAMP-47810)

* È stato risolto un problema che impediva agli utenti di accedere alla consegna principale dalla consegna secondaria e-mail o SMS. (CAMP-47986)

* È stato risolto un problema che poteva causare un consumo eccessivo di CPU e memoria durante l’invio di messaggi transazionali tramite l’API REST se un evento personalizzato risultava mancante. (CAMP-47147)

* È stato risolto un errore relativo all’API di messaggistica transazionale che talvolta impediva l’invio di messaggi in tempo reale.

* È stato risolto un problema a causa del quale i rapporti non venivano ricevuti dopo l’utilizzo dell’opzione per **Send report on schedule**. (CAMP-48583, CAMP-47786)

* È stato risolto un problema a causa del quale i rapporti ricevuti dopo l’utilizzo dell’opzione **Send report now** risultavano incompleti e mancanti. (CAMP-48583)

* È stato risolto un problema relativo a E-mail Designer a causa del quale le dimensioni di un’immagine venivano ridotte durante il caricamento. (CAMP-47017)

* È stato risolto un problema che impediva la visualizzazione di ogni modello di Experience Manager disponibile durante la creazione di una consegna. (CAMP-48132)

* È stato corretto un errore che impediva al collegamento Campaign, nella pagina di riepilogo di una consegna inviata, di reindirizzare gli utenti alla campagna correlata. (CAMP-48012)

* È stato risolto un problema in E-mail Designer a causa del quale l’integrazione del servizio core Assets continuava a non riuscire nel tentativo di selezionare una risorsa. (CAMP-47446)

* È stato risolto un problema che bloccava alcune consegne di Journey Orchestration a causa del fatto che Campaign non supportava le marche temporali con un valore esatto (cioè con ultime cifre pari a 00) inviate dagli eventi da Journey Orchestration.

## Versione 21.1 - Febbraio 2021 {#release-21-1---february-2021}

**Novità**

<table> 
<thead> 
<tr> 
<th> <strong>Servizio di feedback delle e-mail</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Il servizio di feedback delle e-mail (EFS, Email Feedback Service) è un servizio scalabile che acquisisce direttamente i commenti dall’MTA (Mail Transfer Agent) avanzato, migliorando così la precisione della generazione di rapporti. Questa funzionalità viene rilasciata come versione beta privata e sarà disponibile progressivamente per tutti i clienti nelle versioni future.</p>
<ul>
<li>Vengono ora acquisite tutte le categorie di feedback per la generazione di rapporti completi e precisi.</li>
<li>Il calcolo dell’indicatore <b>Delivered</b> è ora basato sul feedback in tempo reale dall’MTA avanzato per una maggiore precisione e reattività.</li>
<li>Il servizio EFS risolve il problema dei ritardi nella generazione sincrona di rapporti sui soft bounce.</li>
</ul>
<p>Per ulteriori informazioni consulta la <a href="../../sending/using/confirming-the-send.md">documentazione dettagliata</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Miglioramenti per l’integrazione con Adobe Experience Manager</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>L’integrazione di Campaign con Adobe Experience Manager è stata migliorata: ora puoi importare contenuti multilingue più facilmente da Adobe Experience Manager. <p>
<p>Adobe Campaign Standard ora rileva automaticamente le varianti di lingua dai contenuti Adobe Experience Manager e consente di importare e creare varianti in blocco, semplificando in modo significativo il numero di passaggi necessari per consentire ai professionisti di creare una campagna multilingue basata su contenuti Adobe Experience Manager.</p>
<p>Per ulteriori informazioni consulta la <a href="../../integrating/using/creating-multilingual-email-aem.md">documentazione dettagliata</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<!--
<table> 
<thead> 
<tr> 
<th> <strong>Unified Experience Cloud interface</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaign header bar has been changed to unify and improve your experience across all Experience Cloud products and services. These changes are designed to make your life easier, including:</p>
<ul>
<li>Easier switching between your organizations or to a different application.</li>
<li>Improved User Help – Bringing the Experience League into the product, search results also include results from community forums and more video content, giving you easier access to more content to help get the most out of the application. We've also added a feedback mechanism right in the Help menu, making it easier to report issues or share your ideas.</li>
<li>Improved Notifications – Notifications drop-down now has two tabs: one for your own product notifications, and one for more global product announcements.</li>
</ul>
<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>
<p>NOTE: This change will be progressively rolled out to all customer environments between Feb 10 and March 1st.
</p>
</td> 
</tr> 
</tbody> 
</table>
-->

**Miglioramenti**

* L’**integrazione Microsoft Dynamics 365** è stata migliorata con un’applicazione di integrazione self-service dedicata e un processo di implementazione migliorato. [Ulteriori informazioni](../../integrating/using/d365-acs-get-started.md)

* Sono stati apportati miglioramenti per facilitare la risoluzione dei problemi legati al processo di messaggistica transazionale. Gli amministratori tecnici di Adobe ora possono utilizzare il tracciamento su qualsiasi processo senza riavviarlo.

* L’elenco **Profiles** ora consente di cercare record basati su uno dei seguenti campi: e-mail, nome, cognome o campi personalizzati aggiunti nel filtro avanzato durante l’estensione della risorsa profilo. Questa funzione è disponibile anche nelle API di Campaign Standard mediante il parametro filterType. [Ulteriori informazioni](../../audiences/using/integrated-customer-profile.md)

* È stato modificato un parametro in base al numero di contenitori in cui è in esecuzione il processo di pooling del database di messaggistica transazionale. Questo consente di distribuire uniformemente il carico tra tutti i contenitori utilizzati e di ottimizzare le prestazioni.

* È ora disponibile la nuova funzione **GetOption** nelle attività che utilizzano variabili evento dopo aver richiamato un flusso di lavoro con parametri esterni. Consente di restituire il valore di una funzione specificata. [Ulteriori informazioni](../../automating/using/customizing-workflow-external-parameters.md)

* Una nuova opzione consente a Campaign Standard di **verificare la disponibilità di memoria fisica** nel sistema prima di avviare un flusso di lavoro. Se la memoria risulta insufficiente, l’esecuzione del flusso di lavoro verrà posticipata fino a quando la memoria disponibile raggiungerà una soglia adeguata. In questo modo si evita un ulteriore degrado delle prestazioni e si riduce il rischio di interruzioni. Il flusso di lavoro riprenderà automaticamente una volta diminuito il carico sul server e aumentata la memoria disponibile. Questa opzione è di sola lettura e non può essere modificata. [Ulteriori informazioni](../../automating/using/best-practices-workflows.md#execution)

* È disponibile un nuovo processo in Adobe Campaign Standard che consente di migrare più facilmente dall’app mobile SDK v4 legacy a **Adobe Experience Platform Mobile SDK**. Consulta [questa pagina](../../administration/using/sdkv4-migration.md).

**Altre modifiche**

* Il messaggio di errore che si verificava durante la preparazione dei messaggi al raggiungimento del limite di 100 download di contenuto nell’ora precedente viene ora visualizzato come messaggio di avvertenza. Ora, al raggiungimento del limite, viene visualizzata un’avvertenza che consente di procedere con la consegna.

* Quando si arricchisce il contenuto di un messaggio transazionale, i collegamenti non vengono più richiamati al momento del recupero dei dati dalla tabella Profile. In questo modo si riduce la latenza durante la preparazione dei messaggi e si evitano dati del profilo vuoti a causa di una relazione errata definita con la tabella del profilo.

* La configurazione tecnica dell’istanza è stata ottimizzata per garantire stabilità. (CAMP-45681)

* La gestione delle sessioni è stata migliorata per ottimizzare la memoria. (CAMP-45901, CAMP-46767)

* L’attività **Transfer file** genera ora una variabile aggiuntiva (filesCount) che contiene il numero di file caricati o scaricati. (CAMP-45842) [Ulteriori informazioni](../../automating/using/transfer-file.md#output-variables)

* Il connettore SMS ora può inviare più parametri opzionali con ogni messaggio. [Ulteriori informazioni](../../administration/using/sms-protocol.md)

* Gli utenti con il ruolo DATAMODEL ora possono pubblicare estensioni del registro di consegna. (CAMP-46604)

* Per maggiore chiarezza, è stato riformulato il messaggio di errore visualizzato durante il tentativo di pubblicare una risorsa che ha come target una risorsa personalizzata non più esistente. (CAMP-46893)

* Nell’elenco **Preferred language** sono state aggiunte le seguenti lingue: indonesiano - Indonesia (in-id), inglese - Svezia (en-se), inglese - Asia pacifica (en-ap), inglese - Giappone (en-jp), spagnolo - America latina (es-la). (CAMP-46351)

* Il selettore per la selezione dei profili durante il test di una pagina di destinazione ora utilizza la risorsa profilBase invece del profilo, per evitare errori di timeout.

* Il formato di registro SMPP è stato migliorato.

* Sono stati aggiunti parametri opzionali per le funzioni JS cryptString e decryptString corrispondenti alle API di Adobe Campaign Classic.

* Sono stati migliorati i messaggi di avvertenza o di errore nei registri di preparazione della consegna.

* Sono stati migliorati i registri di errore relativi al tentativo di connessione al servizio Adobe Identity Management (IMS).

* Ora puoi filtrare ulteriormente le dimensioni **Delivery** e **Campaign** utilizzando la barra di ricerca nella funzione di reporting dinamico.

* La data di validità dei messaggi SMS transazionali ora può essere definita dal valore impostato per il parametro di scadenza nell’API per messaggi transazionali. (CAMP-36600)

* Nella funzione di reporting dinamico, il rapporto integrato **Riepilogo della consegna** mostrava dati non corretti per la metrica del tasso di annullamento dell’iscrizione. Per risolvere il problema è stata aggiunta la nuova metrica **Unique unsubscription**. (CAMP-46445)

**Patch**

* È stato risolto un problema che provocava l’esecuzione molto lenta delle consegne a causa di alcuni processi. Era dovuto alla definizione di unità errate per diversi parametri (ad esempio, millisecondi anziché secondi).

* È stato risolto un problema che si verificava quando Mobile SDK inviava una richiesta di tracciamento aperta basata sulla condizione che il valore di deliveryId/MessageID non fosse nullo. Questo generava errori 404 per le consegne con tracciamento disabilitato. Nel payload viene ora inviata una variabile aggiuntiva (acsDeliveryTracking) con informazioni sullo stato di tracciamento della consegna. Questa variabile può avere due valori (attivato o disattivato) a seconda dello stato di tracciamento impostato. [Ulteriori informazioni](../../administration/using/push-tracking.md).

* È stato risolto un problema nei flussi di lavoro che poteva verificarsi se si copiava e incollava un’attività **Deduplication** che era stata eseguita una volta e che sfruttava una risorsa temporanea. Una volta duplicata, la risorsa dell’attività veniva automaticamente impostata su vuota, causando problemi in altre attività del flusso di lavoro. Una volta incollata, la risorsa dell’attività ora rimane la stessa, così che l’errore possa attivarsi il prima possibile anziché in un punto successivo del flusso di lavoro. (CAMP-46903)

* È stato risolto un problema che causava un errore nell’analisi della consegna durante l’invio di un messaggio push transazionale con targeting di profilo, introducendo una nuova [mappatura del target](../../administration/using/target-mappings-in-campaign.md): **Profilo - Evento real-time per push** (*mapRtEventAppSubRcp*). I registri di consegna, esclusione e tracciamento per le [notifiche push transazionali con targeting di profilo](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile) verranno ora memorizzati nelle tabelle *broadLogAppSubRcp*, *excludeLogAppSubRcp* e *trackingLogAppSubRcp*.

  >[!IMPORTANT]
  >
  >A causa di questa modifica, se utilizzi una notifica push transazionale basata su profilo esistente (creata prima dell’aggiornamento ad Adobe Campaign 21.1), ti consigliamo di aggiornare la mappatura di destinazione a quella nuova e pubblicare nuovamente il messaggio. Consulta i [passaggi dettagliati](../../channels/using/transactional-push-notifications.md#change-target-mapping). L’utilizzo della mappatura di destinazione precedente **Profilo - Evento in tempo reale** (*mapRtEventRcp*) può comportare tempi di preparazione più lunghi e deterioramento delle prestazioni.

* È stato risolto un problema che impediva l’esecuzione dei rapporti di consegna quando venivano visualizzate 5000 righe.
* È stato risolto un problema relativo al test A/B che impediva l’aggiornamento del contenuto della variante B dopo una modifica del modello di consegna. (CAMP-45235)
* È stato risolto un problema che causava il blocco del processo di messaggistica transazionale, impedendo l’invio di messaggi.
* È stato risolto un problema che poteva causare problemi di navigazione dopo aver fatto clic su un collegamento interno (ad esempio, quando si accedeva alla consegna principale da una schermata di riepilogo delle bozze).
* È stato risolto un problema che impediva la visualizzazione di tutti i modelli disponibili di contenuto di Experience Manager durante la creazione di una consegna. (CAMP-45990)
* È stato risolto un problema nei flussi di lavoro che poteva impedire la visualizzazione dei messaggi di errore nei registri di consegna dopo l’aggiunta della colonna **Reason** alla scheda dei dati aggiuntivi. (CAMP-45139)
* È stato risolto un problema che poteva verificarsi quando due chiamate di abbonamento all’applicazione avevano lo stesso ID Marketing Cloud (errore “duplicate key value violates unique constraint”).
* È stato risolto un problema che poteva causare problemi di lentezza durante il trascinamento di attività in un flusso di lavoro contenente una grande quantità di attività **Query** e **Read audience**. (CAMP-44511)
* È stato corretto un errore che poteva verificarsi al termine della preparazione dei messaggi transazionali e che impediva il caricamento delle informazioni di reindirizzamento sui server di tracciamento.
* È stato risolto un problema a causa del quale potevano comparire messaggi di errore se si tentava di aprire modelli di importazione o processi di importazione precedenti dopo aver personalizzato la risorsa del flusso di lavoro. (CAMP-46183)
* È stato risolto un problema che poteva impedire l’esecuzione di un’attività **Read audience** se configurata con un nome di pubblico dinamico. (CAMP-46047)
* È stato risolto un problema che impediva la visualizzazione del pulsante **Export list**.
* È stato risolto un problema che poteva causare un errore nel flusso di lavoro **Reporting aggregates**. (CAMP-45979)
* È stato risolto un problema che si verificava durante la creazione di una risorsa personalizzata con una chiave composita personalizzata (contenuto dinamico testo/data).
* È stato risolto un problema che poteva impedire la visualizzazione dei dati di transizione di una query. (CAMP-45669)
* Sono stati corretti alcuni problemi di consumo di memoria relativi alla pubblicazione di risorse personalizzate.
* È stato risolto un problema che si verificava durante la configurazione di una consegna da inviare in una data specifica. Se poi si impostava la consegna affinché venisse inviata immediatamente dopo a conferma, la preparazione della consegna non riusciva e veniva considerata la data specificata inizialmente. (CAMP-44107)
* È stato risolto un problema che impediva l’apertura dei modelli transazionali. (CAMP-47181)
* È stato risolto un problema nel processo di pubblicazione dei messaggi transazionali che poteva causare la duplicazione di tipologie e regole di tipologia con nomi più lunghi di quanto consentito per la stringa. (CAMP-47104)
* È stato risolto un problema nell’attività **External API** che si verificava quando un parametro di input restituiva un record inesistente. (CAMP-47023)
* È stato risolto un problema che poteva impedire la riconnessione del connettore SMPP.
* È stato risolto un problema che si verificava nell’attività **File transfer** durante il download di un file il cui nome conteneva un punto. I caratteri dopo il punto venivano considerati estensione del file. (CAMP-46624)
* È stato risolto un problema che impediva l’esecuzione del pooling del database, causando il blocco dei messaggi transazionali nella coda del router.
* È stato risolto un errore che non impediva l’invio dei registri di consegna annullati.
* È stato risolto un problema che poteva causare un errore nel flusso di lavoro quando si utilizzava un’attività **AND-join**. L’attività modificava automaticamente il set Primary all’ultima transizione collegata, anche se mostrava visivamente la prima. (CAMP-46900)
* È stato risolto un problema che poteva causare l’incorretta assegnazione dello stato Valid agli indirizzi correttamente inseriti in quarantena, con la loro conseguente rimozione dalla quarantena.
* È stato risolto un problema che impediva la visualizzazione di campi personalizzati contenenti caratteri speciali. (CAMP-46805)
* È stato risolto un problema che poteva impedire la visualizzazione di una specifica vista dettagliata di un profilo. Ciò si verificava se la risorsa del profilo era stata estesa con campi personalizzati, con l’opzione **Add a personalized fields section** abilitata.
* È stato risolto un problema che poteva restituire un codice di errore 500 durante l’invio di eventi transazionali. (CAMP-46811)
* È stato risolto un problema che poteva impedire la ricezione di rapporti pianificati tramite e-mail. (CAMP-46891)
* È stato risolto un problema che si verificava quando si collegava una risorsa personalizzata alla risorsa del profilo con un collegamento semplice a 1 cardinalità. Quando si accede a un profilo con un campo risorsa personalizzato vuoto, ora viene visualizzato un messaggio di errore invece di un elenco vuoto.
* È stato risolto un problema che si verificava durante l’utilizzo della sostituzione di un profilo in un flusso di lavoro, a causa del quale la pagina non riusciva a caricare i profili di consegna quando si selezionava il profilo da sostituire. (CAMP-46522)
* È stata risolta una regressione a causa della quale il flusso di lavoro tecnico **Database Cleanup** tentava di eliminare le tabelle di lavoro di consegne scadute, causando i seguenti errori: (CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* È stato risolto il seguente errore che si verificava in alcuni casi quando si utilizzava un filtro personalizzato su risorse personalizzate: (CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* È stato risolto un problema a causa del quale il completamento della funzione **Push notification preparation** impiegava troppo tempo. Questo era causato da un indice mancante nelle tabelle di lavoro transitorie.
* È stato risolto un errore che si verificava durante l’utilizzo dell’opzione **Dimension to reconciliate** in un’attività **Reconciliation** in un flusso di lavoro, se era già stata definita una relazione tra una risorsa personalizzata e una risorsa profilo.
* È stato risolto un problema che si verificava durante l’aggiunta di collegamenti tramite un’attività **Reconciliation** o **Enrichment**. I collegamenti selezionati non venivano visualizzati nella transizione di output.
* È stato risolto un problema che si verificava durante l’utilizzo di un’attività **Segmentation** con consegne ricorrenti in un flusso di lavoro, causando l’invio della consegna a un pubblico errato. (CAMP-46275, CAMP-46470)
* È stato corretto un errore a causa del quale la pubblicazione di risorse personalizzate non riusciva se si tentava di estendere la risorsa del profilo per creare dimensioni di profilo personalizzate per la generazione di rapporti dinamici. (CAMP-46266)
* È stato corretto un errore che si verificava durante l’aggiunta di un collegamento a una tabella File import. Dopo l’aggiunta di un’attività **Enrichment** all’attività **File import**, il collegamento configurato in precedenza scompariva. (CAMP-46557)
* È stato risolto un problema che si verificava durante l’utilizzo di risorse personalizzate collegate ai dati del profilo, a causa del quale l’ordine di visualizzazione nella schermata di configurazione **Details** veniva modificato durante il salvataggio. (CAMP-46312)
* È stato risolto un problema che poteva impedire la visualizzazione dei dati nella generazione di rapporti dinamici a causa di consegne basate su una mappatura di consegna personalizzata.
* È stato corretto un errore che poteva impedire la selezione di una raccolta con un target di risorsa non corretto in un’attività **Query** di un flusso di lavoro.
* È stato risolto un problema che poteva causare la convalida errata di hard bounce da parte del processo InMail.
* È stato corretto un errore che si verificava all’apertura di una schermata di profilo a causa di un errore di collegamento.
* È stato risolto un problema che poteva impedire l’eliminazione di dati GDPR dal flusso di lavoro di pulizia.
* È stato corretto un errore che si verificava quando la configurazione di pianificazione veniva aggiornata manualmente con la tastiera per i parametri di pianificazione della consegna delle e-mail.
* È stato risolto un problema che poteva impedire la modifica di un profilo a causa di parametri non corretti nell’unità organizzativa.
* È stato risolto un problema a causa del quale il campo dell’estensione **Service** restava vuoto e non era possibile impostarlo nelle proprietà **Email**, anche se era impostato nel modello di consegna.
* È stato risolto un problema che poteva causare un tempo di elaborazione delle bozze eccessivamente lungo. (CAMP-45048)
* È stato risolto un problema che poteva impedire l’ordinamento delle colonne nella schermata di panoramica del profilo.
* È stato risolto un problema di generazione delle miniature che poteva verificarsi in Azure nelle varianti e-mail contenenti caratteri cinesi. (CAMP-47152)
* È stata corretta una regressione introdotta in Campaign 20.4 che poteva causare tassi di apertura errati per Gmail a causa del filtraggio degli eventi di tracciamento ricevuti dagli account Gmail. (CAMP-46504)
* È stato risolto un problema che poteva impedire l’importazione di contenuto HTML nel modello di un messaggio transazionale. (CAMP-47318)
* È stato risolto un problema che poteva rallentare la visualizzazione dei rendering nel **report di rendering delle e-mail**. (CAMP-46226)
* È stato risolto un problema che poteva impedire la pubblicazione di risorse personalizzate configurate con un elemento di tipo List nella definizione dello schermo. (CAMP-47217)
* È stato risolto un problema in E-mail Designer che impediva il corretto rendering dei divisori di riga in **Microsoft Outlook** quando questi si trovavano nella parte superiore del contenuto dell’e-mail. (CAMP-46294)
* È stato risolto un problema che causava il blocco della riconciliazione dei KPI con il flusso di lavoro tecnico di **Adobe Analytics**. (CAMP-46576)
* È stato risolto un problema in **E-mail Designer** che impediva la visualizzazione automatica dei frammenti nelle caselle di ricerca durante l’inserimento di blocchi di contenuto. (CAMP-44205)
* È stato risolto un problema in **E-mail Designer** che causava la visualizzazione di caratteri indesiderati nelle e-mail inviate se si utilizzavano emoji nei frammenti. (CAMP-46621)
* È stata corretta una regressione introdotta in 20.4 in **E-mail Designer** che interessava il componente Divider, causando linee più spesse e distorsioni delle immagini nel contenuto. (CAMP-46663)
* È stato risolto un problema che impediva ai pulsanti predefiniti di rimanere centrati quando il messaggio veniva inviato a un indirizzo di Outlook, anche se tali pulsanti erano allineati a destra o a sinistra in **E-mail Designer**. (CAMP-46466)
* È stato risolto un problema che impediva l’aggiornamento dell’elenco dei profili di test durante la ricerca dei profili nell’anteprima di **E-mail Designer**. (CAMP-45265)
* È stato risolto un problema che impediva la visualizzazione dei profili di test personalizzati nell’elenco durante la ricerca dei profili nell’anteprima di **E-mail Designer**. (CAMP-45589)
* È stato risolto un problema che causava la visualizzazione di date sbagliate durante la generazione dei grafici della tendenza dal **report di riepilogo delle consegne**. (CAMP-45521)
