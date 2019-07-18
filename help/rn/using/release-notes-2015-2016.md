---
title: Note sulla versione 2015-2016
seo-title: Note sulla versione 2015-2016
description: Note sulla versione 2015-2016
seo-description: In questa pagina sono elencate tutte le versioni 2015 e 2016 di Adobe Campaign Standard.
page-status-flag: never-activated
uuid: d 5 a 0 f 6 cc -0 bed -46 cf -8 dff -1717 fb 624 f 8 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: riferimento
topic-tags: campaign-standard-release
discoiquuid: a 3 ce 6 b 80-1858-49 d 1-8880-3543181127 f 4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Release Notes 2015-2016{#release-notes}

Stai cercando una versione 2015-2016 di Adobe Campaign Standard?

Ogni rilascio viene fornito con nuove funzionalità e patch. Fate clic su una versione per visualizzarne il contenuto.

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 16.11 - November 2016 {#release-16-11---november-2016}

### New capabilities {#new-capabilities}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Deliverability exclusion rules<br /> </td> 
   <td> Un elenco di soppressione globale crittografato viene ora gestito nell'istanza di prestabilità per evitare di essere inserito in blacklist a causa di attività dannose, in particolare l'utilizzo di un'abbondanza.<br /> Per ogni consegna di e-mail, due regole di tipologie predefinite confrontano gli indirizzi e-mail del destinatario con gli indirizzi vietati o i nomi di dominio contenuti in questo elenco. In caso di corrispondenza, tale destinatario è escluso dalla popolazione di destinazione.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/filtering-rules.md#default-deliverability-exclusion-rules">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> General optimization<br /> </td> 
   <td> Questo aggiornamento include numerose modifiche e patch che correggono i problemi incontrati dai nostri client. The global platform performances have also been optimized. <br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches}

#### General {#general}

* Risolti diversi problemi di sicurezza.
* Risolti diversi problemi relativi ai campi vuoti o ai campi duplicati nell'API REST.
* Ora potete creare messaggi SMS e notifiche push direttamente dalla home page dell'applicazione.

#### Emails and SMS messages {#emails-and-sms-messages}

* È stato risolto un problema che impediva agli utenti di caricare i file zip nell'editor contenuto.
* È stato risolto un problema che impediva l'apertura di una prova dopo l'invio.
* Fixed an issue that led to an error message displaying when accessing the **[!UICONTROL Hot Clicks]** report on an A/B test email.
* Fixed an issue that prevented modifications made using the **[!UICONTROL Show source]** mode from being applied.
* È stato risolto un problema che poteva impedire l'importazione di file modello xml predittivi.
* A new screen dedicated to importing data for the subject line trained model is now available in **[!UICONTROL Administration > Channels > Emails > Predictive Subject Line]** .
* È stato risolto un problema che consentiva agli utenti non amministratori di modificare le maschere autorizzate nella schermata di configurazione e-mail.

#### Push notifications {#push-notifications}

* Fixed an issue that prevented sending logs and event logs from being displayed for the recipients after sending a push notification using the **[!UICONTROL Send push on profiles]** template.
* È stato risolto un problema che poteva impedire la creazione di nuove applicazioni mobili.

#### Workflows {#workflows}

* Fixed a performance issue that occured when using the **[!UICONTROL Subscription]** activity.
* È stato risolto un problema che impediva il funzionamento di un flusso di lavoro quando il suo nome interno conteneva uno spazio.

#### Integrations {#integrations}

* Fixed an issue that could lead to an error being displayed when using the **Image shared from Adobe Marketing Cloud** option in an email.

#### Custom resources {#custom-resources}

* API migliorate: anteprima tra due pubblicazioni di campi API estesi.
* È stato risolto un problema che impediva la cancellazione di una risorsa personalizzata prima della pubblicazione.
* È stato risolto un problema che impediva la fase di estensione dei profili e le chiavi di identificazione con un campo dinamico.
* È stato risolto un problema che poteva verificarsi durante l'aggiunta di collegamenti in una risorsa personalizzata.

## Release 16.10 - October 2016 {#release-16-10---october-2016}

### New capabilities {#new-capabilities-1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Email predictive subject line<br /> </td> 
   <td> Quando si modifica un'e-mail, una nuova opzione consente di provare diversi oggetti e di ottenere una stima della relativa velocità di apertura prima di inviarla. Ciò è possibile creando un modello personalizzato basato sui dati di consegna passati o utilizzando un modello predefinito specifico per il settore. Questa funzione è disponibile per i messaggi e-mail e per i database contenenti contenuto inglese. <br /> Per ulteriori informazioni sull'attivazione e sull'utilizzo, consulta la documentazione <a href="../../designing/using/personalizing-the-subject-line-of-an-email.md#predictive-subject-line">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> SMS transactional messaging<br /> </td> 
   <td> Il canale SMS è stato aggiunto alle funzionalità di messaggistica transazionali di Adobe Campaign. Sono ora supportati due canali per i messaggi transazionali: e-mail e SMS.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/configuring-transactional-messaging.md#creating-an-event">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Follow-up message for transactional messaging<br /> </td> 
   <td> È ora possibile creare un flusso di lavoro per un evento. Ciò significa che potete inviare un messaggio di follow-up ai clienti che hanno ricevuto in precedenza un messaggio transazionale. Potete filtrare la destinazione per tipo di evento, per gli eventi broadlogs e per i registri di tracciamento. Nel messaggio di follow-up, potrete sfruttare il contenuto dell'evento (payload). <br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/follow-up-messages.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Extended Profile &amp; Services API<br /> </td> 
   <td> Ora potete esporre campi estesi nell'API Profilo e Servizi. Il meccanismo di pubblicazione consente alle API di mappare i campi estesi delle risorse personalizzate di Profili o Servizi. For this to work, the <strong>Datamodel</strong> role has been added. Questo nuovo ruolo consente all'utente di configurare un set di amministratori che avranno accesso al modello dati.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-1}

#### General {#general-1}

* Risolti diversi problemi di sicurezza.

#### Emails and SMS messages {#emails-and-sms-messages-1}

* The SMS external account configuration screen ( **[!UICONTROL Administration > Channels > SMS > SMS accounts]** ) has been improved. Several parameters have been added in the **[!UICONTROL SMSC specifics]** section to support error codes in the "Text" field.

#### Push notifications {#push-notifications-1}

* Fixed an issue that prevented the predefined filters from being displayed when editing the audience of a push notification based on the **[!UICONTROL Send via push notification]** (mobileApp) template.
* The mobile application configuration screen ( **[!UICONTROL Administration > Channels > Push Notification > Mobile applications]** ) now displays a message to indicate that the iOS or Android platform has been successfully created.

#### Landing pages {#landing-pages}

* È stato risolto un problema che impediva l'invio delle e-mail di conferma all'invio di una pagina di destinazione.

#### Audiences and queries {#audiences-and-queries}

* Risolti diversi problemi che si verificavano quando si selezionava un profilo nell'editor query.

#### Transactional messages {#transactional-messages}

* Risolto un errore che impediva la pubblicazione di un modello transazionale.
* È stato risolto un problema che causava l'attivazione di eventi attivati nell'elenco degli eventi.

#### Integrations {#integrations-1}

* È stato risolto un problema che impediva l'utilizzo di un'audience condivisa in una consegna dopo l'aggiornamento dell'audience.
* Fixed an issue that prevented a shared asset ( **[!UICONTROL Image shared from Adobe Marketing Cloud]** option) from being used in a landing page.
* Risolti problemi che si verificavano durante la modifica di un pubblico condiviso importato da Adobe Audience Manager.

## Release 16.9 - September 2016 {#release-16-9---september-2016}

