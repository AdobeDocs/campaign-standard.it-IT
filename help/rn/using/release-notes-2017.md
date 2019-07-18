---
title: Note sulla versione 2017
seo-title: Note sulla versione 2017
description: Note sulla versione 2017
seo-description: In questa pagina sono elencate tutte le versioni 2017 di Adobe Campaign Standard.
page-status-flag: never-activated
uuid: d 73 f 8186-e 309-441 b -969 d -71 d 0 a 1 c 33 cf 4
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: riferimento
topic-tags: campaign-standard-release
discoiquuid: 1 cfd 9 b 3 b -9 b 3 e -4587-9 c 46-b 6 fb 02131654
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Release Notes 2017{#release-notes}

Stai cercando una versione specifica di Adobe Campaign Standard 2017?

Ogni rilascio viene fornito con nuove funzionalità e patch. Fate clic su una versione per visualizzarne il contenuto.

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 17.10 - October 2017 {#release-17-10---october-2017}

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
   <td> Fatigue Management<br /> </td> 
   <td> Fatigue Management consente di creare regole di affaticamento per gestire la comunicazione con i profili. Le regole di fatigue sono facilmente create, ma sono estremamente flessibili grazie a funzionalità quali il conteggio dei messaggi su più canali (inclusi i messaggi transazionali), il conteggio solo di specifici invii o l'applicazione di regole a profili specifici.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/fatigue-rules.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Content creation: Import from a URL<br /> </td> 
   <td> L'importazione da un URL consente di recuperare rapidamente i contenuti creativi da un sito Web per creare e-mail per qualsiasi tipo di distribuzione. Inoltre, potete semplificare il processo creativo consentendo a terze parti di condividere direttamente i contenuti tramite un URL. Il contenuto importato può essere utilizzato in modo flessibile come parte di una singola consegna o a livello di modello, garantendo la coerenza del marchio per tutte le campagne correlate, sia che si tratti di messaggi basati su flusso di lavoro che di transazioni, e includa test A/B o multivariati. L'importazione da un URL converte e tiene traccia automaticamente di tutti i collegamenti per monitorare le prestazioni e-mail tramite Reporting dinamico.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../designing/using/importing-content-from-a-url.md">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches}

#### Platform {#platform}

* È stato risolto un problema che poteva impedire la corretta decompressione dei file compressi di grandi dimensioni.
* È stata migliorata la sicurezza nella gestione del marchio. La modifica del nome e dell'indirizzo del mittente è ora riservato agli amministratori tecnici di Adobe.
* Per migliorare la sicurezza, il contenuto generato dall'utente (immagini, pagine speculari, pagine di destinazione ecc.) non può più essere servita dal dominio adobe.com. È ora obbligatorio utilizzare il proprio dominio per gestire queste risorse, utilizzando il marchio.
* È stato risolto un problema di interfaccia durante la visualizzazione e il filtro delle attività di marketing.
* È stato risolto un problema che impediva l'aggiornamento dei campi data di iscrizione con una chiamata POST Rest.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail}

* È stato corretto un problema a causa del quale, se si effettuava il targeting di un'audience di tipo elenco in un messaggio, la preparazione non andava a buon fine.
* Lingue mancanti aggiunte nelle funzionalità di consegna delle e-mail in più lingue.
* La miniatura del contenuto, visualizzata sul dashboard di distribuzione, ora viene aggiornata automaticamente quando l'utente modifica il contenuto e salva.
* Risolto un problema correlato alla zona temporale che impediva l'apertura di una consegna.

#### Push notifications {#push-notifications}

* When configuring the push notification channel, the push provider platform for iOS should be **apns** and for Android **gcm**.
* Risolto un errore che impediva l'aggiunta dell'app mobile iOS nell'interfaccia Adobe Campaign.
* Le notifiche push ora sono supportate sia nelle applicazioni mobili Android che utilizzano GCM che FCM.
* Risolto un errore che impediva il salvataggio del contenuto durante la duplicazione di un modello di notifica push.
* Ora è possibile creare o aggiornare un profilo dal database Adobe Campaign riconciliando i dati degli utenti delle applicazioni mobili.
* Adobe Campaign ora stabilisce la priorità dell'elaborazione delle notifiche push transazionali attraverso notifiche push standard.

#### Reports {#reports}

* È stato risolto un problema che impediva la visualizzazione delle percentuali di clic sul contenuto dell'e-mail.
* È stato risolto un problema relativo alla metrica blacklist conteggiata come rimbalzo netto anziché rimbalzo.
* È stato risolto un problema che causava la visualizzazione di conteggi negativi nei dati di riepilogo.
* È stato risolto un problema che causava il conteggio dei profili nel segmento di età errato.
* Sono state modificate le formule di calcolo leggero e netto di rimbalzo.

#### Workflows {#workflows}

* Fixed an issue in the **[!UICONTROL Load file]** activity that could lead to errors after manually adding and removing columns in the activity.
* The **[!UICONTROL deliverabilityUpdate]** technical workflow is now scheduled to run at 2am, server time.
* È stato corretto un problema di sicurezza che consentiva l'esportazione di un elenco senza il ruolo di esportazione.
* Fixed an issue with the **[!UICONTROL Reconciliation]** activity.
* Fixed an issue with the use of wildcard characters in the **[!UICONTROL File Transfer]** activity.

#### Profiles and audiences {#profiles-and-audiences}

* È stato risolto un problema che poteva impedire la corretta partecipazione di una query in alcuni casi specifici, comportando risultati erronei.
* È stato risolto un problema che impediva l'accesso ai profili se questi erano stati impostati come destinazione in un messaggio preparato ma non mai inviato e scaduto.

#### Integrations {#integrations}

* È stato risolto un problema che poteva impedire la visualizzazione e la selezione corretta di alcune Origini dati create per Triggers.

#### Custom resources {#custom-resources}

* È stato risolto un problema che si verificava nelle schermate dell'elenco in cui le righe di risorse personalizzate potevano essere visualizzate senza dati.
* È stato risolto un problema che impediva la visualizzazione di campi booleani con valore "False" nelle risorse personalizzate.

## Release 17.9 - September 2017 {#release-17-9---september-2017}

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
   <td> Library of Email templates<br /> </td> 
   <td> Ecco altri diciotto modelli reattivi progettati in due fantastici temi: Astro e Feather. Questi modelli personalizzabili sono agnostici del settore e pronti per essere utilizzati. I modelli includono contenuti per diversi casi di utilizzo per rendere le campagne di marketing e-mail progettate e distribuite in modo più rapido, efficiente e straordinario che mai.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../start/using/about-templates.md#content-templates">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic Reporting with Profile Data<br /> </td> 
   <td> La funzione di reporting dinamico fornisce rapporti aziendali completamente personalizzabili e in tempo reale. Con questa release, una potente funzione di reporting dinamico consente di accedere ai dati di profilo, consentendo l'analisi demografica in base a dimensioni del profilo quali genere, città, codice postale ed età, oltre a dati di campagna e-mail funzionali come aperture e clic. Grazie alla stessa intuitiva interfaccia di trascinamento, è più facile che mai determinare la campagna e-mail eseguita rispetto ai segmenti di clienti più importanti.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../reporting/using/about-dynamic-reports.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mass Subscription with Origin &amp; Date<br /> </td> 
   <td> Con questo miglioramento di iscrizione di massa, ora è possibile archiviare le informazioni di iscrizione (origine e data) direttamente nel database Adobe Campaign Standard tramite l'attività Servizi iscrizione in un flusso di lavoro.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/subscription-services.md">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-1}

#### Platform {#platform-1}

* Alcuni clienti devono essere in grado di sfruttare un ID proveniente da Adobe Campaign Standard in quanto non gestiscono una chiave univoca per identificare i propri record. This ID (**ACS ID**) can be exported as well as used as a reconciliation key while updating the data. For more information, refer to the [detailed documentation](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* Il protocollo FTP è obsoleto. Ora è necessario utilizzare l'SFTP. Per non bloccare le implementazioni esistenti, le configurazioni esistenti sull'FTP continueranno a funzionare come prima, ma l'opzione non verrà visualizzata per le nuove attività.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-1}

* È ora possibile creare nuovi criteri di avviso per utilizzarli nelle notifiche di avviso sulla distribuzione. For more information, refer to the [detailed documentation](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Le notifiche relative agli avvisi sulla distribuzione hanno una nuova progettazione e l'esperienza dell'utente della dashboard è stata migliorata.
* Now when a routing external account is disabled, a warning is displayed in the impacted deliveries (email, SMS and push) and the **Preview** button is hidden in these deliveries.
* È stato risolto un problema che causava un errore nell'anteprima di un test A/B sul contenuto e-mail quando il testo dinamico era abilitato nell'oggetto.

#### Transactional messages {#transactional-messages}

* Ora è possibile definire quando si desidera inviare un messaggio di follow-up, ad esempio 3 giorni dopo l'invio di un messaggio. For more information, refer to the [detailed documentation](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* È ora possibile definire la data in cui i messaggi transazionali collegati a un evento devono essere inviati.
* Risolto un problema che causava un errore SQL durante l'esecuzione di un flusso di lavoro contenente un messaggio di follow-up dopo l'eliminazione di profili collegati a eventi ricevuti ed elaborati.
* Risolto un errore che impediva di eliminare un profilo collegato a un evento.
* È stato risolto un problema che poteva impedire la reindirizzamento dei collegamenti tracciati.
* È stato risolto un problema che impediva di disattivare il tracciamento per alcuni collegamenti in un messaggio e-mail o SMS.

#### Reports {#reports-1}

* The **Hot clicks** report has been improved. Inoltre, è possibile visualizzare i clic attivi in base a ciascun contenuto condizionale definito in una consegna e per visualizzare clic su ogni esecuzione di consegne ricorrenti o messaggi transazionali. For more information, refer to the [detailed documentation](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* È stato risolto un problema che impediva al dato di quarantena di recuperare dati corretti.
* È stato aggiunto un nuovo intervallo di tempo predefinito al widget calendario.
* The [dynamic report metrics](../../reporting/using/indicator-calculation.md) and the [campaigns' KPIs](../../sending/using/confirming-the-send.md) (displayed on the dashboard of sent messages) have been aligned for more coherence.
* È stato risolto un problema che poteva causare l'arresto anomalo di pipeline su debian 7.

#### Workflows {#workflows-1}

* È stato risolto un problema che poteva impedire il funzionamento della conservazione dei file importati.

#### Integrations {#integrations-1}

* Ora sono supportati evar ed eventi per l'integrazione di Analytics e Campaign.
* Quando si invia un'e-mail con il contenuto del carrello abbandonato, il parametro di payload degli elementi rimossi dal carrello è ora facoltativo.

#### Profiles and audiences {#profiles-and-audiences-1}

* Adobe Campaign fornisce ora un rapporto che mostra il numero di profili attivi. Questo rapporto è solo informativo, non ha un impatto diretto sulla fatturazione. For more information, refer to the [detailed documentation](../../audiences/using/active-profiles.md).
* È stato risolto un problema che impediva la sottoscrizione dei profili a un servizio quando si utilizzavano Profili e API di Servizi.

## Release 17.7 - July 2017 {#release-17-7---july-2017}

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
   <td> Multilingual email and SMS deliveries<br /> </td> 
   <td> Puoi definire ed eseguire le consegne e-mail e SMS in più lingue tramite una singola distribuzione basata sulla lingua preferita dei clienti specifici dei clienti. Segnala le prestazioni di ogni distribuzione fino alla lingua e ai singoli livelli.<br /> Un numero sempre maggiore di aziende si occupa della distribuzione del contenuto in più lingue, che crescono in casa e all'estero. Di conseguenza, la semplificazione della distribuzione dei messaggi localizzati è una parte fondamentale di una strategia efficace di comunicazione dei clienti per le multinazionali, aziende di paesi con più lingue, e aziende che desiderano personalizzare ulteriormente i contenuti a livello di lingua, a prescindere dalla posizione dei clienti. For more information, refer to the <a href="../../channels/using/creating-a-multilingual-email.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign Notifications<br /> </td> 
   <td> Ricevi notifiche su importanti attività di sistema direttamente in Adobe Campaign Standard. Ti verrà notificato, ad esempio, l'avanzamento delle distribuzioni in corso o quando un flusso di lavoro viene visualizzato in un errore.<br /> Le notifiche in tempo reale tengono informati gli interessati e forniscono agli utenti la possibilità di intervenire immediatamente e direttamente sulle notifiche dell'attività dall'interno dell'applicazione. Il risultato per i team è l'agilità avanzata, l'efficienza e l'esecuzione più fluida delle campagne. For more information, refer to the <a href="../../administration/using/sending-internal-notifications.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery Alerting<br /> </td> 
   <td> Oltre a visualizzare le notifiche direttamente in Adobe Campaign Standard, Adobe Campaign fornisce anche un sistema di avvisi e-mail per attivare avvisi e-mail agli utenti o alle parti interessate esterne di importanti attività del sistema. Puoi creare, gestire e ricevere avvisi personalizzabili e dashboard per tenere traccia dei successi e degli errori della distribuzione.<br /> L'Informativa sulla distribuzione di Adobe Campaign aumenta l'efficienza, mantenendo tutti gli utenti Adobe Campaign coinvolti in una società automaticamente informati sullo stato di esecuzione, tramite e-mail e dashboard. For more information, refer to the <a href="../../sending/using/receiving-alerts-when-failures-happen.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Encrypted Declared ID in Datasources<br /> </td> 
   <td> Per inviare attivatori e-mail e SMS senza necessità di un profilo esistente in Campaign, utilizzate informazioni di contatto crittografate (indirizzo e-mail o numero di telefono) come ID dichiarato. Dato che gli ID dichiarati crittografati possono essere decodificati da Adobe Campaign Standard, Campaign ora può creare nuovi profili marketing quando ricevi tipi di pubblico da altre soluzioni Experience Cloud contenenti contatti precedentemente sconosciuti.<br /> Esegui in tempo reale i clienti e i potenziali clienti non noti sia tramite e-mail che SMS per migliorare fedeltà nella base clienti esistente e acquisire nuovi clienti rispettivamente. Sfrutta al massimo i dati dei cookie di prime parti (da Adobe Audience Manager *) quando i potenziali clienti si autenticano e sfruttano tali informazioni in Adobe Campaign. <br /> * È necessario Adobe Audience Manager. For more information, refer to the <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> KPI sharing from Campaign to Analytics<br /> </td> 
   <td> Condividi i dati della campagna con Adobe Analytics per misurare le metriche marketing e-mail da Campaign, insieme ad altre iniziative pubblicitarie e pubblicitarie attraverso la conversione, unificando il comportamento pre e post clic.<br /> Consente di tenere traccia direttamente delle prestazioni complessive e di individuare sinergie con programmi esterni in Analytics. Applica le tue conoscenze da questa visualizzazione consolidata alle campagne; in definitiva, il miglioramento dei tassi di apertura, click-through e conversione aumenta i profitti e le prestazioni complessive delle campagne. <br /> Adobe Analytics è obbligatorio. For more information, refer to the <a href="../../integrating/using/about-campaign-analytics-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Direct Mail Channel - Return To Sender<br /> </td> 
   <td> Sono ora supportati gli scambi di file flat con provider di servizi di Direct Mail che includono le informazioni sul mittente. Questo miglioramento al canale Direct Mail consente di escludere gli indirizzi postali corrispondenti dalle comunicazioni future.<br /> Questo consente agli esperti di marketing di ricevere notifiche di un indirizzo errato e di contattare il cliente attraverso altri canali o di incoraggiarlo ad aggiornare l'indirizzo postale. Ciò riduce anche il numero di dollari di marketing sprecato mentre gli esperti di marketing evitano di inviare e-mail a indirizzi non corretti. <br /> Direct Mail è disponibile come canale aggiuntivo. For more information, refer to the <a href="../../channels/using/return-to-sender.md">detailed documentation</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-2}

#### General {#general}

* È stato risolto un problema che consentiva a qualsiasi elenco di esportare gli elenchi. Now only users with the **[!UICONTROL Export]** role are allowed to.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-2}

* Fixed an issue with the **updateDeliveryExecInfo** workflow that set the **To deliver** indicator to 0 for SMS deliveries.
* In the **Advanced parameters** of the delivery template’s properties, the **Routing** drop-down list now only displays external accounts corresponding to the template message type. Ad esempio, un modello di consegna tramite e-mail visualizza solo gli account esterni e-mail.
* Fixed an issue with the **[!UICONTROL Text]** preferred email format defined for test profiles.
* È stato risolto un problema che causava un errore Javascript nel momento in cui si selezionava il fuso orario predefinito nella schermata di definizione della pianificazione di una consegna.
* È stato risolto un problema che impediva la visualizzazione delle abbondanze nei registri di invio.
* Nella schermata di selezione dei modelli della procedura guidata di creazione della distribuzione, i modelli di follow-up e test A/B sono ora nascosti per impostazione predefinita. For more information, refer to the [detailed documention](../../channels/using/creating-an-email.md).
* È stato risolto un problema che consentiva a qualsiasi utente di inviare le consegne. Now only users with the **[!UICONTROL Start deliveries]** role are allowed to. For more information, refer to the [detailed documention](../../sending/using/confirming-the-send.md).

#### Push notifications {#push-notifications-1}

* Fixed an issue with the **Campaign Tracking Endpoint** URL that prevented reporting.
* È stato risolto un problema che impediva la visualizzazione del titolo della notifica push sui dispositivi Android.
* È stato risolto un problema che impediva la visualizzazione della notifica push sui dispositivi iOS quando la notifica push conteneva solo un titolo (e nulla nel corpo del messaggio).
* È stato risolto un problema che impediva il tracciamento degli URL allegati per supporti in una consegna, che impediva la incorporazione di video e immagini nella distribuzione. Il tracciamento degli URL del tipo mediaattachmenturl è ora disattivato per impostazione predefinita per le notifiche push.

#### Reports {#reports-2}

* È stato corretto un problema a causa del quale i valori venivano visualizzati diversi tra grafici e tabelle.
* Risolto un problema che mostrava valori di notifica push come valori e-mail.
* È stato risolto un problema che causava la visualizzazione di valori sconosciuti quando una consegna veniva creata all'esterno di una campagna.
* Risolto un problema che mostrava i dati del rapporto SMS come dati dell'applicazione mobile.

#### Workflows {#workflows-2}

* Ora potete filtrare i registri di flusso di lavoro (periodo di tempo e ricerca del testo). For more information, refer to the [detailed documention](../../automating/using/executing-a-workflow.md#monitoring).
* È ora disponibile un'opzione nelle consegne del flusso di lavoro per disattivare la conferma prima dell'invio.
* È stato risolto un problema che impediva l'impostazione di una transizione in uscita nella procedura guidata di creazione della distribuzione periodica.
* È stato risolto un problema che si verificava quando si utilizzava un'attività di query di workflow basata su un campo di risorse personalizzato con un'enumerazione che aveva molti valori.

## Release 17.5 - May 2017 {#release-17-5---may-2017}

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
   <td> Direct mail<br /> </td> 
   <td> Interagisci con la barriera digitale e connettiti al mondo fisico con il primo canale offline di Adobe Campaign Standard, Direct Mail. Questa funzione consente di personalizzare e generare il file richiesto dai provider di posta diretta come parte delle campagne multicanale. Utilizza Posta diretta per coinvolgere nuovamente i clienti o per migliorare la customer experience con un efficace punto di contatto tattile che indirizza i clienti all'app, al sito Web o allo store.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-direct-mail.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email BCC<br /> </td> 
   <td> Ccn e-mail consente di salvare messaggi e-mail univoci inviati a singoli destinatari, consentendo così al marchio di archiviarli. Aggiungendo un indirizzo e-mail Ccn a tutte le e-mail, i clienti Adobe Campaign Standard possono conservare una copia esatta di ogni e-mail con questa funzione. Si tratta di un requisito legale comune per il settore dei servizi finanziari ed è utile per aiutare i centri dei clienti a risolvere i conflitti in tempo reale.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/configuring-email-channel.md#archiving-emails">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-3}

#### Interface updates {#interface-updates}

* In the top bar, the **[!UICONTROL Timeline]** link has been removed and replaced with a link to **[!UICONTROL Programs & Campaigns]** .

#### Emails and SMS messages {#emails-and-sms-messages}

* Fixed an issue which displayed the wrong color for the **[!UICONTROL Retry in progress]** delivery status. Il colore era grigio invece di blu.

#### Workflows {#workflows-3}

* Fixed an issue that occurred when changing the action to perform in a **[!UICONTROL Transfer file]** activity.

#### Reports {#reports-3}

* The **[!UICONTROL Spam]** and **[!UICONTROL Spam rate]** indicator calculations have been changed.
* The **[!UICONTROL Bounce]** metrics have been improved for a more accurate result.

#### Push notifications {#push-notifications-2}

* È stato risolto un problema che impediva di fare clic su un evento push nella cronologia di marketing di un profilo.
* L'utilizzo delle notifiche push nei flussi di lavoro è stato migliorato.

## Release 17.4 - April 2017 {#release-17-4---april-2017}

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
   <td> Enhanced Image edition capabilities with the Creative SDK<br /> </td> 
   <td> Ora puoi accedere a un set completo di funzioni di Creative SDK per migliorare le immagini direttamente nell'editor contenuto quando si modificano e-mail o pagine di destinazione.<br /> Questa funzione non richiede l'acquisizione di soluzioni Creative Cloud aggiuntive.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../designing/using/modifying-images-with-the-adobe-creative-sdk.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional push notifications<br /> </td> 
   <td> Il canale dell'applicazione Mobile è stato aggiunto alle funzionalità di messaggistica transazionali di Adobe Campaign. Sono ora supportati tre canali per i messaggi transazionali: e-mail, SMS e notifiche push.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/transactional-push-notifications.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recurring push notifications<br /> </td> 
   <td> Ora puoi configurare notifiche push ricorrenti in un flusso di lavoro. Potete utilizzare notifiche push ricorrenti in situazioni in cui i clienti si aspettano aggiornamenti periodici come promemoria settimanale per ritirare nuovi contenuti o promozioni.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/push-notification-delivery.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple Storage Service (S3) connector<br /> </td> 
   <td> Ora è possibile utilizzare il connettore Amazon S 3 (Amazon) per importare o esportare dati in Adobe Campaign. Può essere configurato in un'attività del flusso di lavoro. La configurazione viene effettuata in un account esterno.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/external-accounts.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver integration live<br /> </td> 
   <td> L'integrazione tra Adobe Campaign e Dreamweaver è ora live. Ora funziona con l'ultima versione ufficiale di Dreamweaver (17.0.2).<br /> Richiede l'installazione dell'estensione Integrazione di Adobe Campaign da qui: <a href="http://adobe.ly/acdw_addon">http://adobe.ly/acdw_addon</a><br /> Per ulteriori informazioni, consultate questo <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">video</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-4}

#### Platform {#platform-2}

* Risolto un problema di consumo della memoria.

#### Emails and SMS messages {#emails-and-sms-messages-1}

* È stato risolto un problema che impediva la corretta sincronizzazione del contenuto con le modifiche più recenti durante l'anteprima di un messaggio.
* È stato risolto un problema che impediva la creazione o l'eliminazione di una regola di elaborazione e-mail MX o Dominio.
* È stato risolto un problema che impediva l'invio di e-mail con più alias.
* È stato risolto un problema che impediva la visualizzazione dei registri di distribuzione delle abbondanze nei registri di invio.
* È stato risolto un problema che causava un errore durante la visualizzazione degli URL tracciati di una consegna senza URL nel relativo contenuto.
* È stato risolto un problema che impediva l'applicazione corretta degli attributi delle dimensioni di un'immagine nel messaggio inviato.

#### Transactional messages {#transactional-messages-1}

* Il campo rteventhistoid non viene più esposto come campo di personalizzazione in un modello di messaggio transazionale.

#### Landing pages {#landing-pages}

* We have optimized the **[!UICONTROL by email]** filter used in landing pages to reconcile new subscribers with database profiles.
* È stato risolto un problema che causava l'immissione di input di testo gratuiti invece delle caselle di controllo quando venivano utilizzati campi booleani in una configurazione di modulo.
* È stato risolto un problema che impediva la generazione delle miniature delle pagine di destinazione.

#### Workflows {#workflows-4}

* Fixed a display error when editing an **[!UICONTROL End]** or **[!UICONTROL External Signal]** activity (on Safari only).
* Improved the error message displayed when editing a **[!UICONTROL Read Audience]** activity containing an erroneous audience.
* È stato risolto un problema che poteva causare un errore SQL durante l'esecuzione di un'attività di iscrizione.

#### Integrations {#integrations-2}

* Dati dei punti di interesse: È stato corretto un errore che si verificava durante il conteggio degli abbonati alla posizione.

#### Audiences and queries {#audiences-and-queries}

* È stato risolto un problema che impediva l'utilizzo di aggregati e aggregati medi in una raccolta nell'editor query.
* È stato risolto un problema che poteva impedire il ricaricamento dell'editor query dopo la modifica della risorsa del filtro.

#### Reports {#reports-4}

* È stato risolto un problema che impediva il calcolo corretto delle metriche di tasso di apertura durante la selezione di più righe in una tabella.
* Risolto un errore che mostrava solo le metriche come valori interi. Ora è possibile visualizzare metriche con decimali.

#### Push notifications {#push-notifications-3}

* È stato risolto un problema che impediva la visualizzazione di un messaggio di errore durante la creazione di un'applicazione Android collegata a un'app mobile non creata in MCPNS.
* È stato risolto un problema che consentiva a un utente di aggiungere suoni a una notifica invisibile.

## Release 17.2 - March 2017 {#release-17-2---march-2017}

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
   <td> Dynamic reporting<br /> </td> 
   <td> Dynamic Reporting (Generazione di rapporti dinamica) fornisce una nuova generazione di rapporti aziendali completamente personalizzabili e in tempo reale. In base a tabelle pivot e grafici dinamici, questa funzione consente di trascinare variabili e dimensioni per analizzare l'efficienza e l'efficacia delle campagne di marketing. La funzione di reporting dinamico consente anche di creare rapporti aziendali personalizzati da zero e di salvarli per un uso successivo.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../reporting/using/about-dynamic-reports.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver integration (Labs)<br /> </td> 
   <td> Con l'integrazione di Adobe Campaign e Dreamweaver, ora è disponibile un processo integrato per la creazione di campagne e-mail con le soluzioni Adobe.<br /> Puoi modificare le e-mail di Adobe Campaign in Dreamweaver e avere i contenuti sincronizzati senza soluzione di continuità tra entrambe le soluzioni.<br /> Per la release iniziale, l'integrazione è disponibile come funzione "Labs" e funziona solo con la versione beta preliminare di Dreamweaver. Se desiderate attivarlo, contattate AC-DW-integration@adobe.com.<br /> Per ulteriori informazioni, consultate questo <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">video</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Manual send time optimization<br /> </td> 
   <td> Ora puoi definire manualmente un'ora di invio personalizzata per destinatario, a livello di consegna o tramite un flusso di lavoro. <br /> Sono disponibili due nuove opzioni: <br /> 
    <ul> 
     <li> Tutti i destinatari ricevono il messaggio con il fuso orario considerato. </li> 
     <li> Ogni destinatario riceve il messaggio in una data e in un'ora calcolate definite da una formula. </li> 
    </ul> For more information, refer to the <a href="../../sending/using/optimizing-the-sending-time.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push notifications New capabilities<br /> </td> 
   <td> The push notification channel has been enhanced with several new capabilities:<br /> 
    <ul> 
     <li> Nuova interfaccia di authoring </li> 
     <li> Notifiche silenziose </li> 
     <li> Push interattivo </li> 
     <li> Supporto per contenuti avanzati </li> 
     <li> Calcolatore dimensioni payload </li> 
    </ul> For more information, refer to the <a href="../../channels/using/about-push-notifications.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: new Signal activity<br /> </td> 
   <td> Trigger a workflow from another workflow using the new <span class="uicontrol">Signal</span> activity.<br /> Grazie alla capacità di avviare un flusso di lavoro da un altro, ora puoi supportare percorsi cliente più complessi. Puoi monitorare meglio i percorsi dei clienti e reagire in caso di problemi.<br /> Sono state aggiornate diverse attività del flusso di lavoro:<br /> 
    <ul> 
     <li> <span class="uicontrol">End</span> activity: una nuova scheda consente di specificare un flusso di lavoro da attivare dopo l'esecuzione dell'attività. </li> 
     <li> <span class="uicontrol">Aggiorna</span> attività dati: utilizzate la nuova transizione in uscita vuota per aggiungere un'attività <strong>finale</strong> che attiva un altro flusso di lavoro. Le transizioni vuote in uscita non contengono dati e non occupano spazio inutile sul sistema </li> 
    </ul> For more information, refer to the <a href="../../automating/using/external-signal.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: new Read audience activity<br /> </td> 
   <td> Avviate il processo di targeting con un'audience esistente che potete selezionare e perfezionare facilmente in un'unica attività.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/read-audience.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest data<br /> </td> 
   <td> I dati dei punti di interesse integrano Adobe Campaign con Adobe Analytics per dispositivi mobili. A brand can collect data from users' mobile locations - called <strong>Points of Interest</strong> - when users open the brand's app. Questo consente al marchio di sfruttare i flussi di lavoro di Adobe Campaign per inviare messaggi personalizzati in base alle posizioni degli utenti. Questo canale sfrutta l'SDK del servizio di base Mobile.<br /> Nota: per utilizzare questa funzione è necessario disporre di Analytics per dispositivi mobili, una soluzione a pagamento.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> REST APIs<br /> </td> 
   <td> Le risorse collegate a qualsiasi livello ai profili o alle risorse dei servizi sono ora disponibili nell'API.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### General {#general-1}

* Ora è possibile aggiungere dati di profilo durante l'esportazione di registri di consegna.

#### Emails and SMS messages {#emails-and-sms-messages-2}

* Fixed an issue causing the **[!UICONTROL Request confirmation before sending messages]** option to remain selected even after unchecking it and saving the delivery.
* È stato risolto un problema che poteva impedire la pubblicazione di e-mail transazionali.
* È stato risolto un problema che impediva la corretta sincronizzazione del contenuto con le modifiche più recenti prima dell'anteprima di una consegna.

#### Landing pages {#landing-pages-1}

* Risolto un errore che impediva la modifica di un utente quando si faceva clic sul contenuto di una pagina di destinazione.

#### Workflows {#workflows-5}

* Fixed an issue that could prevent from reading the content of the reject transition of a **[!UICONTROL Load file]** activity.
* Fixed an issue that prevented swapped columns to be properly taken into account when configuring a **[!UICONTROL Load file]** activity.

## Release 17.1 - January 2017 {#release-17-1---january-2017}

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
   <td> Log export for external reporting<br /> </td> 
   <td> Esporta registri quali la consegna e i registri di tracciamento per elaborarli nei tuoi strumenti di reporting o BI preferiti. Potete utilizzare flussi di lavoro semplici con query incrementali per automatizzare le esportazioni regolari dei nuovi registri.<br /> Oltre alla disponibilità di risorse di registro dal selettore risorse, sono stati apportati miglioramenti alle attività <a href="../../automating/using/incremental-query.md">di query</a> incrementali ed <a href="../../automating/using/extract-file.md">Estrazione</a> :<br /> 
    <ul> 
     <li> <span class="uicontrol">La query incrementale</span> ora consente di utilizzare un campo data per recuperare dati nuovi o aggiornati. Precedentemente, tutti i risultati delle esecuzioni precedenti venivano esclusi automaticamente, anche se venivano aggiornati dall'ultima esecuzione. </li> 
     <li> <span class="uicontrol">Il file</span> Extract ora può esportare etichette per i valori di enumerazione invece di ID. </li> 
    </ul> Queste attività sono disponibili per gli amministratori che hanno accesso a tutte le unità geografiche e org.<br /> Per ulteriori informazioni sull'esportazione dei registri, consulta la documentazione <a href="../../automating/using/exporting-logs.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Marketing capabilities for transactional messages<br /> </td> 
   <td> Gli addetti al marketing possono inviare messaggi transazionali basati sui profili di marketing dei clienti. This allows them to:<br /> 
    <ul> 
     <li> Apply marketing typology rules such as <span class="uicontrol">Blacklisted address</span> . </li> 
     <li> Includi il collegamento di annullamento iscrizione all'interno dei messaggi. </li> 
     <li> Aggiungete i messaggi transazionali al reporting globale della distribuzione. </li> 
     <li> Sfrutta i messaggi transazionali nel percorso del cliente. </li> 
    </ul> For more information, refer to the <a href="../../channels/using/profile-transactional-messages.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional Messaging API<br /> </td> 
   <td> The Transactional Messaging API is now available through <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, making it easier to use and to monitor:<br /> 
    <ul> 
     <li> Potete trarre vantaggio dalle funzionalità di reporting e monitoraggio delle piattaforme adobe. io. </li> 
     <li> L'autenticazione viene ora eseguita utilizzando l'autenticazione basata sui token adobe. io, anziché la whitelist IP, rendendo il processo di protezione più semplice. </li> 
     <li> Tutte le API ora sono integrate su una singola piattaforma, rendendo più semplice che mai aggiungere funzionalità di messaggistica transazionali all'integrazione se già supportate l'API Profilo e Servizi. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### General {#general-2}

* The **[!UICONTROL Access authorization]** options have returned to the landing page properties.
* È stato risolto un problema che potrebbe aver causato il rendering di una vecchia immagine invece dell'immagine corretta. Questo si verificava se l'immagine sorgente era stata aggiornata nella definizione del contenuto di una pagina di destinazione o di destinazione.
* È stato risolto un problema che impediva agli utenti di modificare alcuni campi in un account esterno SFTP esistente.
* Risolti diversi problemi dell'interfaccia utente. Ad esempio, gli utenti possono ora modificare gli attributi del profilo e salvare le modifiche senza problemi nell'interfaccia utente.

#### Emails and SMS messages {#emails-and-sms-messages-3}

* È stato risolto un problema relativo ai modelli di consegna con contenuto HTML contenente un

#### Push notifications {#push-notifications-4}

* È stato risolto un problema che potrebbe aver impedito il postback da un'applicazione al server Adobe Campaign.
* Fixed an issue that may have prevented **[!UICONTROL Play a sound]** and **[!UICONTROL Custom fields]** to be taken into account for Android.
* È stato risolto un problema che potrebbe aver causato l'aggiunta di un carattere di escape aggiuntivo ai caratteri Unicode utilizzati per Emojis.
* Quando il token di registrazione di un abbonato diventa in lista nera, lo stato corrispondente ora viene aggiornato immediatamente nell'elenco degli abbonati di Adobe Campaign.

#### Workflows {#workflows-6}

* È stato risolto un problema che potrebbe aver impedito anteprime di query sulle risorse dell'evento (ad es. rtevent).
* The reject file generated by a **[!UICONTROL Load file]** activity can now be retrieved in its outbound transition and processed in the next activity. For example, upload the reject file via an SFTP server using **[!UICONTROL Transfer file]** .
* Fixed an issue that may have prevented a user from limiting the population of a segment if **[!UICONTROL Temporary resource]** was selected in the **[!UICONTROL General]** tab of **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** le attività non possono più essere impostate per attivare un flusso di lavoro più volte ogni 10 minuti.
* Fixed an issue that may have prevented **[!UICONTROL Use common columns]** from working properly in an **[!UICONTROL Union]** activity.

#### Integrations {#integrations-3}

* È stato risolto un problema che potrebbe aver causato un errore durante la distribuzione di un trigger evento in Adobe Campaign. Questo errore si verificava quando i metadati «Probabilità di ritorno in 30 giorni» erano stati aggiunti al trigger di abbandono in Adobe Marketing Cloud.
* È stato risolto un problema che potrebbe aver causato che il flusso di lavoro tecnico cancelli il campo Dimensione Target durante l'importazione di audience dal servizio di base Persone. Le query successive non potevano recuperare le audience importate.
* Fixed an issue that may have caused the **[!UICONTROL Save audience]** activity of a workflow to fail when the option **[!UICONTROL Share in Adobe Marketing Cloud]** was checked.

