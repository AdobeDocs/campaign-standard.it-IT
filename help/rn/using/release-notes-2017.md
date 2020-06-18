---
title: Note sulla versione 2017
description: In questa pagina sono elencate tutte le versioni 2017 del Adobe Campaign Standard .
page-status-flag: never-activated
uuid: d73f8186-e309-441b-969d-71d0a1c33cf4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 1cfd9b3b-9b3e-4587-9c46-b6fb02131654
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 50c3188e1bc0eb92fd52637988834ce8538335a3
workflow-type: tm+mt
source-wordcount: '4631'
ht-degree: 5%

---


# Note sulla versione 2017{#release-notes}

Stai cercando una versione specifica del Adobe Campaign Standard  2017?

Ogni versione include nuove funzioni e patch. Fate clic su una versione per visualizzarne il contenuto.

Visualizza gli aggiornamenti [della](../../rn/using/documentation-updates.md) documentazione più recenti per  Adobe Campaign Standard. Per una versione più recente, consulta questa [pagina](../../rn/using/release-notes.md).

## Rilascio 17.10 - ottobre 2017 {#release-17-10---october-2017}

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
   <td> Fatigue Management<br /> </td> 
   <td> La funzione Fatigue Management consente di creare regole per la gestione della comunicazione eccessiva con i profili. Le regole di affaticamento sono facili da creare, ma sono estremamente flessibili con funzionalità quali conteggio dei messaggi su più canali (inclusi i messaggi transazionali), conteggio solo di consegne specifiche o applicazione di regole a profili specifici.<br /> Per ulteriori informazioni, consulta la <a href="../../sending/using/fatigue-rules.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creazione di contenuti: Importazione da un URL<br /> </td> 
   <td> L’importazione da un URL consente di recuperare rapidamente i contenuti creativi da un sito Web per creare e-mail per qualsiasi tipo di invio. Inoltre, potete semplificare il processo creativo consentendo a terze parti di condividere direttamente il contenuto tramite un URL. Il contenuto importato può essere utilizzato in modo flessibile come parte di un'unica consegna o a livello di modello, garantendo la coerenza del marchio per tutte le campagne correlate, siano esse basate su workflow o messaggi transazionali, e includendo test A/B o multivariati. L’importazione da un URL converte e tiene traccia automaticamente di tutti i collegamenti per monitorare le prestazioni delle e-mail tramite Dynamic Reporting (Generazione di rapporti dinamica).<br /> Per ulteriori informazioni, consulta la <a href="../../designing/using/using-existing-content.md#importing-content-from-a-url">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Platform_

* È stato risolto un problema che poteva impedire la corretta decompressione dei file ZIP di grandi dimensioni.
* La sicurezza nella gestione del marchio è stata migliorata. La modifica del nome e dell&#39;indirizzo del mittente di un marchio ora è riservata agli amministratori tecnici Adobe.
* Per migliorare la sicurezza, i contenuti generati dagli utenti (immagini, pagine mirror, pagine di destinazione, ecc.) non può più essere servito dal dominio adobe.com. È ora obbligatorio utilizzare il proprio dominio per gestire queste risorse, tramite l&#39;utilizzo del marchio.
* È stato risolto un problema di interfaccia durante la visualizzazione e il filtro delle attività di marketing.
* È stato risolto un problema che impediva l&#39;aggiornamento dei campi della data di iscrizione con una chiamata API POST Rest.

_E-mail, SMS e posta diretta_

* È stato risolto un problema che poteva impedire il targeting di un pubblico di tipo elenco in un messaggio, causando il fallimento della preparazione.
* Lingue mancanti aggiunte nelle funzionalità di distribuzione di e-mail in più lingue.
* La miniatura del contenuto, visualizzata sul dashboard di distribuzione, ora viene aggiornata automaticamente quando l&#39;utente modifica e salva il contenuto.
* È stato risolto un problema relativo al fuso orario che impediva l&#39;apertura di una consegna.

_Notifiche push_

* Quando si configura il canale di notifica push, la piattaforma del provider push per iOS deve essere **apns** e per Android **gcm**.
* È stato corretto un errore che impediva l&#39;aggiunta dell&#39;app mobile iOS nell&#39;interfaccia del Adobe Campaign .
* Le notifiche push ora sono supportate sia nelle applicazioni mobili Android con abilitazione GCM che nelle applicazioni mobili FCM.
* È stato corretto un errore che impediva il salvataggio del contenuto durante la duplicazione di un modello di notifica push.
* È ora possibile creare o aggiornare un profilo dal database del Adobe Campaign  riconciliando i dati degli utenti dell&#39;applicazione mobile.
*  Adobe Campaign ora dà priorità all&#39;elaborazione delle notifiche push transazionali rispetto alle notifiche push standard.

_Rapporti_

