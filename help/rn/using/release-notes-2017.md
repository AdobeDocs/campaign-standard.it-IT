---
title: Note sulla versione 2017
description: In questa pagina sono elencate tutte le versioni del 2017 di Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: 73a1ec49-fcbc-406b-9590-1ad20da9e73b
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '4613'
ht-degree: 8%

---

# Note sulla versione 2017{#release-notes}

Stai cercando una versione specifica 2017 di Adobe Campaign Standard?

Ogni versione include nuove funzioni e patch. Fai clic su una versione per visualizzarne il contenuto.

Visualizza le ultime [aggiornamenti della documentazione](../../rn/using/documentation-updates.md) per Adobe Campaign Standard. Se cerchi una versione più recente, consulta questa [page](../../rn/using/release-notes.md).

## Versione 17.10 - Ottobre 2017 {#release-17-10---october-2017}

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
   <td> Gestione dell’eccesso<br /> </td> 
   <td> La gestione dell’affaticamento consente di creare regole di affaticamento per gestire la comunicazione eccessiva con i profili. Le regole di affaticamento sono facili da creare, ma sono estremamente flessibili con funzionalità quali il conteggio dei messaggi su più canali (inclusi i messaggi transazionali), il conteggio solo di consegne specifiche o l’applicazione di regole a profili specifici.<br /> Per ulteriori informazioni, consulta la <a href="../../sending/using/fatigue-rules.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creazione di contenuti: Importazione da un URL<br /> </td> 
   <td> L’importazione da un URL ti consente di recuperare rapidamente il contenuto creativo da un sito web per creare e-mail per qualsiasi consegna. Inoltre, puoi semplificare il processo creativo consentendo a terzi di condividere direttamente i contenuti tramite un URL. Il contenuto importato può essere utilizzato in modo flessibile come parte di una singola consegna o a livello di modello, garantendo la coerenza del marchio per tutte le campagne correlate, siano esse basate su flusso di lavoro o messaggi transazionali, e includere test A/B o multivariati. L’importazione da un URL converte e tiene traccia automaticamente di tutti i collegamenti per monitorare le prestazioni delle e-mail tramite Reporting dinamico.<br /> Per ulteriori informazioni, consulta la <a href="../../designing/using/using-existing-content.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Piattaforma_

* È stato risolto un problema che poteva impedire la corretta decompressione dei file ZIP di grandi dimensioni.
* La sicurezza nella gestione del marchio è stata migliorata. La modifica del nome e dell’indirizzo del mittente di un marchio è ora riservata agli amministratori tecnici di Adobe.
* Per migliorare la sicurezza, contenuti generati dall’utente (immagini, pagine mirror, pagine di destinazione, ecc.) non può più essere servito dal dominio adobe.com . È ora obbligatorio utilizzare il proprio dominio per gestire queste risorse tramite l’utilizzo del branding.
* È stato risolto un problema di interfaccia che si verificava durante la visualizzazione e il filtraggio delle attività di marketing.
* È stato risolto un problema che impediva l’aggiornamento dei campi della data di abbonamento con una chiamata API POST Rest.

_E-mail, messaggi SMS e direct mail_

* È stato risolto un problema che poteva impedire il targeting di un pubblico di tipo elenco in un messaggio, causando un errore di preparazione.
* Lingue mancanti aggiunte nelle funzionalità di consegna e-mail multilingue.
* La miniatura del contenuto, visualizzata sul dashboard di consegna, viene ora aggiornata automaticamente quando l’utente modifica il contenuto e lo salva.
* È stato risolto un problema relativo al fuso orario che impediva l’apertura di una consegna.

_Notifiche push_

* Durante la configurazione del canale di notifica push, la piattaforma del provider push per iOS deve essere **apns** e per Android **gcm**.
* È stato corretto un errore che impediva l’aggiunta dell’app mobile iOS nell’interfaccia di Adobe Campaign.
* Le notifiche push sono ora supportate sia nelle applicazioni mobili Android abilitate per GCM sia nelle applicazioni mobili abilitate per FCM.
* È stato corretto un errore che impediva il salvataggio del contenuto durante la duplicazione di un modello di notifica push.
* È ora possibile creare o aggiornare un profilo dal database Adobe Campaign riconciliando i dati degli utenti delle applicazioni mobili.
* Adobe Campaign ora dà priorità all’elaborazione delle notifiche push transazionali rispetto alle notifiche push standard.

_Rapporti_

* È stato risolto un problema che impediva la visualizzazione delle percentuali di hot click nel contenuto dell’e-mail.
* È stato risolto un problema relativo alla metrica del  di elenco Bloccati che veniva conteggiata come rimbalzo rigido invece di un rimbalzo.
* È stato risolto un problema che causava la visualizzazione dei conteggi negativi nei dati di riepilogo.
* È stato risolto un problema che causava il conteggio dei profili nel segmento di età errato.
* Le formule di calcolo soft e hard bounce sono state modificate.