### New capabilities {#new-capabilities-2}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Remarketing Triggers<br /> </td> 
   <td> Integration between the core service <span class="uicontrol">Triggers</span> and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).<br /> In Adobe Marketing Cloud puoi definire i diversi attivatori, ossia i comportamenti dei clienti che desideri monitorare, come tutti i clienti che hanno abbandonato il carrello o il modulo, rimosso un prodotto dal loro carrello o persino quelli la cui sessione è scaduta. Quando crei un trigger, definisci la condizione dell'attivatore e i dati che verranno inviati nell'evento (pload) ad Adobe Campaign. <br /> In Adobe Campaign, selezionate l'attivatore creato in precedenza, ingrandite i dati dell'evento con i dati di datamart e definite un modello di messaggio transazionali collegato a tale trigger. Ad esempio, quando un client abbandona il carrello, un evento viene inviato ad Adobe Campaign che può quindi sfruttare questo evento tramite un'e-mail di remarketing inviata al client entro 15 minuti.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages: Pause / Unpublish<br /> </td> 
   <td> Ora potete sospendere la pubblicazione di un modello transazionale mentre ne aggiornate il contenuto. I messaggi corrispondenti non vengono più inviati, ma sono memorizzati nel database. Quando si riprende, i messaggi in coda vengono elaborati e inviati se non sono scaduti.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication">dettagliata</a>.<br /> Ora potete annullare la pubblicazione di eventi e modelli transazionali. I messaggi corrispondenti non vengono più inviati e non sono memorizzati nel database.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Multibranding<br /> </td> 
   <td> I client con più marchi possono ora gestirli nella stessa istanza. Branding è una funzione gestita dall'amministratore dell'istanza Adobe Campaign che consente di configurare in modo centralizzato tutti i parametri relativi a un marchio all'interno di Adobe Campaign. Ciò include elementi quali il logo a parametri più tecnici come URL di tracciamento, analisi Web, URL server, nome dominio e così via.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/branding.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Responsive email design preview<br /> </td> 
   <td> Questa funzione consente di verificare la capacità di risposta dell'e-mail sui diversi tipi di dispositivi. In the email preview, a grid has been added to test your email on various screen sizes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push notifications<br /> </td> 
   <td> È stato aggiunto un nuovo canale per consentire agli esperti di marketing di inviare notifiche push personalizzate e segmentate sui dispositivi mobili iOS e Android. I messaggi possono essere inviati tramite una singola consegna o mediante un'attività di flusso di lavoro. La compatibilità con i messaggi transazionali sarà disponibile nelle versioni future. This channel leverages the Mobile core service’s SDK (available <a href="https://marketing.adobe.com/developer/gallery/marketing-cloud-mobile-libraries">here</a>).<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-push-notifications.md">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-2}

#### General {#general-2}

* Questa release introduce nuove funzionalità di filtro e ricerca negli elenchi delle interfacce. Questa nuova funzione è disponibile, ad esempio, nei registri (consegna, tracciamento), servizi (iscrizione, cronologia iscrizione), audience e transizioni del flusso di lavoro.
* Sono stati risolti diversi problemi di visualizzazione relativi al numero di punti di contatto in un profilo cliente.
* Risolti diversi problemi di tipologia.

#### Emails and SMS messages {#emails-and-sms-messages-2}

* Risolto un errore che consentiva la modifica di prove errate. Ora sono di sola lettura.
* È stato risolto un problema che causava la blacklist di un destinatario in blacklist quando un SMS era troppo lungo o aveva problemi di codifica.

#### Custom resources {#custom-resources-1}

* Risolto un errore che impediva la visualizzazione di tutti i risultati quando si utilizzavano filtri avanzati di una risorsa personalizzata.

#### Transactional messages {#transactional-messages-1}

* Ora viene aggiunto automaticamente un prefisso all'identificatore di una nuova definizione dell'evento.
* L'icona che rappresenta i messaggi transazionali nell'interfaccia è stata modificata.

#### Integrations {#integrations-2}

* Fixed a display error that would occur when a high resolution image was inserted via the **Dynamic image from Adobe Target** option.
* Risolto un errore che consentiva di salvare un pubblico condiviso anche se l'ID di destinazione non era impostato nell'origine dati AMC.

## Release 16.7 - July 2016 {#release-16-7---july-2016}

### New capabilities {#new-capabilities-3}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Enriched transactional messages<br /> </td> 
   <td> Ora potete collegare i modelli transazionali con il database Adobe Campaign per recuperare informazioni che consentono di arricchire il contenuto dei messaggi transazionali.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic URLs for images<br /> </td> 
   <td> Questa nuova funzionalità consente di personalizzare un'origine immagine inserendo blocchi di contenuto e testo dinamico a scopo di tracciamento e personalizzazione.<br /> È quindi possibile trarre profitto dalle funzionalità dei contenuti multimediali dinamici di AEM Assets (S 7) immettendo parametri negli URL delle immagini. Ad esempio, potete inviare un'e-mail con immagini personalizzate che indicano «Hello Alexandre, ottenere le ultime notizie sugli eventi in programma a Parigi!» oppure «Ciao Frank, ottenete le ultime notizie sugli eventi in programma in New York!».<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../designing/using/personalizing-urls.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integration with People Core Service<br /> </td> 
   <td> The Adobe Marketing Cloud <strong>Declared IDs</strong> are now covered by the integration between Adobe Campaign and People Core Service (Profiles &amp; Audiences).<br /> Ciò significa che puoi importare segmenti ed esportare audience costituite da <strong>ID visitatore</strong>o <strong>ID dichiarati</strong>.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery logs<br /> </td> 
   <td> The MTA logs (delivery server) now display the complete history of each message, particularly all of the delivery attempts as well as the associated error statuses, and this has no impact on the application's performance.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-3}

#### General {#general-3}

* È stato corretto un errore che poteva causare la visualizzazione di campi non rilevanti invece dei campi che dovevano essere completati. Ciò si verifica dopo che l'operatore di confronto è stato modificato più volte durante la modifica di una condizione in una query.
* Fixed the behavior of the option **[!UICONTROL The last X days/months/quarters/years]** when defining a relative filtering condition for a date field. Il periodo calcolato è ora un periodo di scorrimento relativo alla data e all'ora del server e non basato su calendario.

#### Workflows {#workflows-1}

* Fixed an error that would return an incorrect list of values in the screen for selecting the targeting dimension in the properties of a **[!UICONTROL Query]** activity.
* Fixed an error that would force the **Exists** operator to be selected when adding an average or count aggregate on a collection element in a **[!UICONTROL Query]** activity.

#### Content editing {#content-editing}

* È stato corretto un errore che poteva causare problemi di visualizzazione (responsive design) durante l'importazione di contenuto HTML: gli attributi di stile non vengono più riscritti quando il contenuto viene aperto per la prima volta dopo l'importazione.
* Risolto un errore che non bloccava il blocco causato da una condizione aggiunta in una variante di contenuto dinamico.
* È stato risolto un errore causato dall'aggiunta di una casella di controllo nel contenuto di una pagina di destinazione. Casella di controllo non utilizzabile.
* Risolto un errore che poteva verificarsi quando si eliminava testo in un blocco se il cursore veniva posizionato all'inizio del blocco.

#### Transactional messages {#transactional-messages-2}

* Quando si integra un sito Web, ora è possibile definire una data di scadenza per qualsiasi evento specificato. Una volta superata questa data, il messaggio corrispondente all'evento non può più essere inviato.

## Release 16.6 - June 2016 {#release-16-6---june-2016}

### New capabilities {#new-capabilities-4}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Profiles and Services API<br /> </td> 
   <td> <span class="uicontrol">I profili e l'API di Adobe</span> Campaign sono disponibili nel portale <a href="https://www.adobe.io/products/campaign">adobe. io</a> . Ciò consente di aggiornare, aggiungere ed eliminare i profili di Adobe Campaign, nonché di iscriversi o annullare la sottoscrizione ai servizi tramite le chiamate REST.<br /> Per ulteriori informazioni, consulta la <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">descrizione dettagliata dell'API</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-4}