* È stato risolto un problema che impediva la visualizzazione delle percentuali di clic con il tasto di scelta rapida nel contenuto dell&#39;e-mail.
* È stato risolto un problema relativo alla metrica elenco blocchi che veniva conteggiata come rimbalzo rigido invece di rimbalzo.
* È stato risolto un problema che causava la visualizzazione dei conteggi negativi nei dati di riepilogo.
* È stato risolto un problema che causava il conteggio dei profili nel segmento di età errato.
* Le formule di calcolo soft e hard bounce sono cambiate.

_Flussi di lavoro_

* È stato risolto un problema nell&#39; **[!UICONTROL Load file]** attività che poteva causare errori dopo l&#39;aggiunta e la rimozione manuale delle colonne nell&#39;attività.
* Il flusso di lavoro **[!UICONTROL deliverabilityUpdate]** tecnico è ora pianificato per essere eseguito alle 2 del mattino, ora del server.
* È stato risolto un problema di sicurezza che consentiva di eseguire un&#39;esportazione di elenco senza il ruolo di esportazione.
* È stato risolto un problema relativo all&#39; **[!UICONTROL Reconciliation]** attività.
* È stato risolto un problema relativo all&#39;utilizzo di caratteri jolly nell&#39; **[!UICONTROL File Transfer]** attività.

_Profili e pubblico_

* È stato risolto un problema che poteva impedire che in alcuni casi specifici si tenesse correttamente conto di una condizione di una query, generando risultati erronei.
* È stato risolto un problema che impediva l&#39;accesso ai profili se questi venivano utilizzati come destinazione in un messaggio preparato ma mai inviato e scaduto.

_Integrazioni_

* È stato risolto un problema che poteva impedire la corretta visualizzazione e selezione di alcune origini dati create per gli attivatori.

_Risorse personalizzate_

* È stato risolto un problema che si verificava nelle schermate elenco per cui le righe di risorse personalizzate potevano essere visualizzate senza alcun dato.
* È stato risolto un problema che impediva la visualizzazione di campi di tipo booleano con valore &#39;False&#39; in risorse personalizzate.

## Rilascio 17.9 - settembre 2017 {#release-17-9---september-2017}

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
   <td> Libreria di modelli e-mail<br /> </td> 
   <td> Sono stati introdotti diciotto nuovi modelli reattivi creati in due splendidi temi: Astro e Feather. Questi modelli personalizzabili non sono agnostici del settore e sono pronti per essere utilizzati immediatamente. I modelli includono contenuti per una serie di casi di utilizzo per progettare e distribuire le campagne di e-mail marketing in modo più rapido, efficiente e perfetto che in passato.<br /> Per ulteriori informazioni, consulta la <a href="../../designing/using/using-reusable-content.md#content-templates">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Generazione di rapporti dinamici con dati profilo<br /> </td> 
   <td> Dynamic Reporting offre rapporti aziendali completamente personalizzabili e in tempo reale. Con questa release, un potente miglioramento alla funzione di reporting dinamico aggiunge l'accesso ai dati del profilo, consentendo l'analisi demografica per dimensioni del profilo quali genere, città, codice postale ed età, oltre ai dati funzionali delle campagne e-mail come aperture e clic. Grazie alla stessa interfaccia intuitiva, è più facile determinare le prestazioni della campagna e-mail rispetto ai segmenti di clienti più importanti.<br /> Per ulteriori informazioni, consulta la <a href="../../reporting/using/about-dynamic-reports.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Iscrizione di massa con origine e data<br /> </td> 
   <td> Grazie a questo miglioramento dell'iscrizione di massa, ora potete memorizzare le informazioni di iscrizione (origine e data) direttamente nel database del Adobe Campaign Standard  tramite l'attività Servizi iscrizione in un flusso di lavoro.<br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/subscription-services.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Platform_

* Alcuni clienti devono poter utilizzare un ID proveniente da  Adobe Campaign Standard, in quanto non gestiscono una chiave univoca per identificare i propri record. Questo ID (ID **** ACS) può essere esportato e utilizzato come chiave di riconciliazione durante l&#39;aggiornamento dei dati. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* Il protocollo FTP è stato dichiarato obsoleto. È ora necessario utilizzare SFTP. Per non bloccare le implementazioni esistenti, le configurazioni esistenti sull&#39;FTP continueranno a funzionare come prima, ma l&#39;opzione non verrà visualizzata per le nuove attività.

_E-mail, SMS e posta diretta_

* È ora possibile creare nuovi criteri di avviso per utilizzarli nelle notifiche di avviso relative alla consegna. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Le notifiche di avviso sulla consegna hanno una nuova progettazione e l&#39;esperienza utente del dashboard di avvisi sulla consegna è stata migliorata.
* Ora, quando un account esterno di routing è disattivato, nelle consegne interessate viene visualizzato un avviso (e-mail, SMS e push) e il pulsante **Anteprima** è nascosto in queste consegne.
* È stato risolto un problema che causava un errore nell&#39;anteprima di un test A/B sul contenuto dell&#39;e-mail quando il testo dinamico era abilitato nella riga oggetto.

_Messaggi transazionali_

