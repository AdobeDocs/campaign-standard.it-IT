---
title: Note sulla versione 2015-2016
description: In questa pagina sono elencate tutte le versioni 2015 e 2016 di Adobe Campaign Standard.
page-status-flag: never-activated
uuid: d5a0f6cc-0bed-46cf-8dff-1717fb624f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: a3ce6b80-1858-49d1-8880-3543181127f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d1ec5dddcf4c1aa3fe6338d35b381986ba32a28d

---


# Note sulla versione 2015-2016{#release-notes}

Stai cercando una versione specifica di Adobe Campaign Standard per il periodo 2015-2016?

Ogni versione include nuove funzioni e patch. Fate clic su una versione per visualizzarne il contenuto.

Visualizza gli ultimi aggiornamenti [della](../../rn/using/documentation-updates.md) documentazione per Adobe Campaign Standard. Per una versione più recente, consulta questa [pagina](../../rn/using/release-notes.md).

## Rilascio 16.11 - novembre 2016 {#release-16-11---november-2016}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Regole di esclusione della realizzazione<br /> </td> 
   <td> Un elenco di soppressione globale crittografato viene ora gestito nell'istanza di recapito per evitare di essere inserito in blacklist a causa di attività dannose, in particolare l'utilizzo di uno Spamtrap.<br /> Per ogni consegna di e-mail, due regole di tipologia predefinite confrontano gli indirizzi e-mail dei destinatari con gli indirizzi o i nomi di dominio vietati contenuti in questo elenco. In presenza di una corrispondenza, il destinatario viene escluso dalla popolazione di destinazione.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/filtering-rules.md#default-deliverability-exclusion-rules"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ottimizzazione generale<br /> </td> 
   <td> Questo aggiornamento include numerose modifiche e patch che risolvono i problemi riscontrati dai nostri clienti. Anche le prestazioni globali della piattaforma sono state ottimizzate. <br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* Sono stati risolti diversi problemi di sicurezza.
* Sono stati risolti diversi problemi relativi ai campi vuoti o duplicati nell’API REST.
* Ora puoi creare messaggi SMS e notifiche push direttamente dalla home page dell&#39;applicazione.

_E-mail e messaggi SMS_

* È stato risolto un problema che impediva agli utenti di caricare file zip nell&#39;editor del contenuto.
* È stato risolto un problema che impediva l&#39;apertura di una prova dopo l&#39;invio.
* È stato risolto un problema che causava la visualizzazione di un messaggio di errore durante l&#39;accesso al **[!UICONTROL Hot Clicks]**report in un&#39;e-mail di test A/B.
* È stato risolto un problema che impediva l&#39;applicazione delle modifiche apportate utilizzando la **[!UICONTROL Show source]**modalità.
* È stato risolto un problema che poteva impedire l&#39;importazione di file predittivi del modello xml della linea oggetto.
* È ora disponibile una nuova schermata dedicata all&#39;importazione di dati per il modello di formazione della linea oggetto in **[!UICONTROL Administration > Channels > Emails > Predictive Subject Line]**.
* È stato risolto un problema che consentiva agli utenti non amministratori di modificare le maschere autorizzate nella schermata di configurazione dell&#39;e-mail.

_Notifiche push_

* È stato risolto un problema che impediva la visualizzazione dei registri e dei registri eventi di invio per i destinatari dopo l&#39;invio di una notifica push tramite il **[!UICONTROL Send push on profiles]**modello.
* È stato risolto un problema che poteva impedire la creazione di nuove applicazioni mobili.

_Flussi di lavoro_

* È stato risolto un problema di prestazioni che si verificava durante l&#39;utilizzo dell&#39; **[!UICONTROL Subscription]**attività.
* È stato risolto un problema che impediva il funzionamento di un flusso di lavoro quando il suo nome interno conteneva uno spazio.

_Integrazioni_

* È stato risolto un problema che poteva causare un errore durante l&#39;utilizzo dell&#39;opzione **Immagine condivisa da Adobe Marketing Cloud** in un messaggio e-mail.

_Risorse personalizzate_

* Anteprima del registro API migliorata tra due pubblicazioni di campi API estesi.
* È stato risolto un problema che impediva l&#39;eliminazione di una risorsa personalizzata prima della pubblicazione.
* È stato risolto un problema che impediva l&#39;estensione dei profili e l&#39;impostazione delle chiavi di identificazione con un campo dinamico.
* È stato risolto un problema che poteva verificarsi quando si aggiungevano collegamenti in una risorsa personalizzata.

## Rilascio 16.10 - ottobre 2016 {#release-16-10---october-2016}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Riga oggetto predittivo e-mail<br /> </td> 
   <td> Quando modificate un’e-mail, una nuova opzione consente di provare righe oggetto diverse e ottenere una stima del tasso di apertura prima di inviarla. Ciò è possibile grazie alla formazione del proprio modello in base ai dati di consegna passati o tramite un modello predefinito specifico per il settore. Questa funzione è disponibile per i messaggi e-mail e per i database che contengono solo contenuti in lingua inglese. <br /> Per ulteriori informazioni sull'attivazione e l'utilizzo di tale funzionalità, consultare la documentazione <a href="../../designing/using/subject-line.md#predictive-subject-line"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Messaggi transazionali SMS<br /> </td> 
   <td> Il canale SMS è stato aggiunto alle funzionalità di messaggistica transazionali di Adobe Campaign. Per i messaggi transazionali sono ora supportati due canali: email e SMS.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/configuring-transactional-messaging.md#creating-an-event"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Messaggio di follow-up per i messaggi transazionali<br /> </td> 
   <td> È ora possibile creare un flusso di lavoro per il targeting di un evento. Questo significa che puoi inviare un messaggio di follow-up ai clienti che in precedenza avevano ricevuto un messaggio transazionale. Potete filtrare la destinazione in base al tipo di evento, ai registri di trasmissione e ai registri di tracciamento. Nel messaggio di follow-up, potrete sfruttare il contenuto dell'evento (payload). <br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/follow-up-messages.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> API profili e servizi estesi<br /> </td> 
   <td> Ora puoi esporre i campi estesi nell'API Profilo e Servizi. Il meccanismo di pubblicazione consente alle API di mappare i campi estesi delle risorse personalizzate Profili o Servizi. A questo scopo è stato aggiunto il ruolo <strong>Datamodel</strong> . Questo nuovo ruolo consente all'utente di configurare un set di amministratori che avranno accesso al modello dati.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension"></a>dettagliata.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* Sono stati risolti diversi problemi di sicurezza.

_E-mail e messaggi SMS_

* La schermata di configurazione dell&#39;account esterno SMS ( **[!UICONTROL Administration > Channels > SMS > SMS accounts]**) è stata migliorata. Diversi parametri sono stati aggiunti nella**[!UICONTROL SMSC specifics]** sezione per supportare i codici di errore nel campo &quot;Testo&quot;.

_Notifiche push_

* È stato risolto un problema che impediva la visualizzazione dei filtri predefiniti durante la modifica del pubblico di una notifica push basata sul modello **[!UICONTROL Send via push notification]**(mobileApp).
* La schermata di configurazione dell&#39;applicazione mobile ( **[!UICONTROL Administration > Channels > Push Notification > Mobile applications]**) ora mostra un messaggio per indicare che la piattaforma iOS o Android è stata creata correttamente.

_Pagine di destinazione_

* Sono stati risolti dei problemi che impedivano l&#39;invio di e-mail di conferma all&#39;invio di un modulo della pagina di destinazione.

_Audience e query_

* Sono stati risolti diversi problemi che si verificavano durante la selezione di un profilo nell&#39;editor di query.

_Messaggi transazionali_

* È stato corretto un errore che impediva l&#39;annullamento della pubblicazione di un modello transazionale.
* È stato risolto un problema che causava la visualizzazione degli eventi di attivazione nell&#39;elenco degli eventi.

_Integrazioni_

* È stato risolto un problema che impediva l&#39;utilizzo di un&#39;audience condivisa in una consegna dopo l&#39;aggiornamento di tale audience.
* È stato risolto un problema che impediva l&#39;utilizzo di una risorsa condivisa ( **[!UICONTROL Image shared from Adobe Marketing Cloud]**opzione) in una pagina di destinazione.
* Risolti i problemi che si verificavano durante la modifica di un&#39;audience condivisa importata da Adobe Audience Manager.

