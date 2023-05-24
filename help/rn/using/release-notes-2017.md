---
title: Note sulla versione 2017
description: In questa pagina sono elencate tutte le versioni di Adobe Campaign Standard del 2017.
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 73a1ec49-fcbc-406b-9590-1ad20da9e73b
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '4562'
ht-degree: 8%

---

# Note sulla versione 2017{#release-notes}

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
   <td> La gestione dell’affaticamento consente di creare regole di affaticamento per gestire la comunicazione eccessiva con i profili. Le regole di affaticamento sono facilmente costruibili, ma sono estremamente flessibili con funzionalità quali il conteggio dei messaggi tra più canali (inclusi i messaggi transazionali), il conteggio solo di consegne specifiche o l’applicazione di regole a profili specifici.<br /> Per ulteriori informazioni, consulta la <a href="../../sending/using/fatigue-rules.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creazione di contenuti: importazione da un URL<br /> </td> 
   <td> L’importazione da un URL consente di recuperare rapidamente il contenuto creativo da un sito web per creare e-mail per qualsiasi consegna. Inoltre, puoi semplificare il processo creativo consentendo a terze parti di condividere i contenuti direttamente tramite un URL. Il contenuto importato può essere utilizzato in modo flessibile come parte di una singola consegna o a livello di modello, garantendo la coerenza del brand per tutte le campagne correlate, siano esse messaggi basati su flusso di lavoro o messaggi transazionali, e includendo test A/B o multivariati. L’importazione da un URL converte e tiene traccia automaticamente di tutti i collegamenti per monitorare le prestazioni delle e-mail tramite Reporting dinamico.<br /> Per ulteriori informazioni, consulta la <a href="../../designing/using/using-existing-content.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Piattaforma_

* È stato risolto un problema che poteva impedire la corretta decompressione dei file compressi di grandi dimensioni.
* È stata migliorata la sicurezza nella gestione del brand. La modifica del nome e dell’indirizzo del mittente di un brand è ora riservata agli amministratori tecnici Adobi.
* Per migliorare la sicurezza, contenuti generati dall’utente (immagini, pagine mirror, pagine di destinazione, ecc.) non può più essere gestito dal dominio adobe.com. È ora obbligatorio utilizzare il proprio dominio per gestire queste risorse tramite l’utilizzo del branding.
* È stato risolto un problema di interfaccia che si verificava durante la visualizzazione e il filtraggio delle attività di marketing.
* È stato risolto un problema che impediva l’aggiornamento dei campi della data di abbonamento con una chiamata API POST Rest.

_E-mail, messaggi SMS e direct mail_

* È stato risolto un problema che poteva impedire il targeting di un pubblico di tipo elenco in un messaggio, causando un errore di preparazione.
* Sono state aggiunte lingue mancanti nelle funzionalità di consegna e-mail multilingue.
* La miniatura del contenuto, visualizzata nel dashboard di consegna, ora viene aggiornata automaticamente quando l’utente modifica il contenuto e lo salva.
* È stato risolto un problema relativo al fuso orario che impediva l’apertura di una consegna.

_Notifiche push_

* Durante la configurazione del canale di notifica push, la piattaforma del provider push per iOS deve essere **apns** e per Android **gcm**.
* È stato corretto un errore che impediva l’aggiunta dell’app mobile iOS all’interfaccia di Adobe Campaign.
* Le notifiche push sono ora supportate sia su applicazioni mobili GCM che su applicazioni mobili Android abilitate per FCM.
* È stato corretto un errore che impediva il salvataggio del contenuto durante la duplicazione di un modello di notifica push.
* È ora possibile creare o aggiornare un profilo dal database di Adobe Campaign riconciliando i dati degli utenti delle app mobili.
* Adobe Campaign ora dà priorità all’elaborazione delle notifiche push transazionali rispetto alle notifiche push standard.

_Rapporti_

* È stato risolto un problema che impediva la visualizzazione delle percentuali di hot click nel contenuto dell’e-mail.
* È stato risolto un problema relativo alla metrica di inserisco nell&#39;elenco Bloccati del che veniva conteggiata come mancato recapito permanente anziché come mancato recapito.
* È stato risolto un problema che causava la visualizzazione dei conteggi negativi nei dati di riepilogo.
* È stato risolto un problema a causa del quale venivano conteggiati i profili nel segmento di età sbagliato.
* Le formule di calcolo dei mancati recapiti non permanenti e permanenti sono state modificate.

_Flussi di lavoro_