_Flussi di lavoro_

* È stato risolto un problema in **[!UICONTROL Load file]** attività che potrebbe causare errori dopo l’aggiunta e la rimozione manuale di colonne nell’attività.
* La **[!UICONTROL deliverabilityUpdate]** è ora pianificata l’esecuzione del flusso di lavoro tecnico alle 2 del mattino, ora del server.
* È stato risolto un problema di sicurezza che consentiva di eseguire un’esportazione di elenchi senza il ruolo di esportazione.
* È stato risolto un problema relativo alla **[!UICONTROL Reconciliation]** attività.
* È stato risolto un problema relativo all’utilizzo di caratteri jolly nel **[!UICONTROL File Transfer]** attività.

_Profili e pubblico_

* È stato risolto un problema che poteva impedire la corretta considerazione di una condizione di una query in alcuni casi specifici, dando luogo a risultati errati.
* È stato risolto un problema che poteva impedire l’accesso ai profili destinati in un messaggio preparato ma non inviato e scaduto.

_Integrazioni_

* È stato risolto un problema che poteva impedire la corretta visualizzazione e selezione di alcune origini dati create per Triggers.

_Risorse personalizzate_

* È stato risolto un problema che si verificava nelle schermate elenco in cui era possibile visualizzare righe di risorse personalizzate senza alcun dato.
* È stato risolto un problema che impediva la visualizzazione di campi di tipo booleano con valore &quot;False&quot; nelle risorse personalizzate.

## Versione 17.9 - Settembre 2017 {#release-17-9---september-2017}

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
   <td> Vi presentiamo diciotto nuovi modelli dinamici progettati in due bellissimi temi: Astro e Feather. Questi modelli personalizzabili non riguardano l’industria e sono pronti per essere utilizzati immediatamente. I modelli includono contenuti per una serie di casi d’uso per progettare e distribuire le tue campagne di marketing e-mail in modo più rapido, efficiente e bello che mai.<br /> Per ulteriori informazioni, consulta la <a href="../../designing/using/using-reusable-content.md#content-templates">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Reporting dinamico con i dati del profilo<br /> </td> 
   <td> La funzione di reporting dinamico offre rapporti aziendali completamente personalizzabili e in tempo reale. Con questa versione, un potente miglioramento al Reporting dinamico aggiunge l’accesso ai dati di profilo, abilitando l’analisi demografica per dimensioni di profilo come genere, città, codice postale ed età, oltre ai dati funzionali delle campagne e-mail come aperture e clic. Con la stessa interfaccia intuitiva a trascinamento, è più facile che mai determinare le prestazioni della campagna e-mail rispetto ai segmenti di clienti più importanti.<br /> Per ulteriori informazioni, consulta la <a href="../../reporting/using/about-dynamic-reports.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abbonamento di massa con origine e data<br /> </td> 
   <td> Con questo miglioramento dell’abbonamento di massa, ora puoi archiviare le informazioni sull’abbonamento (origine e data) direttamente nel database Adobe Campaign Standard tramite l’attività Subscription Services in un flusso di lavoro.<br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/subscription-services.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Piattaforma_

* Alcuni clienti devono poter sfruttare un ID proveniente da Adobe Campaign Standard in quanto non gestiscono una chiave univoca per identificare i propri record. Questo ID (**ID ACS**) può essere esportata e utilizzata come chiave di riconciliazione durante l’aggiornamento dei dati. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* Il protocollo FTP è stato dichiarato obsoleto. Ora devi utilizzare SFTP. Per non bloccare le implementazioni esistenti, le configurazioni esistenti sull&#39;FTP continueranno a funzionare come prima, ma l&#39;opzione non verrà visualizzata per le nuove attività.

_E-mail, messaggi SMS e direct mail_

* È ora possibile creare nuovi criteri di avviso da utilizzare nelle notifiche di avviso sulla consegna. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Le notifiche di avviso sulla consegna hanno una nuova progettazione e l’esperienza utente del dashboard di avviso sulla consegna è stata migliorata.
* Ora, quando un account esterno di indirizzamento è disabilitato, nelle consegne interessate (e-mail, SMS e push) e nella **Anteprima** Questo pulsante è nascosto in queste consegne.
* È stato risolto un problema che causava un errore nell’anteprima di un test A/B sul contenuto dell’e-mail quando il testo dinamico era abilitato nella riga dell’oggetto.

_Messaggi transazionali_