## Rilascio 16.9 - settembre 2016 {#release-16-9---september-2016}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Attivatori di osservazioni<br /> </td> 
   <td> L'integrazione tra <span class="uicontrol">Triggers</span> del servizio di base e Adobe Campaign consente di inviare e-mail personalizzate ai clienti come reazione a comportamenti specifici tracciati sul sito Web da Adobe Analytics (entro 15 minuti).<br /> In Adobe Marketing Cloud, potete definire i diversi attivatori, ossia i comportamenti dei clienti che desiderate monitorare, come tutti i clienti che hanno abbandonato il carrello o la loro forma, rimosso un prodotto dal carrello o persino i clienti la cui sessione è scaduta. Quando crei un attivatore, definisci la condizione del trigger e i dati che verranno inviati nell'evento (caricamento) ad Adobe Campaign. <br /> In Adobe Campaign, selezionate l'attivatore precedentemente creato, arricchite i dati dell'evento con i dati del datamart e definite un modello di messaggio transazionale collegato a tale attivatore. Ad esempio, quando un cliente abbandona il carrello, un evento viene inviato ad Adobe Campaign, che può quindi sfruttare questo evento tramite un messaggio e-mail di remarketing inviato al cliente entro 15 minuti.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Messaggi transazionali: Pausa/Annulla pubblicazione<br /> </td> 
   <td> Ora potete sospendere la pubblicazione di un modello transazionale mentre ne aggiornate il contenuto. I messaggi corrispondenti non vengono più inviati, ma vengono memorizzati nel database. Durante la ripresa, i messaggi in coda vengono elaborati e inviati se non sono scaduti.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication"></a>dettagliata.<br /> Ora potete anche annullare la pubblicazione di eventi e modelli transazionali. I messaggi corrispondenti non vengono più inviati e non vengono memorizzati nel database.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Multibranding<br /> </td> 
   <td> I client con più marchi ora possono gestirli nella stessa istanza. Il marchio è una funzione gestita dall'amministratore dell'istanza di Adobe Campaign che consente di configurare centralmente tutti i parametri relativi a un marchio all'interno di Adobe Campaign. Questo include elementi come il logo a parametri più tecnici come tracciamento di URL, Web Analytics, URL del server, nome di dominio, ecc.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/branding.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Anteprima della progettazione e-mail reattiva<br /> </td> 
   <td> Questa funzione consente di verificare la reattività dell’e-mail su diversi tipi di dispositivi. Nell’anteprima dell’e-mail, è stata aggiunta una griglia per testare l’e-mail su diverse dimensioni di schermo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifiche push<br /> </td> 
   <td> È stato aggiunto un nuovo canale per consentire agli esperti di marketing di inviare notifiche push personalizzate e segmentate su dispositivi mobili iOS e Android. I messaggi possono essere inviati tramite una singola consegna o tramite un'attività di flusso di lavoro. La compatibilità con i messaggi transazionali sarà disponibile nelle versioni future. Questo canale sfrutta l'SDK del servizio core Mobile (disponibile <a href="https://marketing.adobe.com/developer/gallery/marketing-cloud-mobile-libraries">qui</a>).<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-push-notifications.md"></a>dettagliata.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* Questa versione introduce nuove funzionalità di filtraggio e ricerca negli elenchi di interfaccia. Questa nuova funzione è disponibile, ad esempio, nei registri (consegna, tracciamento), nei servizi (iscrizione, cronologia iscrizioni), nei tipi di pubblico e nelle transizioni dei flussi di lavoro.
* Sono stati risolti diversi problemi di visualizzazione relativi al numero di punti di contatto in un profilo cliente.
* Sono stati corretti diversi problemi di tipologia.

_E-mail e messaggi SMS_

* È stato corretto un errore che consentiva la modifica di prove errate. Ora sono di sola lettura.
* È stato corretto un problema a causa del quale un destinatario veniva incluso in blacklist quando un SMS era troppo lungo o presentava problemi di codifica.

_Risorse personalizzate_

* È stato corretto un errore che impediva la visualizzazione di tutti i risultati quando si utilizzavano i filtri avanzati di una risorsa personalizzata.

_Messaggi transazionali_

* Un prefisso viene ora aggiunto automaticamente all&#39;identificatore di una nuova definizione di evento.
* L&#39;icona che rappresenta i messaggi transazionali nell&#39;interfaccia è stata modificata.

_Integrazioni_

* È stato corretto un errore di visualizzazione che si verificava quando un&#39;immagine ad alta risoluzione veniva inserita tramite l&#39;opzione **Immagine dinamica da Adobe Target** .
* Risolto un errore che consentiva di salvare un&#39;audience condivisa anche se l&#39;ID di destinazione non era impostato in Origine dati AMC.

## Rilascio 16.7 - Luglio 2016 {#release-16-7---july-2016}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Messaggi transazionali avanzati<br /> </td> 
   <td> Ora puoi collegare i modelli transazionali al database di Adobe Campaign per recuperare le informazioni che consentono di arricchire il contenuto dei messaggi transazionali.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL dinamici per le immagini<br /> </td> 
   <td> Questa nuova funzionalità consente di personalizzare un’origine immagine inserendo blocchi di contenuto e testo dinamico a scopo di tracciamento e personalizzazione.<br /> Diventa quindi possibile, tra le altre cose, sfruttare le funzionalità dei contenuti multimediali dinamici di AEM Assets (S7) immettendo parametri negli URL delle immagini. Ad esempio, potete inviare una e-mail con immagini personalizzate in cui si legge "Ciao Alexandre, scopri le ultime notizie sugli eventi in programma a Parigi!" o "Ciao Frank, ricevi le ultime notizie sugli eventi in programma a New York!".<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../designing/using/personalization.md#personalizing-urls"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrazione con il servizio di base Persone<br /> </td> 
   <td> Gli ID <strong>dichiarati</strong> di Adobe Marketing Cloud ora sono coperti dall'integrazione tra Adobe Campaign e il servizio core Persone (Profili e pubblico).<br /><strong> Questo significa che puoi importare segmenti ed esportare tipi di pubblico costituiti da </strong>Visitor<strong>ID o </strong>Dichiared<br />ID.Per ulteriori informazioni, consulta la documentazione <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Registri di consegna<br /> </td> 
   <td> I registri MTA (server di consegna) ora mostrano la cronologia completa di ciascun messaggio, in particolare tutti i tentativi di consegna e i relativi stati di errore, e questo non ha alcun impatto sulle prestazioni dell'applicazione.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* È stato corretto un errore che poteva causare la visualizzazione di campi irrilevanti al posto dei campi da completare. Ciò si verifica dopo che l&#39;operatore di confronto è stato modificato più volte durante la modifica di una condizione in una query.
* È stato corretto il comportamento dell&#39;opzione **[!UICONTROL The last X days/months/quarters/years]**durante la definizione di una condizione di filtro relativa per un campo data. Il periodo calcolato è ora un periodo scorrevole relativo alla data e all&#39;ora del server e non basato sul calendario.

_Flussi di lavoro_

* Risolto un errore che restituiva un elenco errato di valori nella schermata per la selezione della dimensione di targeting nelle proprietà di un&#39; **[!UICONTROL Query]**attività.
* È stato corretto un errore che causava la selezione dell&#39;operatore **Exists** quando si aggiungeva un aggregato medio o di conteggio su un elemento raccolta in un&#39; **[!UICONTROL Query]**attività.

_Modifica del contenuto_

* È stato corretto un errore che poteva causare problemi di visualizzazione (progettazione reattiva) durante l&#39;importazione di contenuto HTML: gli attributi di stile non vengono più riscritti quando il contenuto viene aperto per la prima volta dopo essere stato importato.
* È stato corretto un errore di non blocco causato dall&#39;aggiunta di una condizione in una variante di contenuto dinamica.
* È stato corretto un errore causato dall’aggiunta di una casella di controllo nel contenuto di una pagina di destinazione. La casella di controllo era inutilizzabile.
* È stato corretto un errore che si verificava durante l&#39;eliminazione del testo in un blocco se il cursore era posizionato all&#39;inizio del blocco in questione.

_Messaggi transazionali_

* Quando integrate un sito Web, ora potete definire una data di scadenza per un determinato evento. Una volta trascorsa questa data, il messaggio corrispondente all&#39;evento non può più essere inviato.

## Rilascio 16.6 - Giugno 2016 {#release-16-6---june-2016}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> API Profili e servizi<br /> </td> 
   <td> L'API Adobe Campaign <span class="uicontrol">Profili e servizi</span> è disponibile nel portale <a href="https://www.adobe.io/products/campaign">adobe.io</a> . Questo consente di aggiornare, aggiungere ed eliminare i profili di Adobe Campaign e di sottoscrivere o annullare l'iscrizione ai servizi tramite chiamate REST.<br /> Per ulteriori informazioni, consultate la descrizione <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">dettagliata dell'API</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* Le descrizioni comandi sono ora disattivate sui dispositivi mobili per garantire che le informazioni visualizzate sullo schermo siano di facile lettura.