#### General {#general-4}

* I suggerimenti sono ora disattivati sui dispositivi mobili per garantire che le informazioni visualizzate sullo schermo siano facili da leggere.
* È stato corretto un errore che impediva all'utente di scorrere il contenuto di determinate aree nella schermata ipad.
* Sono stati corretti diversi errori di compatibilità riscontrati durante la modifica del contenuto in Internet Explorer 11.
* È stato risolto un errore che poteva impedire l'accesso ai registri dettagliati quando l'importazione dei dati non andava a buon fine.
* Risolto un errore che poteva impedire il salvataggio di un filtro di intervallo.
* Risolto un errore che impediva la visualizzazione degli elementi di una risorsa durante la configurazione del modo in cui viene visualizzato un elenco.
* Risolto un errore in query editor explorer. I risultati restituiti dal campo di ricerca sono stati mantenuti nella cronologia di ricerca e continuano a essere visualizzati a ogni nuova ricerca.

#### Emails and SMS messages {#emails-and-sms-messages-3}

* È stato corretto un errore che impediva la restituzione nei registri di consegna delle informazioni collegate a rimbalzi.
* Risolto un errore che impediva l'accesso al contesto in un blocco di contenuto dinamico di un messaggio transazionali.
* È stato corretto un errore che impediva la definizione di un collegamento URL nel contenuto dinamico del contenuto di un'e-mail.
* È stata corretta la visualizzazione della barra superiore della procedura guidata di creazione della distribuzione.
* La chiave primaria di una consegna non può più essere utilizzata come campo personalizzato.

#### Workflows {#workflows-2}