* È stato risolto un problema in **[!UICONTROL Load file]** attività che potrebbe causare errori dopo l’aggiunta e la rimozione manuale di colonne nell’attività.
* Il **[!UICONTROL deliverabilityUpdate]** il flusso di lavoro tecnico è ora pianificato per l’esecuzione alle 2, ora del server.
* È stato risolto un problema di sicurezza che consentiva di eseguire un’esportazione di elenco senza il ruolo di esportazione.
* È stato risolto un problema relativo al **[!UICONTROL Reconciliation]** attività.
* È stato risolto un problema relativo all’utilizzo di caratteri jolly nella sezione **[!UICONTROL File Transfer]** attività.

_Profili e pubblico_

* È stato risolto un problema che poteva impedire la corretta considerazione di una condizione di una query in alcuni casi specifici, generando risultati errati.
* È stato risolto un problema che poteva impedire l’accesso ai profili targetizzati in un messaggio preparato, ma mai inviato e scaduto.

_Integrazioni_

* È stato risolto un problema che poteva impedire la corretta visualizzazione e selezione di alcune Origini dati create per Triggers.

_Risorse personalizzate_

* È stato risolto un problema che si verificava nelle schermate elenco, a causa del quale le righe di risorse personalizzate potevano essere visualizzate senza alcun dato.
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
   <td> Presentazione di diciotto nuovi modelli reattivi progettati in due splendidi temi: Astro e Feather. Questi modelli personalizzabili sono indipendenti dal settore e pronti per essere utilizzati immediatamente. I modelli includono contenuti per una varietà di casi d’uso, per progettare e distribuire le campagne di e-mail marketing in modo più rapido, efficiente e bello che mai.<br /> Per ulteriori informazioni, consulta la <a href="../../designing/using/using-reusable-content.md#content-templates">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Reporting dinamico con i dati profilo<br /> </td> 
   <td> Reporting dinamico fornisce report aziendali completamente personalizzabili e in tempo reale. Con questa versione, un potente miglioramento al Reporting dinamico aggiunge l’accesso ai dati del profilo, consentendo l’analisi demografica per dimensioni di profilo come genere, città, codice postale ed età, oltre ai dati funzionali delle campagne e-mail come aperture e clic. Con la stessa interfaccia di trascinamento facile da usare, determinare le prestazioni della campagna e-mail rispetto ai segmenti di clienti più importanti è più semplice che mai.<br /> Per ulteriori informazioni, consulta la <a href="../../reporting/using/about-dynamic-reports.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abbonamento di massa con origine e data<br /> </td> 
   <td> Con questo miglioramento di massa degli abbonamenti, ora puoi memorizzare le informazioni sull’abbonamento (origine e data) direttamente nel database di Adobe Campaign Standard tramite l’attività Subscription Services in un flusso di lavoro.<br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/subscription-services.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Piattaforma_

* Alcuni clienti devono essere in grado di sfruttare un ID proveniente da Adobe Campaign Standard in quanto non gestiscono una chiave univoca per identificare i propri record. Questo ID (**ID ACS**) può essere esportato e utilizzato come chiave di riconciliazione durante l’aggiornamento dei dati. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* Il protocollo FTP verrà dichiarato obsoleto. Al suo posto, ora devi utilizzare SFTP. Per non bloccare le implementazioni esistenti, le configurazioni esistenti su FTP continueranno a funzionare come prima, ma l’opzione non verrà visualizzata per le nuove attività.

_E-mail, messaggi SMS e direct mail_

* Ora è possibile creare nuovi criteri di avviso da utilizzare nelle notifiche di avviso di consegna. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* La progettazione delle notifiche degli avvisi di consegna è nuova ed è stata migliorata l’esperienza utente del dashboard degli avvisi di consegna.
* Ora, quando un account esterno di indirizzamento è disabilitato, viene visualizzato un avviso nelle consegne interessate (e-mail, SMS e push) e nel **Anteprima** in queste consegne.
* È stato risolto un problema che causava un errore nell’anteprima di un test A/B sul contenuto dell’e-mail quando il testo dinamico era abilitato nella riga dell’oggetto.

_Messaggi transazionali_

* È ora possibile definire quando inviare un messaggio di follow-up, ad esempio 3 giorni dopo l’invio di un messaggio sulle transazioni. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* È ora possibile definire la data a partire dalla quale devono essere inviati i messaggi transazionali collegati a un evento.
* È stato risolto un problema che causava un errore SQL durante l’esecuzione di un flusso di lavoro contenente un messaggio di follow-up dopo l’eliminazione di profili collegati a eventi ricevuti ed elaborati.
* È stato corretto un errore che impediva di eliminare un profilo collegato a un evento.
* È stato risolto un problema che poteva impedire il funzionamento del reindirizzamento dei collegamenti tracciati.
* È stato risolto un problema che impediva la disattivazione del tracciamento per alcuni collegamenti in un messaggio e-mail o SMS.

