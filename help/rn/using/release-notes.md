---
solution: Campaign Standard
product: campaign
title: Ultima versione
description: Questa pagina presenta dettagli sul contenuto dell’ultima versione Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: 41f2280c72a2f6bee3e4e972fab17a7ac94b966c
workflow-type: tm+mt
source-wordcount: '2610'
ht-degree: 4%

---


# Ultima versione{#latest-release}

[Pianificazione del rilascio](../../rn/using/release-planning.md) | [Versioni del Pannello di controllo Campaign](https://docs.adobe.com/content/help/it-IT/control-panel/using/release-notes.html) | [Aggiornamenti alla documentazione](../../rn/using/documentation-updates.md) | [Note sulla versione precedenti](../../rn/using/release-notes-2020.md) | [Funzioni obsolete](../../rn/using/deprecated-features.md)

## Versione 21.1 - febbraio 2021 {#release-21-1---february-2021}

**Novità**

<table> 
<thead> 
<tr> 
<th> <strong>Servizio di feedback e-mail</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Il servizio EFS (Email Feedback Service) è un servizio scalabile che acquisisce direttamente i commenti dall'MTA avanzato, migliorando così la precisione dei rapporti. Questa funzionalità viene rilasciata come versione beta privata e sarà disponibile progressivamente per tutti i clienti nelle release future.</p>
<ul>
<li>Tutte le categorie di feedback vengono ora acquisite per la generazione di rapporti completi e precisi.</li>
<li>Il calcolo dell'indicatore <b>Consegnato</b> è ora basato sul feedback in tempo reale dall'MTA Avanzato per una maggiore precisione e reattività.</li>
<li>EFS risolve il problema dei ritardi con la generazione di rapporti di rimbalzi software sincroni.</li>
</ul>
<p>Per ulteriori informazioni consulta la <a href="../../sending/using/confirming-the-send.md#email-feedback-service">documentazione dettagliata</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Miglioramenti all'integrazione Adobe Experience Manager</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>L'integrazione con Adobe Experience Manager è stata migliorata: ora è possibile importare contenuti multilingue più facilmente da Adobe Experience Manager. <p>
<p> Adobe Campaign Standard ora rileva automaticamente le varianti di lingua dai contenuti Adobe Experience Manager e consente l'importazione e la creazione di varianti in massa, semplificando in modo significativo il numero di passaggi necessari per consentire a un professionista di creare una campagna multilingue basata sui contenuti Adobe Experience Manager.</p>
<p>Per ulteriori informazioni consulta la <a href="../../integrating/using/creating-multilingual-email-aem.md">documentazione dettagliata</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Interfaccia di Experience Cloud  unificata</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p> barra dell'intestazione Adobe Campaign è stata modificata per unificare e migliorare la vostra esperienza in tutti  prodotti e servizi del Experience Cloud. Queste modifiche sono state progettate per facilitare la vostra vita, tra cui:</p>
<ul>
<li>Passaggio più semplice tra le organizzazioni o a un'altra applicazione.</li>
<li>Guida utente migliorata: inserendo l'Experience League  nel prodotto, i risultati della ricerca includono anche i risultati dei forum della community e altri contenuti video, per un accesso più semplice a più contenuti per trarre il massimo dall'applicazione. È stato inoltre aggiunto un meccanismo di feedback nel menu Aiuto, che semplifica la segnalazione dei problemi o la condivisione delle idee.</li>
<li>Notifiche migliorate - Il menu a discesa Notifiche ora include due schede: uno per le notifiche sui prodotti e uno per gli annunci sui prodotti globali.</li>
</ul>
<p>Per ulteriori informazioni consulta la <a href="../../start/using/interface-description.md#top-bar">documentazione dettagliata</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

**Miglioramenti**

* **L&#39;** integrazione con Microsoft Dynamics 365 è stata migliorata con un&#39;app di integrazione self-service dedicata e un processo di implementazione migliorato. [Ulteriori informazioni](../../integrating/using/d365-acs-get-started.md)

* Sono stati apportati miglioramenti per facilitare la risoluzione dei problemi in caso di problemi con il processo di messaggistica transazionale.  amministratori tecnici di Adobe ora possono utilizzare la traccia su qualsiasi processo senza riavviarla.

* L&#39;elenco **Profili** ora consente di cercare record basati su uno dei seguenti campi: e-mail, nome, cognome o campi personalizzati aggiunti nel filtro avanzato durante l’estensione della risorsa del profilo. Questa funzione è disponibile anche nelle API Campaign Standard mediante il parametro filterType. [Ulteriori informazioni](../../audiences/using/integrated-customer-profile.md)

* Un parametro è stato modificato in base al numero di contenitori in cui è in esecuzione il processo di pooling del database di messaggistica transazionale. Questo consente di distribuire uniformemente il carico tra tutti i contenitori utilizzati e di ottenere prestazioni ottimali.

* È ora disponibile una nuova funzione **GetOption** nelle attività che utilizzano variabili evento dopo aver chiamato un flusso di lavoro con parametri esterni. Consente di restituire il valore di una funzione specificata. [Ulteriori informazioni](../../automating/using/customizing-workflow-external-parameters.md)

* Una nuova opzione consente al Campaign Standard di **verificare la disponibilità di memoria fisica** sul sistema prima di avviare un flusso di lavoro. Se la quantità di memoria è troppo bassa, l&#39;esecuzione del flusso di lavoro verrà posticipata fino a quando la memoria del sistema raggiungerà questa soglia. In questo modo si evita un ulteriore degrado delle prestazioni e si riduce il rischio di un&#39;interruzione. Il flusso di lavoro riprenderà automaticamente una volta terminato il caricamento sul server e aumentato la memoria. Questa opzione è di sola lettura e non può essere modificata. [Ulteriori informazioni](../../automating/using/best-practices-workflows.md#execution)

* È disponibile un nuovo processo in  Adobe Campaign Standard che consente di migrare più facilmente dall&#39;applicazione mobile SDK v4 precedente a **Adobe Experience Platform Mobile SDK**. Consulta [questa pagina](../../administration/using/sdkv4-migration.md).

**Altre modifiche**

* È stato modificato un errore in un avviso durante la preparazione dei messaggi, quando viene raggiunto il limite di 100 download di contenuto per ora di scorrimento. Ora viene visualizzato un avviso quando viene raggiunto il limite, che consente di procedere con la consegna.

* Quando si arricchisce un contenuto di messaggi transazionali, i collegamenti non vengono più recuperati quando si recuperano dati dalla tabella Profilo, riducendo la latenza durante la preparazione dei messaggi ed evitando dati vuoti del profilo a causa di una relazione errata definita con la tabella del profilo.

* La configurazione tecnica dell&#39;istanza è stata ottimizzata per garantire stabilità. (CAMP-45681)

* La gestione delle sessioni è stata migliorata per ottimizzare la memoria. (CAMP-45901, CAMP-46767)

* L&#39;attività **Trasferisci file** genera ora una variabile aggiuntiva (filesCount) che contiene il numero di file caricati o scaricati. (CAMP-45842) [Ulteriori informazioni](../../automating/using/transfer-file.md#output-variables)

* Il connettore SMS ora può inviare più parametri opzionali con ogni messaggio. [Ulteriori informazioni](../../administration/using/sms-protocol.md)

* Gli utenti con il ruolo DATAMODEL ora possono pubblicare le estensioni del registro di consegna. (CAMP-46604)

* È stato reso più chiaro il messaggio di errore visualizzato durante il tentativo di pubblicazione di una risorsa per una risorsa personalizzata non esistente. (CAMP-46893)

* Nell&#39;elenco **Lingua preferita** sono state aggiunte le seguenti lingue: Indonesiano - Indonesia (in-id), inglese - Svezia (en-se), inglese - Asia Pacific (en-ap), inglese - Giappone (en-jp), spagnolo - America latina (es-la). (CAMP-46351)

* Il selettore per la selezione dei profili durante il test di una pagina di destinazione ora utilizza la risorsa profilBase invece del profilo per evitare il timeout.

* Il formato di registro SMPP è stato migliorato.

* Sono stati aggiunti parametri opzionali per le funzioni JS cryptString e deciptString in base alle API di Adobe Campaign Classic.

* Miglioramento dei messaggi di avviso o di errore nei registri di preparazione della consegna.

* Registri di errore migliorati durante il tentativo di connessione  Adobe  Identity Management Service (IMS).

* Ora puoi filtrare ulteriormente le dimensioni **Consegna** e **Campagna** utilizzando la barra di ricerca nella generazione di rapporti dinamici.

* La data di validità dei messaggi SMS transazionali ora può essere definita dal valore impostato per il parametro di scadenza nell&#39;API Messaggi transazionali. (CAMP-36600)

* Nel reporting dinamico, il report **Riepilogo consegna** incorporato mostrava dati non corretti per la metrica della tariffa non sottoscritta. Per risolvere il problema è stata aggiunta una nuova metrica denominata **Unsubscription univoca**. (CAMP-46445)

**Patch**

* È stato risolto un problema che causava un&#39;esecuzione molto lenta delle consegne a causa di determinati processi. Ciò è dovuto a unità errate definite per diversi parametri (ad esempio, millisecondi anziché secondi).

* È stato risolto un problema che si verificava quando Mobile SDK inviava una richiesta di tracciamento aperta basata sulla condizione che deliveryId/MessageID non fosse null. In questo modo si verificherebbero 404 errori per le consegne con tracciamento disabilitato. Nel payload viene ora inviata una variabile aggiuntiva (acsDeliveryTracking) con informazioni sullo stato di tracciamento della consegna. Questa variabile può avere due valori attivi o disattivati a seconda dello stato di tracciamento impostato. [Ulteriori informazioni](../../administration/using/push-tracking.md).

* È stato risolto un problema nei flussi di lavoro che poteva verificarsi quando si copiava e incollava un&#39;attività **Deduplication** che era stata eseguita una volta e che sfruttava una risorsa temporanea. Una volta duplicata, la risorsa dell&#39;attività veniva automaticamente impostata su vuota, causando problemi in altre attività del flusso di lavoro. Una volta incollata, la risorsa dell&#39;attività ora rimarrà la stessa, affinché l&#39;errore possa essere attivato il prima possibile anziché successivamente nel flusso di lavoro. (CAMP-46903)

* È stato risolto un problema che causava un errore di analisi del recapito durante l&#39;invio di profili di targeting dei messaggi push transazionali, introducendo una nuova mappatura [target](../../administration/using/target-mappings-in-campaign.md): **Profilo - Evento in tempo reale per Push** (*mapRtEventAppSubRcp*). I registri di consegna, esclusione e tracciamento per le [notifiche push transazionali per un profilo](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile) verranno ora memorizzati nelle tabelle *wideLogAppSubRcp*, *excludeLogAppSubRcp* e *trackingLogAppSubRcp*.
* È stato risolto un problema che impediva l&#39;esecuzione dei rapporti di consegna quando venivano visualizzate 5000 righe.
* È stato risolto un problema con il test A/B che impediva l&#39;aggiornamento del contenuto della variante B dopo la modifica del modello di consegna. (CAMP-45235)
* È stato risolto un problema che causava il blocco del processo di messaggistica transazionale, impedendo l&#39;invio di messaggi.
* È stato risolto un problema che poteva causare problemi di navigazione dopo aver fatto clic su un collegamento interno (ad esempio, quando si accedeva alla consegna principale da una schermata di riepilogo delle prove).
* È stato risolto un problema che impediva la visualizzazione di tutti i modelli di contenuto  Experience Manager disponibili durante la creazione di una consegna. (CAMP-45990)
* È stato risolto un problema nei flussi di lavoro che poteva impedire la visualizzazione dei messaggi di errore nei registri di consegna dopo l&#39;aggiunta della colonna **Reason** alla scheda dati aggiuntiva. (CAMP-45139)
* È stato risolto un problema che poteva verificarsi quando due chiamate di iscrizione all&#39;app avevano lo stesso ID Marketing Cloud (il valore chiave duplicato viola l&#39;errore del vincolo univoco).
* È stato risolto un problema che poteva causare problemi di lentezza durante il trascinamento di attività in un flusso di lavoro contenente una grande quantità di attività **Query** e **Leggi pubblico**. (CAMP-44511)
* È stato corretto un errore che poteva verificarsi al termine della preparazione dei messaggi transazionali, impedendo il caricamento delle informazioni di reindirizzamento sui server di tracciamento.
* È stato risolto un problema che poteva visualizzare messaggi di errore quando si tentava di aprire modelli di importazione o processi di importazione precedenti dopo aver personalizzato la risorsa del flusso di lavoro. (CAMP-46183)
* È stato risolto un problema che poteva impedire l&#39;esecuzione di un&#39;attività **Leggi pubblico** se configurata con un nome di audience dinamico. (CAMP-46047)
* È stato risolto un problema che impediva la visualizzazione del pulsante **Export list**
* È stato risolto un problema che poteva causare un errore nel flusso di lavoro **Aggregati di reporting**. (CAMP-45979)
* È stato risolto un problema che si verificava durante la creazione di una risorsa personalizzata con una chiave composita personalizzata (testo/data contenuto dinamico).
* È stato risolto un problema che poteva impedire la visualizzazione dei dati di transizione della query. (CAMP-45669)
* Sono stati corretti i problemi di consumo di memoria relativi alla pubblicazione di risorse personalizzate.
* È stato risolto un problema che si verificava durante la configurazione di una consegna da inviare in una data specifica. Se la consegna è stata impostata per essere inviata immediatamente dopo la conferma, la preparazione della consegna non è riuscita e la data specificata inizialmente è stata ancora presa in considerazione. (CAMP-44107)
* È stato risolto un problema che impediva l&#39;apertura dei modelli transazionali. (CAMP-47181)
* È stato risolto un problema nel processo di pubblicazione dei messaggi transazionali che poteva causare la duplicazione di tipologie e regole di tipologia con nomi superiori alle dimensioni stringa consentite. (CAMP-47104)
* È stato risolto un problema nell&#39;attività **API esterna** che si verificava quando un parametro di input restituiva un record che non esisteva. (CAMP-47023)
* È stato risolto un problema che poteva impedire il riconnessione del connettore SMPP.
* È stato risolto un problema che si verificava nell&#39;attività **Trasferimento file** durante il download di un file contenente un punto nel nome. I caratteri successivi al punto sono stati considerati come estensione del file. (CAMP-46624)
* È stato risolto un problema che impediva l&#39;esecuzione del pool di database, causando il blocco dei messaggi transazionali nella coda del router.
* È stato corretto un errore che non impediva l&#39;invio dei log di consegna annullati.
* È stato risolto un problema che poteva causare un errore nel flusso di lavoro quando si utilizzava un&#39;attività **AND-join**. L&#39;attività ha modificato automaticamente il set Primario all&#39;ultima transizione collegata, anche se mostrava visivamente la prima transizione cablata. (CAMP-46900)
* È stato risolto un problema che poteva causare la corretta quarantena degli indirizzi il cui stato veniva impostato in modo non corretto su Valido, rimuovendoli dalla quarantena.
* È stato risolto un problema che impediva la visualizzazione di campi personalizzati contenenti caratteri speciali. (CAMP-46805)
* È stato risolto un problema che poteva impedire la visualizzazione di una visualizzazione dettagliata specifica per un profilo. Ciò si verificava se la risorsa del profilo era stata estesa con campi personalizzati con l&#39;opzione **Aggiungi una sezione di campi personalizzati** abilitata.
* È stato risolto un problema che poteva restituire un codice di errore 500 durante l&#39;invio di eventi transazionali. (CAMP-46811)
* È stato risolto un problema che poteva impedire la ricezione di rapporti pianificati tramite e-mail. (CAMP-46891)
* È stato risolto un problema che si verificava quando si collegava una risorsa personalizzata alla risorsa del profilo con un semplice collegamento 1 cardinalità. Quando si accede a un profilo con un campo di risorse personalizzato vuoto, ora viene visualizzato un messaggio di errore invece di un elenco vuoto.
* È stato risolto un problema che si verificava durante l&#39;utilizzo della sostituzione del profilo in un flusso di lavoro a causa del quale la pagina non riusciva a caricare i profili di consegna quando si selezionava il profilo da sostituire. (CAMP-46522)
* È stato risolto un problema di regressione a causa del quale il flusso di lavoro tecnico **Pulizia del database** tentava di eliminare le tabelle di consegna scadute, causando i seguenti errori: (CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* È stato corretto il seguente errore che si verificava in alcuni casi quando si utilizzava il filtro personalizzato per risorse personalizzate: (CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* È stato risolto un problema per cui **La preparazione delle notifiche push** impiegava troppo tempo per essere completata. Ciò è stato causato da un indice mancante nelle tabelle di lavoro transitorie.
* È stato corretto un errore che si verificava durante l&#39;utilizzo dell&#39;opzione **Dimension per riconciliare** in un&#39;attività **Riconciliazione** in un flusso di lavoro se era già stata definita una relazione tra una risorsa personalizzata e una risorsa profilo.
* È stato risolto un problema che si verificava durante l&#39;aggiunta di collegamenti tramite un&#39;attività **Riconciliazione** o **Arricchimento**. I collegamenti selezionati non venivano visualizzati nella transizione di output.
* È stato risolto un problema che si verificava durante l&#39;utilizzo di un&#39;attività **Segmentazione** con consegne ricorrenti in un flusso di lavoro che causava l&#39;invio della consegna a un&#39;audience errata. (CAMP-46275, CAMP-46470)
* È stato corretto un errore a causa del quale la pubblicazione di risorse personalizzate non riusciva quando si tentava di estendere la risorsa Profilo per creare dimensioni di profilo personalizzate per il reporting dinamico. (CAMP-46266)
* È stato corretto un errore che si verificava durante l&#39;aggiunta di un collegamento a una tabella di importazione dei file. Dopo l&#39;aggiunta di un&#39;attività **Enrichment** all&#39;attività **Importazione file**, il collegamento configurato in precedenza è scomparso. (CAMP-46557)
* È stato risolto un problema che si verificava durante l&#39;utilizzo di risorse personalizzate collegate ai dati Profilo a causa del quale l&#39;ordine di visualizzazione nella schermata di configurazione **Details** veniva modificato durante il salvataggio. (CAMP-46312)
* È stato risolto un problema che poteva impedire la visualizzazione dei dati nei rapporti dinamici a causa di consegne basate su una mappatura di consegna personalizzata.
* È stato corretto un errore che poteva impedire la selezione di una raccolta con una destinazione di risorsa non corretta in un&#39;attività **Query** del flusso di lavoro.
* È stato risolto un problema che poteva causare la convalida errata del processo InMail.
* È stato corretto un errore che si verificava all&#39;apertura di una schermata di profilo a causa di un errore di collegamento.
* È stato risolto un problema che poteva impedire l’eliminazione di dati GDPR dal flusso di lavoro di pulizia.
* È stato corretto un errore che si verificava quando la configurazione di pianificazione veniva aggiornata manualmente con la tastiera nei parametri di pianificazione della distribuzione delle e-mail.
* È stato risolto un problema che poteva impedire la modifica di un profilo a causa di parametri non corretti nell&#39;unità organizzativa.
* È stato risolto un problema che consentiva al campo dell&#39;estensione **Service** di essere vuoto e impossibile da impostare nelle proprietà **Email**, anche se era impostato nel modello di consegna.
* È stato risolto un problema che poteva causare un tempo di elaborazione delle prove. (CAMP-45048)
* È stato risolto un problema che poteva impedire l&#39;ordinamento delle colonne in una schermata di panoramica del profilo.
* È stato risolto un problema di generazione delle miniature che poteva verificarsi in Azure nelle varianti e-mail contenenti caratteri cinesi. (CAMP-47152)
* È stata corretta una regressione introdotta in Campaign 20.4 che potrebbe causare tassi di apertura errati per Gmail a causa del filtraggio degli eventi di tracciamento ricevuti dagli account Gmail. (CAMP-46504)
* È stato risolto un problema che poteva impedire l&#39;importazione di contenuto HTML in un modello di messaggio transazionale. (CAMP-47318)
* È stato risolto un problema che poteva rallentare la visualizzazione dei rendering nel report di rendering **Email**. (CAMP-46226)
* È stato risolto un problema che poteva impedire la pubblicazione di risorse personalizzate configurate con un elemento di tipo Elenco nella definizione dello schermo. (CAMP-47217)
* È stato risolto un problema in Designer e-mail che impediva il corretto rendering dei divisori di riga in **Microsoft Outlook** quando questi si trovavano nella parte superiore del contenuto dell&#39;e-mail. (CAMP-46294)
* È stato risolto un problema che causava il blocco del flusso di lavoro tecnico dei KPI con **Adobe Analytics**. (CAMP-46576)
* È stato risolto un problema in **Email Designer** che impediva la visualizzazione automatica dei frammenti nelle caselle di ricerca durante l&#39;inserimento di blocchi di contenuto. (CAMP-44205)
* È stato risolto un problema in **E-mail Designer** che causava la visualizzazione di caratteri indesiderati nelle e-mail inviate durante l&#39;utilizzo di emoji nei frammenti. (CAMP-46621)
* È stata corretta una regressione introdotta in 20.4 in **Email Designer** che ha avuto un impatto sul componente Divider, causando ulteriori altezze di riga e distorsioni di immagine nel contenuto. (CAMP-46663)
* È stato risolto un problema che impediva ai pulsanti predefiniti di rimanere centrati quando il messaggio veniva inviato a una cassetta postale di Outlook, anche se tali pulsanti erano allineati a destra o a sinistra in **Email Designer**. (CAMP-46466)
* È stato risolto un problema che impediva l&#39;aggiornamento dell&#39;elenco dei profili di test durante la ricerca dei profili nell&#39;anteprima **Email Designer**. (CAMP-45265)
* È stato risolto un problema che impediva la visualizzazione dei profili di test personalizzati nell&#39;elenco durante la ricerca dei profili nell&#39;anteprima di **Email Designer**. (CAMP-45589)
* È stato risolto un problema che causava la visualizzazione di date non corrispondenti durante la generazione di elementi grafici di tendenza dal report di riepilogo della distribuzione **a1/>.** (CAMP-45521)
