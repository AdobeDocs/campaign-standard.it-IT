---
title: Note sulla versione 2018
seo-title: Note sulla versione 2018
description: Note sulla versione 2018
seo-description: In questa pagina sono elencate tutte le versioni 2018 di Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 99 f 92 a 54-4 b 3 d -48 b 9-b 08 d-e 98 b 24 e 75 f 62
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: riferimento
topic-tags: campaign-standard-release
discoiquuid: e 54 f 8305-7 e 32-4193-8 e 5 a-b 5 d 87 b 03038 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Release Notes 2018{#release-notes}

Stai cercando una versione specifica di Adobe Campaign Standard 2018?

Ogni rilascio viene fornito con nuove funzionalità e patch. Fate clic su una versione per visualizzarne il contenuto.

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 18.9 - September 2018 {#release-18-9---september-2018}

### What's new? {#what-s-new-}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> In-App messaging (beta)<br /> </td> 
   <td> La messaggistica in-app consente di coinvolgere più efficacemente gli utenti delle app mobili fornendo un'interazione contestuale e consentendoti di raggiungere gli utenti che hanno rinunciato alle notifiche push. Utilizzate i messaggi in-app insieme alle notifiche push per creare un'esperienza altamente personalizzata e pertinente. Ciò porta alla conversione e al mantenimento degli utenti dell'app.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-in-app-messaging.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Launch integration for mobile apps (beta)<br /> </td> 
   <td> L'integrazione di Adobe Launch con Adobe Campaign ora semplifica e automatizza il processo di attivazione delle proprietà app mobile in Campaign utilizzando l'SDK V 5 di Mobile.<br /> Per ulteriori informazioni, consulta la documentazione <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements}

* Adobe Campaign Standard ora supporta la versione 4 dell'API Amazon S 3.

### Other changes {#other-changes}

* Negli aggiornamenti, esiste ora una distinzione tra il numero massimo di connessioni e il numero massimo di messaggi all'ora. Quando vengono raggiunti i limiti, è possibile sapere perché la velocità è limitata. In precedenza, lo stesso messaggio ('quota soddisfatto ') veniva applicato a entrambi i casi.
* Quando si configura un'applicazione mobile in Campaign, l'utente ora può sapere se il certificato iOS e il server server Android sono stati caricati correttamente e la data di scadenza è stata impostata.

   For more on this, refer to the detailed documentation on how to configure a mobile application using [SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) and [SDK V5](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

* Esegue il targeting degli utenti su un'app mobile specifica selezionando un'app mobile durante la definizione delle proprietà della campagna. Questa funzione è destinata ai canali di messaggistica push e in-app.

   For more information, refer to the [detailed documentation](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Quando si seleziona un blocco di contenuto utilizzando l'interfaccia di Creative Designer, tutti i blocchi di contenuto dell'elenco vengono ora caricati e visualizzati. (CAMP -27311)

   For more on this, refer to the [detailed documentation](../../designing/using/adding-a-content-block.md).

### Patches {#patches}

* È stato risolto un problema che causava discrepanze nel conteggio di registro tra il dashboard e-mail e il rapporto di riepilogo delle e-mail per le e-mail transazionali. (CAMP -28237
* È stato risolto un problema in flussi di lavoro che poteva visualizzare un messaggio di errore durante l'importazione di un file tramite un'attività di trasferimento file. (CAMP -27435)
* È stato corretto un problema di deselezione casuale dei servizi con pagine di destinazione contenenti più di 25 servizi nel modulo. (CAMP -26572)
* È stato risolto un problema in flussi di lavoro che impediva la configurazione di account esterni con un URL SFTP quando si utilizzava l'attività di trasferimento file. (CAMP -26475)
* È stato risolto un problema che impediva l'aggiornamento del rapporto di riepilogo dei servizi. (CAMP -26301)
* Risolto un problema nei flussi di lavoro quando si utilizzava un'attività di arricchimento, che impediva a un campo personalizzato di visualizzare la data corretta. (CAMP -26242)
* È stato risolto un problema che impediva l'aggiornamento delle date di iscrizione del servizio durante l'importazione tramite importazione file.
* Risolto un errore con l'attività del file di caricamento che impediva ai flussi di lavoro di importare file (CAMP -27068).
* È stato risolto un problema che causava il numero errato di iscrizioni nei rapporti di riepilogo Servizi (CAMP -25587).
* È stato risolto un problema di discrepanza dei dati tra i rapporti Adobe Analytics e Adobe Campaign. (CAMP -25393)
* È stato risolto un problema che poteva impedire a un utente limitato di accedere. (CAMP -27381)
* È stato risolto un problema che poteva impedire la visualizzazione dell'elenco di contenuti Adobe Experience Manager durante la modifica di un'e-mail utilizzando Creative Designer. (CAMP -27181)
* È stato risolto un problema che poteva impedire l'apertura di Creative Designer causando un errore. (CAMP -27304)
* È stato risolto un problema che impediva il corretto trascinamento del trascinamento in Creative Designer quando si utilizzava Internet Explorer 11.
* È stato risolto un problema che causava la visualizzazione di immagini caricate da una videocamera e ripresa in modalità verticale in una posizione ruotata non desiderata.
* È stato risolto un problema che causava informazioni di selezione non chiare quando si utilizzava l'interfaccia dell'editor query in Creative Designer.
* È stato risolto un problema che impediva di duplicare correttamente un elemento quando si utilizzava l'interfaccia di query in Creative Designer.
* È stato risolto un problema che causava la trasmissione di messaggi SMS ai destinatari in lista nera anche se erano stati annullati tramite una risposta automatica. (CAMP -27128)
* Fixed an issue that prevented displaying the errors that caused the **Database Cleanup** workflow to fail. (CAMP -26876)
* È stato risolto un problema che poteva impedire l'eliminazione di campi personalizzati in una definizione di notifica push. (CAMP -25588)

## Release 18.7 - July 2018 {#release-18-7---july-2018}

### What's new? {#what-s-new--1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> High priority flag for Android push notifications<br /> </td> 
   <td> Flag di priorità elevato per Android - Abilita la distribuzione di una notifica push con priorità elevata per le app Android, che induce il dispositivo sleep a svegliarsi ed eseguire un'elaborazione limitata. La priorità predefinita è Normale, che può ritardare la consegna dei messaggi per salvare la batteria. <br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Typology filter for mobile app subscribers<br /> </td> 
   <td> Iscrizioni di supporto nel filtro tipografico - Quando si specificano i criteri di filtraggio per una regola di tipo tipologia, le iscrizioni dell'applicazione possono essere selezionate come dimensioni di filtraggio e targeting, fornendo la possibilità di filtrare gli attributi per gli utenti con o senza un profilo. <br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/about-typology-rules.md#typology-rules">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Automated content import from a URL during message preparation<br /> </td> 
   <td> È ora possibile importare contenuto e-mail da un URL durante la fase di preparazione. Per le consegne e-mail ricorrenti, il contenuto HTML più recente viene recuperato ogni volta che il messaggio viene preparato assicura che il contenuto sia sempre aggiornato al momento dell'invio del messaggio e-mail. Questa funzione consente anche di creare una distribuzione pianificata con contenuto da un URL anche se il contenuto non è ancora pronto.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign release notification message<br /> </td> 
   <td> Ora viene visualizzato un messaggio pop-up quando un utente accede dopo l'aggiornamento dell'istanza a una nuova versione. Il messaggio indica il numero di versione e include un collegamento alle note sulla versione. You can choose to hide the message until the next release. <br /> </td> 
  </tr> 
  <tr> 
   <td> User management<br /> </td> 
   <td> La funzionalità relativa all'unità geografica ora non è disponibile per le nuove istanze Campaign Standard, nonché per le istanze esistenti senza unità geografiche create a partire dalla release 18.7.<br /> Per ulteriori informazioni, consultate questa <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">pagina</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements-1}

* The Adobe Campaign and Adobe Target integration now allows you to leverage Target’s [Permissions](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html) feature. Quando si inserisce un'immagine dinamica da Adobe Target in un'e-mail, ora è possibile specificare una proprietà Target (in corrispondenza del codice_ proprietà).
* Le risorse personalizzate che dispongono di un collegamento di copia alla risorsa dei profili ora sono considerate in base alle richieste di accesso/eliminazione della privacy GDPR. Per i collegamenti semplici alla quinta entità e i collegamenti alla raccolta N, è necessario selezionare "Deleting/Duplicating the Target record" (Eliminazione/Duplicazione dei record a cui fa riferimento il collegamento) nella risorsa personalizzata. Per i collegamenti semplici di 0 o 1 cardinalità, selezionate "Eliminazione/Duplicazione del record implica l'eliminazione o la duplicazione del record di destinazione a cui fa riferimento il collegamento".

### Other changes {#other-changes-1}

* La condivisione del report è stata incrementata da uno a quattro minuti per evitare errori di timeout.
* Quando si modifica il contenuto di un'e-mail, per impostazione predefinita viene aperto il nuovo Creative Designer. Se lo desiderate, potete comunque tornare all'editor di contenuto predefinito in qualsiasi momento dopo aver salvato le modifiche. For more on this, refer to the [detailed documentation](../../designing/using/about-email-content-design.md).
* In Creative Designer, è ora possibile aggiungere un nuovo componente contenuto a un messaggio e-mail: il carosello. For more on this, refer to the [detailed documentation](../../designing/using/defining-the-email-structure.md#about-content-components).
* In a transactional message hot click report, when you click the **Change profile** button, now only the test profiles linked to the event that you defined for your transactional message are listed.

### Patches {#patches-1}

* È stato risolto un problema relativo al filtro query byemail che non restituiva risultati. (CAMP -23420)
* È stato risolto un problema che consentiva a un utente standard di accedere a determinate funzionalità o schermate limitate agli amministratori (/rest/head/* endpoint, screens di messaggistica transazionali, profili e pubblico importazione).
* È stato risolto un problema che impediva all'eliminazione della privacy GDPR di elaborare risorse personalizzate se il nome iniziava da un numero.
* Risolto un errore che impediva all'attività Salva pubblico di condividere gli abbonati all'applicazione in Adobe Experience Cloud.
* È stato risolto un problema relativo all'attività di trasferimento file che poteva verificarsi quando il nome del file conteneva spazi vuoti. (CAMP -25936)
* È stato risolto un problema che poteva verificarsi quando si utilizzava il pulsante di riconnessione dopo la scadenza di una sessione. (CAMP -25560)
* È stato risolto un problema che poteva causare esclusioni durante l'invio di consegne con ottimizzazione del fuso orario associata alle regole fatiali. (CAMP -25425)
* È stato risolto un problema che si verificava quando si utilizzava la funzionalità GDPR API, che impediva l'eliminazione di dati con un collegamento di tipo 0-1.
* È stato risolto un problema che poteva causare un messaggio di errore durante l'annullamento dell'edizione di una regola di tipo «affaticamento».
* È stato risolto un problema che poteva verificarsi durante l'anteprima di un contenuto di consegna dopo la modifica.
* È stato risolto un problema che poteva verificarsi durante l'elaborazione dei file ZIP CSV durante l'utilizzo dell'opzione Decompression.
* È stato risolto un problema in Creative Designer che generava font e formattazione indesiderati durante la modifica del testo con stili ingenerati a un collegamento o alla modifica di tale collegamento. (CAMP -26001)
* È stato risolto un problema che impediva al report clic di attivazione di visualizzare le percentuali per ogni condizione nelle consegne contenenti contenuto dinamico. Precedentemente erano visualizzati solo i clic sulla variante predefinita.

## Release 18.6 - June 2018 {#release-18-6---june-2018}

### Improvements {#improvements-2}

* The **[!UICONTROL History]** API has been added to Adobe.IO. Consente di accedere alle informazioni relative alla cronologia di marketing di un profilo: numero di punti di contatto, invii inviati, URL pagina speculare ecc. For more on this, refer to the [dedicated use case](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#how-to-retrieve-the-mirror-page-for-a-delivery-sent-to-a-profile) .
* The **[!UICONTROL Database cleanup]** technical workflow has been optimized in order to ensure better performance for database backup.
* Creative Designer per e-mail è ora disponibile anche in francese e tedesco.

### Other changes {#other-changes-2}

* **[!UICONTROL Compute stats]** Un pulsante è stato aggiunto nella **[!UICONTROL Deployment]** finestra delle consegne inviate. Consente di recuperare i KPI più recenti, ad esempio se i risultati dell'invio richiedono troppo tempo per l'aggiornamento o non sono stati considerati. For more on this, refer to this [section](../../sending/using/confirming-the-send.md).
* In the **Update for deliverability** out-of-the-box technical workflow, functional administrators can now define the number of consecutive errors to ignore in the **Update rules** javascript activity. Per impostazione predefinita, il valore del campo è impostato su 0, ovvero tutti gli errori verranno ignorati.
* Il codice SQL generato durante la gestione delle condizioni di restrizione dell'accesso unitario è stato ottimizzato.
* The **[!UICONTROL Update]** activity now allows you to add, update or delete data related to subscriptions (nms:appSubscriptionRcp table).
* The **[!UICONTROL Update delivery execution]** technical workflow has been divided into two workflows in order to optimize performance: - **[!UICONTROL Update delivery execution]**: updates the delivery's tracking. Viene avviato ogni 10 minuti per impostazione predefinita. **[!UICONTROL Update delivery indicators]**: aggiorna i KPI della consegna, che vengono avviati ogni ora per impostazione predefinita. For more on technical workflows, refer to this [section](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* When a delivery is sending messages, the status in the **[!UICONTROL Deployment]** section can now have two values: **[!UICONTROL Sending]**: the messages are being sent. **[!UICONTROL Sending (retry)]**: È in corso un pass di prova.
* Users with the **[!UICONTROL Delivery preparation]** role are now able to send proofs. (CAMP -24313)
* The **Enable TLS over SMPP** option has been added to the **SMS routing via SMPP** external account. For more on this refer to this [section](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

### Patches {#patches-2}

* È stato risolto un problema che poteva impedire l'invio di e-mail quando si includeva un'immagine dinamica da Adobe Target (CAMP -24848).
* Fixed an issue with the **[!UICONTROL Privacy Access/Delete Request]** technical workflows, which did not complete if any of the requests failed.
* È stato risolto un problema che impediva al servizio Core Privacy di ricevere gli aggiornamenti di stato della richiesta da Campaign.
* È stato risolto un problema che impediva il corretto funzionamento del flusso di lavoro tecnico **[!UICONTROL Import shared audience]** (CAMP-25465).
* È stato risolto un problema che impediva la marcatura delle richieste sulla privacy di Campaign come completato nel servizio Privacy core.
* È stato risolto un problema che impediva ad alcuni utenti di accedere a Campaign Standard tramite l'autenticazione IMS quando l'Adobe ID era troppo lungo. (CAMP -24095)
* È stato risolto un problema in Creative Designer che poteva verificarsi durante la rimozione dei moduli di contenuto. (CAMP -25242)
* È stato risolto un problema che si verificava durante l'utilizzo delle regole di offensioni delle notifiche push per gli abbonati senza profilo nel database. (CAMP -25344)
* È stato risolto un problema che poteva visualizzare un messaggio di errore durante l'accesso ai registri di esclusione delle consegne. (CAMP -24724)
* È stato risolto un problema che impediva la preparazione delle prove nelle istanze con registri di invio estesi.
* Fixed two issues that could occur when publishing custom resources with the **[!UICONTROL Sending log]** extension activated.
* È stato risolto un problema che poteva verificarsi con la durata della consegna non presa in considerazione nelle consegne ricorrenti.
* Fixed an issue that could occur when sorting data in the **[!UICONTROL Client data]** menu, for custom resources with more than 100K records. (CAMP -24308)
* È stato risolto un problema relativo alle dimensioni del profilo personalizzate che non venivano considerate quando si utilizzava la funzione di ricerca nei report dinamici.
* È stato risolto un problema relativo alla visualizzazione di dati internazionali per i livelli Account nei report dinamici.
* Ora è possibile creare un servizio senza un messaggio di conferma iscrizione o annullamento dell'iscrizione.

## Release 18.5 - May 2018 {#release-18-5---may-2018}

### What's new? {#what-s-new--2}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> GDPR: Core Service Integration<br /> </td> 
   <td> L'integrazione con i servizi core della privacy consente di automatizzare le richieste GDPR in un contesto multi-soluzione tramite una singola chiamata API JSON. <br /> Le richieste GDPR inviate dal servizio core privacy a tutte le soluzioni Experience Cloud ora vengono gestite automaticamente da Campaign. <br /> Per ulteriori informazioni, consulta la documentazione <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push improvements - detailed delivery feedback<br /> </td> 
   <td> Adobe Campaign ora offre la possibilità di ricevere commenti dettagliati (invio di registri di esclusione et) sui messaggi push dai fornitori (APNS/GCM) tramite MCPNS.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery logs extension<br /> </td> 
   <td> L'estensione dei registri di distribuzione consente di estendere i registri di invio con dati di profilo e codice del segmento proveniente dai flussi di lavoro. Queste informazioni possono essere utilizzate in Rapporti dinamici e ti permettono di tenere un'istantanea di alcune informazioni al momento di invio.<br /> Esistono 2 casi d'uso:<br /> 
    <ul> 
     <li> Esportare estensioni estese con dati «bloccati»: Come esperto di marketing, desidero esportare tutti i profili in cui il codice del segmento è uguale a "A" (disponibile dal motore del flusso di lavoro). </li> 
     <li> Segmentation on "frozen" data: As a marketer, I would like to <strong>retarget</strong> all profiles who have won 1000 loyalty points since the last sending or where segment code was equal to "A". </li> 
    </ul> For more information, refer to the <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic reporting with Custom profile data<br /> </td> 
   <td> Questa funzione consente di creare e gestire i rapporti in base ai dati di profilo personalizzati creati durante l'estensione delle risorse del profilo. Potete suddividere i rapporti in base a attributi di profilo come ad esempio programma fedeltà, canale preferito, ecc.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements-3}

* La memoria complessiva e l'utilizzo della CPU dell'applicazione sono stati migliorati

### Other changes {#other-changes-3}

* L'attività del flusso di lavoro Leggi audience ora può leggere le audience di Experience Cloud. In precedenza, questa attività poteva leggere solo le audience di Query ed Elenco. Refer to the [detailed documentation](../../automating/using/read-audience.md). (CAMP -23623)
* L'identificatore dell'origine dati condiviso predefinita è ora in modalità di sola lettura e non può più essere modificato. La modifica di questo identificatore potrebbe causare problemi durante la condivisione di audience con Experience Cloud.
* L'importazione di audience da Audience Manager ora funziona con file suddivisi. In precedenza, solo l'ultimo file del segmento veniva importato dal flusso di lavoro tecnico importsharedaudience.
* Gli account esterni di AWS S 3 ora supportano le aree e il meccanismo di autenticazione della versione 4. Refer to the [detailed documentation](../../administration/using/external-accounts.md).
* La finestra di selezione Risorse ora dovrebbe essere caricata più rapidamente e consentire di selezionare una risorsa e uscire dalla finestra senza problemi.
* Le proprietà e la struttura dei flussi di lavoro tecnici possono ora essere modificate dagli utenti con diritti di amministrazione e appartenenti alle unità organizzative e geografiche «All».
* Sono stati apportati miglioramenti nell'interfaccia dell'attività Segmentazione durante la creazione di nuovi segmenti: La scheda Limitazione ora viene visualizzata direttamente dopo l'aggiunta di un limite. I nomi dei nuovi segmenti ora vengono incrementati («Segmento 1», «Segmento 2», ecc.).
* Un campo "nextprocessingdate" viene aggiunto alla risorsa Workflow. Questo campo è visibile solo tramite chiamate REST API, consente di visualizzare i flussi di lavoro successivi nelle date di elaborazione.
* Il campo "sourceid" è ora esposto nella risorsa dei registri di tracciamento (nms: Trackinglog.
* È ora possibile esportare il totale e i valori Totali clic possono essere esportati in un file semplice tramite un flusso di lavoro. (CAMP -24186)
* " Inglese - Danmark "è ora disponibile nell'elenco delle lingue preferite nei profili. (CAMP -23728)
* Quando si utilizza un'attività di segmentazione con un collegamento di dati aggiuntivo (targetdata), un messaggio informa ora che i dati non sono disponibili all'esterno del flusso di lavoro. Questo messaggio viene visualizzato facendo clic sul pulsante Conteggio o Anteprima dall'attività di segmentazione. (CAMP -23651)
* Sono stati apportati miglioramenti per ottimizzare lo spazio su disco utilizzato dai flussi di lavoro: (CAMP -21979): I file elaborati dall'attività «Carica file» ora vengono eliminati per impostazione predefinita. Un'opzione consente di mantenere le esigenze specifiche. Quando un flusso di lavoro viene eliminato, la sua cartella dedicata viene eliminata automaticamente dalla directory del server.

### Patches {#patches-3}

* È stato risolto un problema a causa del quale alcuni eventi di reporting non erano associati a eventi di tracciamento, poiché il campo eventdate non veniva popolato correttamente.
* È stato risolto un problema che impediva la visualizzazione dei campi personalizzati nella finestra di anteprima di una consegna push.
* È stato risolto un problema che impediva il ritorno a capo del testo nel corpo del messaggio di una notifica push nella finestra di anteprima.
* È stato risolto un problema che si verificava durante l'invio di una distribuzione da un flusso di lavoro quando la destinazione principale era vuota.
* È stato risolto un problema che impediva l'accesso a una mappatura di destinazione se collegata a uno schema non esistente.
* È stato risolto un problema che poteva verificarsi durante l'importazione di un file ZIP tramite un'attività di caricamento file. (CAMP -24309)
* È stato risolto un problema che causava un errore postgresql durante l'invio di una consegna ricorrente. (CAMP -23613)
* È stato risolto un problema che causava un messaggio di errore durante l'invio di una richiesta REST API con un attributo JSON vuoto. (CAMP -23506)
* È stato risolto un problema in profili che impostava per maiuscola i caratteri dopo il carattere "ß". (CAMP -23136)
* È stato risolto un problema che si verificava durante l'invio di consegne utilizzate con la condizione di idoneità o la condizione di idoneità di un blocco dinamico quando si utilizzavano attributi da uno schema collegato di profilo. (CAMP -22751)
* È stato risolto un problema che impediva di eliminare i servizi. (CAMP -22050)
* È stato risolto un problema che impediva la modifica dei valori Paese o Stato in un profilo di test. (CAMP -20426)
* È stato risolto un problema che poteva impedire il caricamento di Creative Designer. (CAMP -24573)
* È stato risolto un problema che impediva l'aggiunta di caratteri aggiunti dopo campi di personalizzazione nell'oggetto dell'e-mail. (CAMP -24113)

## Release 18.4 - April 2018 {#release-18-4---april-2018}

### Patches {#patches-4}

#### Platform {#platform}

* È stato corretto un errore che impediva di elaborare correttamente le richieste di accesso o eliminazione del GDPR. Questo comportamento è stato osservato in alcuni rari casi in cui i dati estratti contenevano uno dei seguenti caratteri: &amp; &lt; &gt; "'.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail}

* È stato risolto un problema che potrebbe causare la sovrascrittura dei KPI con valori errati se la sincronizzazione broadlog richiedeva più di un'ora.

#### Workflows {#workflows}

* Miglioramento della gestione della memoria e delle prestazioni ottimizzate nei flussi di lavoro.

#### Reporting {#reporting}

* Il flusso di lavoro di condivisione KPI ora recupera i valori di consegna per gli ultimi 2 mesi invece degli ultimi 6 mesi. È stato risolto un problema con la condivisione di un account esterno KPI che mostrava date troncate.
* Fixed an issue which could lead to certain messages not being taken into account in **Sent**, **Delivered** and **Bounce** metrics.
* Fixed an error which occurred when the chosen time range in the **Delivery Summary Report** was too long.

#### Custom resources {#custom-resources}

* Risolto un errore che causava la mancata preparazione delle risorse personalizzate.

## Release 18.3 - March 2018 {#release-18-3---march-2018}

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
   <td> EU General Data Protection Regulation (GDPR)<br /> </td> 
   <td> GDPR è la nuova legge sulla privacy dell'Unione Europea (EU), che armonizza e modernizza i requisiti di protezione dei dati entreranno in vigore il 25 maggio 2018. Il GDPR si applica ai clienti di Adobe Campaign che contengono dati per i dati dei dati residenti nell'Unione Europea.<br /> In aggiunta alle funzionalità sulla privacy già disponibili in Adobe Campaign (comprese la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), stiamo sfruttando questa opportunità nel nostro ruolo come Elaboratore dati per includere funzionalità aggiuntive, per semplificare la preparazione come controller dati per determinate richieste GDPR:<br /> 
    <ul> 
     <li> Da destra a accesso: consente ai dati dell'oggetto di ricevere una copia dei dati personali acquisiti dai controller dati, inclusi i dati archiviati in Adobe Campaign. </li> 
     <li> Da destra a Elimina: concede al soggetto dati i dati personali acquisiti dai controller dati cancellati, inclusi i dati archiviati in Adobe Campaign. </li> 
    </ul> For more information, refer to the <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer for Email (Beta)<br /> </td> 
   <td> Il nuovo Creative Designer di Adobe Campaign offre un'esperienza di creazione completamente integrata in Campaign, consentendo la creazione visiva rapida e intuitiva di e-mail personalizzate e personalizzate senza dover eseguire script su una sola riga di codice. Grazie alla potente interfaccia di trascinamento, Creative Designer consente di ridimensionare la creazione e-mail in modo da consentire agli utenti di iniziare da una slate vuota o di sfruttare frammenti o modelli di contenuto esistenti. <br /> Le funzionalità chiave includono:<br /> 
    <ul> 
     <li> Progettazione visiva e creazione di e-mail reattive e completamente personalizzate tramite un'interfaccia a trascinamento, incrementata dalle integrazioni native Creative Cloud </li> 
     <li> Creare e salvare un modello di contenuto e-mail e sfruttare i modelli salvati per facilitare la creazione di e-mail </li> 
     <li> Creare e salvare frammenti di contenuto (ad esempio intestazione, piè di pagina, articolo, ecc.) per semplificare la creazione di contenuti e garantire coerenza del marchio </li> 
     <li> Passaggio da una creazione all'altra tramite trascinamento e modifica diretta HTML di un messaggio e-mail a clic su un pulsante </li> 
    </ul> Creative Designer per e-mail è disponibile solo in inglese.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../designing/using/about-email-content-design.md#about-the-email-designer">dettagliata</a> e guarda questo <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">video</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Multilingual Push Deliveries<br /> </td> 
   <td> La stessa interfaccia multilingue, già presente sui canali E-mail e SMS, è stata aggiunta al canale push per aiutarti a coinvolgere i clienti, indipendentemente dalla lingua preferita.<br /> Questa funzionalità offre una soluzione scalabile e automatica per i clienti che gestiscono campagne push su più aree e desiderano indirizzare gli utenti nella lingua preferita. Consente di caricare tutte le varianti lingingue tramite un foglio di calcolo impostato su un'unica distribuzione push, con un solo clic. Adobe Campaign esegue quindi una segmentazione automatica basata sulle preferenze dell'utente, per ridurre i licenziamenti semplificando i flussi di lavoro e i rapporti.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/creating-a-multilingual-push-notification.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Use of Custom Resources in Transactional Messaging<br /> </td> 
   <td> Oltre ai campi forniti, la messaggistica transazionale ora consente di utilizzare risorse personalizzate per arricchire il contenuto dei messaggi.<br /> Ad esempio:<br /> 
    <ul> 
     <li> Sfruttare i campi personalizzati come criteri di riconciliazione per far corrispondere un messaggio di transazione a un profilo </li> 
     <li> Sfruttare profili, servizi e dati collegati completi per personalizzare ulteriormente i messaggi transazionali </li> 
    </ul> For more information, refer to the <a href="../../administration/using/configuring-transactional-messaging.md">detailed documentation</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### Platform {#platform-1}

* È stato risolto un problema che impediva l'esportazione di più di 5000 record da un elenco.
* È stato risolto un problema durante l'esportazione dei dati in file denominati con campi di personalizzazione.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-1}

* È stato risolto un problema che causava troncamento SMS con più parti, poiché le dimensioni delle parti venivano calcolate in caratteri invece che in byte.
* Added an option which allows the **[!UICONTROL Delivered]** or **[!UICONTROL Bounces + Errors]** KPIs to be updated in real time after sending your delivery. Vengono ricalcolati direttamente dal SR (Report Status) ricevuto dal fornitore.
* È stato risolto un problema relativo al widget calendario nel pianificatore di consegna.
* Risolto un problema di visualizzazione quando si apriva una destinazione per una seconda volta in una consegna inviata.
* È stato risolto un problema che causava un messaggio di errore durante la richiesta di una data di inizio, durante la creazione di un modello e-mail con una data di invio ritardata.
* È stato risolto un problema che poteva causare problemi di rendering delle immagini durante la modifica del contenuto di una distribuzione.
* È stato risolto un problema con le prove di stampa durante la duplicazione di una campagna.
* È stato risolto un problema che causava un messaggio di errore durante l'accesso a un modello di campagna tramite la barra di navigazione, dopo l'aggiunta di una consegna al flusso di lavoro.
* È stato risolto un problema che poteva impedire la selezione automatica di un messaggio e-mail di test A/B, che impediva l'invio dell'e-mail. This behavior could occur if the delivery was in **[!UICONTROL retryInProgress]** state.
* Risolto un problema che potrebbe portare a un messaggio di errore durante la riapertura dei parametri di un'e-mail di test A/B.

#### Audiences &amp; queries {#audiences-e-queries}

* È stato risolto un problema che impediva l'accesso ai dati e l'impostazione di query per i destinatari replicati da Adobe Campaign Classic a Standard.
* Fixed an issue that occurred when using a filter type field in the query editor, after using the **Count** or **Preview** buttons.

#### Workflows {#workflows-1}

* The **Billing** workflow has been optimized to improve the delivery preparation delay.
* È stato risolto un problema che impediva la visualizzazione dei dati sulla popolazione in una transizione in uscita quando si utilizzava un'attività di consegna ricorrente.
* Fixed an issue that prevented reject records from being displayed in a transition after an **Update data** activity.
* Fixed an issue which could cause the **deliverabilityUpdate** technical workflow to fail.

#### Integrations {#integrations}

* È stato risolto un problema che impediva l'invio corretto dei caratteri internazionali ad Adobe Analytics.
* Le risorse dovrebbero ora venire caricate più rapidamente quando si tenta di inserire un'immagine dalla libreria delle risorse Experience Cloud in un messaggio.
* È stato risolto un problema che poteva impedire la chiusura della finestra di selezione delle risorse in alcuni casi.
* Da un dettaglio dati, ora puoi accedere direttamente al relativo flusso di lavoro per controllare lo stato del flusso di lavoro.
* Ora è possibile aggiornare lo schema Triggers direttamente durante la definizione o la modifica di un evento di attivazione. Con questa modifica, non è più necessario annullare la pubblicazione del trigger e crearne un altro.

#### Transactional messages {#transactional-messages}

* Risolto un errore con il modello di messaggio transazionali quando la risorsa di consegna veniva estesa.
* È ora possibile eliminare i messaggi transazionali.

## Release 18.2 - February 2018 {#release-18-2---february-2018}

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
   <td> Subscription - subscribe or unsubscribe a list of profiles to multiple services<br /> </td> 
   <td> The <strong>Subscription Services</strong> workflow activity now allows you to subscribe or unsubscribe a list of profiles to multiple services. Nel flusso di lavoro, importa un file contenente i profili e, per ciascun profilo, il tipo di operazione e il servizio. The <strong>Subscription Services</strong> activity will be able to use this information and handle dynamically all your profiles subscriptions and unsubscriptions at once.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/subscription-services.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Enrichment activity - enrich data based on previous transitions<br /> </td> 
   <td> The new <span class="uicontrol">Enrichment</span> workflow activity allows you to leverage the inbound transitions and complete the output transition with additional data. Se esegui il targeting dei profili, l'attività di arricchimento ti permette di arricchire le informazioni sui profili con ulteriori dati non memorizzati nel database (ad esempio, provenienti da un file importato).<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/enrichment.md">dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### Platform {#platform-2}

* La barra superiore dell'interfaccia di Adobe Campaign è stata aggiornata con il nuovo menu Experience Cloud.
* Fixed an issue which prevented the link to **[!UICONTROL Offers]** from being displayed in the solution dropdown list.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-2}

* La fase di preparazione della distribuzione è stata migliorata per migliorare le prestazioni.
* Sono stati corretti diversi problemi che potrebbero causare la corruzione dei registri di tracciamento in alcune situazioni di nicchia.
* Risolto un problema di aggiornamento della data di contatto che si verificava quando la data di contatto veniva modificata tra preparazione della distribuzione e conferma. Ora, quando modificate la data di contatto dopo la preparazione, dovete preparare nuovamente la consegna prima di poter confermare l'invio. See the [detailed documentation](../../sending/using/preparing-the-send.md).

#### Push notifications {#push-notifications}

* Risolto un errore che impediva ad alcuni campi di personalizzazione di funzionare nelle notifiche push iOS.
* Risolto un errore che visualizzava il clic e le percentuali di apertura come 0% nel dashboard delle notifiche push.

#### Reports {#reports}

* Risolto un errore che mostrava l'elenco dei report come vuoto in alcuni browser.
* Fixed an error that occurred in the **[!UICONTROL Report sharing]** technical workflow just before its expiration limit was reached.

#### Workflows {#workflows-2}

* È stato risolto un problema che impediva l'accesso alle attività dopo il trascinamento.
* Fixed an issue that could cause the order of output transitions of a **[!UICONTROL Segmentation]** activity to change in some situations.
* Risolto un errore che si verificava durante la lettura di un'audience contenente un campo di tipo enumerazione e precedentemente salvata da un flusso di lavoro
* Fixed an issue causing the **[!UICONTROL Request confirmation before sending messages]** option to remain checked even after unchecking it when defining the scheduling properties of a delivery created in a workflow.
* Automatic removal of duplicate rows (DISTINCT clause) can now be disabled in **[!UICONTROL Query]** activities, via a new option located in the **[!UICONTROL Additional data]** tab. La disattivazione dell'opzione è consigliata per la definizione di molti (oltre 100) elementi aggiuntivi, per motivi di prestazioni.

#### Integrations {#integrations-1}

* Some improvements were made to the **[!UICONTROL Data sources]** configuration screen.

### Known issues {#known-issues}

È consigliabile non utilizzare Internet Explorer versione 11 a causa di possibili problemi di visualizzazione.

Alcuni problemi potrebbero verificarsi quando si utilizzano collegamenti di aiuto contestuali dall'interfaccia Campaign. Verranno corretti in 18.3.

## Release 18.1 - January 2018 {#release-18-1---january-2018}

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
   <td> Reporting for Fatigue Management<br /> </td> 
   <td> Reporting for Fatigue Management è un rapporto dedicato e configurabile che mostra l'impatto delle regole di affaticamento sulle consegne nei canali e-mail, push, SMS e posta diretta in un intervallo di date specificato prima dell'invio. Grazie alla possibilità aggiunta di poter vedere rapidamente tutte le campagne in conflitto in una vista singola, gli addetti al marketing possono pianificare campagne di marketing in base alle regole di affaticamento in modo più efficace, dando priorità alle comunicazioni.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Report sharing<br /> </td> 
   <td> La condivisione di rapporti consente di condividere i rapporti con gli utenti Adobe Campaign come allegati e-mail, inclusi i metodi periodici automatizzati. Gli utenti che ricevono rapporti periodici possono annullare l'iscrizione a tali comunicazioni tramite un collegamento dedicato in ogni e-mail.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../reporting/using/reporting-interface.md#share-tab">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push New capabilities<br /> </td> 
   <td> Anteprima messaggio push - Anteprima delle notifiche push sui dispositivi iOS e Android dall'editor contenuto notifiche push per visualizzare esattamente ciò che i destinatari vedranno prima di testare o eseguire la consegna.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">dettagliata</a>.<br /> Contenuto disponibile - Quando le app non vengono aperte in periodi di tempo prolungati, i loro dati possono diventare obsoleti. In questo modo i dati devono essere aggiornati o sostituiti nel momento in cui un utente apre l'app, causando ritardi nell'utilizzo dell'app. Con il supporto aggiunto di Content Available (Contenuto disponibile), gli utenti Adobe Campaign possono richiamare l'app per aggiornare i dati in background durante la distribuzione di una notifica push, consentendo coerenza e controllo maggiori sull'esperienza in-app dell'utente.<br /> Contenuto variabile - Con il supporto aggiunto di Contenuto variabile, gli utenti di Adobe Campaign possono ora sfruttare le estensioni delle app mobili per modificare ulteriormente il contenuto o la presentazione delle notifiche push in arrivo inviate da Adobe Campaign. For example, users can leverage Mutable Content to: <br /> 
    <ul> 
     <li> decrittografare i dati inviati in formato crittografato </li> 
     <li> scaricare immagini o altri file multimediali e aggiungerli come allegati a una notifica </li> 
     <li> modificare il corpo o il testo del titolo di una notifica </li> 
     <li> aggiungere un identificatore di thread a una notifica </li> 
    </ul> For more information on Content Available and Mutable Content, refer to the <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">detailed documentation</a>.<br /><strong>Avviso:</strong> questi aggiornamenti sulle notifiche push richiedono ai clienti di aggiornare le applicazioni mobili. Refer to <a href="https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">this technote</a> for more information.<br /> </td> 
  </tr> 
  <tr> 
   <td> Time-zone optimized deliveries<br /> </td> 
   <td> Pianificare notifiche e-mail, SMS e push ricorrenti da inviare in un giorno/ora specifico nel fuso orario di ogni destinatario, garantendo che i messaggi vengano consegnati al momento giusto senza configurare più consegne. <br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/scheduler.md">dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API Signal activity triggering<br /> </td> 
   <td> È ora possibile attivare un'attività di segnale per i flussi di lavoro direttamente dall'API standard di Adobe Campaign.<br /> Per ulteriori informazioni, consulta la documentazione <a class="anchorLink" href="https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity" target="_blank">dettagliata</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-7}

#### Platform {#platform-3}

* La ricerca del profilo è stata ottimizzata per migliorare le prestazioni.
* L'identificatore interno dei gruppi di protezione predefiniti è ora in modalità di sola lettura per gli utenti standard.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-3}

* È stato corretto un problema di visualizzazione che si verificava durante l'inserimento di emoji nel contenuto delle consegne.
* È stato risolto un problema che consentiva all'utente di accedere ai registri di invio quando la distribuzione era ancora in versione.
* The **[!UICONTROL Scheduler]** activity now allows you to send your deliveries depending on the recipient's time zone.
* SMS: The option **[!UICONTROL Store incoming MO]** in the database has been added to external accounts. When checked, all incoming SMS will be stored into the **inSMS** table.
* SMS: I servizi sono ora collegati a un evento anziché a un modello transazionale.
* SMS: Il timeout connessione SMTP predefinito è stato ridotto a 30 secondi.

#### Push notifications {#push-notifications-1}

* Risolto un errore che impediva la sospensione delle consegne di notifiche push.
* Aggiunta un'opzione nelle opzioni avanzate di notifica push per richiamare l'applicazione con una notifica push.
* È stato aggiunto un pulsante di pausa per il video di anteprima delle notifiche push.
* L'anteprima delle notifiche push è ora disponibile per dispositivi diversi come iphone, Android, tablet.

   tutti i canali

#### Reports {#reports-1}

* È stato corretto un errore che causava percentuali superiori al 100%.
* È stato risolto un problema che impediva agli utenti di scaricare i rapporti in CSV.
* Added a new **[!UICONTROL Report]** item in the homepage.

#### Workflows {#workflows-3}

* È stato risolto un problema che causava un messaggio di errore quando si utilizzavano dati aggiuntivi in una query e aggiungevano alias contenenti spazi. I caratteri non alfanumerici vengono sostituiti da "_".
* È stato risolto un problema a causa del quale, in alcuni casi, i KPI di calcolo dei flussi di lavoro tecnici potevano essere interrotti per impostazione predefinita.

#### Profiles and audiences {#profiles-and-audiences}

* Risolto un errore che si verificava aggiungendo più filtri nella query di un'audience.
* È stato corretto un problema di visualizzazione che si verificava quando si cambiava l'immagine di un profilo.
* Aggiunta una descrizione comandi che mostra il numero esatto di risultati dopo il conteggio della popolazione di una query.
* È stato risolto un problema che poteva impedire all'utente di selezionare un'audience o di chiudere la finestra del selettore del pubblico.
* L'elenco delle funzioni disponibili nell'editor delle espressioni è stato aggiornato. The **FormatCurrency** and **ConvertCurrency** functions have been removed.