* È ora possibile definire quando inviare un messaggio di follow-up, ad esempio 3 giorni dopo l’invio di un messaggio sulle transazioni. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* È ora possibile definire la data a partire dalla quale i messaggi transazionali collegati a un evento devono essere inviati.
* È stato risolto un problema che causava un errore SQL durante l’esecuzione di un flusso di lavoro contenente un messaggio di follow-up dopo l’eliminazione dei profili collegati agli eventi ricevuti ed elaborati.
* È stato corretto un errore che impediva l’eliminazione di un profilo collegato a un evento.
* È stato risolto un problema che poteva impedire il funzionamento del reindirizzamento dei collegamenti tracciati.
* È stato risolto un problema che impediva la disattivazione del tracciamento per alcuni collegamenti in un messaggio e-mail o SMS.

_Rapporti_

* La **Hot click** la relazione è stata migliorata. Inoltre, è ora possibile visualizzare gli hot click in base a ciascun contenuto condizionale definito in una consegna e visualizzare gli hot click per ogni esecuzione di consegne ricorrenti o messaggi transazionali. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* È stato risolto un problema che impediva alla metrica di quarantena di recuperare i dati corretti.
* Al widget calendario è stato aggiunto un nuovo intervallo di tempo preimpostato.
* La [metriche di rapporto dinamiche](../../reporting/using/indicator-calculation.md) e [KPI delle campagne](../../sending/using/confirming-the-send.md) (visualizzati sul dashboard dei messaggi inviati) sono stati allineati per una maggiore coerenza.
* È stato risolto un problema che poteva causare l’arresto anomalo della pipeline su debian 7.

_Flussi di lavoro_

* È stato risolto un problema che poteva impedire il funzionamento della conservazione dei file importati.

_Integrazioni_

* Le eVar e gli eventi sono ora supportati per l’integrazione di Analytics e Campaign.
* Quando si invia un’e-mail con il contenuto del carrello abbandonato, il parametro payload per gli elementi rimossi dal carrello è ora facoltativo.

_Profili e pubblico_

* Adobe Campaign ora fornisce un rapporto che mostra il numero di profili attivi. Questo rapporto è solo informativo, non ha un impatto diretto sulla fatturazione. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../audiences/using/active-profiles.md).
* È stato risolto un problema che impediva ai profili di effettuare l’abbonamento a un servizio durante l’utilizzo dell’API Profiles and Services .

## Versione 17.7 - Luglio 2017 {#release-17-7---july-2017}

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
   <td> Consegne e-mail e SMS multilingue<br /> </td> 
   <td> Definisci ed esegui le consegne e-mail e SMS multilingue tramite un’unica consegna basata sulla lingua preferita dei clienti segmentati automaticamente. Rapporto sulle prestazioni di ogni consegna fino al livello della lingua e dei singoli livelli.<br /> Sempre più aziende devono affrontare la sfida di distribuire contenuti in più lingue man mano che crescono sia in patria che all'estero. La semplificazione della consegna dei messaggi localizzati costituisce pertanto un elemento chiave di una strategia di comunicazione efficace per i clienti delle multinazionali; imprese in paesi con più lingue; e le aziende che desiderano personalizzare ulteriormente i propri contenuti a livello linguistico, indipendentemente dal luogo in cui risiedono i clienti. Per ulteriori informazioni, consulta la <a href="../../channels/using/creating-a-multilingual-email.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifiche di Adobe Campaign<br /> </td> 
   <td> Ricevi notifiche relative a importanti attività di sistema direttamente in Adobe Campaign Standard. Ad esempio, riceverai una notifica sull’avanzamento delle consegne in corso o quando si verifica un errore in un flusso di lavoro.<br /> Le notifiche in tempo reale tengono informate le parti interessate e forniscono agli utenti la possibilità di intervenire immediatamente e direttamente sulle notifiche di attività dall’interno dell’applicazione. Il risultato per i team è un'agilità avanzata, un'efficienza e un'esecuzione più fluida delle campagne. Per ulteriori informazioni, consulta la <a href="../../administration/using/sending-internal-notifications.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avvisi sulla consegna<br /> </td> 
   <td> Oltre a visualizzare le notifiche direttamente in Adobe Campaign Standard, Adobe Campaign fornisce ora un sistema di avvisi e-mail per attivare avvisi e-mail a utenti o soggetti esterni per importanti attività del sistema. Crea, gestisci e ricevi avvisi e dashboard personalizzabili per tenere traccia dei successi o degli errori di consegna.<br /> Gli avvisi sulla consegna di Adobe Campaign aumentano l’efficienza mantenendo tutti gli utenti Adobe Campaign coinvolti in un’azienda automaticamente informati sullo stato di esecuzione della consegna, tramite e-mail e dashboard. Per ulteriori informazioni, consulta la <a href="../../sending/using/receiving-alerts-when-failures-happen.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> ID dichiarato crittografato nelle origini dati<br /> </td> 
   <td> Invia attivatori e-mail e SMS senza bisogno di un profilo esistente in Campaign utilizzando informazioni di contatto crittografate (indirizzo e-mail o numero di telefono) come ID dichiarato. Poiché gli ID dichiarati crittografati possono essere decodificati da Adobe Campaign Standard, Campaign può ora creare nuovi profili commerciabili alla ricezione di tipi di pubblico da altre soluzioni di Experience Cloud contenenti contatti precedentemente sconosciuti.<br /> Puoi indirizzare l’attività a clienti e potenziali clienti sconosciuti in tempo reale tramite e-mail e SMS per migliorare la fidelizzazione della base di clienti esistente e acquisire nuovi clienti rispettivamente. Sfrutta al meglio i tuoi dati sui cookie di prime parti (da Adobe Audience Manager*) una volta che i potenziali clienti si autenticano e sfrutta tali informazioni in Adobe Campaign. <br /> *È richiesto Adobe Audience Manager. Per ulteriori informazioni, consulta la <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Condivisione di KPI (Key Performance Indicator) da Campaign ad Analytics<br /> </td> 
   <td> Condividi i dati delle campagne con Adobe Analytics per misurare le metriche di marketing e-mail da Campaign insieme ad altre attività di marketing e pubblicitarie tramite la conversione, unificando il comportamento pre e post-clic.<br /> Monitora direttamente le prestazioni complessive e scopri sinergie con programmi esterni in Analytics. Applica di nuovo alle campagne il tuo apprendimento da questa vista consolidata; in ultima analisi, il miglioramento dei tassi di conversione, apertura e click-through, incrementando le entrate e le prestazioni complessive della campagna. <br /> È richiesto Adobe Analytics. Per ulteriori informazioni, consulta la <a href="../../integrating/using/about-campaign-analytics-integration.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Canale direct mailing - Restituzione al mittente<br /> </td> 
   <td> Sono ora supportati gli scambi di file Flat con provider Direct Mail che incorporano le informazioni Return to Sender. Questo miglioramento al canale Direct Mail consente di escludere gli indirizzi postali corrispondenti dalle comunicazioni future.<br /> Questo consente agli addetti al marketing di ricevere una notifica di indirizzo errato e di interagire con il cliente tramite altri canali o di incoraggiarli ad aggiornare il proprio indirizzo postale. Questo riduce anche il numero di dollari di marketing sprecati, in quanto gli addetti al marketing evitano di inviare posta a indirizzi errati. <br /> Direct Mail è disponibile come canale aggiuntivo. Per ulteriori informazioni, consulta la <a href="../../channels/using/return-to-sender.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* È stato risolto un problema che consentiva a qualsiasi utente di esportare elenchi. Ora solo gli utenti con **[!UICONTROL Export]** Il ruolo è consentito.