* È stato corretto un errore che impediva all&#39;utente di scorrere il contenuto di alcune aree sullo schermo dell&#39;iPad.
* Sono stati corretti diversi errori di compatibilità rilevati durante la modifica del contenuto in Internet Explorer 11.
* È stato corretto un errore che impediva l&#39;accesso ai registri dettagliati in caso di mancata riuscita dell&#39;importazione dei dati per la prima volta.
* È stato corretto un errore che poteva impedire il salvataggio di un filtro di intervallo.
* È stato corretto un errore che impediva la visualizzazione degli elementi di una risorsa durante la configurazione della modalità di visualizzazione di un elenco.
* È stato corretto un errore in Query Editor Explorer. I risultati restituiti dal campo di ricerca sono stati conservati nella cronologia delle ricerche e sono stati visualizzati per ogni nuova ricerca.

_E-mail e messaggi SMS_

* È stato corretto un errore che impediva il recupero delle informazioni collegate ai rimbalzi nei registri di consegna.
* È stato corretto un errore che impediva l&#39;accesso al contesto in un blocco di contenuto dinamico di un messaggio transazionale.
* È stato corretto un errore che impediva la definizione di un collegamento URL sul testo dinamico nel contenuto di un&#39;e-mail.
* È stata corretta la visualizzazione della barra superiore della procedura guidata per la creazione della consegna.
* La chiave primaria di una consegna non può più essere utilizzata come campo di personalizzazione.

_Flussi di lavoro_

* Le transizioni tra due attività di un flusso di lavoro ora mostrano il numero di elementi calcolati e trasferiti da un&#39;attività all&#39;altra.
* I campi non compatibili ora vengono nascosti quando in un&#39; **[!UICONTROL Query]**attività vengono aggiunti dati aggiuntivi.
* La finestra di definizione aggregata, visualizzata quando si aggiungono dati aggiuntivi, è stata migliorata per offrire solo opzioni compatibili con i dati in uso (ad esempio: il calcolo di una media è possibile solo per i dati numerici).
* L&#39;avvio o il riavvio di un flusso di lavoro tecnico integrato ora può essere eseguito solo da un utente con diritti di amministrazione.

_Pagine di destinazione_

* È stato corretto un errore che poteva troncare le chiavi di codifica AES a 32 bit nelle proprietà di una pagina di destinazione.
* È stato corretto un errore che impediva la corretta visualizzazione dell&#39;editor query durante la definizione di una condizione di visibilità o durante l&#39;aggiunta di contenuto dinamico a una pagina di destinazione.

_Risorse personalizzate_

* L&#39; **[!UICONTROL Switch to parameters]**opzione ora è nascosta quando si definisce un filtro correlato alle sottoscrizioni di un profilo a un servizio.
* È stato corretto un errore che poteva verificarsi quando un collegamento di tipo 0-1 veniva configurato da una risorsa personalizzata.
* È stato corretto un errore che, se pertinente, poteva impedire la modifica del valore **predefinito** Costante definito quando si aggiungeva un campo **Data e ora** in una risorsa personalizzata.

## Rilascio 16.5 - maggio 2016 {#release-16-5---may-2016}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Filtri predefiniti<br /> </td> 
   <td> Gli amministratori possono ora creare filtri avanzati che vengono visualizzati nell'editor di query sotto forma di regole preconfigurate. La selezione di questi filtri consente agli utenti di sviluppare più facilmente configurazioni complesse in un'interfaccia semplificata, ad esempio per la definizione di un pubblico.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../developing/using/configuring-filter-definition.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: Servizi iscrizione<br /> </td> 
   <td> Una nuova attività Servizi <span class="uicontrol"></span> iscrizione offre la possibilità di iscriversi a un servizio a più profili o di annullarne l’iscrizione da un servizio con un’unica azione.<br /> Questa attività può essere utilizzata dopo aver eseguito un targeting o importato un file con dati identificati.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/subscription-services.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: arricchimento dei dati<br /> </td> 
   <td> La scheda Dati <span class="uicontrol"></span> aggiuntivi è ora disponibile nelle attività di tipo <span class="uicontrol">Query</span> . Questa funzionalità consente di arricchire i dati di destinazione della query e di trasferire tali dati alle seguenti attività del flusso di lavoro, dove è possibile sfruttarli.<br /> Dopo aver aggiunto dati aggiuntivi, puoi applicare un livello di filtro aggiuntivo ai dati di destinazione iniziale creando condizioni basate sui dati aggiuntivi definiti.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/query.md#enriching-data"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Guida contestuale<br /> </td> 
   <td> Una funzione di aiuto contestuale è ora disponibile nelle diverse schermate di Adobe Campaign. Ciò significa che, con un solo clic, è possibile accedere direttamente alla documentazione sulla funzionalità attualmente in uso. Per visualizzare la guida contestuale, fare clic su '?' nell’angolo superiore destro dello schermo, come illustrato nell’esempio seguente.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* Varie interfacce Nuove funzionalità conformi agli standard di Marketing Cloud.
* Standardizzazione dei diversi tipi di elenco a discesa.

_E-mail e messaggi SMS_

* È stato corretto un errore che impediva l&#39;invio di e-mail in caso fosse specificata la maschera dell&#39;indirizzo di errore.
* Il protocollo TLS ora è supportato per la consegna delle e-mail. Una nuova colonna nella gestione MX consente di definire il comportamento TLS desiderato per ciascun dominio.
* L&#39;interfaccia SMS è stata migliorata.

_Flussi di lavoro_

* Interfaccia del flusso di lavoro Nuove funzionalità.
* È stato corretto un errore che si verificava durante la visualizzazione delle azioni rapide.
* È stato corretto un errore che poteva causare un errore in un flusso di lavoro quando si utilizzava un&#39;attività di **[!UICONTROL Segmentation]**tipo contenente un collegamento 1-N.
* È stato corretto un errore che impediva l&#39;apertura delle transizioni di un flusso di lavoro su un dispositivo ibrido.
* È stato corretto un errore che impediva la visualizzazione del pulsante Pausa all&#39;avvio di un flusso di lavoro per la prima volta.

_Editor di contenuti_

* L&#39;editor contenuti ora consente di personalizzare qualsiasi URL contenuto in un&#39;e-mail o in una pagina di destinazione. Fare riferimento alla documentazione [](../../designing/using/personalization.md#personalizing-urls)dettagliata.
* È stato corretto un errore che poteva causare la perdita di immagini aggiunte nella procedura guidata di creazione della distribuzione e il relativo contenuto veniva successivamente modificato.

_Risorse personalizzate_

* È stato corretto un errore che si verificava durante l&#39;aggiunta di un collegamento personalizzato di tipo 1-N nella schermata di configurazione di una risorsa personalizzata.
* Migliorata la visualizzazione della barra di avanzamento durante la preparazione e la pubblicazione di risorse personalizzate.
* È stato corretto un errore che si verificava durante la visualizzazione dell&#39;elenco di collegamenti di una risorsa personalizzata.

_Messaggi transazionali_

* La facilità di utilizzo dell&#39;interfaccia e le prestazioni e la robustezza del motore di messaggi transazionali sono stati ottimizzati.
* Ora è possibile sospendere temporaneamente la pubblicazione di un modello di messaggio transazionale. Per ulteriori informazioni, consulta la documentazione [](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication)dettagliata.
* È stato corretto un errore che poteva causare l&#39;aggiunta di un blocco di contenuto con una dimensione di targeting incompatibile in un modello di messaggio transazionale.
* È stato corretto un errore che impediva la visualizzazione dell&#39;anteprima API in una schermata di configurazione dell&#39;evento.

_Audience e query_

* Diverse patch relative all&#39;utilizzo delle date nell&#39;editor di query. Fare riferimento alla documentazione [](../../automating/using/editing-queries.md#creating-queries)dettagliata.

_Amministrazione_

* È stato risolto un errore relativo al nome del gruppo di sicurezza &quot;Utenti standard&quot; che impediva agli utenti di effettuare l&#39;accesso.

## Rilascio 16.3 - marzo 2016 {#release-16-3---march-2016}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Interfaccia e navigazione<br /> </td> 
   <td> L'interfaccia di Adobe Campaign è stata migliorata per rendere la navigazione e le operazioni semplici e intuitive.<br /> Ora potete spostarvi dalla barra superiore dell’applicazione. I menu avanzati sono accessibili selezionando il logo di <strong>Adobe Campaign</strong> .<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../start/using/interface-description.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: Salva audience<br /> </td> 
   <td> Una nuova opzione, <span class="uicontrol">Crea e quindi aggiorna un'audience</span> , è ora disponibile nell'attività <span class="uicontrol">Salva audience</span> . Questa opzione consente di inserire manualmente un'etichetta di pubblico. Se l'etichetta immessa corrisponde a un'audience esistente, verrà aggiornata. Se l'audience non esiste, verrà creata.<br /> Inoltre, l'audience verrà aggiornata ogni volta che viene eseguito (di nuovo) il flusso di lavoro.<br /> Puoi sempre selezionare la modalità di aggiornamento del pubblico: completa il pubblico con nuovi dati o sostituisci l'intero insieme dei dati del pubblico ad ogni esecuzione.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/save-audience.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: Segmentazione<br /> </td> 
   <td> L'attività <span class="uicontrol">Segmentazione</span> ora consente all'utente di segmentare i dati di una risorsa temporanea. Ad esempio: i dati di un file importato.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/segmentation.md"></a>dettagliata.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* È stato corretto un errore di visualizzazione che si verificava durante l&#39;ordinamento di un elenco: la freccia che indica l&#39;ordinamento di una colonna può essere utilizzata solo per alcuni tipi di dati.