_Rapporti_

* Il **Hot click** Il report è stato migliorato. Inoltre, ora è possibile visualizzare gli hot click in base a ciascun contenuto condizionale definito in una consegna e gli hot click per ogni esecuzione di consegne ricorrenti o messaggi transazionali. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* È stato risolto un problema che impediva alla metrica di quarantena di recuperare i dati corretti.
* Al widget del calendario è stato aggiunto un nuovo intervallo di tempo predefinito.
* Il [metriche report dinamici](../../reporting/using/indicator-calculation.md) e [KPI delle campagne](../../sending/using/confirming-the-send.md) (visualizzati nel dashboard dei messaggi inviati) sono stati allineati per una maggiore coerenza.
* È stato risolto un problema che poteva causare l’arresto anomalo del pipeline su debian 7.

_Flussi di lavoro_

* È stato risolto un problema che poteva impedire il funzionamento della conservazione dei file importati.

_Integrazioni_

* Le eVar e gli eventi sono ora supportati per l’integrazione di Analytics e Campaign.
* Quando si invia un’e-mail con il contenuto del carrello abbandonato, il parametro di payload per gli elementi rimossi dal carrello è ora facoltativo.

_Profili e pubblico_

* Adobe Campaign ora fornisce un rapporto che mostra il numero di profili attivi. Questo report è solo informativo, non ha un impatto diretto sulla fatturazione. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../audiences/using/active-profiles.md).
* È stato risolto un problema che impediva l’abbonamento a un servizio dei profili quando si utilizzava l’API Profiles and Services.

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
   <td> Definisci ed esegui consegne e-mail e SMS multilingue tramite un’unica consegna basata sulla lingua preferita dei clienti segmentati automaticamente. Rapporto sulle prestazioni di ogni consegna fino al livello della lingua e dei singoli livelli.<br /> Sono sempre più numerose le aziende che devono affrontare la sfida di distribuire contenuti in più lingue man mano che crescono in patria e all'estero. Di conseguenza, la semplificazione della consegna dei messaggi localizzati è un elemento chiave di un'efficace strategia di comunicazione con i clienti per le aziende multinazionali, le aziende in paesi con più lingue e le aziende che desiderano personalizzare ulteriormente i propri contenuti a livello linguistico indipendentemente dal luogo in cui risiedono i clienti. Per ulteriori informazioni, consulta la <a href="../../channels/using/creating-a-multilingual-email.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifiche di Adobe Campaign<br /> </td> 
   <td> Ricevi notifiche su importanti attività di sistema direttamente in Adobe Campaign Standard. Ad esempio, riceverai una notifica sull’avanzamento delle consegne in corso o quando un flusso di lavoro è in errore.<br /> Le notifiche in tempo reale tengono informate le parti interessate e forniscono agli utenti la possibilità di agire immediatamente e direttamente sulle notifiche di attività dall’interno dell’applicazione. Il risultato per i team è l’agilità avanzata, l’efficienza e l’esecuzione più fluida delle campagne. Per ulteriori informazioni, consulta la <a href="../../administration/using/sending-internal-notifications.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Avvisi sulla consegna<br /> </td> 
   <td> Oltre a visualizzare le notifiche direttamente in Adobe Campaign Standard, Adobe Campaign ora fornisce anche un sistema di avvisi e-mail per attivare gli avvisi e-mail per gli utenti o le parti interessate esterne di importanti attività del sistema. Crea, gestisci e ricevi avvisi e dashboard personalizzabili per tenere traccia dei successi o degli errori di consegna.<br /> Avvisi sulla consegna di Adobe Campaign migliora l’efficienza mantenendo tutti gli utenti Adobe Campaign coinvolti in un’azienda automaticamente informati sullo stato di esecuzione della consegna tramite e-mail e dashboard. Per ulteriori informazioni, consulta la <a href="../../sending/using/receiving-alerts-when-failures-happen.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Crittografia dell’ID dichiarato nelle origini dati<br /> </td> 
   <td> Invia trigger e-mail e SMS senza la necessità di un profilo esistente in Campaign utilizzando informazioni di contatto crittografate (indirizzo e-mail o numero di telefono) come ID dichiarato. Poiché gli ID dichiarati crittografati possono essere decodificati da Adobe Campaign Standard, Campaign può ora creare nuovi profili commerciabili quando riceve tipi di pubblico da altre soluzioni Experience Cloud contenenti contatti precedentemente sconosciuti.<br /> Puoi indirizzare l’attività a clienti potenziali e sconosciuti in tempo reale tramite e-mail e SMS per migliorare la fedeltà alla base di clienti esistente e acquisire nuovi clienti, rispettivamente. Sfrutta al meglio i dati dei cookie di prime parti (da Adobe Audience Manager*) una volta che i potenziali clienti si autenticano e sfruttano tali informazioni in Adobe Campaign. <br /> *È richiesto Adobe Audience Manager. Per ulteriori informazioni, consulta la <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Condivisione di KPI (Key Performance Indicator) da Campaign ad Analytics<br /> </td> 
   <td> Condividi i dati della campagna con Adobe Analytics per misurare le metriche di e-mail marketing da Campaign insieme ad altre attività di marketing e pubblicitarie attraverso la conversione, unificando il comportamento prima e dopo il clic.<br /> Monitora direttamente le prestazioni complessive e scopri le sinergie con i programmi esterni in Analytics. Applica alle tue campagne il tuo apprendimento da questa visualizzazione consolidata; in ultima analisi, migliora i tassi di apertura, click-through e conversione, aumentando i ricavi e le prestazioni complessive della campagna. <br /> Adobe Analytics è obbligatorio. Per ulteriori informazioni, consulta la <a href="../../integrating/using/about-campaign-analytics-integration.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Canale direct mailing - Rendi al mittente<br /> </td> 
   <td> Sono ora supportati gli scambi di file Flat con i provider Direct Mail che incorporano le informazioni Return to Sender. Questo miglioramento al canale Direct Mail consente di escludere gli indirizzi postali corrispondenti da comunicazioni future.<br /> Ciò consente agli addetti al marketing di ricevere notifiche su indirizzi non corretti e di interagire con il cliente attraverso altri canali o di incoraggiarli ad aggiornare il proprio indirizzo postale. Questo riduce anche il numero di dollari di marketing sprecati, in quanto gli esperti di marketing evitano di inviare e-mail a indirizzi errati. <br /> Direct mailing è disponibile come canale aggiuntivo. Per ulteriori informazioni, consulta la <a href="../../channels/using/return-to-sender.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* È stato risolto un problema che consentiva a qualsiasi utente di esportare gli elenchi. Ora solo gli utenti con **[!UICONTROL Export]** ruolo sono consentiti.