_E-mail, messaggi SMS e direct mail_

* È stato risolto un problema relativo alla **updateDeliveryExecInfo** flusso di lavoro che imposta **Per fornire** su 0 per le consegne SMS.
* In **Parametri avanzati** delle proprietà del modello di consegna, **Indirizzamento** l’elenco a discesa ora visualizza solo gli account esterni corrispondenti al tipo di messaggio modello. Ad esempio, un modello di consegna e-mail visualizza solo account esterni per e-mail.
* È stato risolto un problema relativo alla **[!UICONTROL Text]** formato e-mail preferito definito per i profili di test.
* È stato risolto un problema che causava un errore Javascript durante la selezione del fuso orario predefinito nella schermata di definizione della pianificazione di una consegna.
* È stato risolto un problema che impediva la visualizzazione delle trap nei registri di invio.
* Nella schermata di selezione dei modelli della procedura guidata di creazione della consegna, i modelli di test A/B e di follow-up ora sono nascosti per impostazione predefinita. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../channels/using/creating-an-email.md).
* È stato risolto un problema che consentiva a qualsiasi utente di inviare consegne. Ora solo gli utenti con **[!UICONTROL Start deliveries]** Il ruolo è consentito. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../sending/using/confirming-the-send.md).

_Notifiche push_

* È stato risolto un problema relativo alla **Endpoint di tracciamento campagna** URL che impediva la generazione di rapporti.
* È stato risolto un problema che impediva la visualizzazione del titolo della notifica push sui dispositivi Android.
* È stato risolto un problema che impediva la visualizzazione della notifica push sui dispositivi iOS quando la notifica push conteneva solo un titolo (e nulla nel corpo del messaggio).
* È stato risolto un problema che impediva il tracciamento degli URL degli allegati multimediali in una consegna, impedendo l’incorporamento di video e immagini nella consegna. Il tracciamento degli URL del tipo mediaAttachmentURL è ora disattivato per impostazione predefinita per le notifiche push.

_Rapporti_

* È stato corretto un problema a causa del quale i valori apparivano diversi tra grafici e tabelle.
* È stato corretto un problema a causa del quale i valori delle notifiche push venivano visualizzati come valori e-mail.
* È stato risolto un problema che mostrava valori sconosciuti durante la creazione di una consegna al di fuori di una campagna.
* È stato risolto un problema che mostrava i dati del rapporto SMS come dati dell’app mobile.