* Le transizioni tra due attività di un flusso di lavoro ora mostrano il totale degli elementi calcolati e trasferiti da un'attività a un'altra.
* Incompatible fields are now hidden when additional data is added in a **[!UICONTROL Query]** activity.
* La finestra di definizione aggregata visualizzata quando si aggiungono ulteriori dati è stata migliorata alle opzioni di offerte compatibili con i dati in uso (ad esempio: il calcolo di una media è possibile solo per i dati numerici.
* L'avvio o il riavvio di un flusso di lavoro tecnico integrato può essere eseguito solo da un utente con diritti di amministrazione.

#### Landing pages {#landing-pages-1}

* È stato corretto un errore che poteva troncare i tasti di codifica AES a 32 bit nelle proprietà di una pagina di destinazione.
* Risolto un errore che impediva la visualizzazione corretta dell'editor query durante la definizione di una condizione di visibilità o di aggiunta di contenuti dinamici a una pagina di destinazione.

#### Custom resources {#custom-resources-2}

* The **[!UICONTROL Switch to parameters]** option is now hidden when defining a filter related to a profile's subscriptions to a service.
* Risolto un errore che poteva verificarsi quando un collegamento di tipo 0-1 veniva configurato da una risorsa personalizzata.
* Fixed an error that, where relevant, could prevent the defined **Constant default value** from being edited when adding a **Date and time** type field in a custom resource.

## Release 16.5 - May 2016 {#release-16-5---may-2016}

### New capabilities {#new-capabilities-5}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Predefined filters<br /> </td> 
   <td> Gli amministratori possono ora creare filtri avanzati che vengono visualizzati nell'editor query sotto forma di regole pre-configurate. La selezione di tali filtri consente agli utenti di sviluppare configurazioni complesse in modo più semplice durante la definizione di un'audience, ad esempio.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../developing/using/configuring-filter-definition.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Subscription Services<br /> </td> 
   <td> A new <span class="uicontrol">Subscription Services</span> activity offers the possibility of subscribing several profiles to a service or unsubscribing them from a service with in a single action.<br /> Questa attività può essere utilizzata dopo aver eseguito un targeting o importato un file con dati identificati.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/subscription-services.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: data enrichment<br /> </td> 
   <td> The <span class="uicontrol">Additional data</span> tab is now available in <span class="uicontrol">Query</span> type activities. Questa funzionalità consente di arricchire i dati mirati dalla query e di trasferire questi dati alle seguenti attività del flusso di lavoro, in cui può essere sfruttata.<br /> Dopo aver aggiunto ulteriori dati, è possibile applicare un livello di filtro aggiuntivo ai dati inizialmente mirati creando condizioni in base ai dati aggiuntivi definiti.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/query.md#enriching-data">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Contextual help<br /> </td> 
   <td> Ora è disponibile una funzione di aiuto contestuale tra le diverse schermate di Adobe Campaign. Questo significa che, con un solo clic, potete accedere direttamente alla documentazione sulla funzionalità in uso. Per visualizzare la guida contestuale, fai clic su «?» icon in the upper-right corner of the screen, as shown in the example below.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### General {#general-5}

* Varie interfacce Nuove funzionalità conformi agli standard di Marketing Cloud.
* Standardizzazione dei diversi tipi di elenco a discesa.

#### Emails and SMS messages {#emails-and-sms-messages-4}

* Risolto un errore che impediva l'invio delle e-mail se veniva specificata la maschera dell'indirizzo di errore.
* Il protocollo TLS è ora supportato per la consegna delle e-mail. Una nuova colonna nella gestione MX consente di definire il comportamento TLS desiderato per ogni dominio.
* L'interfaccia SMS è stata migliorata.

#### Workflows {#workflows-3}

* Varie interfacce di flusso di lavoro Nuove funzionalità.
* Risoluzione di un errore che si verificava durante la visualizzazione delle azioni rapide.
* Fixed an error that could cause a workflow to fail when using a **[!UICONTROL Segmentation]** type activity containing a 1-N link.
* È stato corretto un errore che impediva la apertura delle transizioni di un flusso di lavoro su un dispositivo ibrido.
* Risolto un errore che impediva la visualizzazione del pulsante Pausa quando si avviava un workflow per la prima volta.

#### Content editor {#content-editor}

* L'editor di contenuto ora consente di personalizzare qualsiasi URL contenuto in un'e-mail o in una pagina di destinazione. Refer to the [detailed documentation](../../designing/using/personalizing-urls.md).
* È stato corretto un errore a causa del quale le immagini venivano perse quando venivano aggiunte nella procedura guidata di creazione della distribuzione e il contenuto veniva modificato successivamente.

#### Custom resources {#custom-resources-3}

* Risoluzione di un errore che si verificava durante l'aggiunta di un collegamento personalizzato 1-N nella schermata di configurazione di una risorsa personalizzata.
* Migliorata la visualizzazione della barra di avanzamento durante la preparazione e la pubblicazione di risorse personalizzate.
* Risoluzione di un errore che si verificava durante la visualizzazione dell'elenco di collegamenti di una risorsa personalizzata.

#### Transactional messages {#transactional-messages-3}

* L'interfaccia utente dell'interfaccia e le prestazioni e la robustezza del motore dei messaggi transazionali sono state ottimizzate.
* È ora possibile sospendere temporaneamente la pubblicazione di un modello di messaggio transazionale. For more on this, refer to the [detailed documentation](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication).
* È stato corretto un errore che poteva causare l'aggiunta di un blocco di contenuto con una dimensione di targeting incompatibile in un modello di messaggio transazionale.
* Risolto un errore che impediva la visualizzazione dell'anteprima API nella schermata di configurazione dell'evento.

#### Audiences and queries {#audiences-and-queries-1}

* Varie patch riguardo l'utilizzo delle date nell'editor query. Refer to the [detailed documentation](../../automating/using/editing-queries.md#creating-queries).

#### Administration {#administration}

* Risolto un errore relativo al nome del gruppo di protezione "Utenti standard", che impediva agli utenti di effettuare l'accesso.

## Release 16.3 - March 2016 {#release-16-3---march-2016}

### New capabilities {#new-capabilities-6}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Interface and navigation<br /> </td> 
   <td> L'interfaccia di Adobe Campaign è stata migliorata per rendere la navigazione e le operazioni semplice e intuitiva.<br /> Ora si passa dalla barra superiore dell'applicazione. The advanced menus are accessible by selecting the <strong>Adobe Campaign</strong> logo.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../start/using/interface-description.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Save audience<br /> </td> 
   <td> A new option, <span class="uicontrol">Create then update an audience</span> , is now available in the <span class="uicontrol">Save audience</span> activity. Questa opzione consente di inserire manualmente un'etichetta di tipo pubblico. Se l'etichetta inserita corrisponde a un'audience esistente, verrà aggiornata. Se l'audience non esiste, verrà creata.<br /> Inoltre, l'audience viene aggiornata ogni volta che il flusso di lavoro viene eseguito (di nuovo).<br /> Potete sempre selezionare la modalità di aggiornamento del pubblico: completa l'audience con nuovi dati o sostituisci tutti i dati del pubblico a ogni esecuzione.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/save-audience.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Segmentation<br /> </td> 
   <td> The <span class="uicontrol">Segmentation</span> activity now allows the user to segment the data of a temporary resource. Ad esempio: i dati di un file importato.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/segmentation.md">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### General {#general-6}

* È stato corretto un errore di visualizzazione che si verificava durante l'ordinamento di un elenco: La freccia che indica l'ordinamento di una colonna può essere invertita solo per alcuni tipi di dati.
* Risolto un errore che limitava il numero di elementi visualizzati in un menu a discesa quando una regola veniva aggiunta in una query.

#### Emails and SMS messages {#emails-and-sms-messages-5}

* Risolto un errore che poteva impedire l'accesso al rapporto di rendering delle e-mail.
* La preparazione di invio per un messaggio ora restituisce un errore se l'indirizzo del mittente non viene fornito.

#### Workflows {#workflows-4}

* Alcune opzioni di formattazione del file erano visibili, ma non venivano considerate quando veniva estratto un file in formato CSV. Queste opzioni ora non sono più visibili.
* Fixed an error caused when the **[!UICONTROL Delete the source files after transfer]** option was checked for a **[!UICONTROL SFTP]** type file transfer.
* Fixed an error that could prevent the counter and preview of **[!UICONTROL Query]** data from being displayed after refreshing the page.
* È stato risolto un errore causato dall'apertura di determinate transizioni in un flusso di lavoro, in particolare dopo un'attività di consegna o una query in cui le dimensioni di targeting e filtro erano diverse.
* Risolto un errore che non consentiva di inserire un campo di personalizzazione in un'attività di consegna di un flusso di lavoro se il flusso di lavoro non veniva salvato dopo l'aggiunta dell'attività.
* Risolto un errore che impediva la visualizzazione della dimensione di targeting delle transizioni in uscita di un'attività di consegna e-mail.

#### Landing pages {#landing-pages-2}

* Risolto un errore che impediva il corretto funzionamento dei campi di personalizzazione in un blocco di contenuto localizzabile in una pagina di destinazione.

#### Custom resources {#custom-resources-4}

* Fixed an error that prevented a search on a custom resource from being carried out if the **[!UICONTROL Add search fields]** option of the resource screen definition was checked and if several fields were selected in the **[!UICONTROL Filter zone composition]** .

## Release 16.2 - February 2016 {#release-16-2---february-2016}

### New capabilities {#new-capabilities-7}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> A/B test for emails<br /> </td> 
   <td> Ora potete eseguire test A/B sul contenuto, l'oggetto o il nome mittente delle e-mail. Questa nuova funzionalità può sottoporre a test fino a tre varianti di un elemento.<br /> Quando si crea un'e-mail da uno dei nuovi modelli specifici dei test A/B, un nuovo passaggio nella procedura guidata di creazione consente di definire i parametri del test.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/designing-an-a-b-test-email.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Brand management<br /> </td> 
   <td> Ora puoi definire uno o più marchi per inserire in modo centralizzato i parametri che influenzano l'identità di un marchio. Adobe Campaign consente di creare marchi e di collegarli alla distribuzione o ai modelli delle pagine di destinazione.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/branding.md#assigning-a-brand-to-an-email">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Incremental query<br /> </td> 
   <td> A new workflow activity, <span class="uicontrol">Incremental query</span> , allows you to carry out a query which, on every execution, targets only the new results. I risultati delle esecuzioni precedenti vengono esclusi automaticamente. Linked to a <span class="uicontrol">Scheduler</span> activity, you can define the execution frequency of the <span class="uicontrol">Incremental query</span> .<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/incremental-query.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages<br /> </td> 
   <td> È stata migliorata l'interfaccia utente dell'interfaccia dei messaggi transazionali. All business process management linked to transactional messages is currently centralized in the <span class="uicontrol">Marketing plans</span> &gt; <span class="uicontrol">Transactional messages</span> menu. È stata migliorata anche la configurazione dell'evento. Gli eventi ora vengono gestiti in modo indipendente da risorse personalizzate.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-transactional-messaging.md">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-7}

#### General {#general-7}

* Sono stati corretti diversi errori di visualizzazione nei rapporti, negli elenchi e nelle query.
* Sono stati corretti diversi errori di compatibilità e visualizzazione sui dispositivi mobili.

#### Emails and SMS messages {#emails-and-sms-messages-6}

* Risoluzione di un errore che poteva impedire la visualizzazione del pulsante utilizzato per inserire campi di personalizzazione durante la creazione di un messaggio (e-mail o SMS).
* Risolto un errore che poteva impedire la trasmissione corretta dei messaggi SMS inviati tramite Mblox.

#### Audiences and queries {#audiences-and-queries-2}

* È stato corretto un errore di conteggio che poteva essere causato durante l'aggiunta di una condizione aggiuntiva in una query, dopo aver modificato la dimensione di filtro.
* È stato corretto un errore che potrebbe portare a un'impaginazione errata durante l'anteprima dei risultati di una query.

#### Content editing {#content-editing-1}

* Risolto un errore che poteva impedire la corretta presa in considerazione della configurazione di contenuto dinamica quando si utilizzava un'enumerazione personalizzata.

#### Workflows {#workflows-5}

* Fixed an error that could prevent any action in a workflow from being carried out if there was an empty line in the **[!UICONTROL Fields to update]** tab of an **[!UICONTROL Update data]** activity.
* Risolto un errore che impediva l'importazione di dati contenenti informazioni sull'unità geografica/organizzativa.
* Fixed an error caused by adding a **[!UICONTROL Change axis]** type of **[!UICONTROL Exclusion]** rule.
* Fixed an error that could lead to an unwanted additional segment being created when manipulating an outbound transition of a **[!UICONTROL Segmentation]** activity.
* Risolto un errore causato caricando un file in un modello di flusso di lavoro.
* Fixed an error that could prevent spaces from being used as column separators in a **[!UICONTROL Load file]** activity.

#### Custom resources {#custom-resources-5}

* Risolto un errore che impediva la riscrittura dello stato di una risorsa personalizzata dopo l'importazione di un pacchetto, se la risorsa era pubblicata al momento dell'esportazione.

#### Packages {#packages}

* Risolto un errore che impediva l'esportazione di un pacchetto contenente un flusso di lavoro.
* Risolto un errore che poteva impedire selezione di diversi elementi della stessa risorsa.

## Release 16.1 - January 2016 {#release-16-1---january-2016}

### New capabilities {#new-capabilities-8}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> The following email specific reports have been added: <span class="uicontrol">Complaints</span> , <span class="uicontrol">Opens</span> , and <span class="uicontrol">Unsubscriptions</span> .<br /> Sono stati apportati i seguenti rapporti: <span class="uicontrol">Riepilogo</span> distribuzione, <span class="uicontrol">Riepilogo</span> rimbalzo, <span class="uicontrol">Consegna consegna</span> e Indicatori <span class="uicontrol">di tracciamento</span> .<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../reporting/using/defining-the-report-period.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Query editing<br /> </td> 
   <td> The query editor has been improved and now allows you to scan the <strong>1-N</strong> type links.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/editing-queries.md#creating-queries">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Content personalization<br /> </td> 
   <td> As for email or landing page editing, the input interface for content block display conditions has been improved.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: column definition when importing<br /> </td> 
   <td> The <span class="uicontrol">Load file</span> activity now allows you to configure the columns of an imported file in detail: expected data type, date and time format, processing to apply in case of an empty value or an error, and value remapping.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/load-file.md#column-format">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mapping of SMS encodings<br /> </td> 
   <td> Ora è possibile definire mappature di codifiche di messaggi SMS personalizzati per i fornitori non utilizzando codifica standard. Un amministratore può eseguire la configurazione delle mappature personalizzate e definire l'ordine in cui dovrebbero essere considerati.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/configuring-sms-channel.md#smsc-specifics">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-8}

#### General {#general-8}

* Compatibilità migliorata con Internet Explorer e Chrome per dispositivi ibridi/touchscreen.
* Risolto un errore che potrebbe causare la perdita di tutti i dati immessi per un nuovo profilo utente/profilo/test se l'indirizzo e-mail conteneva errori di sintassi.

#### Emails and SMS messages {#emails-and-sms-messages-7}

* Risolto un errore che poteva impedire la generazione della miniatura del contenuto nella schermata di anteprima e-mail.
* Risolto un errore che poteva impedire che il contenuto non elaborato di un messaggio (e-mail o SMS) venisse visualizzato nella schermata di anteprima del messaggio.

#### Audiences and queries {#audiences-and-queries-3}

* Fixed an error that could prevent a **Query** type audience from being created in the **Service** resource.
* Risolto un errore che poteva impedire la visualizzazione corretta dell'elenco della funzione durante la modifica di una condizione di query in modalità avanzata.
* Fixed an error that could prevent a **Query** type audience from being created if it contained criteria based on collections.
* Risolto un errore che poteva impedire la creazione di query contenenti filtri al momento della creazione dei KPI.
* È stato corretto un errore che poteva impedire l'anteprima del contenuto di un'audience creata da un flusso di lavoro.

#### Custom resources {#custom-resources-6}

* Risolto un errore che poteva causare l'arresto anomalo del server se una risorsa personalizzata conteneva un campo con un valore predefinito dinamico.
* Fixed an error caused by moving, then deleting an element in the **[!UICONTROL Detail screen configuration]** section while defining screens of a custom resource.
* Fixed an error that occurred when a default value had been defined for an **integer** list that did not include **0** in its range of possible values.
* Risolto un errore che poteva impedire l'aggiunta di un elemento nella configurazione dello schermo di dettaglio di una risorsa personalizzata dopo la reinizializzazione.

#### Workflows {#workflows-6}

* È stato corretto un errore che poteva causare la visualizzazione di registri di tutte le attività in un flusso di lavoro anziché la visualizzazione solo di quelli dell'attività selezionata.
* Fixed an error in the **[!UICONTROL Scheduler]** activity. The **[!UICONTROL Day of the month]** option was not correctly taken into account and replaced by **[!UICONTROL Week day]** .
* Fixed an error that could prevent a **[!UICONTROL Scheduler]** activity from working correctly with the expiration mode set to **[!UICONTROL After a certain number of iterations]** .
* Fixed an error that occurred when exporting data using an **[!UICONTROL Extract file]** activity. Il numero di righe presenti nel file di esportazione era inferiore al numero di elementi esportati.
* Fixed an error that could prevent a file in a **[!UICONTROL Load file]** activity from being selected.
* Fixed an error that prevented fields that were to be updated in an **[!UICONTROL Update data]** activity from being deleted.
* È stato risolto un errore che impediva il salvataggio delle modifiche apportate a un flusso di lavoro dopo aver aperto i registri di esecuzione del flusso di lavoro.
* Fixed an error that caused a **[!UICONTROL Load file]** activity to be executed twice if it was configured to use the file from its inbound transition and this file had been loaded using a **[!UICONTROL Transfer file]** activity.
* Fixed an error that could prevent certain temporary entities from being correctly processed by an **Exclusion** activity.
* Fixed an error that could prevent a **[!UICONTROL Query]** activity from being executed correctly if the targeting dimension and the filtering dimension configured in the activity were different.
* Fixed an error concerning the automatic naming of outbound transitions added to a **[!UICONTROL Fork]** activity that could prevent the workflow from being saved.

#### Content editing {#content-editing-2}

* È stato corretto un errore che poteva portare a un'icona o a una barra di ricerca che veniva visualizzata in modo indesiderabile durante la modifica del contenuto.

#### Landing pages {#landing-pages-3}

* Risolto un errore che impediva l'importazione di una pagina di destinazione tramite importazione pacchetto.

#### Transactional messages {#transactional-messages-4}

* È ora possibile specificare un indirizzo IP affidabile nei parametri di protezione dell'operatore agente push Messaggio messaggio.
* Risolto un errore che poteva impedire la creazione di un nuovo tipo di evento.

## Release 15.11 - November 2015 {#release-15-11---november-2015}

### New capabilities {#new-capabilities-9}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> SMS Channel<br /> </td> 
   <td> Ora puoi inviare messaggi SMS con Adobe Campaign.<br /> Come per le e-mail, puoi creare nuovi SMS dalle campagne e dall'elenco delle attività di marketing. Puoi anche creare messaggi SMS singoli e periodici da un flusso di lavoro.<br /> Queste comunicazioni SMS si basano sui modelli che è possibile configurare dall'elenco dei modelli di consegna. È disponibile un modello predefinito.<br /> Tali comunicazioni SMS utilizzano il protocollo SMPP 3.4, utilizzato dalla maggior parte dei router SMS.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-sms-messages.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploring transitions<br /> </td> 
   <td> Ora potete esplorare i dati e la relativa struttura nell'ultima transizione di un flusso di lavoro. This allows you to check that the processes applied by each activity correspond to your needs.<br /> </td> 
  </tr> 
  <tr> 
   <td> File pre- and post-processing in workflows<br /> </td> 
   <td> You can now carry out additional processing on a data file when importing or exporting it via the <span class="uicontrol">Load file</span> and <span class="uicontrol">Extract file</span> activities.<br /> Per impostazione predefinita, è possibile decomprimere e comprimere un file in formato GZIP in queste attività.<br /> Per ulteriori informazioni, consultate la documentazione relativa alle <a href="../../automating/using/load-file.md">attività Carica ed</a> <a href="../../automating/using/extract-file.md">Estrai file</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> Deliverability reports<br /> </td> 
   <td> È disponibile un rapporto di rendering e-mail. Questo rapporto consente di visualizzare i diversi rendering di un messaggio in base al supporto e al servizio di messaggio utilizzati per leggerlo.<br /> Il riepilogo del report presenta anche il numero di messaggi ricevuti, messaggi spam, messaggi non ricevuti e messaggi in attesa di ricezione.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../sending/using/email-rendering.md#email-rendering-report-description">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Package Management<br /> </td> 
   <td> It is now possible to import and export images in packages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quick actions<br /> </td> 
   <td> Alcune azioni vengono visualizzate quando si passa il mouse sopra o dopo aver selezionato un elemento in un elenco o in un flusso di lavoro. Alcune di queste azioni sono ora visualizzate come icone attorno agli elementi interessati per facilitare l'accesso. These quick actions can be used to duplicate an element, delete it, show the detail, etc.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-9}

#### General {#general-9}

* È stato corretto un errore che poteva impedire l'accesso ai parametri generali di un'istanza da un account amministratore.
* **I dati mobili** sono ora correttamente considerati nelle risorse personalizzate.
* È stato corretto un errore di visualizzazione nell'elenco di importazioni semplificate eseguite in caso di modifica dello stato del modello corrispondente.

#### Landing pages {#landing-pages-4}

* Risolti alcuni elementi dei modelli di pagina di destinazione che potevano essere visualizzati in modo errato in francese sulle istanze inglese.

#### Audiences {#audiences}

* È stato corretto un errore che poteva impedire che i tipi di pubblico importati da Adobe Marketing Cloud venissero visualizzati nell'elenco dei tipi di pubblico.
* Risolto un errore che poteva forzare la distinzione tra maiuscole e minuscole durante la definizione di una query.
* Risolto un errore che poteva impedire che le audience venissero filtrate durante la definizione di una query.
* Risolto un errore che poteva impedire l'annullamento di un'azione in un'audience.

#### Workflows {#workflows-7}

* Fixed an error that could prevent the fields that were to be updated in an **[!UICONTROL Update data]** activity from manually being configured.
* Fixed an error that could cause the **[!UICONTROL Query]** activity to load infinitely when opened if the workflow had not been saved after having placed the activity in the diagram.
* Fixed an error that could cause the server to stop while counting or previewing an audience selected from a **[!UICONTROL Query]** in a workflow.
* È stato corretto un errore non critico che poteva essere visualizzato quando veniva aperta un'attività in un flusso di lavoro.
* Fixed an error that prevented a **[!UICONTROL Scheduler]** activity from being configured to execute a workflow several times a day.
* È stato corretto un errore che poteva causare campi in cui non era possibile eseguire una query in alcune attività del flusso di lavoro.
* Fixed an error that could prevent the user from locating the KPIs added from a **[!UICONTROL Query]** on deliveries in the outbound transition.
* È stato corretto un errore che poteva impedire la creazione di un'audience di file dopo l'importazione di un file in un flusso di lavoro.
* Fixed an error that could prevent data from being updated on profiles if the **location/address3** field of the resource was used.
* Risolto un errore che impediva la duplicazione delle raccolte eterogenee di attività in un flusso di lavoro.
* È stato risolto un errore che impediva la visualizzazione di SQL, consentendo la diagnosi di errori per una consegna ricorrente in un flusso di lavoro.

#### Content editor {#content-editor-1}

* Risolto un errore che impediva la ricerca nel codice sorgente di una pagina di destinazione o di un'e-mail.

#### Packages {#packages-1}

* Sono stati corretti diversi errori che potevano impedire l'esportazione di alcuni tipi di elementi in pacchetti (in particolare pagine di destinazione, flussi di lavoro).
* Risolto un errore che causava la visualizzazione dell'etichetta di importazione del pacchetto prima se l'etichetta era stata modificata.
* È stato corretto un errore che poteva causare la visualizzazione di risorse incompatibili nell'elenco di risorse exportabili.

## Release 15.10 - October 2015 {#release-15-10---october-2015-}

### New capabilities {#new-capabilities-10}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Workflows: Deduplication activity<br /> </td> 
   <td> Nei flussi di lavoro è ora disponibile una nuova attività dedicata alla deduplicazione dei dati. Questa attività consente di filtrare qualsiasi duplicato nelle destinazioni in base ai criteri scelti.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/deduplication.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Improved diagram<br /> </td> 
   <td> Nell'area di lavoro del flusso di lavoro, è ora possibile utilizzare diverse scelte rapide da tastiera per selezionare, aprire ed eliminare le attività.<br /> Anche l'allineamento dell'attività è stato migliorato e consente di organizzare meglio un flusso di lavoro.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/workflow-interface.md#workspace">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Extract file activity<br /> </td> 
   <td> The date and time of the export is now automatically added to the labels of the files exported using an <span class="uicontrol">Extract file</span> activity. This way the files generated are unique.<br /> </td> 
  </tr> 
  <tr> 
   <td> Simplified data import<br /> </td> 
   <td> The name of the template from which a simplified import was carried out is now visible by default in the import list and in the detail of each import.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> Improvement and extended possibilities for managing and defining links for custom resources.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-10}

#### Email {#email}

* Risolto un errore che impediva il corretto funzionamento di un collegamento di annullamento dell'iscrizione a un servizio da una pagina speculare.
* È stato corretto un errore che poteva impedire la corretta visualizzazione dell'etichetta di consegna e-mail nella pagina di modifica e-mail.
* Fixed an error that could prevent an external **[!UICONTROL Routing]** account from being selected in a duplicated delivery template.

#### Audiences {#audiences-1}

* Risolto un errore provocato durante un conteggio di audience se nella query veniva utilizzato un collegamento 1-N.
* Risolto un errore che poteva impedire che un profilo venisse selezionato nel pubblico di destinazione di un'e-mail.

#### Workflows {#workflows-8}

* È stato corretto un errore che poteva causare problemi di visualizzazione durante la configurazione di un'e-mail di consegna in un flusso di lavoro.
* Fixed an error that could prevent the **[!UICONTROL Load file]** activity from working correctly. Viene visualizzato un messaggio di errore vuoto.
* Fixed an error that could prevent the **[!UICONTROL Transfer file]** activity from working correctly. I diritti di accesso non venivano sempre considerati correttamente.
* Fixed an error that could prevent a file from being exported if the workflow contained a **[!UICONTROL Recurring email]** .
* È stato risolto un errore che poteva impedire la creazione di un'e-mail in un flusso di lavoro o impedire che l'oggetto e il contenuto definito vengano considerati.
* Fixed an error that could prevent a reconciliation key from being selected in an **[!UICONTROL Update data]** activity when configuring the workflow of a simplified import template.
* Risolto un errore che poteva impedire il salvataggio di un flusso di lavoro dopo l'eliminazione di un'attività.

#### Platform {#platform}

* Risolto un errore che poteva impedire la creazione di un nuovo elemento se una risorsa personalizzata conteneva un collegamento al tipo di risorsa di quell'elemento.
* Risolto un errore che potrebbe causare un ritardo di 15 minuti per la scrittura di alcuni registri.
* Fixed an error that could prevent the marketing activity list from being displayed when sorted by the **[!UICONTROL Date]** or **[!UICONTROL Indicators]** columns.

#### Landing pages {#landing-pages-5}

* È stato corretto un errore che si verificava quando si selezionava un profilo di prova per visualizzare in anteprima una pagina di destinazione.

#### Transactional messages {#transactional-messages-5}

* Risolto un errore che poteva causare l'arresto anomalo dell'applicazione dopo l'eliminazione di un evento in un profilo di prova.

#### Reports {#reports}

* Fixed an error that could cause incorrect data to be sent for the reports **[!UICONTROL deliveryThroughputReport]** and **[!UICONTROL deliveryTrackingReport]** .

#### Content editor {#content-editor-2}

* È stato corretto un errore di gestione tag HTML che si verificava durante l'elaborazione dei blocchi di contenuto dinamici.

## Release 15.8 - August 2015 {#release-15-8---august-2015}

### New capabilities {#new-capabilities-11}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Simplified data import<br /> </td> 
   <td> È ora possibile importare i dati in modo semplificato.<br /> Gli utenti semplicemente selezionano un modello predefinito da un amministratore e caricano il file contenente i dati da importare. Un flusso di lavoro definito nel modello viene eseguito in modo trasparente per l'utente, che può accedere ai dettagli del risultato dell'importazione e al registro di eventuali errori.<br /> I dati di questi file possono essere inseriti nel database o essere utilizzati come mezzo per creare un pubblico direttamente.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/about-data-import-and-export.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creating programs and campaigns<br /> </td> 
   <td> Ora, le campagne e i programmi sono configurati in modo che il giorno in cui vengono creati viene automaticamente usato come data di inizio.<br /> La data di fine è configurata in base alla data di inizio, ad esempio:<br /> 
    <ul> 
     <li> D +186 per programmi </li> 
     <li> D +61 per campagne </li> 
    </ul> For more information, refer to the <a href="../../start/using/programs-and-campaigns.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> The list of tracked URLs is now read only.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages<br /> </td> 
   <td> Ora puoi gestire messaggi transazionali personalizzati per eventi quali cambio di password o conferme dopo la creazione di un account.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-transactional-messaging.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> Sono state aggiunte diverse funzionalità, ad esempio: estensione di un profilo di test, gestione dello stato ed eliminazione delle risorse.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../developing/using/resource-statuses.md">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-11}

#### Display {#display}

* È stato corretto un errore che potrebbe portare a due campi che venivano nominati nell'editor query in Safari.

#### Content editor {#content-editor-3}

* Risolto un errore che impediva l'utilizzo dei caratteri '&lt;','&amp;'è&gt;'in un oggetto dell'e-mail.

#### Email {#email-1}

* Risolto un errore che impediva all'utente di aggiungere testo dopo il testo dinamico.

#### Lists {#lists}

* Fixed an error that prevented the **Message** column in workflow execution logs from being exported correctly.

#### Profiles and audiences {#profiles-and-audiences}

* Risolto un errore che causava una doppia conferma di quando un elemento veniva duplicato o eliminato. **Dispositivi ibridi che utilizzano solo Internet Explorer 11**.

#### Workflows {#workflows-9}

* È stato corretto un errore che poteva impedire l'invio di e-mail da un flusso di lavoro.
* Fixed an error that could prevent a workflow from executing when the name of the rejection file was not specified in a **[!UICONTROL Load file]** activity.
* Fixed an error that could prevent a workflow from executing when the **[!UICONTROL Execution frequency]** of a **[!UICONTROL Schedule]** activity was set to **[!UICONTROL Daily]** .

#### Platform {#platform-1}

* Risolto un errore che impediva la generazione delle miniature in un ambiente bilanciato con caricamento.

## Release 15.7 - July 2015 {#release-15-7---july-2015}

### New capabilities {#new-capabilities-12}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Exporting lists<br /> </td> 
   <td> Ora potete esportare contenuto dagli elenchi in un file in formato CSV. This function is available in all screens with a <strong>List</strong> mode (for example: profile list).<br /> I dati esportati sono i dati delle colonne visualizzate durante l'esportazione. Modificando l'elenco, è quindi possibile selezionare i dati da esportare.<br /> Per ulteriori informazioni sull'utilizzo di questa funzionalità, consulta la documentazione <a href="../../automating/using/exporting-lists.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integration with Adobe Profiles &amp; Audiences<br /> </td> 
   <td> You can now share audiences between Adobe Campaign and your other Adobe Marketing Cloud solutions:<br /> 
    <ul> 
     <li> Export: when you save an audience composed of profiles in a workflow, a new <span class="uicontrol">Share in Adobe Marketing Cloud</span> option allows you to add profiles to an existing audience or to create a new audience. </li> 
     <li> Import: by creating a <strong>List</strong> type audience from the audience management screen, a new option allows you to identify it as an <span class="uicontrol">Adobe Marketing Cloud Audience</span> . Puoi quindi selezionare un pubblico condiviso esistente per importarlo in Adobe Campaign. </li> 
    </ul> For more information on configuring and using this functionality, refer to the <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Dynamic content<br /> </td> 
   <td> L'interfaccia dinamica del contenuto è stata migliorata. Le frecce ora vengono visualizzate per consentire la navigazione tra i diversi contenuti dinamici direttamente nel corpo dell'e-mail.<br /> Per ulteriori informazioni sull'utilizzo di questa funzionalità, consulta la documentazione <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Dynamic text<br /> </td> 
   <td> From the content editor of an email, you can now define dynamic text:<br /> 
    <ul> 
     <li> in un oggetto e-mail, </li> 
     <li> in modalità HTML, </li> 
     <li> o in modalità Testo. </li> 
    </ul> For more information on using this functionality, refer to the <a href="../../designing/using/defining-dynamic-text.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Programs and campaigns - Reports<br /> </td> 
   <td> L'interfaccia e la grafica dei rapporti sono state migliorate.<br /> Per ulteriori informazioni sull'utilizzo di questa funzionalità, consulta la documentazione <a href="../../reporting/using/defining-the-report-period.md">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-12}