_E-mail, messaggi SMS e direct mail_

* È stato risolto un problema relativo al **updateDeliveryExecInfo** flusso di lavoro che imposta **Da consegnare** per le consegne SMS.
* In **Parametri avanzati** delle proprietà del modello di consegna, la **Indirizzamento** nell’elenco a discesa ora vengono visualizzati solo gli account esterni corrispondenti al tipo di messaggio del modello. Ad esempio, un modello di consegna e-mail visualizza solo gli account e-mail esterni.
* È stato risolto un problema relativo al **[!UICONTROL Text]** formato e-mail preferito definito per i profili di test.
* È stato risolto un problema che causava un errore JavaScript in durante la selezione del fuso orario predefinito nella schermata di definizione della pianificazione di una consegna.
* È stato risolto un problema che impediva la visualizzazione delle trap nei registri di invio.
* Nella schermata di selezione dei modelli della procedura guidata di creazione della consegna, i modelli di test A/B e di follow-up ora sono nascosti per impostazione predefinita. Per ulteriori informazioni, consulta [documentazione dettagliata](../../channels/using/creating-an-email.md).
* È stato risolto un problema che consentiva a qualsiasi utente di inviare consegne. Ora solo gli utenti con **[!UICONTROL Start deliveries]** ruolo sono consentiti. Per ulteriori informazioni, consulta [documentazione dettagliata](../../sending/using/confirming-the-send.md).

_Notifiche push_

* È stato risolto un problema relativo al **Endpoint di tracciamento campagna** URL che impediva la generazione di rapporti.
* È stato risolto un problema che impediva la visualizzazione del titolo della notifica push sui dispositivi Android.
* È stato risolto un problema che impediva la visualizzazione della notifica push sui dispositivi iOS quando la notifica push conteneva solo un titolo (e nulla nel corpo del messaggio).
* È stato risolto un problema che impediva il tracciamento degli URL degli allegati multimediali in una consegna, impedendo l’incorporamento di video e immagini nella consegna. Il tracciamento degli URL di tipo mediaAttachmentURL ora è disattivato per impostazione predefinita per le notifiche push.

_Rapporti_