_Flussi di lavoro_

* Ora puoi filtrare i registri del flusso di lavoro (periodo di tempo e ricerca testo). Per ulteriori informazioni, consulta la [documentazione dettagliata](../../automating/using/monitoring-workflow-execution.md).
* È ora disponibile un’opzione nelle consegne del flusso di lavoro per disattivare la conferma prima dell’invio.
* È stato risolto un problema che impediva l’impostazione di una transizione in uscita nella procedura guidata di creazione della consegna ricorrente.
* È stato risolto un problema che si verificava durante l’utilizzo di un’attività di query del flusso di lavoro basata su un campo di risorse personalizzato con un’enumerazione con molti valori

## Versione 17.5 - Maggio 2017 {#release-17-5---may-2017}

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
   <td> Direct mailing<br /> </td> 
   <td> Sfruttate la barriera digitale e collegatevi al mondo fisico con il primo canale offline di Adobe Campaign Standard, Direct Mail. Questa funzione ti consente di personalizzare e generare il file richiesto dai provider di direct mailing come parte delle campagne cross-channel. Utilizza Direct Mail per coinvolgere nuovamente i clienti o per migliorare l’esperienza del cliente con un accattivante punto di contatto tattile che indirizza i clienti all’app, al sito web o allo store.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/about-direct-mail.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ccn e-mail<br /> </td> 
   <td> Ccn e-mail consente di salvare messaggi e-mail univoci inviati ai singoli destinatari, consentendo in tal modo al marchio di archiviarli. Aggiungendo un indirizzo e-mail Ccn a tutte le e-mail, i clienti Adobe Campaign Standard possono mantenere una copia esatta di ogni e-mail con questa funzione. Si tratta di un requisito giuridico comune per il settore dei servizi finanziari ed è utile per aiutare i centri di assistenza clienti a risolvere i conflitti in tempo reale.<br /> Per ulteriori informazioni, consulta la <a href="../../sending/using/archiving.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Aggiornamenti dell’interfaccia_

* Nella barra superiore, il **[!UICONTROL Timeline]** il collegamento è stato rimosso e sostituito con un collegamento a **[!UICONTROL Programs & Campaigns]** .

_E-mail e messaggi SMS_

* È stato risolto un problema che visualizzava il colore errato per il **[!UICONTROL Retry in progress]** stato di consegna. Il colore era grigio invece del blu.

_Flussi di lavoro_

* È stato risolto un problema che si verificava durante la modifica dell&#39;azione da eseguire in un **[!UICONTROL Transfer file]** attività.

_Rapporti_

* La **[!UICONTROL Spam]** e **[!UICONTROL Spam rate]** i calcoli degli indicatori sono stati modificati.
* La **[!UICONTROL Bounce]** sono state migliorate le metriche per ottenere risultati più precisi.

_Notifiche push_

* È stato risolto un problema che impediva di fare clic su un evento push nella cronologia di marketing di un profilo.
* È stato migliorato l’utilizzo delle notifiche push nei flussi di lavoro.

## Versione 17.4 - Aprile 2017 {#release-17-4---april-2017}

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
   <td> Funzionalità di editing immagine migliorate con Creative SDK<br /> </td> 
   <td> Ora puoi accedere a un set completo di funzioni fornite da Creative SDK per migliorare le immagini direttamente nell’editor dei contenuti durante la modifica di e-mail o la destinazione di una pagina.<br /> Questa funzione non richiede l’acquisizione di soluzioni Creative Cloud aggiuntive.<br /> Per ulteriori informazioni, consulta la <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifiche push transazionali<br /> </td> 
   <td> Il canale dell’applicazione Mobile è stato aggiunto alle funzionalità di messaggistica transazionale di Adobe Campaign. Sono ora supportati tre canali per i messaggi transazionali: notifiche e-mail, SMS e push.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/transactional-push-notifications.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifiche push ricorrenti<br /> </td> 
   <td> Ora puoi configurare notifiche push ricorrenti in un flusso di lavoro. Puoi utilizzare notifiche push ricorrenti in situazioni in cui i clienti si aspettano aggiornamenti periodici, come promemoria settimanali per estrarre nuovi contenuti o promozioni.<br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/push-notification-delivery.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Connettore Amazon Simple Storage Service (S3)<br /> </td> 
   <td> È ora possibile utilizzare il connettore Amazon Simple Storage Service (S3) per importare o esportare dati in Adobe Campaign. Può essere configurato in un’attività del flusso di lavoro. La configurazione viene eseguita in un account esterno.<br /> Per ulteriori informazioni, consulta la <a href="../../administration/using/external-accounts.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrazione live Dreamweaver<br /> </td> 
   <td> L’integrazione tra Adobe Campaign e Dreamweaver è ora live. Ora funziona con l’ultima versione ufficiale di Dreamweaver (17.0.2).<br /> È necessaria l’installazione dell’estensione Adobe Campaign Integration. Per ulteriori informazioni, consulta <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=it">video</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Piattaforma_