* Risolto un errore che limitava il numero di elementi visualizzati in un menu a discesa quando una regola veniva aggiunta in una query.

_E-mail e messaggi SMS_

* È stato corretto un errore che poteva impedire l’accesso al report di rendering e-mail.
* La fase di preparazione dell&#39;invio per un messaggio ora restituisce un errore se l&#39;indirizzo del mittente non è specificato.

_Flussi di lavoro_

* Alcune opzioni di formattazione del file erano visibili, ma non tenevano conto quando veniva estratto un file in formato CSV. Queste opzioni ora non sono più visibili.
* È stato risolto un errore che si verificava quando l&#39; **[!UICONTROL Delete the source files after transfer]**opzione era selezionata per il trasferimento di un file di**[!UICONTROL SFTP]** tipo.
* È stato corretto un errore che poteva impedire la visualizzazione del contatore e dell&#39;anteprima dei **[!UICONTROL Query]**dati dopo l&#39;aggiornamento della pagina.
* È stato corretto un errore causato dall&#39;apertura di determinate transizioni in un flusso di lavoro, in particolare dopo un&#39;attività di consegna o una query in cui le dimensioni di targeting e filtro erano diverse.
* È stato corretto un errore che impediva l&#39;inserimento di un campo di personalizzazione in un&#39;attività di distribuzione di un flusso di lavoro se il flusso di lavoro non veniva salvato dopo l&#39;aggiunta dell&#39;attività.
* È stato corretto un errore che impediva la visualizzazione della dimensione di targeting della transizione in uscita di un&#39;attività di consegna delle e-mail.

_Pagine di destinazione_

* È stato corretto un errore che impediva il corretto funzionamento dei campi di personalizzazione in un blocco di contenuto localizzabile in una pagina di destinazione.

_Risorse personalizzate_

* È stato corretto un errore che impediva di eseguire una ricerca su una risorsa personalizzata se l&#39; **[!UICONTROL Add search fields]**opzione della definizione della schermata delle risorse era selezionata e se erano stati selezionati più campi nella**[!UICONTROL Filter zone composition]** .

## Rilascio 16.2 - febbraio 2016 {#release-16-2---february-2016}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Test A/B per le e-mail<br /> </td> 
   <td> È ora possibile eseguire test A/B sul contenuto, l'oggetto o il nome del mittente delle e-mail. Questa nuova funzionalità può sottoporre a test fino a tre varianti di un elemento.<br /> Quando create un messaggio e-mail da uno dei nuovi modelli specifici per i test A/B, un nuovo passaggio nella procedura guidata di creazione consente di definire i parametri del test.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/designing-an-a-b-test-email.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Gestione del marchio<br /> </td> 
   <td> Ora puoi definire uno o più marchi per immettere centralmente i parametri che influiscono sull'identità di un marchio. Adobe Campaign consente di creare questi marchi e di collegarli ai modelli delle pagine di destinazione o di consegna.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/branding.md#assigning-a-brand-to-an-email"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: Query incrementale<br /> </td> 
   <td> Una nuova attività del flusso di lavoro, Query <span class="uicontrol"></span> incrementale, consente di eseguire una query che, a ogni esecuzione, esegue solo il targeting dei nuovi risultati. I risultati delle esecuzioni precedenti vengono automaticamente esclusi. Collegato a un'attività <span class="uicontrol">Scheduler</span> , puoi definire la frequenza di esecuzione della query <span class="uicontrol"></span> Incremental.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/incremental-query.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Messaggi transazionali<br /> </td> 
   <td> La facilità di utilizzo dell'interfaccia dei messaggi transazionali è stata migliorata. La gestione di tutti i processi aziendali collegati ai messaggi transazionali è attualmente centralizzata nel menu <span class="uicontrol">piani</span> di marketing &gt; Messaggi <span class="uicontrol"></span> transazionali. È stata migliorata anche la configurazione dell’evento. Gli eventi vengono ora gestiti in modo indipendente dalle risorse personalizzate.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-transactional-messaging.md"></a>dettagliata.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* Sono stati corretti diversi errori di visualizzazione in report, elenchi e query.
* Sono stati corretti diversi errori di compatibilità e visualizzazione sui dispositivi mobili.

_E-mail e messaggi SMS_

* È stato corretto un errore che poteva impedire la visualizzazione del pulsante utilizzato per inserire campi di personalizzazione durante la creazione di un messaggio (e-mail o SMS).
* È stato corretto un errore che poteva impedire la corretta trasmissione dei messaggi SMS inviati tramite Mblox.

_Audience e query_

* È stato corretto un errore di conteggio che poteva essere causato dall&#39;aggiunta di una condizione aggiuntiva in una query, dopo aver modificato la dimensione di filtro.
* È stato corretto un errore che poteva causare un&#39;impaginazione non corretta durante l&#39;anteprima dei risultati di una query.

_Modifica del contenuto_

* È stato corretto un errore che poteva impedire che la configurazione del contenuto dinamico venisse presa in considerazione correttamente quando si utilizzava un&#39;enumerazione personalizzata.

_Flussi di lavoro_

* È stato corretto un errore che poteva impedire l&#39;esecuzione di qualsiasi azione in un flusso di lavoro in presenza di una riga vuota nella **[!UICONTROL Fields to update]**scheda di un&#39;**[!UICONTROL Update data]** attività.
* È stato corretto un errore che impediva l&#39;importazione di dati contenenti informazioni di unità geografica/organizzativa.
* È stato corretto un errore causato dall&#39;aggiunta di un **[!UICONTROL Change axis]**tipo di**[!UICONTROL Exclusion]** regola.
* È stato corretto un errore che poteva causare la creazione di un segmento aggiuntivo indesiderato durante la manipolazione di una transizione in uscita di un&#39; **[!UICONTROL Segmentation]**attività.
* È stato corretto un errore causato dal caricamento di un file in un modello di workflow.
* È stato corretto un errore che poteva impedire l&#39;utilizzo degli spazi come separatori di colonna in un&#39; **[!UICONTROL Load file]**attività.

_Risorse personalizzate_

* È stato corretto un errore che impediva la rielaborazione dello stato di una risorsa personalizzata dopo l&#39;importazione di un pacchetto, se la risorsa era stata pubblicata al momento dell&#39;esportazione.

_Pacchetti_

* È stato corretto un errore che impediva l&#39;esportazione di un pacchetto contenente un flusso di lavoro.
* È stato corretto un errore che poteva impedire la selezione di diversi elementi della stessa risorsa.

## Rilascio 16.1 - gennaio 2016 {#release-16-1---january-2016}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Rapporti<br /> </td> 
   <td> Sono stati aggiunti i seguenti rapporti e-mail specifici: <span class="uicontrol">Reclami</span> , <span class="uicontrol">Aperture</span> e <span class="uicontrol">Annulla iscrizioni</span> .<br /> Sono stati migliorati i seguenti rapporti: Riepilogo <span class="uicontrol">della</span> consegna , <span class="uicontrol">Sintetico</span> rimbalzo , Velocità di <span class="uicontrol">consegna</span> , e indicatori <span class="uicontrol">di</span> tracciamento .<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../reporting/using/defining-the-report-period.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Modifica query<br /> </td> 
   <td> L'editor di query è stato migliorato e ora è possibile eseguire la scansione dei collegamenti di tipo <strong>1-N</strong> .<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/editing-queries.md#creating-queries"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Personalizzazione dei contenuti<br /> </td> 
   <td> Per quanto riguarda la modifica delle e-mail o della pagina di destinazione, l'interfaccia di input per le condizioni di visualizzazione dei blocchi di contenuto è stata migliorata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: definizione delle colonne durante l'importazione<br /> </td> 
   <td> L'attività <span class="uicontrol">Carica file</span> ora consente di configurare nel dettaglio le colonne di un file importato: tipo di dati previsto, formato data e ora, elaborazione da applicare in caso di un valore vuoto o di un errore e mappatura del valore.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/load-file.md#column-format"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mapping delle codifiche SMS<br /> </td> 
   <td> È ora possibile definire mappature delle codifiche di messaggi SMS personalizzati per i fornitori che non utilizzano la codifica standard. Un amministratore può eseguire la configurazione di mappature personalizzate e definire l'ordine in cui si dovrebbe tenere conto di tali mappature.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/configuring-sms-channel.md#smsc-specifics"></a>dettagliata.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* È stata migliorata la compatibilità con Internet Explorer e Chrome per dispositivi ibridi/touchscreen.