* È stato corretto un problema a causa del quale i valori venivano visualizzati in modo diverso nei grafici e nelle tabelle.
* È stato corretto un problema a causa del quale i valori delle notifiche push venivano visualizzati come valori e-mail.
* È stato risolto un problema a causa del quale i valori venivano visualizzati come sconosciuti al momento della creazione di una consegna al di fuori di una campagna.
* È stato corretto un problema a causa del quale i dati del rapporto SMS venivano visualizzati come dati di applicazioni mobili.

_Flussi di lavoro_

* Ora puoi filtrare i registri del flusso di lavoro (periodo di tempo e ricerca di testo). Per ulteriori informazioni, consulta [documentazione dettagliata](../../automating/using/monitoring-workflow-execution.md).
* Nelle consegne dei flussi di lavoro è ora disponibile un’opzione per disattivare la conferma prima dell’invio.
* È stato risolto un problema che impediva di impostare una transizione in uscita nella procedura guidata di creazione di una consegna ricorrente.
* È stato risolto un problema che si verificava durante l’utilizzo di un’attività di query del flusso di lavoro basata su un campo risorsa personalizzato con un’enumerazione con molti valori

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
   <td> Infrangi la barriera digitale e collegati al mondo fisico con il primo canale offline di Adobe Campaign Standard, Direct Mail. Questa funzione ti consente di personalizzare e generare il file richiesto dai provider di direct mailing come parte delle campagne cross-channel. Utilizza Direct Mail per coinvolgere nuovamente i clienti o per migliorare l’esperienza del cliente con un punto di contatto tattile convincente che spinge i clienti a visitare la tua app, il tuo sito web o il tuo store.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/about-direct-mail.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Invia e-mail in Ccn<br /> </td> 
   <td> Ccn e-mail consente di salvare messaggi e-mail univoci inviati a singoli destinatari, consentendo in tal modo al brand di archiviarli. Aggiungendo un indirizzo e-mail Ccn a tutte le e-mail, i clienti di Adobe Campaign Standard possono conservare una copia esatta di ogni e-mail con questa funzione. Si tratta di un requisito legale comune per il settore dei servizi finanziari ed è utile per assistere i centri di assistenza clienti nella risoluzione dei conflitti in tempo reale.<br /> Per ulteriori informazioni, consulta la <a href="../../sending/using/archiving.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Aggiornamenti dell’interfaccia_

* Nella barra superiore, il **[!UICONTROL Timeline]** il collegamento è stato rimosso e sostituito con un collegamento a **[!UICONTROL Programs & Campaigns]** .

_E-mail e messaggi SMS_

* È stato risolto un problema che causava la visualizzazione di un colore errato per **[!UICONTROL Retry in progress]** stato della consegna. Il colore era grigio invece che blu.

_Flussi di lavoro_

* È stato risolto un problema che si verificava durante la modifica dell’azione da eseguire in una **[!UICONTROL Transfer file]** attività.

_Rapporti_

* Il **[!UICONTROL Spam]** e **[!UICONTROL Spam rate]** i calcoli dell&#39;indicatore sono stati modificati.
* Il **[!UICONTROL Bounce]** Le metriche sono state migliorate per ottenere risultati più precisi.

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
   <td> Ora puoi accedere a un set completo di funzioni basate su Creative SDK per migliorare le immagini direttamente nell’editor dei contenuti durante la modifica delle e-mail o delle pagine di destinazione.<br /> Questa funzione non richiede l'acquisizione di soluzioni Creative Cloud aggiuntive.<br /> Per ulteriori informazioni, consulta la <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifiche push transazionali<br /> </td> 
   <td> Il canale dell’applicazione mobile è stato aggiunto alle funzionalità di messaggistica transazionale di Adobe Campaign. Sono ora supportati tre canali per i messaggi transazionali: e-mail, SMS e notifiche push.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/transactional-push-notifications.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notifiche push ricorrenti<br /> </td> 
   <td> Ora puoi configurare le notifiche push ricorrenti in un flusso di lavoro. Puoi utilizzare notifiche push ricorrenti in situazioni in cui i clienti si aspettano aggiornamenti periodici, come promemoria settimanali per estrarre nuovi contenuti o promozioni.<br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/push-notification-delivery.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Connettore Amazon Simple Storage Service (S3)<br /> </td> 
   <td> Il connettore Amazon Simple Storage Service (S3) può ora essere utilizzato per importare o esportare dati in Adobe Campaign. Può essere impostato in un’attività del flusso di lavoro. La configurazione viene eseguita in un account esterno.<br /> Per ulteriori informazioni, consulta la <a href="../../administration/using/external-accounts.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrazione live di Dreamweaver<br /> </td> 
   <td> L’integrazione tra Adobe Campaign e Dreamweaver è ora live. Ora funziona con l'ultima versione ufficiale di Dreamweaver (17.0.2).<br /> È necessaria l'installazione dell'estensione dell'integrazione di Adobe Campaign. Per ulteriori informazioni, consulta questa <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=it">video</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Piattaforma_