* È ora possibile definire quando si desidera inviare un messaggio di follow-up, ad esempio 3 giorni dopo l&#39;invio di un messaggio transazionale. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* È ora possibile definire la data a partire dalla quale inviare i messaggi transazionali collegati a un evento.
* È stato risolto un problema che causava un errore SQL durante l&#39;esecuzione di un flusso di lavoro contenente un messaggio di follow-up dopo l&#39;eliminazione dei profili collegati agli eventi ricevuti ed elaborati.
* È stato corretto un errore che impediva di eliminare un profilo collegato a un evento.
* È stato risolto un problema che poteva impedire il funzionamento del reindirizzamento dei collegamenti tracciati.
* È stato risolto un problema che impediva di disabilitare il tracciamento per alcuni collegamenti in un messaggio e-mail o SMS.

_Rapporti_

* Il rapporto **Clic** con attivazione è stato migliorato. Inoltre, ora è possibile visualizzare clic a seconda di ogni contenuto condizionale definito in una consegna e visualizzare clic per ogni esecuzione di consegne ricorrenti o messaggi transazionali. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* È stato risolto un problema che impediva alla metrica quarantena di recuperare dati corretti.
* Al widget del calendario è stato aggiunto un nuovo intervallo di tempo predefinito.
* Le metriche [dei report](../../reporting/using/indicator-calculation.md) dinamici e i KPI [delle](../../sending/using/confirming-the-send.md) campagne (visualizzati sul dashboard dei messaggi inviati) sono stati allineati per una maggiore coerenza.
* È stato risolto un problema che poteva causare l&#39;arresto anomalo del gasdotto su debian 7.

_Flussi di lavoro_

* È stato risolto un problema che poteva impedire il funzionamento della conservazione dei file importati.

_Integrazioni_

* Ora sono supportati eVar ed eventi per l&#39;integrazione con Analytics e Campaign .
* Quando si invia un&#39;e-mail con il contenuto del carrello abbandonato, il parametro payload per gli elementi rimossi dal carrello ora è facoltativo.

_Profili e pubblico_

*  Adobe Campaign ora fornisce un rapporto che mostra il numero di profili attivi. Questo rapporto è solo informativo, non ha un impatto diretto sulla fatturazione. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../audiences/using/active-profiles.md).
* È stato risolto un problema che impediva la sottoscrizione dei profili a un servizio quando si utilizzava l&#39;API Profili e servizi.