#### Installation {#installation}

* I nomi delle istanze di Adobe Campaign sono ora limitati a 32 caratteri.

#### Workflows {#workflows-10}

* Risolto un errore che poteva impedire il targeting di una risorsà consegnà durante la modifica di una query in un flusso di lavoro.
* È stato corretto un errore che poteva impedire l'elaborazione di alcune risorse collegate durante la modifica di una query in un flusso di lavoro.
* Fixed an error that could prevent a **Recurring delivery** activity from being modified if the workflow had already been executed.

#### Emails {#emails}

* Risoluzione di un errore che impediva la selezione degli errori di sintassi javascript prima di inviare un'e-mail quando un contenuto dinamico era stato aggiunto tramite l'editor di espressioni.

#### Landing pages {#landing-pages-6}

* Risolto un errore che impediva la modifica di una pagina di destinazione da un tablet.

#### Assets Core Service {#assets-core-service}

* Quando si seleziona una risorsa condivisa da un'e-mail o una pagina di destinazione in fase di modifica, l'elenco delle risorse disponibili viene ora filtrato per Adobe Campaign.

## Release 15.6 - June 2015 {#release-15-6---june-2015}

### New capabilities {#new-capabilities-13}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Workflows: Reconciliation activity<br /> </td> 
   <td> A new <strong>Reconciliation</strong> activity links unidentified data (for example, after importing a file) with existing resources within a workflow.<br /> Questa attività viene utilizzata essenzialmente per scopi di gestione dati. It responds to two different use cases:<br /> 
    <ul> 
     <li> <strong>Aggiunta di relazioni</strong>: Una <strong>scheda Relazioni</strong> consente di aggiungere collegamenti tra dati in entrata e diverse dimensioni del database Adobe Campaign. </li> 
     <li> <strong>Identificazione dati</strong>: Una <strong>scheda Identificazione</strong> consente di associare semplicemente i dati in entrata alle colonne in una dimensione esistente nel database Adobe Campaign. Quando lascia l'attività, i dati sono identificati come appartenenti alla dimensione specificata. </li> 
    </ul> Refer to the <a href="../../automating/using/reconciliation.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Extract file activity<br /> </td> 
   <td> A new <strong>Extract file</strong> activity allows you to export data from the Adobe Campaign database in the form of an external file from a workflow. <br /> Limitazione: al momento non è possibile utilizzare nomi dinamici per i file di output.<br /> Consulta la documentazione <a href="../../automating/using/extract-file.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Scheduler activity<br /> </td> 
   <td> Improved widget that allows you to select the execution time of the <strong>Scheduler</strong> activity in a workflow.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Transfer file activity<br /> </td> 
   <td> SFTP is now supported.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> The <span class="uicontrol">Development</span> menu now allows users with admin rights to enrich the data templates provided by creating their own custom resources, such as purchase or product tables. <br /> Anche le risorse predefinite possono essere estese per aggiungere nuovi campi.<br /> Inoltre, è possibile configurare la navigazione nelle schermate corrispondenti a risorse personalizzate nuove o estese.<br /> Consulta la documentazione <a href="../../developing/using/data-model-concepts.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Test profiles<br /> </td> 
   <td> The <strong>Middle name</strong> and <strong>Title</strong> of the test profiles can now be selected when configuring the list of test profiles.<br /> </td> 
  </tr> 
  <tr> 
   <td> Content editor: Dynamic content<br /> </td> 
   <td> Potete definire contenuti diversi che verranno visualizzati in modo dinamico all'utente in base alle condizioni definite dall'editor di espressioni.<br /> Consulta la documentazione <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> A <strong>Test profiles</strong> column is now available in an email's sending logs.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-13}