* Risolto un errore che poteva causare la perdita di tutti i dati immessi per un nuovo profilo utente/profilo/test se l&#39;indirizzo e-mail indicato conteneva errori di sintassi.

_E-mail e messaggi SMS_

* È stato corretto un errore che poteva impedire la generazione della miniatura del contenuto nella schermata di anteprima dell’e-mail.
* È stato corretto un errore che poteva impedire la visualizzazione del contenuto non elaborato di un messaggio (e-mail o SMS) nella schermata di anteprima del messaggio.

_Audience e query_

* Risolto un errore che poteva impedire la creazione di un pubblico di tipo **Query** nella risorsa **Servizio** .
* È stato corretto un errore che poteva impedire la corretta visualizzazione dell&#39;elenco delle funzioni durante la modifica di una condizione di una query in modalità avanzata.
* È stato corretto un errore che poteva impedire la creazione di un pubblico di tipo **Query** se conteneva criteri basati sulle raccolte.
* È stato corretto un errore che poteva impedire la creazione di query contenenti filtri per i KPI di consegna.
* È stato corretto un errore che poteva impedire l&#39;anteprima del contenuto di un&#39;audience creata da un flusso di lavoro.

_Risorse personalizzate_

* È stato corretto un errore che poteva causare un arresto anomalo del server se una risorsa personalizzata conteneva un campo con un valore dinamico predefinito.
* È stato corretto un errore causato dallo spostamento, quindi dall&#39;eliminazione di un elemento nella **[!UICONTROL Detail screen configuration]**sezione durante la definizione delle schermate di una risorsa personalizzata.
* È stato corretto un errore che si verificava quando era stato definito un valore predefinito per un elenco di **numeri interi** che non includeva **0** nell&#39;intervallo di valori possibili.
* È stato corretto un errore che poteva impedire l&#39;aggiunta di un elemento nella configurazione della schermata di dettaglio di una risorsa personalizzata dopo una reinizializzazione.

_Flussi di lavoro_

* È stato corretto un errore che poteva causare la visualizzazione dei log di tutte le attività di un flusso di lavoro invece di visualizzare solo quelle dell&#39;attività selezionata.
* Risolto un errore nell&#39; **[!UICONTROL Scheduler]**attività. L&#39;**[!UICONTROL Day of the month]** opzione non è stata presa in considerazione correttamente e sostituita da **[!UICONTROL Week day]**.
* È stato corretto un errore che poteva impedire a un&#39; **[!UICONTROL Scheduler]**attività di funzionare correttamente con la modalità di scadenza impostata su**[!UICONTROL After a certain number of iterations]** .
* Risolto un errore che si verificava durante l&#39;esportazione di dati tramite un&#39; **[!UICONTROL Extract file]**attività. Il numero di righe presenti nel file di esportazione era inferiore al numero di elementi esportati.
* È stato corretto un errore che poteva impedire la selezione di un file in un&#39; **[!UICONTROL Load file]**attività.
* È stato corretto un errore che impediva l&#39;eliminazione dei campi che venivano aggiornati in un&#39; **[!UICONTROL Update data]**attività.
* È stato corretto un errore che impediva il salvataggio delle modifiche apportate a un flusso di lavoro dopo l’apertura dei registri di esecuzione del flusso di lavoro.
* Risolto un errore che causava l&#39;esecuzione di un&#39; **[!UICONTROL Load file]**attività due volte se era configurata per l&#39;utilizzo del file dalla sua transizione in ingresso e questo file era stato caricato utilizzando un&#39;**[!UICONTROL Transfer file]** attività.
* Risolto un errore che poteva impedire ad alcune entità temporanee di essere elaborate correttamente da un&#39;attività **Esclusione** .
* È stato corretto un errore che poteva impedire a un&#39; **[!UICONTROL Query]**attività di essere eseguita correttamente se la dimensione di targeting e la dimensione di filtro configurate nell&#39;attività erano diverse.
* È stato corretto un errore relativo alla denominazione automatica delle transizioni in uscita aggiunte a un&#39; **[!UICONTROL Fork]**attività che poteva impedire il salvataggio del flusso di lavoro.

_Modifica del contenuto_

* È stato corretto un errore che poteva causare la visualizzazione non desiderata di un&#39;icona o di una barra di ricerca durante la modifica del contenuto.

_Pagine di destinazione_

* È stato corretto un errore che impediva l&#39;importazione di una pagina di destinazione tramite l&#39;importazione di un pacchetto.

_Messaggi transazionali_

* È ora possibile specificare un indirizzo IP attendibile nei parametri di sicurezza dell&#39;operatore agente push di Message Center.
* È stato corretto un errore che poteva impedire la creazione di un nuovo tipo di evento.

## Rilascio 15.11 - novembre 2015 {#release-15-11---november-2015}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Canale SMS<br /> </td> 
   <td> Ora puoi inviare messaggi SMS con Adobe Campaign.<br /> Come per le e-mail, puoi creare nuove consegne di SMS dalle campagne e dall'elenco delle attività di marketing. Puoi anche creare messaggi SMS singoli e ricorrenti da un flusso di lavoro.<br /> Queste consegne mediante SMS si basano su modelli che puoi configurare dall’elenco dei modelli di consegna. È disponibile un modello predefinito.<br /> Queste consegne di SMS utilizzano il protocollo SMPP 3.4, utilizzato dalla maggior parte dei router SMS.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-sms-messages.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Esplorazione delle transizioni<br /> </td> 
   <td> È ora possibile esaminare i dati e la relativa struttura nell'ultima transizione di un flusso di lavoro. Questo consente di verificare che i processi applicati da ogni attività corrispondano alle proprie esigenze.<br /> </td> 
  </tr> 
  <tr> 
   <td> Pre-elaborazione e post-elaborazione dei file nei flussi di lavoro<br /> </td> 
   <td> È ora possibile eseguire un'ulteriore elaborazione su un file di dati durante l'importazione o l'esportazione tramite le attività <span class="uicontrol">Carica file</span> ed <span class="uicontrol">Estrai file</span> .<br /> Per impostazione predefinita, in queste attività potete decomprimere e comprimere un file in formato GZIP.<br /> Per ulteriori informazioni, consultare la documentazione relativa alle attività <a href="../../automating/using/load-file.md">Carica file</a> ed <a href="../../automating/using/extract-file.md">Estrai file</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> Rapporti sulla distribuzione<br /> </td> 
   <td> È ora disponibile un rapporto di rendering per e-mail. Questo rapporto consente di visualizzare i diversi rendering di un messaggio in base al supporto e al servizio messaggi utilizzato per leggerlo.<br /> Il riepilogo del rapporto mostra anche il numero di messaggi ricevuti, messaggi spam, messaggi non ricevuti e messaggi in attesa di ricezione.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../sending/using/email-rendering.md#email-rendering-report-description"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Gestione pacchetti<br /> </td> 
   <td> È ora possibile importare ed esportare le immagini nei pacchetti.<br /> </td> 
  </tr> 
  <tr> 
   <td> Azioni rapide<br /> </td> 
   <td> Alcune azioni vengono visualizzate quando si passa il puntatore del mouse sopra o dopo aver selezionato un elemento in un elenco o in un flusso di lavoro. Alcune di queste azioni sono ora visualizzate come icone intorno agli elementi interessati per facilitare l'accesso. Queste azioni rapide possono essere utilizzate per duplicare un elemento, eliminarlo, mostrare i dettagli, ecc.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* È stato corretto un errore che poteva impedire l&#39;accesso ai parametri generali di un&#39;istanza da un account amministratore.
* **I dati mobili** vengono ora presi correttamente in considerazione nelle risorse personalizzate.
* È stato corretto un errore di visualizzazione nell&#39;elenco delle importazioni semplificate eseguite, causato dalla modifica dello stato del modello corrispondente.

_Pagine di destinazione_

* Sono stati corretti alcuni elementi dei modelli delle pagine di destinazione che potevano essere visualizzati in modo non corretto in francese sulle istanze inglesi.

_Audiences_

* È stato corretto un errore che poteva impedire ai tipi di pubblico importati da Adobe Marketing Cloud di essere visualizzati nell&#39;elenco dei tipi di pubblico.
* È stato corretto un errore che poteva forzare la distinzione tra maiuscole e minuscole durante la definizione di una query.
* È stato corretto un errore che poteva impedire ai tipi di pubblico di essere filtrati durante la definizione di una query.
* È stato corretto un errore che poteva impedire la cancellazione di un&#39;azione in un&#39;audience.