## Rilascio 17.7 - luglio 2017 {#release-17-7---july-2017}

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
   <td> Invio di e-mail e SMS in più lingue<br /> </td> 
   <td> Definite ed eseguite le consegne di e-mail e SMS in più lingue attraverso un'unica distribuzione basata sulla lingua preferita dei clienti segmentati automaticamente. Report sulle prestazioni di ogni distribuzione fino al livello della lingua e dei singoli livelli.<br /> Sempre più aziende devono affrontare la sfida di distribuire contenuti in più lingue man mano che crescono sia in patria che all'estero. La semplificazione della distribuzione dei messaggi localizzati è pertanto un elemento chiave di una strategia di comunicazione efficace per le multinazionali; società in paesi con più lingue; e le aziende che desiderano personalizzare ulteriormente i propri contenuti a livello linguistico, indipendentemente dal luogo in cui risiedono i clienti. Per ulteriori informazioni, consulta la <a href="../../channels/using/creating-a-multilingual-email.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifiche Adobe Campaign<br /> </td> 
   <td> Ricevi notifiche relative a importanti attività di sistema direttamente all'interno  Adobe Campaign Standard. Ad esempio, riceverai una notifica sull’avanzamento delle distribuzioni in corso o se un flusso di lavoro è in errore.<br /> Le notifiche in tempo reale tengono informate le parti interessate e forniscono agli utenti la possibilità di agire immediatamente e direttamente sulle notifiche delle attività dall'interno dell'applicazione. Il risultato per i team è un'agilità avanzata, un'efficienza e un'esecuzione più fluida delle campagne. Per ulteriori informazioni, consulta la <a href="../../administration/using/sending-internal-notifications.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avvisi sulla distribuzione<br /> </td> 
   <td> Oltre a visualizzare le notifiche direttamente nel  Adobe Campaign Standard,  Adobe Campaign ora fornisce anche un sistema di avvisi e-mail per attivare avvisi e-mail a utenti o parti interessate esterne di importanti attività del sistema. Crea, gestisci e ricevi avvisi e dashboard personalizzabili per tenere traccia dei successi o degli errori di consegna.<br />  avvisi sulla distribuzione del Adobe Campaign aumenta l'efficienza, tenendo tutti gli utenti  Adobe Campaign coinvolti in una società informati automaticamente sullo stato di esecuzione della consegna, tramite e-mail e dashboard. Per ulteriori informazioni, consulta la <a href="../../sending/using/receiving-alerts-when-failures-happen.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> ID dichiarato crittografato nelle origini dati<br /> </td> 
   <td> Invia attivatori e-mail e SMS senza bisogno di un profilo esistente in Campaign utilizzando come ID dichiarato le informazioni di contatto crittografate (indirizzo e-mail o numero di telefono). Poiché gli ID dichiarati crittografati possono essere decodificati da  Adobe Campaign Standard, Campaign ora può creare nuovi profili marketing quando riceve audience da altre soluzioni Experience Cloud  contenenti contatti precedentemente sconosciuti.<br /> Clienti Target e potenziali clienti non noti in tempo reale, sia tramite e-mail che tramite SMS, per migliorare la fedeltà nella base di clienti esistente e acquisire nuovi clienti rispettivamente. Sfrutta al meglio i tuoi dati di cookie di prime parti (da  Adobe Audience Manager*) una volta che i potenziali clienti si autenticano e sfrutta tali informazioni nel Adobe Campaign . <br /> * Adobe Audience Manager è richiesto. Per ulteriori informazioni, consulta la <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Condivisione KPI da Campaign a  Analytics<br /> </td> 
   <td> Condividi i dati delle campagne con Adobe  Analytics per misurare le metriche di marketing relative alle e-mail da Campaign insieme ad altre attività di marketing e pubblicità tramite la conversione, unificando il comportamento pre e post-clic.<br /> Monitora direttamente le prestazioni complessive e scopri sinergie con i programmi esterni in  Analytics. Applica le tue conoscenze da questa vista consolidata alle campagne; in ultima analisi, il miglioramento dei tassi di apertura, click-through e conversione per incrementare le entrate e le prestazioni complessive delle campagne. <br /> È richiesto Adobe  Analytics. Per ulteriori informazioni, consulta la <a href="../../integrating/using/about-campaign-analytics-integration.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Canale Direct Mail - Ritorno Al Mittente<br /> </td> 
   <td> Sono ora supportati gli scambi di file flat con i provider di Direct Mail che includono informazioni sul ritorno al mittente. Questo miglioramento al canale Direct Mail consente di escludere gli indirizzi postali corrispondenti dalle comunicazioni future.<br /> Questo consente agli addetti al marketing di ricevere una notifica di indirizzo errato e di interagire con il cliente attraverso altri canali o di incoraggiarlo ad aggiornare il suo indirizzo postale. Questo riduce anche il numero di dollari di marketing sprecati, in quanto gli esperti di marketing evitano di inviare posta a indirizzi errati. <br /> Direct Mail è disponibile come canale aggiuntivo. Per ulteriori informazioni, consulta la <a href="../../channels/using/return-to-sender.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* È stato risolto un problema che consentiva a qualsiasi utente di esportare elenchi. Ora è consentito solo agli utenti con **[!UICONTROL Export]** ruolo.

_E-mail, SMS e posta diretta_

* È stato risolto un problema con il flusso di lavoro **updateDeliveryExecInfo** che impostava l&#39;indicatore **Per distribuire** su 0 per le consegne via SMS.
* Nei parametri **** avanzati delle proprietà del modello di consegna, l&#39;elenco a discesa **Routing** ora visualizza solo gli account esterni corrispondenti al tipo di messaggio del modello. Ad esempio, un modello di consegna per e-mail visualizza solo gli account esterni per le e-mail.
* È stato risolto un problema con il formato e-mail **[!UICONTROL Text]** preferito definito per i profili di test.
* È stato risolto un problema che causava un errore Javascript nella selezione del fuso orario predefinito nella schermata di definizione della pianificazione di una consegna.
* È stato risolto un problema che impediva la visualizzazione dei trap nei registri di invio.
* Nella schermata di selezione dei modelli della procedura guidata per la creazione della consegna, i modelli di test A/B e follow-up ora sono nascosti per impostazione predefinita. For more information, refer to the [detailed documention](../../channels/using/creating-an-email.md).
* È stato risolto un problema che consentiva a qualsiasi utente di inviare le consegne. Ora è consentito solo agli utenti con **[!UICONTROL Start deliveries]** ruolo. For more information, refer to the [detailed documention](../../sending/using/confirming-the-send.md).

_Notifiche push_

* È stato risolto un problema con l&#39;URL dell&#39;endpoint **di tracciamento** campagna che impediva il reporting.
* È stato risolto un problema che impediva la visualizzazione del titolo della notifica push sui dispositivi Android.
* È stato risolto un problema che impediva la visualizzazione della notifica push sui dispositivi iOS quando la notifica push conteneva solo un titolo (e niente nel corpo del messaggio).
* È stato corretto un problema a causa del quale veniva forzato il tracciamento degli URL degli allegati multimediali in una distribuzione, che impediva l&#39;incorporazione di video e immagini nella distribuzione. Il tracciamento degli URL del tipo mediaAttachmentURL ora è disattivato per impostazione predefinita per le notifiche push.

_Rapporti_