* È stato risolto un problema di consumo di memoria.

_E-mail e messaggi SMS_

* È stato risolto un problema che impediva la corretta sincronizzazione del contenuto con le ultime modifiche durante l’anteprima di un messaggio.
* È stato risolto un problema che impediva la creazione o l’eliminazione di una regola di elaborazione e-mail MX o Dominio.
* È stato risolto un problema che poteva impedire l’invio di e-mail con più alias.
* È stato risolto un problema che impediva la visualizzazione dei registri di consegna di trap nei registri di invio della consegna.
* È stato risolto un problema che causava un errore durante la visualizzazione degli URL tracciati di una consegna senza URL nel relativo contenuto.
* È stato risolto un problema che impediva la corretta applicazione degli attributi di dimensione dell’immagine nel messaggio inviato.

_Messaggi transazionali_

* Il campo rtEventHistoId non è più esposto come campo di personalizzazione in un modello di messaggio transazionale.

_Pagine di destinazione_

* Abbiamo ottimizzato il **[!UICONTROL by email]** filtro utilizzato nelle pagine di destinazione per riconciliare i nuovi sottoscrittori con i profili di database.
* È stato risolto un problema che causava la visualizzazione di input di testo libero invece delle caselle di controllo durante l’utilizzo di campi booleani in una configurazione del modulo.
* È stato risolto un problema che impediva la generazione delle miniature delle pagine di destinazione.

_Flussi di lavoro_

* È stato corretto un errore di visualizzazione durante la modifica di un **[!UICONTROL End]** o **[!UICONTROL External Signal]** (solo su Safari).
* È stato migliorato il messaggio di errore visualizzato durante la modifica di un **[!UICONTROL Read Audience]** attività contenente un pubblico errato.
* È stato risolto un problema che poteva causare un errore SQL durante l’esecuzione di un’attività di sottoscrizione.

_Integrazioni_

* Dati dei punti di interesse: è stato corretto un errore che si verificava durante il conteggio degli abbonati alla posizione.

_Tipi di pubblico e query_

* È stato risolto un problema che impediva l’utilizzo di aggregati di somma e media in una raccolta nell’editor delle query.
* È stato risolto un problema che poteva impedire il ricaricamento dell’editor delle query dopo la modifica della risorsa del filtro.

_Rapporti_

* È stato risolto un problema che impediva il corretto calcolo delle metriche a tasso aperto quando si selezionavano più righe in una tabella.
* È stato corretto un errore che mostrava solo le metriche come valori interi. Le metriche possono ora essere visualizzate con decimali.

_Notifiche push_

* È stato risolto un problema che impediva la visualizzazione di un messaggio di errore durante la creazione di un’applicazione Android collegata a un’app mobile non creata in MCPNS.
* È stato risolto un problema che consentiva a un utente di aggiungere suoni a una notifica silenziosa.