* È stato risolto un problema di consumo di memoria.

_E-mail e messaggi SMS_

* È stato risolto un problema che impediva la corretta sincronizzazione del contenuto con le modifiche più recenti durante l’anteprima di un messaggio.
* È stato risolto un problema che impediva la creazione o l’eliminazione di una regola di elaborazione e-mail MX o Domain.
* È stato risolto un problema che poteva impedire l’invio di e-mail con più alias.
* È stato risolto un problema che impediva la visualizzazione dei registri di consegna delle trap nei registri di invio della consegna.
* È stato risolto un problema che causava un errore durante la visualizzazione degli URL tracciati di una consegna senza URL nel relativo contenuto.
* È stato risolto un problema che impediva la corretta applicazione degli attributi di dimensione di un’immagine nel messaggio inviato.

_Messaggi transazionali_

* Il campo rtEventHistoId non è più esposto come campo di personalizzazione in un modello di messaggio transazionale.

_Pagine di destinazione_

* Il **[!UICONTROL by email]** filtro utilizzato nelle pagine di destinazione per riconciliare i nuovi abbonati con i profili di database.
* È stato risolto un problema che causava la visualizzazione di input di testo libero invece di caselle di controllo quando si utilizzavano campi booleani in una configurazione di modulo.
* È stato risolto un problema che impediva la generazione delle miniature delle pagine di destinazione.

_Flussi di lavoro_

* È stato corretto un errore di visualizzazione durante la modifica di un’ **[!UICONTROL End]** o **[!UICONTROL External Signal]** attività (solo su Safari).
* È stato migliorato il messaggio di errore visualizzato durante la modifica di un **[!UICONTROL Read Audience]** attività contenente un pubblico errato.
* È stato risolto un problema che poteva causare un errore SQL durante l’esecuzione di un’attività di sottoscrizione.

_Integrazioni_

* Dati dei punti di interesse: è stato corretto un errore che si verificava durante il conteggio degli abbonati alla posizione.

_Tipi di pubblico e query_

* È stato risolto un problema che impediva l’utilizzo degli aggregati di somma e media in una raccolta nell’editor delle query.
* È stato risolto un problema che poteva impedire il ricaricamento dell’editor delle query dopo la modifica della risorsa del filtro.

_Rapporti_