* È stato corretto un problema a causa del quale i valori apparivano diversi tra grafici e tabelle.
* È stato corretto un problema a causa del quale i valori delle notifiche push venivano visualizzati come valori e-mail.
* È stato risolto un problema che mostrava valori sconosciuti quando si creava una consegna al di fuori di una campagna.
* È stato corretto un problema a causa del quale i dati del report SMS venivano visualizzati come dati dell&#39;applicazione mobile.

_Flussi di lavoro_

* È ora possibile filtrare i registri del flusso di lavoro (periodo di tempo e ricerca del testo). For more information, refer to the [detailed documention](../../automating/using/monitoring-workflow-execution.md).
* È ora disponibile un&#39;opzione nelle consegne del flusso di lavoro per disattivare la conferma prima dell&#39;invio.
* È stato risolto un problema che impediva di impostare una transizione in uscita nella creazione guidata di consegna ricorrente.
* È stato risolto un problema che si verificava durante l&#39;utilizzo di un&#39;attività di query del flusso di lavoro basata su un campo di risorse personalizzato con un&#39;enumerazione contenente molti valori

## Rilascio 17.5 - maggio 2017 {#release-17-5---may-2017}

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
   <td> Direct mail<br /> </td> 
   <td> Sfruttate la barriera digitale e collegatevi al mondo fisico con  primo canale offline del Adobe Campaign Standard, Direct Mail. Questa funzione consente di personalizzare e generare il file richiesto dai provider di posta diretta nell'ambito delle campagne multicanale. Utilizza Posta diretta per coinvolgere nuovamente i clienti o per migliorare l'esperienza dei clienti con un accattivante punto di contatto tattile che indirizza i clienti all'app, al sito Web o allo store.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/about-direct-mail.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ccn e-mail<br /> </td> 
   <td> Ccn e-mail consente di salvare messaggi e-mail univoci inviati a singoli destinatari, consentendo al marchio di archiviarli. Aggiungendo un indirizzo e-mail CCN a tutte le e-mail,  clienti di Adobe Campaign Standard possono conservare una copia esatta di ogni e-mail con questa funzione. Si tratta di un requisito giuridico comune per il settore dei servizi finanziari ed è utile per aiutare i centri di assistenza clienti a risolvere i conflitti in tempo reale.<br /> Per ulteriori informazioni, consulta la <a href="../../sending/using/archiving.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Aggiornamenti dell&#39;interfaccia_

* Nella barra superiore, il **[!UICONTROL Timeline]** collegamento è stato rimosso e sostituito con un collegamento a **[!UICONTROL Programs & Campaigns]** .

_E-mail e messaggi SMS_

* È stato risolto un problema che causava la visualizzazione del colore errato per lo stato **[!UICONTROL Retry in progress]** di consegna. Il colore era grigio invece del blu.

_Flussi di lavoro_

* È stato risolto un problema che si verificava durante la modifica dell&#39;azione da eseguire in un&#39; **[!UICONTROL Transfer file]** attività.

_Rapporti_

* I calcoli **[!UICONTROL Spam]** e gli **[!UICONTROL Spam rate]** indicatori sono stati modificati.
* Le **[!UICONTROL Bounce]** metriche sono state migliorate per ottenere risultati più precisi.

_Notifiche push_

* È stato risolto un problema che impediva di fare clic su un evento push nella cronologia marketing di un profilo.
* È stato migliorato l&#39;utilizzo delle notifiche push nei flussi di lavoro.

## Rilascio 17.4 - Aprile 2017 {#release-17-4---april-2017}

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
   <td> Funzionalità edizione delle immagini migliorate con Creative SDK<br /> </td> 
   <td> Ora potete accedere a un set completo di funzioni basato su Creative SDK per migliorare le immagini direttamente nell'editor dei contenuti durante la modifica di e-mail o la pagina di destinazione.<br /> Questa funzione non richiede l'acquisizione di soluzioni Creative Cloud aggiuntive.<br /> Per ulteriori informazioni, consulta la <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifiche push transazionali<br /> </td> 
   <td> Il canale dell'applicazione Mobile è stato aggiunto  funzionalità  messaggi transazionali. Sono ora supportati tre canali per i messaggi transazionali: e-mail, SMS e notifiche push.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/transactional-push-notifications.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifiche push ricorrenti<br /> </td> 
   <td> Ora puoi configurare notifiche push ricorrenti in un flusso di lavoro. Potete utilizzare notifiche push ricorrenti in situazioni in cui i clienti si aspettano aggiornamenti periodici, come promemoria settimanali per il check-out di nuovi contenuti o promozioni.<br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/push-notification-delivery.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Connettore Amazon S3 (Simple Storage Service)<br /> </td> 
   <td> È ora possibile utilizzare il connettore Amazon S3 per importare o esportare dati  Adobe Campaign. Può essere impostato in un'attività del flusso di lavoro. La configurazione viene eseguita in un account esterno.<br /> Per ulteriori informazioni, consulta la <a href="../../administration/using/external-accounts.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrazione Dreamweaver live<br /> </td> 
   <td> L'integrazione tra  Adobe Campaign e Dreamweaver ora è live. Ora funziona con l'ultima versione ufficiale di Dreamweaver (17.0.2).<br /> Ciò richiede l'installazione di  estensione Integrazione Adobe Campaign da qui: <a href="https://adobe.ly/acdw_addon">https://adobe.ly/acdw_addon</a><br /> Per ulteriori informazioni, consultate questo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">video</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Platform_