#### Lists {#lists-1}

* Se si elimina un elemento da un elenco ora si aggiorna automaticamente l'elenco.
* È stato corretto un errore che impediva la selezione degli elementi da un elenco contenente una sola colonna.
* Risolto un errore che causava la perdita delle modifiche apportate alla visualizzazione di un elenco dopo l'aggiornamento della pagina.
* Sia il nome centrale che il titolo dei profili di prova possono essere visualizzati nell'elenco dei profili di prova.
* Risolto un errore che si verificava quando si selezionava una casella di controllo in un elenco con Mozilla Firefox.

#### Audiences {#audiences-2}

* Fixed an error that prevented the **[!UICONTROL Add]** button from being used in the audience interface.

#### Emails {#emails-1}

* Risolto un errore javascript che impediva l'utilizzo del pulsante di anteprima due volte in una riga durante la modifica di un'e-mail.
* Fixed an error that prevented the **[!UICONTROL Edit properties]** and **[!UICONTROL Show proofs]** buttons from being used on Microsoft Surface Pro3 tablets using Internet Explorer 11.
* È stato corretto un errore che poteva impedire la visualizzazione dei registri di invio dell'e-mail.

#### Landing pages {#landing-pages-7}

* Fixed an error that prevented the **Brand logo** content block from being used when editing content in a landing page.
* Risolto un errore che impediva la visualizzazione delle pagine di destinazione nell'elenco delle attività di marketing se per la pagina di destinazione venivano specificate date di validità.