_Flussi di lavoro_

* È stato corretto un errore che poteva impedire la configurazione manuale dei campi che dovevano essere aggiornati in un&#39; **[!UICONTROL Update data]**attività.
* È stato corretto un errore che poteva causare il caricamento infinito dell&#39; **[!UICONTROL Query]**attività all&#39;apertura se il flusso di lavoro non era stato salvato dopo l&#39;inserimento dell&#39;attività nel diagramma.
* È stato corretto un errore che poteva causare l&#39;interruzione del server durante il conteggio o l&#39;anteprima di un&#39;audience selezionata da un **[!UICONTROL Query]**flusso di lavoro.
* È stato corretto un errore non critico che poteva essere visualizzato all&#39;apertura di un&#39;attività in un flusso di lavoro.
* È stato corretto un errore che impediva a un&#39; **[!UICONTROL Scheduler]**attività di essere configurata per eseguire un flusso di lavoro più volte al giorno.
* È stato corretto un errore che poteva causare la visualizzazione di campi nei quali non era possibile eseguire una query in determinate attività del flusso di lavoro.
* È stato corretto un errore che poteva impedire all&#39;utente di individuare i KPI aggiunti da una consegna **[!UICONTROL Query]**in uscita nella transizione in uscita.
* È stato corretto un errore che poteva impedire la creazione di un pubblico di file dopo l&#39;importazione di un file in un flusso di lavoro.
* È stato corretto un errore che poteva impedire l&#39;aggiornamento dei dati sui profili in caso di utilizzo del campo **location/address3** della risorsa.
* È stato corretto un errore che impediva la duplicazione di raccolte eterogenee di attività in un flusso di lavoro.
* È stato corretto un errore che impediva la visualizzazione dell&#39;SQL, consentendo la diagnosi degli errori per una consegna periodica in un flusso di lavoro.

_Editor di contenuti_

* È stato corretto un errore che impediva la ricerca nel codice sorgente di una pagina di destinazione o di un messaggio e-mail.

_Pacchetti_

* Sono stati corretti diversi errori che potevano impedire l&#39;esportazione di determinati tipi di elementi nei pacchetti (in particolare pagine di destinazione, flussi di lavoro).
* È stato corretto un errore che causava la visualizzazione dell&#39;etichetta di importazione del pacchetto precedente se l&#39;etichetta era stata modificata.
* È stato corretto un errore che poteva causare la visualizzazione di risorse incompatibili nell&#39;elenco delle risorse esportabili.

## Rilascio 15.10 - ottobre 2015 {#release-15-10---october-2015-}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Flussi di lavoro: Attività di deduplicazione<br /> </td> 
   <td> Nei flussi di lavoro è ora disponibile una nuova attività dedicata alla deduplicazione dei dati. Questa attività consente di filtrare eventuali duplicati nelle destinazioni in base ai criteri scelti.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/deduplication.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: Diagramma migliorato<br /> </td> 
   <td> Nell'area di lavoro del flusso di lavoro, è ora possibile utilizzare diverse scelte rapide da tastiera per selezionare, aprire ed eliminare le attività.<br /> È stato inoltre migliorato l'allineamento delle attività e consente di organizzare meglio i flussi di lavoro visivamente.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/workflow-interface.md#workspace"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: Estrai attività file<br /> </td> 
   <td> La data e l'ora dell'esportazione vengono ora aggiunte automaticamente alle etichette dei file esportati tramite un'attività file <span class="uicontrol"></span> Extract. In questo modo i file generati sono univoci.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importazione semplificata dei dati<br /> </td> 
   <td> Il nome del modello da cui è stata eseguita l'importazione semplificata ora è visibile per impostazione predefinita nell'elenco di importazione e nei dettagli di ogni importazione.<br /> </td> 
  </tr> 
  <tr> 
   <td> Risorse personalizzate<br /> </td> 
   <td> Miglioramento e possibilità estese per la gestione e la definizione di collegamenti per risorse personalizzate.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_E-mail_

* È stato corretto un errore che impediva il corretto funzionamento di un collegamento di annullamento iscrizione da una pagina mirror.
* È stato corretto un errore che poteva impedire la corretta visualizzazione dell’etichetta di consegna e-mail nella pagina di modifica dell’e-mail.
* È stato corretto un errore che poteva impedire la selezione di un **[!UICONTROL Routing]**account esterno in un modello di consegna duplicato.

_Audiences_

* È stato risolto un errore che si verificava durante un conteggio di audience se nella query era stato utilizzato un collegamento da 1 a 1.
* È stato corretto un errore che poteva impedire la selezione di un profilo nel pubblico di destinazione di una e-mail di consegna.

_Flussi di lavoro_

* È stato corretto un errore che poteva causare problemi di visualizzazione durante la configurazione di una distribuzione e-mail in un flusso di lavoro.
* È stato corretto un errore che poteva impedire il corretto funzionamento dell&#39; **[!UICONTROL Load file]**attività. Viene quindi visualizzato un messaggio di errore vuoto.
* È stato corretto un errore che poteva impedire il corretto funzionamento dell&#39; **[!UICONTROL Transfer file]**attività. I diritti di accesso non sono sempre stati presi in considerazione correttamente.
* È stato corretto un errore che poteva impedire l’esportazione di un file se il flusso di lavoro conteneva un **[!UICONTROL Recurring email]**.
* È stato corretto un errore che poteva impedire la creazione di un&#39;e-mail di consegna in un flusso di lavoro o impedire che l&#39;oggetto e il contenuto definito venissero presi in considerazione.
* È stato corretto un errore che poteva impedire la selezione di una chiave di riconciliazione in un&#39;attività durante la configurazione del flusso di lavoro di un modello di importazione semplificato. **[!UICONTROL Update data]**
* È stato corretto un errore che poteva impedire il salvataggio di un flusso di lavoro dopo l&#39;eliminazione di un&#39;attività.

_Piattaforma_

* È stato corretto un errore che poteva impedire la creazione di un nuovo elemento se una risorsa personalizzata conteneva un collegamento al tipo di risorsa dell&#39;elemento.
* È stato corretto un errore che poteva causare un ritardo di 15 minuti per la scrittura di alcuni registri.
* È stato corretto un errore che poteva impedire la visualizzazione dell&#39;elenco delle attività di marketing in base alle **[!UICONTROL Date]**colonne o**[!UICONTROL Indicators]** .

_Pagine di destinazione_

* È stato corretto un errore che si verificava quando si selezionava un profilo di prova per visualizzare in anteprima una pagina di destinazione.

_Messaggi transazionali_

* È stato corretto un errore che poteva causare l&#39;arresto anomalo dell&#39;applicazione dopo l&#39;eliminazione di un evento in un profilo di prova.

_Rapporti_

* Risolto un errore che poteva causare l&#39;invio di dati non corretti per i report **[!UICONTROL deliveryThroughputReport]**e**[!UICONTROL deliveryTrackingReport]** .

_Editor di contenuti_

* È stato corretto un errore di gestione tag HTML che si verificava durante l&#39;elaborazione dei blocchi di contenuto dinamici.

## Rilascio 15.8 - Agosto 2015 {#release-15-8---august-2015}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Importazione semplificata dei dati<br /> </td> 
   <td> È ora possibile importare i dati in modo semplificato.<br /> Gli utenti possono semplicemente selezionare un modello predefinito da un amministratore e caricare il file contenente i dati da importare. Un flusso di lavoro definito nel modello viene eseguito in modo trasparente per l'utente, che può accedere ai dettagli del risultato dell'importazione e a un registro di eventuali errori.<br /> I dati di questi file possono essere inseriti nel database o utilizzati come mezzo per creare direttamente un'audience.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/about-data-import-and-export.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creazione di programmi e campagne<br /> </td> 
   <td> Ora, le campagne e i programmi sono configurati in modo che il giorno in cui vengono creati venga utilizzato automaticamente come data di inizio.<br /> La data di fine è configurata in base alla data di inizio, ad esempio:<br /> 
    <ul> 
     <li> D+186 per i programmi </li> 
     <li> D+61 per le campagne </li> 
    </ul> Per ulteriori informazioni, consulta la documentazione <a href="../../start/using/programs-and-campaigns.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> E-mail<br /> </td> 
   <td> L'elenco degli URL tracciati ora è di sola lettura.<br /> </td> 
  </tr> 
  <tr> 
   <td> Messaggi transazionali<br /> </td> 
   <td> Ora puoi gestire messaggi transazionali personalizzati per eventi quali modifiche alla password o conferme dopo la creazione di un account.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-transactional-messaging.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Risorse personalizzate<br /> </td> 
   <td> Sono state aggiunte diverse funzionalità, ad esempio: estensione di un profilo di test, gestione dello stato ed eliminazione di risorse.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../developing/using/resource-statuses.md"></a>dettagliata.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Display_