* È stato corretto un problema di consumo di memoria.

_E-mail e messaggi SMS_

* È stato risolto un problema che impediva la corretta sincronizzazione del contenuto con le ultime modifiche durante l&#39;anteprima di un messaggio.
* È stato risolto un problema che impediva la creazione o l&#39;eliminazione di una regola di elaborazione e-mail MX o Domain.
* È stato risolto un problema che poteva impedire l’invio di e-mail con più alias.
* È stato risolto un problema che impediva la visualizzazione dei log di consegna del trap nei registri di invio del recapito.
* È stato risolto un problema che causava un errore durante la visualizzazione degli URL tracciati di una consegna senza alcun URL nel relativo contenuto.
* È stato risolto un problema che impediva la corretta applicazione degli attributi dimensione dell&#39;immagine nel messaggio inviato.

_Messaggi transazionali_

* Il campo rtEventHistoId non è più esposto come campo di personalizzazione in un modello di messaggio transazionale.

_Pagine di destinazione_

* Abbiamo ottimizzato il **[!UICONTROL by email]** filtro utilizzato nelle pagine di destinazione per riconciliare i nuovi sottoscrittori con i profili di database.
* È stato risolto un problema che causava la visualizzazione di input di testo gratuiti invece delle caselle di controllo quando si utilizzavano campi booleani in una configurazione del modulo.
* È stato risolto un problema che impediva la generazione delle miniature delle pagine di destinazione.

_Flussi di lavoro_

* È stato corretto un errore di visualizzazione durante la modifica di un&#39; **[!UICONTROL End]** attività o **[!UICONTROL External Signal]** un&#39;attività (solo in Safari).
* È stato migliorato il messaggio di errore visualizzato durante la modifica di un&#39; **[!UICONTROL Read Audience]** attività contenente un&#39;audience errata.
* È stato risolto un problema che poteva causare un errore SQL durante l&#39;esecuzione di un&#39;attività di iscrizione.

_Integrazioni_

* Dati dei punti di interesse: è stato corretto un errore che si verificava durante il conteggio dei sottoscrittori della posizione.

_Audience e query_

* È stato risolto un problema che impediva l&#39;utilizzo di aggregati di somma e media in una raccolta nell&#39;editor di query.
* È stato risolto un problema che poteva impedire il ricaricamento dell&#39;editor di query dopo la modifica della risorsa del filtro.

_Rapporti_

* È stato risolto un problema che impediva il corretto calcolo delle metriche Open Rate durante la selezione di più righe in una tabella.
* È stato corretto un errore che mostrava solo le metriche come valori interi. Ora è possibile visualizzare le metriche con i decimali.

_Notifiche push_

* È stato risolto un problema che impediva la visualizzazione di un messaggio di errore durante la creazione di un&#39;applicazione Android collegata a un&#39;app mobile che non era stata creata correttamente in MCPNS.
* È stato risolto un problema che consentiva a un utente di aggiungere suoni a una notifica invisibile.