#### Workflows {#workflows-11}

* Fixed an error that prevented limiting a segment in group mode from working correctly when configuring a **Segmentation** activity.
* Fixed an error that prevented a transition from being selected after having configured a **Segmentation** activity.
* Fixed an error that prevented a transition from being deleted after having configured a **Segmentation** activity.
* Fixed an error that prevented populations from being counted and previewed within a **Segmentation** activity.
* Risolto un errore che impediva l'eliminazione di un'e-mail ricorrente.
* Fixed an error that caused data from a deleted **Transfer file** activity to appear in a new **Transfer file** activity.
* Fixed an error that prevented an exclusion rule from being correctly taken into account within an **Exclusion** activity.
* Risoluzione di un errore che si verificava durante l'eliminazione di un'attività di consegna e-mail in un flusso di lavoro. Le consegne corrispondenti vengono rimosse anche dall'elenco delle attività di marketing.

#### Navigation {#navigation}

* Ora potete utilizzare il tasto di tabulazione per navigare correttamente tra i campi sulla stessa pagina.

## Release 15.4 - April 2015 {#release-15-4---april-2015}

### New capabilities {#new-capabilities-14}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Package exports / Package imports<br /> </td> 
   <td> The <strong>Deployment</strong> menu now allows users with admin rights to exchange resources between different Adobe Campaign instances by exporting and importing packages.<br /> Consulta la documentazione <a href="../../automating/using/managing-packages.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> All reports (except the <strong>Hot clicks</strong> report) can now be accessed from a program. These reports are:<br /> 
    <ul> 
     <li> Distribuzione del programma </li> 
     <li> Indicatori di tracciamento del programma </li> 
     <li> Suddivisione del programma per dominio </li> 
     <li> Programmi non consegnati e rimbalzi </li> 
     <li> URL del programma e flussi di clic </li> 
    </ul> Questi rapporti possono essere filtrati in un determinato periodo (ad es. tre mesi, sei mesi, ecc.). È inoltre possibile filtrare i rapporti delle campagne.<br /> Consulta la documentazione <a href="../../reporting/using/about-dynamic-reports.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: <strong>Email delivery</strong> activity<br /> </td> 
   <td> The <strong>Email delivery</strong> activity in the workflows has been improved. Ora potete trovare e-mail, e-mail ricorrenti e informazioni dettagliate sulle esecuzioni e-mail ricorrenti dall'elenco delle attività di marketing delle applicazioni.<br /> Consulta la documentazione <a href="../../automating/using/email-delivery.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: <strong>Segmentation</strong> activity<br /> </td> 
   <td> The <strong>Segmentation</strong> activity is now available in the workflows. Questa attività consente di creare uno o più segmenti e di collegare un codice di segmento a una popolazione calcolata in base a attività disposte a monte nello stesso flusso di lavoro. Da questa attività, i segmenti possono essere elaborati in una singola transizione o in più transizioni multiple. Ora sono disponibili opzioni per filtrare la popolazione e limitare le dimensioni di ogni segmento per ottimizzare la personalizzazione. Ad esempio, potete selezionare in modo casuale profili corrispondenti a criteri specifici.<br /> Consulta la documentazione <a href="../../automating/using/segmentation.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrations: <strong>Assets Core Service</strong><br /> </td> 
   <td> You can now use shared resources via <strong>Assets Core Service</strong> in your email and landing page contents. Potete gestire le risorse condivise direttamente da Adobe Marketing Cloud.<br /> Consulta la documentazione <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrations: <strong>Adobe Target</strong><br /> </td> 
   <td> You can now insert images that are dynamically computed by <strong>Adobe Target</strong> into your Adobe Campaign emails. Questo consente di offrire diverse versioni della stessa e-mail personalizzate in base ai criteri definiti nei segmenti di Adobe Target.<br /> Consulta la documentazione <a href="../../integrating/using/about-campaign-target-integration.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor: <strong>Block selector</strong><br /> </td> 
   <td> Quando un blocco è selezionato nell'editor di contenuto HTML, un breadcrumb viene visualizzato nella parte inferiore del fuso orario. Questo consente di navigare con facilità e selezionare elementi diversi.<br /> Consulta la documentazione <a href="../../designing/using/managing-landing-page-structure-and-style.md">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Release 15.3 - March 2015 {#release-15-3---march-2015}