## Versione 17.2 - Marzo 2017 {#release-17-2---march-2017}

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
   <td> Reporting dinamico<br /> </td> 
   <td> Dynamic Reporting fornisce una nuova generazione di rapporti aziendali completamente personalizzabili e in tempo reale. Basata su tabelle pivot e grafici, questa funzione consente di trascinare e rilasciare variabili e dimensioni per analizzare l’efficienza e l’efficacia delle campagne di marketing. Il reporting dinamico consente inoltre di creare da zero rapporti aziendali personalizzati e di salvarli per un utilizzo successivo.<br /> Per ulteriori informazioni, consulta la <a href="../../reporting/using/about-dynamic-reports.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrazione Dreamweaver (Labs)<br /> </td> 
   <td> Con l’integrazione di Adobe Campaign e Dreamweaver, ora disponi di un processo integrato per la creazione di campagne e-mail con soluzioni Adobe.<br /> Puoi modificare le e-mail di Adobe Campaign in Dreamweaver e sincronizzare il contenuto senza soluzione di continuità tra le due soluzioni.<br /> Per la versione iniziale, l’integrazione è disponibile come funzione "Labs" e funziona solo con Dreamweaver Pre-Release Beta. Se desideri attivarlo, contatta AC-DW-integration@adobe.com.<br /> Per ulteriori informazioni, consulta <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">video</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ottimizzazione manuale del tempo di invio<br /> </td> 
   <td> Ora puoi definire manualmente un orario di invio personalizzato per destinatario, a livello di consegna o utilizzando un flusso di lavoro. <br /> Sono disponibili due nuove opzioni: <br /> 
    <ul> 
     <li> Tutti i destinatari ricevono il messaggio tenendo conto del loro fuso orario. </li> 
     <li> Ciascun destinatario riceve il messaggio in una data e un'ora calcolate definite da una formula. </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../sending/using/optimizing-the-sending-time.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifiche push Nuove funzionalità<br /> </td> 
   <td> Il canale di notifica push è stato migliorato con diverse nuove funzionalità:<br /> 
    <ul> 
     <li> Nuova interfaccia di authoring </li> 
     <li> Notifiche silenziose </li> 
     <li> Push interattivo </li> 
     <li> Supporto di contenuti avanzati </li> 
     <li> Calcolatore dimensione payload </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../channels/using/about-push-notifications.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: nuova attività Segnale<br /> </td> 
   <td> Attiva un flusso di lavoro da un altro tramite il nuovo <span class="uicontrol">Segnale</span> attività.<br /> Grazie alla possibilità di avviare un flusso di lavoro da un altro, ora puoi supportare percorsi di clienti più complessi. Puoi monitorare meglio i percorsi dei clienti e reagire in caso di problemi.<br /> Sono state aggiornate diverse attività del flusso di lavoro:<br /> 
    <ul> 
     <li> <span class="uicontrol">Fine</span> attività: una nuova scheda ti consente di specificare un flusso di lavoro da attivare dopo l’esecuzione dell’attività. </li> 
     <li> <span class="uicontrol">Update data</span> attività: utilizza la nuova transizione in uscita vuota per aggiungere un <strong>Fine</strong> attività che attiva un altro flusso di lavoro. Le transizioni vuote in uscita non contengono dati e non occupano spazio inutile sul sistema </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../automating/using/external-signal.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: nuova attività Read audience<br /> </td> 
   <td> Avvia il processo di targeting con un pubblico esistente che puoi facilmente selezionare e perfezionare in una sola attività.<br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/read-audience.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dati dei punti di interesse<br /> </td> 
   <td> I dati dei punti di interesse integrano Adobe Campaign con Adobe Analytics per dispositivi mobili. Un marchio può raccogliere dati dalle posizioni mobili degli utenti, denominate <strong>Punti di interesse</strong> - quando gli utenti aprono l’app del brand. Questo consente al brand di sfruttare i flussi di lavoro Adobe Campaign per inviare messaggi personalizzati in base alle posizioni degli utenti. Questo canale sfrutta l’SDK del servizio core Mobile.<br /> Tieni presente che l’utilizzo di questa funzione richiede Analytics for Mobile, una soluzione a pagamento.<br /> Per ulteriori informazioni, consulta la <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API REST<br /> </td> 
   <td> Le risorse collegate a qualsiasi livello ai profili o alle risorse dei servizi sono ora disponibili nell’API.<br /> Per ulteriori informazioni, consulta la <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* È ora possibile aggiungere dati di profilo durante l’esportazione dei registri di consegna.

_E-mail e messaggi SMS_

* È stato risolto un problema che causava la **[!UICONTROL Request confirmation before sending messages]** per rimanere selezionata anche dopo averlo deselezionato e aver salvato la consegna.
* È stato risolto un problema che poteva impedire l’annullamento della pubblicazione delle e-mail transazionali.
* È stato risolto un problema che impediva la corretta sincronizzazione del contenuto con le modifiche più recenti prima di visualizzare l’anteprima di una consegna.

_Pagine di destinazione_

* È stato corretto un errore che impediva agli utenti di apportare modifiche facendo clic nel contenuto di una pagina di destinazione.

_Flussi di lavoro_

* È stato risolto un problema che poteva impedire la lettura del contenuto della transizione di rifiuto di un **[!UICONTROL Load file]** attività.
* È stato risolto un problema che impediva la corretta considerazione delle colonne scambiate durante la configurazione di un **[!UICONTROL Load file]** attività.