## Rilascio 17.2 - marzo 2017 {#release-17-2---march-2017}

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
   <td> Generazione di rapporti dinamici<br /> </td> 
   <td> Dynamic Reporting offre una nuova generazione di report aziendali completamente personalizzabili e in tempo reale. Basata su tabelle pivot e grafici, questa funzione consente di trascinare variabili e dimensioni per analizzare l’efficienza e l’efficacia delle campagne di marketing. Il reporting dinamico consente inoltre di creare da zero i propri rapporti aziendali e di salvarli per un uso successivo.<br /> Per ulteriori informazioni, consulta la <a href="../../reporting/using/about-dynamic-reports.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrazione di Dreamweaver (Labs)<br /> </td> 
   <td> Con l'integrazione  Adobe Campaign e Dreamweaver, ora disponete di un processo integrato per la creazione di campagne e-mail con le soluzioni Adobe.<br /> Potete modificare  e-mail di Adobe Campaign in Dreamweaver e sincronizzare il contenuto senza soluzione di continuità tra le due soluzioni.<br /> Per la versione iniziale, l'integrazione è disponibile come funzione "Labs" e funziona solo con Dreamweaver Pre Release Beta. Se desiderate attivarlo, contattate AC-DW-integration@adobe.com.<br /> Per ulteriori informazioni, consultate questo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">video</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ottimizzazione manuale del tempo di invio<br /> </td> 
   <td> Ora puoi definire manualmente un orario di invio personalizzato per destinatario, a livello di consegna o tramite un flusso di lavoro. <br /> Sono disponibili due nuove opzioni: <br /> 
    <ul> 
     <li> Tutti i destinatari ricevono il messaggio tenendo conto del relativo fuso orario. </li> 
     <li> Ogni destinatario riceve il messaggio a una data e un'ora calcolate definite da una formula. </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../sending/using/optimizing-the-sending-time.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifiche push Nuove funzionalità<br /> </td> 
   <td> Il canale di notifica push è stato migliorato con diverse nuove funzionalità:<br /> 
    <ul> 
     <li> Nuova interfaccia di authoring </li> 
     <li> Notifiche silenziose </li> 
     <li> Push interattivo </li> 
     <li> Supporto per contenuti avanzati </li> 
     <li> Calcolo della dimensione del payload </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../channels/using/about-push-notifications.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: nuova attività di segnale<br /> </td> 
   <td> Attiva un flusso di lavoro da un altro tramite la nuova attività <span class="uicontrol">Segnale</span> .<br /> Grazie alla possibilità di avviare un flusso di lavoro da un altro, ora puoi supportare percorsi cliente più complessi. Puoi monitorare meglio i viaggi dei clienti e reagire in caso di problemi.<br /> Sono state aggiornate diverse attività del flusso di lavoro:<br /> 
    <ul> 
     <li> <span class="uicontrol">End</span> activity: una nuova scheda consente di specificare un flusso di lavoro da attivare dopo l'esecuzione dell'attività. </li> 
     <li> <span class="uicontrol">Aggiorna attività dati</span> : utilizzate la nuova transizione in uscita vuota per aggiungere un'attività <strong>End</strong> che attivi un altro flusso di lavoro. Le transizioni vuote in uscita non contengono dati e non occupano spazio inutile sul sistema </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../automating/using/external-signal.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: nuova attività di lettura dell'audience<br /> </td> 
   <td> Avviate il processo di targeting con un'audience esistente che potete facilmente selezionare e perfezionare in un'unica attività.<br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/read-audience.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dati dei punti di interesse<br /> </td> 
   <td> I dati dei punti di interesse integrano  Adobe Campaign con Adobe  Analytics per dispositivi mobili. Un marchio può raccogliere dati dalle posizioni mobili degli utenti, denominate <strong>Punti di interesse</strong> , quando gli utenti aprono l'app del marchio. Questo consente al marchio di sfruttare i flussi di lavoro  Adobe Campaign per inviare messaggi personalizzati in base alle posizioni degli utenti. Questo canale sfrutta l’SDK del servizio core Mobile.<br /> L'utilizzo di questa funzione richiede  Analytics per Mobile, una soluzione a pagamento.<br /> Per ulteriori informazioni, consulta la <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API REST<br /> </td> 
   <td> Le risorse collegate a qualsiasi livello ai profili o alle risorse dei servizi ora sono disponibili nell'API.<br /> Per ulteriori informazioni, consulta la <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* È ora possibile aggiungere dati di profilo durante l&#39;esportazione dei registri di consegna.

_E-mail e messaggi SMS_

* È stato risolto un problema a causa del quale l&#39; **[!UICONTROL Request confirmation before sending messages]** opzione rimaneva selezionata anche dopo averla deselezionata e aver salvato la consegna.
* È stato risolto un problema che poteva impedire l&#39;annullamento della pubblicazione di e-mail transazionali.
* È stato corretto un problema a causa del quale il contenuto non poteva essere sincronizzato correttamente con le ultime modifiche prima di visualizzare l&#39;anteprima di una distribuzione.

_Pagine di destinazione_

* È stato corretto un errore che impediva di modificare un utente quando faceva clic nel contenuto di una pagina di destinazione.

_Flussi di lavoro_

* È stato risolto un problema che poteva impedire la lettura del contenuto della transizione di rifiuto di un&#39; **[!UICONTROL Load file]** attività.
* È stato risolto un problema che impediva alle colonne scambiate di essere prese in considerazione quando si configurava un&#39; **[!UICONTROL Load file]** attività.