### New capabilities {#new-capabilities-15}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> È ora possibile accedere ai rapporti direttamente da un programma o una campagna. The <strong>Delivery summary</strong> report has been added at a program level.<br /> Consulta la documentazione <a href="../../reporting/using/delivery-summary.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Update data<br /> </td> 
   <td> In the workflows, the available <strong>Update data</strong> activity has a new option, which allows you to automatically link inbound data fields with the fields of an application schema. Questo facilita il processo di selezione per l'aggiornamento dei campi.<br /> Consulta la documentazione <a href="../../automating/using/update-data.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email delivery<br /> </td> 
   <td> In workflows, the advanced options of the <strong>Email delivery</strong> activity can now be accessed via a specific button in the action bar. This button is only available if an <strong>Email delivery</strong> activity is selected. Il vantaggio principale è che consente di aggiungere una transizione in uscita all'attività e di modificare il nome dell'attività così come viene visualizzata nel flusso di lavoro.<br /> Consulta la documentazione <a href="../../automating/using/email-delivery.md">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-14}

#### General {#general-10}

* Risolto un errore che impediva la visualizzazione del destinatario durante la creazione di una consegna.
* Risolto un errore che impediva l'utilizzo di un'audience basata su un'altra condizione «Destinatari che hanno aperto».
* Risolto un errore che impediva l'eliminazione di un profilo vuoto.
* È stato corretto un errore che si verificava durante l'anteprima di una consegna.
* Risolto un errore che impediva la duplicazione di un'attività di marketing.
* Risolto un errore che si verificava durante l'eliminazione di una campagna.