* È stato corretto un errore che poteva causare la sovrapposizione di due campi nell&#39;editor query in Safari.

_Editor di contenuti_

* È stato corretto un errore che impediva l&#39;utilizzo dei caratteri &#39;&lt;&#39;, &#39;&amp;&#39; e &#39;>&#39; in un oggetto e-mail.

_E-mail_

* È stato corretto un errore che impediva all&#39;utente di aggiungere testo dopo il testo dinamico.

_Elenchi_

* È stato corretto un errore che impediva la corretta esportazione della colonna **Messaggio** nei registri di esecuzione del flusso di lavoro.

_Profili e audience_

* È stato corretto un errore che causava una doppia conferma di quando un elemento veniva duplicato o eliminato. **Dispositivi ibridi che utilizzano solo** Internet Explorer 11.

_Flussi di lavoro_

* È stato corretto un errore che poteva impedire l’invio di e-mail da un flusso di lavoro.
* Risolto un errore che poteva impedire l&#39;esecuzione di un flusso di lavoro quando il nome del file di rifiuto non era specificato in un&#39; **[!UICONTROL Load file]**attività.
* Risolto un errore che poteva impedire l&#39;esecuzione di un flusso di lavoro quando **[!UICONTROL Execution frequency]**di un&#39;**[!UICONTROL Schedule]** attività era impostata su **[!UICONTROL Daily]**.

_Piattaforma_

* È stato corretto un errore che impediva la generazione delle miniature in un ambiente con bilanciamento del carico.

## Rilascio 15.7 - Luglio 2015 {#release-15-7---july-2015}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Esportazione di elenchi<br /> </td> 
   <td> Ora potete esportare i contenuti dagli elenchi in un file in formato CSV. Questa funzione è disponibile in tutte le schermate con una modalità <strong>Elenco</strong> (ad esempio: profilo).<br /> I dati esportati sono i dati visualizzati nelle colonne al momento dell’esportazione. Modificando l’elenco, potete quindi selezionare i dati da esportare.<br /> Per ulteriori informazioni sull’utilizzo di questa funzionalità, consulta la documentazione <a href="../../automating/using/exporting-lists.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrazione con Adobe Profili e pubblico<br /> </td> 
   <td> Ora puoi condividere i tipi di pubblico tra Adobe Campaign e le tue altre soluzioni Adobe Marketing Cloud:<br /> 
    <ul> 
     <li> Esporta: quando salvate un'audience composta da profili in un flusso di lavoro, una nuova opzione <span class="uicontrol">Condividi in Adobe Marketing Cloud</span> consente di aggiungere profili a un'audience esistente o di creare una nuova audience. </li> 
     <li> Importa: creando un pubblico di tipo <strong>Elenco</strong> dalla schermata Gestione dell'audience, una nuova opzione consente di identificarlo come pubblico <span class="uicontrol">di</span> Adobe Marketing Cloud. Puoi quindi selezionare un'audience condivisa esistente da importare in Adobe Campaign. </li> 
    </ul> Per ulteriori informazioni sulla configurazione e l’utilizzo di questa funzionalità, consulta la documentazione <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Contenuti dinamici<br /> </td> 
   <td> L'interfaccia del contenuto dinamico è stata migliorata. Le frecce ora sembrano consentire la navigazione tra i diversi contenuti dinamici, direttamente nel corpo dell'e-mail.<br /> Per ulteriori informazioni sull’utilizzo di questa funzionalità, consulta la documentazione <a href="../../designing/using/personalization.md#defining-dynamic-content-in-an-email"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Testo dinamico<br /> </td> 
   <td> Dall’editor dei contenuti di un messaggio e-mail, potete ora definire il testo dinamico:<br /> 
    <ul> 
     <li> in un oggetto e-mail, </li> 
     <li> in modalità HTML, </li> 
     <li> o in modalità Testo. </li> 
    </ul>  Per ulteriori informazioni sull’utilizzo di questa funzionalità, consulta la documentazione <a href="../../channels/using/defining-dynamic-text.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Programmi e campagne - Rapporti<br /> </td> 
   <td> L'interfaccia e la grafica dei rapporti sono stati migliorati.<br /> Per ulteriori informazioni sull’utilizzo di questa funzionalità, consulta la documentazione <a href="../../reporting/using/defining-the-report-period.md"></a>dettagliata.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Installazione_

* I nomi delle istanze di Adobe Campaign ora sono limitati a 32 caratteri.

_Flussi di lavoro_

* È stato corretto un errore che poteva impedire il targeting di una risorsa &#39;consegna&#39; durante la modifica di una query in un flusso di lavoro.
* È stato corretto un errore che poteva impedire l&#39;elaborazione di alcune risorse collegate durante la modifica di una query in un flusso di lavoro.
* È stato corretto un errore che poteva impedire la modifica di un&#39;attività di consegna **** ricorrente se il flusso di lavoro era già stato eseguito.

_E-mail_

* È stato corretto un errore che impediva di controllare gli errori di sintassi JavaScript prima di inviare un messaggio e-mail quando veniva aggiunto un contenuto dinamico tramite l&#39;editor di espressioni.

_Pagine di destinazione_

* È stato corretto un errore che impediva la modifica di una pagina di destinazione da un tablet.

_Servizio di base risorse_

* Quando si seleziona una risorsa condivisa da un&#39;e-mail o una pagina di destinazione in fase di modifica, l&#39;elenco delle risorse disponibili ora viene filtrato per Adobe Campaign.