## Rilascio 17.1 - gennaio 2017 {#release-17-1---january-2017}

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
   <td> Esportazione di log per report esterni<br /> </td> 
   <td> Esporta registri come i registri di consegna e di tracciamento per elaborarli nei tuoi strumenti di reporting o BI preferiti. Puoi utilizzare flussi di lavoro semplici con query incrementali per automatizzare le esportazioni regolari di nuovi registri.<br /> Oltre alla disponibilità delle risorse di registro dal selettore delle risorse, sono stati apportati miglioramenti alle attività <a href="../../automating/using/incremental-query.md">Query</a> incrementale ed <a href="../../automating/using/extract-file.md">Estrai file</a> :<br /> 
    <ul> 
     <li> <span class="uicontrol">La query</span> incrementale ora consente di utilizzare un campo data per recuperare dati nuovi o aggiornati. In precedenza, tutti i risultati delle esecuzioni precedenti venivano automaticamente esclusi, anche se venivano aggiornati dopo l'ultima esecuzione. </li> 
     <li> <span class="uicontrol">Il file</span> di estrazione ora può esportare etichette per i valori di enumerazione invece degli ID. </li> 
    </ul> Queste attività sono disponibili per gli amministratori con accesso a tutte le unità geografiche e organizzative.<br /> Per ulteriori informazioni sull’esportazione dei registri, consulta la documentazione <a href="../../automating/using/exporting-logs.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Funzionalità di marketing per i messaggi transazionali<br /> </td> 
   <td> Gli addetti al marketing ora possono inviare messaggi transazionali basati sui profili di marketing dei clienti. Questo consente loro di:<br /> 
    <ul> 
     <li> Applica regole di tipo marketing, ad esempio <span class="uicontrol">Indirizzo nell'elenco</span> dei blocchi. </li> 
     <li> Includi il collegamento di annullamento della sottoscrizione nei messaggi. </li> 
     <li> Aggiungete i messaggi transazionali al reporting globale sulla distribuzione. </li> 
     <li> Utilizza i messaggi transazionali nel percorso del cliente. </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../channels/using/profile-transactional-messages.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API per messaggi transazionali<br /> </td> 
   <td> L'API Transactional Messaging ora è disponibile tramite <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, semplificando l'utilizzo e il monitoraggio:<br /> 
    <ul> 
     <li> Potete sfruttare le funzionalità di reporting e monitoraggio della piattaforma adobe.io. </li> 
     <li> L'autenticazione ora viene eseguita utilizzando l'autenticazione basata sul token adobe.io invece dell'elenco di autorizzazione IP, semplificando il processo di protezione. </li> 
     <li> Tutte le API sono ora integrate su una singola piattaforma, semplificando al massimo l'aggiunta di funzionalità di messaggistica transazionali all'integrazione se già supportate l'API Profile and Services. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* Le **[!UICONTROL Access authorization]** opzioni sono tornate alle proprietà della pagina di destinazione.
* È stato risolto un problema che poteva causare il rendering di una vecchia immagine invece dell&#39;immagine corretta. Ciò si verificava se l&#39;immagine sorgente era stata aggiornata nella definizione di contenuto di una pagina di consegna o di destinazione.
* È stato risolto un problema che impediva agli utenti di modificare alcuni campi in un account esterno SFTP esistente.
* Sono stati corretti diversi problemi di interfaccia utente. Ad esempio, gli utenti ora possono modificare gli attributi di profilo e salvare le modifiche senza problemi con l&#39;interfaccia utente.

_E-mail e messaggi SMS_

* È stato risolto un problema relativo ai modelli di consegna con contenuto HTML contenente un

_Notifiche push_

* È stato risolto un problema che poteva impedire il postback da un&#39;applicazione al server di Adobe Campaign .
* È stato risolto un problema che poteva impedire **[!UICONTROL Play a sound]** e **[!UICONTROL Custom fields]** di cui tener conto per Android.
* È stato risolto un problema che poteva causare l&#39;aggiunta di un carattere di escape aggiuntivo ai caratteri Unicode utilizzati per Emojis.
* Quando il token di registrazione di un utente iscritto viene aggiunto all&#39;elenco dei blocchi, lo stato corrispondente ora viene aggiornato immediatamente nell&#39;elenco di utenti iscritti dell&#39;applicazione in  Adobe Campaign.

_Flussi di lavoro_

* È stato risolto un problema che poteva impedire l&#39;anteprima delle query sulle risorse dell&#39;evento (ad esempio, rtEvent).
* Il file di rifiuto generato da un&#39; **[!UICONTROL Load file]** attività ora può essere recuperato nella relativa transizione in uscita ed elaborato nell&#39;attività successiva. Ad esempio, caricate il file di rifiuto tramite un server SFTP utilizzando **[!UICONTROL Transfer file]** .
* È stato risolto un problema che poteva impedire a un utente di limitare la popolazione di un segmento se **[!UICONTROL Temporary resource]** era stato selezionato nella **[!UICONTROL General]** scheda di **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** le attività non possono più essere impostate per attivare un flusso di lavoro più volte ogni 10 minuti.
* È stato risolto un problema che poteva impedire **[!UICONTROL Use common columns]** il corretto funzionamento in un&#39; **[!UICONTROL Union]** attività.

_Integrazioni_

* È stato risolto un problema che poteva causare un errore durante la distribuzione di un attivatore evento in  Adobe Campaign. Questo errore si verificava quando i metadati &quot;Probabilità di restituzione entro 30 giorni&quot; erano stati aggiunti al trigger di abbandono in  Adobe Marketing Cloud.
* È stato risolto un problema che poteva causare la cancellazione del campo Dimensione Target da parte del flusso di lavoro tecnico durante l&#39;importazione di audience dal servizio di base Persone. Impossibile recuperare le audience importate dalle query successive.
* È stato risolto un problema che poteva causare il fallimento dell&#39; **[!UICONTROL Save audience]** attività di un flusso di lavoro quando l&#39;opzione **[!UICONTROL Share in Adobe Marketing Cloud]** era selezionata.