* È stato risolto un problema che impediva il calcolo corretto delle metriche del tasso di apertura quando si selezionavano più righe in una tabella.
* È stato corretto un errore a causa del quale le metriche venivano visualizzate solo come valori interi. È ora possibile visualizzare le metriche con i decimali.

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
   <td> Il reporting dinamico fornisce una nuova generazione di rapporti aziendali completamente personalizzabili e in tempo reale. Basata su tabelle pivot dinamiche visive e grafici, questa funzione consente di trascinare e rilasciare variabili e dimensioni per analizzare l’efficienza e l’efficacia delle campagne di marketing. La generazione di rapporti dinamici consente inoltre di creare rapporti aziendali personalizzati da zero e di salvarli per un utilizzo successivo.<br /> Per ulteriori informazioni, consulta la <a href="../../reporting/using/about-dynamic-reports.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrazione Dreamweaver (Labs)<br /> </td> 
   <td> Con l’integrazione di Adobe Campaign e Dreamweaver, ora disponi di un processo integrato per la creazione di campagne e-mail con le soluzioni Adobe.<br /> Puoi modificare le e-mail di Adobe Campaign in Dreamweaver e sincronizzare i contenuti tra le due soluzioni.<br /> Per la versione iniziale, l’integrazione è disponibile come funzione "Labs" e funziona solo con Dreamweaver Pre Release Beta. Se desideri attivarlo, contatta AC-DW-integration@adobe.com.<br /> Per ulteriori informazioni, consulta questa <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=it">video</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ottimizzazione manuale del tempo di invio<br /> </td> 
   <td> Ora puoi definire manualmente un orario di invio personalizzato per destinatario, a livello di consegna o utilizzando un flusso di lavoro. <br /> Sono disponibili due nuove opzioni: <br /> 
    <ul> 
     <li> Tutti i destinatari ricevono il messaggio tenendo conto del loro fuso orario. </li> 
     <li> Ogni destinatario riceve il messaggio in una data e un’ora calcolate definite da una formula. </li> 
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
     <li> Calcolatore dimensioni payload </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../channels/using/about-push-notifications.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: nuova attività segnale<br /> </td> 
   <td> Attiva un flusso di lavoro da un altro flusso di lavoro utilizzando il nuovo <span class="uicontrol">Segnale</span> attività.<br /> Grazie alla possibilità di avviare un flusso di lavoro a partire da un altro, è ora possibile supportare percorsi di clienti più complessi. Puoi monitorare meglio i percorsi dei clienti e reagire in caso di problemi.<br /> Sono state aggiornate diverse attività del flusso di lavoro:<br /> 
    <ul> 
     <li> <span class="uicontrol">Fine</span> attività: una nuova scheda ti consente di specificare un flusso di lavoro da attivare dopo l’esecuzione dell’attività. </li> 
     <li> <span class="uicontrol">Aggiorna dati</span> attività: utilizza la nuova transizione in uscita vuota per aggiungere una <strong>Fine</strong> attività che attiva un altro flusso di lavoro. Le transizioni vuote in uscita non contengono dati e non occupano spazio inutile sul sistema </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../automating/using/external-signal.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flussi di lavoro: nuova attività Read audience<br /> </td> 
   <td> Avvia il processo di targeting con un pubblico esistente che puoi facilmente selezionare e perfezionare in un’attività.<br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/read-audience.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dati dei punti di interesse<br /> </td> 
   <td> I dati dei punti di interesse integrano Adobe Campaign con Adobe Analytics per dispositivi mobili. Un brand può raccogliere dati dalle posizioni mobili degli utenti, chiamate <strong>Punti di interesse</strong> - quando gli utenti aprono l’app del brand. Questo consente al brand di sfruttare i flussi di lavoro di Adobe Campaign per inviare messaggi personalizzati in base alla posizione degli utenti. Questo canale sfrutta l’SDK del servizio core Mobile.<br /> Tieni presente che l’utilizzo di questa funzione richiede Analytics per Mobile, che è una soluzione a pagamento.<br /> Per ulteriori informazioni, consulta la <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API REST<br /> </td> 
   <td> Le risorse collegate a qualsiasi livello alle risorse dei profili o dei servizi sono ora disponibili nell’API.<br /> Per ulteriori informazioni, consulta la <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* Ora è possibile aggiungere i dati del profilo durante l’esportazione dei registri di consegna.

_E-mail e messaggi SMS_

* È stato risolto un problema che causava la **[!UICONTROL Request confirmation before sending messages]** per rimanere selezionata anche dopo averla deselezionata e aver salvato la consegna.
* È stato risolto un problema che poteva impedire l’annullamento della pubblicazione delle e-mail transazionali.
* È stato risolto un problema che impediva la corretta sincronizzazione del contenuto con le modifiche più recenti prima di visualizzare un’anteprima di una consegna.

_Pagine di destinazione_

* È stato corretto un errore che impediva agli utenti di modificare quando facevano clic sul contenuto di una pagina di destinazione.

_Flussi di lavoro_

* È stato risolto un problema che poteva impedire la lettura del contenuto della transizione di rifiuto di una **[!UICONTROL Load file]** attività.
* È stato risolto un problema che impediva di tenere in considerazione correttamente le colonne scambiate durante la configurazione di un **[!UICONTROL Load file]** attività.

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
   <td> Esporta registri come i registri di consegna e di tracciamento per elaborarli negli strumenti di reporting o BI preferiti. Puoi utilizzare flussi di lavoro semplici con query incrementali per automatizzare le esportazioni regolari di nuovi registri.<br /> Oltre alla disponibilità delle risorse di registro dal selettore delle risorse, sono stati apportati miglioramenti alla <a href="../../automating/using/incremental-query.md">Query incrementale</a> e <a href="../../automating/using/extract-file.md">Extract file</a> attività:<br /> 
    <ul> 
     <li> <span class="uicontrol">Query incrementale</span> ora consente di utilizzare un campo data per recuperare dati nuovi o aggiornati. In precedenza, tutti i risultati di esecuzioni precedenti venivano automaticamente esclusi, anche se venivano aggiornati dopo l’ultima esecuzione. </li> 
     <li> <span class="uicontrol">Extract file</span> è ora possibile esportare le etichette per i valori di enumerazione anziché gli ID. </li> 
    </ul> Queste attività sono disponibili per gli amministratori con accesso a tutte le unità geografiche e organizzative.<br /> Per ulteriori informazioni sull’esportazione dei registri, consulta <a href="../../automating/using/exporting-logs.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Funzionalità di marketing per i messaggi transazionali<br /> </td> 
   <td> Gli addetti al marketing possono ora inviare messaggi transazionali basati sui profili di marketing dei clienti. Ciò consente loro di:<br /> 
    <ul> 
     <li> Applicare regole di tipologia di marketing come <span class="uicontrol">Indirizzo sul inserisco nell'elenco Bloccati di</span> . </li> 
     <li> Includere il collegamento di annullamento all’abbonamento nei messaggi; </li> 
     <li> Aggiungere messaggi transazionali al reporting globale sulla distribuzione; </li> 
     <li> Utilizzare messaggi transazionali nel customer journey. </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API di messaggistica transazionale<br /> </td> 
   <td> L’API di messaggistica transazionale è ora disponibile, per facilitarne l’utilizzo e il monitoraggio:<br /> 
    <ul> 
     <li> Puoi sfruttare le funzionalità di reporting e monitoraggio della piattaforma Adobe Developer. </li> 
     <li> L’autenticazione viene ora eseguita utilizzando l’autenticazione basata su token adobe.io invece di inserire nell'elenco Consentiti l’IP, semplificando il processo di sicurezza. </li> 
     <li> Tutte le API sono ora integrate in un’unica piattaforma, il che rende più semplice che mai aggiungere funzionalità di messaggistica transazionale all’integrazione, se già supporti l’API Profilo e Servizi. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Generale_