## Versione 17.1 - Gennaio 2017 {#release-17-1---january-2017}

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
   <td> Esportazione registro per reporting esterno<br /> </td> 
   <td> Esporta i registri, ad esempio quelli di consegna e di tracciamento, per elaborarli negli strumenti di reporting o BI preferiti. Puoi utilizzare flussi di lavoro semplici con query incrementali per automatizzare le esportazioni regolari di nuovi registri.<br /> Oltre alla disponibilità delle risorse di registro dal selettore delle risorse, sono stati apportati miglioramenti al <a href="../../automating/using/incremental-query.md">Incremental query</a> e <a href="../../automating/using/extract-file.md">Extract file</a> attività:<br /> 
    <ul> 
     <li> <span class="uicontrol">Incremental query</span> ora consente di utilizzare un campo data per recuperare dati nuovi o aggiornati. In precedenza, tutti i risultati delle esecuzioni precedenti venivano automaticamente esclusi, anche se sono stati aggiornati dopo l’ultima esecuzione. </li> 
     <li> <span class="uicontrol">Extract file</span> ora è possibile esportare le etichette per i valori di enumerazione invece degli ID. </li> 
    </ul> Queste attività sono disponibili per gli amministratori con accesso a tutte le unità geografiche e organizzative.<br /> Per ulteriori informazioni sull’esportazione dei registri, consulta <a href="../../automating/using/exporting-logs.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Funzionalità di marketing per i messaggi transazionali<br /> </td> 
   <td> Gli addetti al marketing possono ora inviare messaggi transazionali basati sui profili di marketing dei clienti. Questo consente loro di:<br /> 
    <ul> 
     <li> Applicare regole di tipologia di marketing come <span class="uicontrol">Indirizzo sul elenco Bloccati</span> . </li> 
     <li> Includere il collegamento di annullamento all’abbonamento nei messaggi; </li> 
     <li> Aggiungere messaggi transazionali al reporting globale sulla distribuzione; </li> 
     <li> Utilizzare messaggi transazionali nel customer journey. </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API di messaggistica transazionale<br /> </td> 
   <td> L’API di messaggistica transazionale è ora disponibile tramite <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, facilitando l'utilizzo e il monitoraggio:<br /> 
    <ul> 
     <li> Puoi sfruttare le funzionalità di reporting e monitoraggio di adobe.io platform. </li> 
     <li> L’autenticazione viene ora eseguita utilizzando l’autenticazione basata sul token adobe.io invece dell’inserire nell'elenco Consentiti IP, semplificando il processo di sicurezza. </li> 
     <li> Tutte le API sono ora integrate in un’unica piattaforma, semplificando al massimo l’aggiunta di funzionalità di messaggistica transazionale all’integrazione se supporti già l’API Profilo e servizi. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* La **[!UICONTROL Access authorization]** sono tornate alle proprietà della pagina di destinazione.
* È stato risolto un problema che poteva causare il rendering di una vecchia immagine invece dell&#39;immagine corretta. Ciò si verificava se l’immagine sorgente era stata aggiornata nella definizione del contenuto di una consegna o di una pagina di destinazione.
* È stato risolto un problema che impediva agli utenti di modificare alcuni campi in un account esterno SFTP esistente.
* Sono stati risolti diversi problemi relativi all’interfaccia utente. Ad esempio, gli utenti possono ora modificare gli attributi del profilo e salvare le modifiche senza problemi con l’interfaccia utente.

_E-mail e messaggi SMS_

* È stato risolto un problema relativo ai modelli di consegna con contenuto HTML contenente un

_Notifiche push_

* È stato risolto un problema che poteva impedire il postback da un&#39;applicazione al server Adobe Campaign.
* È stato risolto un problema che poteva impedire **[!UICONTROL Play a sound]** e **[!UICONTROL Custom fields]** da prendere in considerazione per Android.
* È stato risolto un problema che poteva causare l’aggiunta di un carattere di escape aggiuntivo ai caratteri Unicode utilizzati per Emojis.
* Quando al elenco Bloccati viene aggiunto il token di registrazione di un utente iscritto, lo stato corrispondente viene aggiornato immediatamente nell’elenco degli abbonati dell’applicazione in Adobe Campaign.

_Flussi di lavoro_

* È stato risolto un problema che poteva impedire le anteprime delle query sulle risorse dell’evento (ad esempio rtEvent).
* Il file di rifiuto generato da un **[!UICONTROL Load file]** ora è possibile recuperare l’attività nella relativa transizione in uscita ed elaborarla nell’attività successiva. Ad esempio, carica il file di rifiuto tramite un server SFTP utilizzando **[!UICONTROL Transfer file]** .
* È stato risolto un problema che poteva impedire a un utente di limitare la popolazione di un segmento se **[!UICONTROL Temporary resource]** è stato selezionato in **[!UICONTROL General]** scheda di **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** le attività non possono più essere impostate per attivare un flusso di lavoro più di una volta ogni 10 minuti.
* È stato risolto un problema che poteva impedire **[!UICONTROL Use common columns]** dal corretto funzionamento in un **[!UICONTROL Union]** attività.

_Integrazioni_

* È stato risolto un problema che poteva causare un errore durante la distribuzione di un trigger di evento in Adobe Campaign. Questo errore si verificava quando i metadati &quot;Probabilità di tornare tra 30 giorni&quot; erano stati aggiunti al trigger di abbandono in Adobe Marketing Cloud.
* È stato risolto un problema che poteva causare la cancellazione del campo Dimension di Target da parte del flusso di lavoro tecnico durante l’importazione di tipi di pubblico dal servizio core Persone . Impossibile recuperare i tipi di pubblico importati dalle query successive.
* È stato risolto un problema che poteva causare il **[!UICONTROL Save audience]** attività di un flusso di lavoro che non riesce quando l’opzione **[!UICONTROL Share in Adobe Marketing Cloud]** è stato controllato.