## Rilascio 15.6 - Giugno 2015 {#release-15-6---june-2015}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Flussi di lavoro: Attività di riconciliazione<br /> </td> 
   <td> Una nuova attività di <strong>riconciliazione</strong> collega i dati non identificati (ad esempio, dopo l'importazione di un file) con le risorse esistenti all'interno di un flusso di lavoro.<br /> Questa attività è essenzialmente utilizzata a scopo di gestione dei dati. Risponde a due diversi casi di utilizzo:<br /> 
    <ul> 
     <li> <strong>Aggiunta di relazioni</strong>: una scheda <strong>Relazioni</strong> consente di aggiungere collegamenti tra dati in entrata e diverse altre dimensioni del database di Adobe Campaign. </li> 
     <li> <strong>Identificazione</strong>dei dati: una scheda <strong>Identificazione</strong> consente di associare semplicemente i dati in entrata alle colonne di una dimensione esistente nel database Adobe Campaign. Quando esce dall'attività, i dati vengono identificati come appartenenti alla dimensione specificata. </li> 
    </ul> Fare riferimento alla documentazione <a href="../../automating/using/reconciliation.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: Estrai attività file<br /> </td> 
   <td> Una nuova attività di file <strong></strong> Extract consente di esportare dati dal database Adobe Campaign sotto forma di file esterno da un flusso di lavoro. <br /> Limitazione: attualmente non è possibile utilizzare nomi dinamici per i file di output.<br /> Fare riferimento alla documentazione <a href="../../automating/using/extract-file.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: Attività di pianificazione<br /> </td> 
   <td> Widget migliorato che consente di selezionare il tempo di esecuzione dell'attività <strong>Scheduler</strong> in un flusso di lavoro.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: Trasferisci attività file<br /> </td> 
   <td> SFTP è ora supportato.<br /> </td> 
  </tr> 
  <tr> 
   <td> Risorse personalizzate<br /> </td> 
   <td> Il menu <span class="uicontrol">Sviluppo</span> ora consente agli utenti con diritti di amministratore di arricchire i modelli di dati forniti mediante la creazione di risorse personalizzate, come le tabelle di acquisto o di prodotto. <br /> È inoltre possibile estendere le risorse pronte all'uso per aggiungere nuovi campi.<br /> È inoltre possibile configurare la navigazione nelle schermate corrispondenti a risorse personalizzate nuove o estese.<br /> Fare riferimento alla documentazione <a href="../../developing/using/data-model-concepts.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Profili di prova<br /> </td> 
   <td> È ora possibile selezionare il nome <strong></strong> centrale e il <strong>titolo</strong> dei profili di test al momento della configurazione dell'elenco dei profili di test.<br /> </td> 
  </tr> 
  <tr> 
   <td> Editor di contenuto: Contenuto dinamico<br /> </td> 
   <td> È possibile definire contenuti diversi che verranno visualizzati in modo dinamico all'utente in base alle condizioni definite tramite l'editor di espressioni.<br /> Fare riferimento alla documentazione <a href="../../designing/using/personalization.md#defining-dynamic-content-in-an-email"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> E-mail<br /> </td> 
   <td> Una colonna Profili <strong>di</strong> test è ora disponibile nei registri di invio del messaggio e-mail.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Elenchi_

* Se si elimina un elemento da un elenco, l&#39;elenco viene aggiornato automaticamente.
* È stato corretto un errore che impediva la selezione di elementi da un elenco contenente una sola colonna.
* È stato risolto un errore che causava la perdita delle modifiche applicate alla visualizzazione di un elenco dopo l&#39;aggiornamento della pagina.
* Ora è possibile visualizzare sia il secondo nome che il titolo dei profili di test nell&#39;elenco dei profili di test.
* È stato corretto un errore che si verificava selezionando una casella di controllo in un elenco con Mozilla Firefox.

_Audiences_

* È stato corretto un errore che impediva l&#39;utilizzo del **[!UICONTROL Add]**pulsante nell&#39;interfaccia dell&#39;audience.

_E-mail_

* È stato corretto un errore JavaScript che impediva al pulsante di anteprima di essere utilizzato due volte in una riga durante la modifica di un&#39;e-mail.
* È stato corretto un errore che impediva l&#39;utilizzo dei **[!UICONTROL Edit properties]**pulsanti e dei**[!UICONTROL Show proofs]** pulsanti sui tablet Microsoft Surface Pro3 con Internet Explorer 11.
* È stato corretto un errore che poteva impedire la visualizzazione dei log di invio di un&#39;e-mail.

_Pagine di destinazione_

* È stato corretto un errore che impediva l&#39;utilizzo del blocco di contenuto del logo **** marchio durante la modifica del contenuto in una pagina di destinazione.
* È stato corretto un errore che impediva la visualizzazione delle pagine di destinazione nell&#39;elenco delle attività di marketing se per la pagina di destinazione erano specificate date di validità.

_Flussi di lavoro_

* È stato corretto un errore che impediva il corretto funzionamento di un segmento in modalità di gruppo durante la configurazione di un&#39;attività di **segmentazione** .
* Risolto un errore che impediva la selezione di una transizione dopo aver configurato un&#39;attività **di segmentazione** .
* Risolto un errore che impediva l&#39;eliminazione di una transizione dopo aver configurato un&#39;attività **di segmentazione** .
* È stato corretto un errore che impediva il conteggio e l&#39;anteprima delle popolazioni all&#39;interno di un&#39;attività di **segmentazione** .
* È stato corretto un errore che impediva l&#39;eliminazione effettiva di un&#39;e-mail ricorrente.
* È stato risolto un errore che causava la visualizzazione dei dati di un&#39;attività del file **di** trasferimento eliminata in una nuova attività del file **di** trasferimento.
* È stato corretto un errore che impediva di tenere correttamente in considerazione una regola di esclusione all&#39;interno di un&#39;attività **Esclusione** .
* È stato corretto un errore che si verificava durante l&#39;eliminazione di un&#39;attività di consegna e-mail in un flusso di lavoro. Le consegne corrispondenti vengono ora rimosse dall&#39;elenco delle attività di marketing.

_Navigazione_

* È ora possibile utilizzare il tasto di tabulazione per navigare correttamente tra i campi della stessa pagina.

## Rilascio 15.4 - Aprile 2015 {#release-15-4---april-2015}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Esportazioni di pacchetti / Importazioni di pacchetti<br /> </td> 
   <td> Il menu <strong>Distribuzione</strong> ora consente agli utenti con diritti di amministratore di scambiare risorse tra diverse istanze di Adobe Campaign esportando e importando pacchetti.<br /> Fare riferimento alla documentazione <a href="../../automating/using/managing-packages.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rapporti<br /> </td> 
   <td> È ora possibile accedere a tutti i rapporti (tranne il rapporto <strong>Hot Click</strong> ) da un programma. Tali rapporti sono:<br /> 
    <ul> 
     <li> Distribuzione dei programmi </li> 
     <li> Indicatori di tracciamento del programma </li> 
     <li> Suddivisione dei programmi per dominio </li> 
     <li> Programmi non consegnabili e rimbalzi </li> 
     <li> URL del programma e flussi di clic </li> 
    </ul> Tali rapporti possono essere filtrati in un determinato periodo (ad esempio tre mesi, sei mesi, ecc.). È inoltre possibile filtrare i rapporti delle campagne.<br /> Fare riferimento alla documentazione <a href="../../reporting/using/about-dynamic-reports.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: Attività di distribuzione <strong></strong> tramite e-mail<br /> </td> 
   <td> È stata migliorata l'attività di distribuzione <strong></strong> delle e-mail nei flussi di lavoro. È ora possibile trovare e-mail, e-mail ricorrenti e informazioni dettagliate sulle esecuzioni ricorrenti di e-mail dall'elenco delle attività di marketing delle applicazioni.<br /> Fare riferimento alla documentazione <a href="../../automating/using/email-delivery.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: Attività di <strong>segmentazione</strong><br /> </td> 
   <td> L'attività <strong>Segmentazione</strong> è ora disponibile nei flussi di lavoro. Questa attività consente di creare uno o più segmenti e di collegare ad essi un codice di segmento da una popolazione calcolata da attività posizionate a monte nello stesso flusso di lavoro. Da questa attività, i segmenti possono essere elaborati in una singola transizione o in diverse transizioni. Ora sono disponibili opzioni per filtrare la popolazione e limitare le dimensioni di ciascun segmento per ottimizzare la personalizzazione. Ad esempio, potete selezionare in modo casuale i profili che corrispondono a criteri specifici.<br /> Fare riferimento alla documentazione <a href="../../automating/using/segmentation.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrazioni: Servizio di base <strong>Assets</strong><br /> </td> 
   <td> Ora puoi utilizzare le risorse condivise tramite il servizio <strong>core</strong> Assets nell'e-mail e nei contenuti delle pagine di destinazione. Puoi gestire le risorse condivise direttamente da Adobe Marketing Cloud.<br /> Fare riferimento alla documentazione <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrazioni: <strong>Adobe Target</strong><br /> </td> 
   <td> Ora puoi inserire nelle e-mail di Adobe Campaign immagini calcolate in modo dinamico da <strong>Adobe Target</strong> . Questo consente di offrire diverse versioni della stessa e-mail personalizzando il contenuto in base ai criteri definiti nei segmenti di Adobe Target.<br /> Fare riferimento alla documentazione <a href="../../integrating/using/about-campaign-target-integration.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor: Selettore <strong>blocchi</strong><br /> </td> 
   <td> Quando si seleziona un blocco nell'editor di contenuti HTML, viene visualizzata una breadcrumb nella parte inferiore dell'area di modifica. Questo consente di navigare e selezionare facilmente diversi elementi.<br /> Fare riferimento alla documentazione <a href="../../channels/using/designing-a-landing-page.md#managing-landing-page-structure-and-style"></a>dettagliata.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Rilascio 15.3 - marzo 2015 {#release-15-3---march-2015}

**Nuove funzionalità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Rapporti<br /> </td> 
   <td> Ora è possibile accedere ai report direttamente da un programma o una campagna. Il rapporto di riepilogo <strong>sulla</strong> consegna è stato aggiunto a livello di programma.<br /> Fare riferimento alla documentazione <a href="../../reporting/using/delivery-summary.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aggiornare dati<br /> </td> 
   <td> Nei flussi di lavoro, l'attività <strong>Aggiorna dati</strong> disponibile dispone di una nuova opzione, che consente di collegare automaticamente i campi dati in entrata con i campi di uno schema dell'applicazione. Questo facilita il processo di selezione per l'aggiornamento dei campi.<br /> Fare riferimento alla documentazione <a href="../../automating/using/update-data.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recapito e-mail<br /> </td> 
   <td> Nei flussi di lavoro, ora è possibile accedere alle opzioni avanzate dell'attività di consegna <strong></strong> e-mail tramite un pulsante specifico nella barra delle azioni. Questo pulsante è disponibile solo se è selezionata un'attività di consegna <strong></strong> e-mail. Il vantaggio principale è che consente di aggiungere una transizione in uscita all'attività e di modificare il nome dell'attività così come viene visualizzata nel flusso di lavoro.<br /> Fare riferimento alla documentazione <a href="../../automating/using/email-delivery.md"></a>dettagliata.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* È stato corretto un errore che impediva la visualizzazione del destinatario durante la creazione di una consegna.
* È stato corretto un errore che impediva l&#39;utilizzo di un&#39;audience basata su una condizione &quot;Destinatari che hanno aperto&quot;.
* È stato corretto un errore che impediva l&#39;eliminazione di un profilo vuoto.
* È stato corretto un errore che si verificava durante l&#39;anteprima di una consegna.
* È stato corretto un errore che impediva la duplicazione di un&#39;attività di marketing.
* È stato corretto un errore che si verificava durante l&#39;eliminazione di una campagna.