* Il **[!UICONTROL Access authorization]** Le opzioni sono tornate alle proprietà della pagina di destinazione.
* È stato risolto un problema che poteva causare il rendering di una vecchia immagine invece dell’immagine corretta. Ciò si verificava se l’immagine sorgente era stata aggiornata nella definizione del contenuto di una consegna o di una pagina di destinazione.
* È stato risolto un problema che impediva agli utenti di modificare alcuni campi in un account esterno SFTP esistente.
* Sono stati risolti diversi problemi relativi all’interfaccia utente. Ad esempio, ora gli utenti possono modificare gli attributi del profilo e salvare le modifiche senza problemi con l’interfaccia utente.

_E-mail e messaggi SMS_

* È stato risolto un problema relativo ai modelli di consegna con contenuto HTML che conteneva un

_Notifiche push_

* È stato risolto un problema che poteva impedire il postback da un’applicazione al server Adobe Campaign.
* È stato risolto un problema che poteva impedire **[!UICONTROL Play a sound]** e **[!UICONTROL Custom fields]** da considerare per Android.
* È stato risolto un problema che poteva causare l’aggiunta di un carattere di escape aggiuntivo ai caratteri Unicode utilizzati per gli emoticon.
* Quando il token di registrazione di un abbonato viene aggiunto al inserisco nell&#39;elenco Bloccati di registrazione, lo stato corrispondente viene immediatamente aggiornato nell’elenco degli abbonati dell’applicazione in Adobe Campaign.

_Flussi di lavoro_

* È stato risolto un problema che poteva impedire le anteprime delle query sulle risorse evento (ad esempio, rtEvent).
* Il file rifiutato generato da un **[!UICONTROL Load file]** l’attività può ora essere recuperata nella relativa transizione in uscita ed elaborata nell’attività successiva. Ad esempio, carica il file rifiutato tramite un server SFTP utilizzando **[!UICONTROL Transfer file]** .
* È stato risolto un problema che poteva impedire a un utente di limitare la popolazione di un segmento se **[!UICONTROL Temporary resource]** è stato selezionato in **[!UICONTROL General]** scheda di **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** non è più possibile impostare le attività per attivare un flusso di lavoro più di una volta ogni 10 minuti.
* È stato risolto un problema che poteva impedire **[!UICONTROL Use common columns]** da funzionare correttamente in un **[!UICONTROL Union]** attività.

_Integrazioni_

* È stato risolto un problema che poteva causare un errore durante la distribuzione di un trigger di evento in Adobe Campaign. Questo errore si verificava quando i metadati &quot;Probabilità di tornare tra 30 giorni&quot; erano stati aggiunti al trigger di abbandono in Adobe Marketing Cloud.
* È stato risolto un problema che poteva causare la cancellazione del campo Dimension Target da parte del flusso di lavoro tecnico durante l’importazione di tipi di pubblico dal servizio core People. Con le query successive non è stato possibile recuperare i tipi di pubblico importati.
* È stato risolto un problema che poteva causare **[!UICONTROL Save audience]** attività di un flusso di lavoro che non riesce quando l’opzione **[!UICONTROL Share in Adobe Marketing Cloud]** è stato controllato.
