---
title: Note sulla versione 2018
description: In questa pagina sono elencate tutte le versioni 2018 di Adobe Campaign Standard.
page-status-flag: mai attivato
uuid: 99f92a54-4b3d-48b9-b08d-e98b24e75f62
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: release standard di campagna
discoiquuid: e54f8305-7e32-4193-8e5a-b5d87b03038c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Note sulla versione 2018{#release-notes}

Stai cercando una versione 2018 specifica di Adobe Campaign Standard?

Ogni versione include nuove funzioni e patch. Fate clic su una versione per visualizzarne il contenuto.

Visualizza gli ultimi aggiornamenti [della](../../rn/using/documentation-updates.md) documentazione per Adobe Campaign Standard. Per una versione più recente, consulta questa [pagina](../../rn/using/release-notes.md).

## Rilascio 18.9 - settembre 2018 {#release-18-9---september-2018}

### What's new? {#what-s-new-}

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Messaggistica in-app (versione beta)<br /> </td> 
   <td> La messaggistica in-app consente di coinvolgere più efficacemente gli utenti delle app mobili fornendo interazione contestuale e consentendo di raggiungere gli utenti che potrebbero aver rinunciato alle notifiche push. Utilizzate la messaggistica in-app insieme alle notifiche push per creare un'esperienza altamente personalizzata e rilevante. Questo consente una migliore conversione e mantenimento degli utenti dell'app.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/about-in-app-messaging.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrazione di Adobe Launch per le app mobili (versione beta)<br /> </td> 
   <td> L'integrazione di Adobe Launch con Adobe Campaign ora semplifica e automatizza il processo di attivazione delle proprietà delle app mobili in Campaign utilizzando Mobile SDK V5.<br /> Per ulteriori informazioni, consulta la documentazione <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html"></a>dettagliata.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Miglioramenti {#improvements}

* Adobe Campaign Standard ora supporta la versione 4 dell'API Amazon S3.

### Altre modifiche {#other-changes}

* Nei log di trasmissione, ora esiste una distinzione tra il numero massimo di connessioni e il numero massimo di messaggi per ora. Una volta raggiunti i limiti, è possibile sapere perché il throughput è limitato. In precedenza, lo stesso messaggio ("quota soddisfatta") era applicato a entrambi i casi.
* Quando si configura un'applicazione mobile in Campaign, l'utente ora può sapere se il certificato iOS e la chiave del server Android sono stati caricati correttamente e la relativa data di scadenza.

   Per ulteriori informazioni, consulta la documentazione dettagliata su come configurare un’applicazione mobile utilizzando [SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) e [SDK V5](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

* Eseguite il targeting degli utenti su una specifica app mobile selezionando un'app mobile mentre definite le proprietà della campagna. Questa funzione è per i canali di messaggistica in-app e push.

   Per ulteriori informazioni, consulta la documentazione [](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification)dettagliata.

* Quando si seleziona un blocco di contenuto tramite l'interfaccia di Creative Designer, tutti i blocchi di contenuto dell'elenco vengono ora caricati e visualizzati. (CAMP-27311)

   Per ulteriori informazioni, consulta la documentazione [](../../designing/using/personalization.md#adding-a-content-block)dettagliata.

### Patch {#patches}

* È stato risolto un problema che causava una discrepanza nei conteggi dei log tra il dashboard e-mail e il rapporto di riepilogo e-mail per le e-mail transazionali. (CAMP-28237)
* È stato risolto un problema nei flussi di lavoro che poteva visualizzare un messaggio di errore durante l'importazione di un file tramite un'attività di trasferimento file. (CAMP-27435)
* È stato risolto un problema con pagine di destinazione contenenti più di 25 servizi che causava la deselezione casuale dei servizi nel modulo. (CAMP-26572)
* È stato risolto un problema nei flussi di lavoro che impediva la configurazione di account esterni con un URL SFTP durante l'utilizzo dell'attività di trasferimento file. (CAMP-26475)
* È stato risolto un problema che impediva l'aggiornamento del rapporto di riepilogo dei servizi. (CAMP-26301)
* È stato risolto un problema nei flussi di lavoro che impediva a un campo personalizzato di visualizzare la data corretta durante l'utilizzo di un'attività di arricchimento. (CAMP-26242)
* È stato risolto un problema che impediva l'aggiornamento delle date di sottoscrizione del servizio durante l'importazione tramite un'importazione di file.
* È stato corretto un errore con l'attività del file di caricamento che impediva ai flussi di lavoro di importare i file (CAMP-27068).
* È stato risolto un problema che causava la visualizzazione di un numero errato di sottoscrizioni nei rapporti di riepilogo del servizio (CAMP-25587).
* È stato risolto un problema di discrepanza dei dati tra i report Adobe Analytics e Adobe Campaign. (CAMP-25393)
* È stato risolto un problema che poteva impedire a un utente con accesso limitato di effettuare l'accesso. (CAMP-27381)
* È stato risolto un problema che poteva impedire la visualizzazione dell'elenco dei contenuti di Adobe Experience Manager durante la modifica di un'e-mail tramite Creative Designer. (CAMP-27181)
* È stato risolto un problema che poteva impedire l'apertura di Creative Designer causando un errore. (CAMP-27304)
* È stato risolto un problema che impediva il corretto funzionamento del trascinamento in Creative Designer quando si utilizzava Internet Explorer 11.
* È stato risolto un problema che causava la visualizzazione delle immagini caricate da una fotocamera e scattate in modalità verticale in una posizione ruotata indesiderata.
* È stato risolto un problema che causava la visualizzazione di informazioni di selezione non chiare durante l'utilizzo dell'interfaccia dell'editor query in Creative Designer.
* È stato risolto un problema che impediva la duplicazione corretta di un elemento quando si utilizzava l'interfaccia dell'editor di query in Creative Designer.
* È stato risolto un problema che impediva l'invio di messaggi SMS ai destinatari inseriti in blacklist anche se questi erano stati annullati dalla sottoscrizione tramite una risposta automatica. (CAMP-27128)
* È stato risolto un problema che impediva la visualizzazione degli errori che causavano il fallimento del flusso di lavoro di pulizia del **database** . (CAMP-26876)
* È stato risolto un problema che poteva impedire l'eliminazione di campi personalizzati in una definizione di notifica push. (CAMP-25588)

## Rilascio 18.7 - Luglio 2018 {#release-18-7---july-2018}

### What's new? {#what-s-new--1}

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Flag ad alta priorità per le notifiche push di Android<br /> </td> 
   <td> Flag ad alta priorità per Android - Abilita la distribuzione di una notifica push con priorità alta per le app Android che fa sì che il dispositivo in sospeso si riattivi ed esegua un'elaborazione limitata. La priorità predefinita è Normale, che può ritardare la consegna del messaggio per risparmiare la batteria. <br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Filtro della tipologia per gli abbonati alle app mobili<br /> </td> 
   <td> Iscrizioni di supporto nel filtro della tipologia: quando si specificano i criteri di filtro per una regola di tipologia, le sottoscrizioni di applicazione possono essere selezionate come dimensioni di filtraggio e targeting, fornendo la possibilità di filtrare gli attributi per gli utenti con o senza un profilo. <br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/about-typology-rules.md#typology-rules"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importazione automatizzata dei contenuti da un URL durante la preparazione dei messaggi<br /> </td> 
   <td> È ora possibile importare contenuti e-mail da un URL durante la fase di preparazione. Per le comunicazioni e-mail ricorrenti, il contenuto HTML più recente viene recuperato ogni volta che il messaggio viene preparato, verificando che il contenuto sia sempre aggiornato al momento dell'invio dell'e-mail. Questa funzione consente inoltre di creare una distribuzione pianificata con contenuto da un URL anche se il contenuto non è ancora pronto.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Messaggio di notifica per il rilascio della campagna<br /> </td> 
   <td> Ora viene visualizzato un messaggio a comparsa quando un utente accede dopo che l'istanza è stata aggiornata a una nuova versione. Il messaggio indica il numero di versione e include un collegamento alle note sulla versione. Puoi scegliere di nascondere il messaggio fino alla versione successiva. <br /> </td> 
  </tr> 
  <tr> 
   <td> Gestione utenti<br /> </td> 
   <td> La funzionalità dell'unità geografica ora non è disponibile per le nuove istanze di Campaign Standard, così come per le istanze esistenti senza unità geografiche create, a partire dalla release 18.7.<br /> Per ulteriori informazioni, consultare questa <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">pagina</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Miglioramenti {#improvements-1}

* L'integrazione di Adobe Campaign e Adobe Target ora consente di sfruttare la funzione [Autorizzazioni](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html) di Target. Quando includete un'immagine dinamica da Adobe Target in un messaggio e-mail, ora potete specificare una proprietà Target (codice a_proprietà).
* Le risorse personalizzate che dispongono di un collegamento di copia per la risorsa dei profili vengono ora prese in considerazione dalle richieste di accesso/eliminazione della privacy GDPR. Per 1 collegamenti semplici di cardinalità e N collegamenti di raccolta cardinalità, è necessario selezionare "Eliminazione/Duplicazione del record di destinazione implica l'eliminazione/duplicazione dei record a cui fa riferimento il collegamento" nella risorsa personalizzata. Per i collegamenti semplici 0 o 1 cardinalità, selezionare "Eliminare/Duplicare il record implica eliminare/duplicare il record di destinazione a cui fa riferimento il collegamento".

### Altre modifiche {#other-changes-1}

* Il timeout di condivisione dei report è stato aumentato da uno a quattro minuti per evitare qualsiasi errore di timeout.
* Quando modificate il contenuto di un messaggio e-mail, per impostazione predefinita viene aperto il nuovo Creative Designer. Se lo desiderate, potete comunque tornare all'editor di contenuti predefinito in qualsiasi momento dopo aver salvato le modifiche. Per ulteriori informazioni, consulta la documentazione [](../../designing/using/overview.md)dettagliata.
* In Creative Designer, è ora possibile aggiungere un nuovo componente contenuto a un messaggio e-mail: il carosello. Per ulteriori informazioni, consulta la documentazione [](../../designing/using/designing-from-scratch.md#about-content-components)dettagliata.
* In un rapporto con un clic del messaggio di transazione, quando fate clic sul pulsante **Modifica profilo** , vengono elencati solo i profili di test collegati all'evento definito per il messaggio di transazione.

### Patch {#patches-1}

* È stato risolto un problema con il filtro query byEmail che non restituiva alcun risultato. (CAMP-23420)
* È stato risolto un problema che consentiva a un utente standard di accedere a determinate funzioni o schermate limitate agli amministratori (endpoint/rest/head/*, schermate di messaggistica transazionali, profili e tipi di pubblico importati).
* È stato risolto un problema che impediva alle richieste di eliminazione della privacy GDPR di elaborare risorse personalizzate se il loro nome iniziava da un numero.
* È stato corretto un errore che impediva all'attività Salva pubblico di condividere gli abbonati all'applicazione in Adobe Experience Cloud.
* È stato risolto un problema relativo all'attività di trasferimento file che poteva verificarsi quando il nome file conteneva spazi vuoti. (CAMP-25936)
* È stato risolto un problema che poteva verificarsi quando si utilizzava il pulsante di riconnessione dopo la scadenza di una sessione. (CAMP-25560)
* È stato risolto un problema che poteva causare esclusioni durante l'invio di consegne con ottimizzazione del fuso orario associata alle regole di affaticamento. (CAMP-25425)
* È stato risolto un problema che, durante l'utilizzo della funzione GDPR API, poteva impedire l'eliminazione di dati con un collegamento di tipo 0-1.
* È stato risolto un problema che poteva causare un messaggio di errore durante l'annullamento dell'edizione di una regola di tipo fatigue.
* È stato risolto un problema che poteva verificarsi durante l'anteprima di un contenuto di consegna dopo la modifica.
* È stato risolto un problema che poteva verificarsi durante l'elaborazione dei file zip CSV durante l'utilizzo dell'opzione di decompressione.
* È stato risolto un problema in Creative Designer a causa del quale i font a colori e la formattazione non desiderati venivano modificati durante la modifica di un testo con lo stile incorporato in un collegamento o durante la modifica di tale collegamento. (CAMP-26001)
* È stato risolto un problema che impediva al rapporto clic con il tasto di scelta rapida di visualizzare le percentuali per ogni condizione nelle consegne contenenti contenuto dinamico. In precedenza, venivano visualizzati solo i clic sulla variante predefinita.

## Rilascio 18.6 - Giugno 2018 {#release-18-6---june-2018}

### Miglioramenti {#improvements-2}

* L' **[!UICONTROL History]** API è stata aggiunta ad Adobe.IO. Consente di accedere alle informazioni relative alla cronologia marketing di un profilo: numero di punti di contatto, consegne inviate, URL pagina mirror ecc. Per ulteriori informazioni, consultare il caso [d'uso](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#how-to-retrieve-the-mirror-page-for-a-delivery-sent-to-a-profile) dedicato.
* Il flusso di lavoro **[!UICONTROL Database cleanup]** tecnico è stato ottimizzato per garantire prestazioni migliori per il backup del database.
* Creative Designer per e-mail è ora disponibile anche in francese e tedesco.

### Altre modifiche {#other-changes-2}

* È stato aggiunto un **[!UICONTROL Compute stats]** pulsante nella **[!UICONTROL Deployment]** finestra delle consegne inviate. Consente di recuperare i KPI più recenti, ad esempio se i risultati dell'invio richiedono troppo tempo per essere aggiornati o se non sono stati presi in considerazione. For more on this, refer to this [section](../../sending/using/confirming-the-send.md).
* Nel flusso di lavoro tecnico **Update for recapito** out-of-the-box, gli amministratori funzionali ora possono definire il numero di errori consecutivi da ignorare nell'attività javascript delle regole **di** aggiornamento. Per impostazione predefinita, il valore del campo è impostato su 0, il che significa che tutti gli errori verranno ignorati.
* Il SQL generato durante la gestione delle condizioni di restrizione dell'accesso dell'unità è stato ottimizzato.
* L' **[!UICONTROL Update]** attività ora consente di aggiungere, aggiornare o eliminare dati relativi alle iscrizioni (tabella nms:appSubscriptionRcp).
* Il flusso di lavoro **[!UICONTROL Update delivery execution]** tecnico è stato suddiviso in due flussi di lavoro per ottimizzare le prestazioni: - **[!UICONTROL Update delivery execution]**: aggiorna il tracciamento della consegna. Per impostazione predefinita, viene avviata ogni 10 minuti. **[!UICONTROL Update delivery indicators]**: aggiorna i KPI della consegna, che vengono avviati ogni ora per impostazione predefinita. Per ulteriori informazioni sui flussi di lavoro tecnici, consulta questa [sezione](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* Quando una consegna invia messaggi, lo stato nella **[!UICONTROL Deployment]** sezione può avere due valori: **[!UICONTROL Sending]**: i messaggi vengono inviati. **[!UICONTROL Sending (retry)]**: è in corso un nuovo passaggio.
* Gli utenti con il **[!UICONTROL Delivery preparation]** ruolo ora possono inviare le prove di stampa. (CAMP-24313)
* L'opzione **Abilita TLS su SMPP** è stata aggiunta al routing **SMS tramite l'account esterno SMPP** . For more on this refer to this [section](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

### Patch {#patches-2}

* È stato risolto un problema che poteva impedire l'invio di e-mail quando includeva un'immagine dinamica da Adobe Target (CAMP-24848).
* È stato risolto un problema relativo ai flussi di lavoro **[!UICONTROL Privacy Access/Delete Request]** tecnici che non venivano completati se una delle richieste non andava a buon fine.
* È stato risolto un problema che impediva al servizio Privacy Core di ricevere gli aggiornamenti dello stato della richiesta da Campaign.
* È stato risolto un problema che impediva il corretto funzionamento del flusso di lavoro tecnico **[!UICONTROL Import shared audience]** (CAMP-25465).
* È stato risolto un problema che impediva alle richieste di privacy per Campaign di essere contrassegnate come completate nel servizio Privacy di base.
* È stato risolto un problema che poteva impedire ad alcuni utenti di accedere a Campaign Standard tramite l'autenticazione IMS quando l'Adobe ID era troppo lungo. (CAMP-24095)
* È stato risolto un problema in Creative Designer che poteva verificarsi durante la rimozione dei moduli di contenuto. (CAMP-25242)
* È stato risolto un problema che si verificava quando si usavano le regole di affaticamento delle notifiche push per gli abbonati senza profilo nel database. (CAMP-25344)
* È stato risolto un problema che poteva visualizzare un messaggio di errore durante l'accesso ai registri di esclusione delle consegne. (CAMP-24724)
* È stato risolto un problema che impediva la preparazione delle prove nelle istanze con log di invio estesi.
* Sono stati risolti due problemi che potevano verificarsi quando si pubblicavano risorse personalizzate con l' **[!UICONTROL Sending log]** estensione attivata.
* È stato risolto un problema che poteva verificarsi quando la durata della consegna non veniva presa in considerazione nelle consegne ricorrenti.
* È stato risolto un problema che poteva verificarsi durante l'ordinamento dei dati nel **[!UICONTROL Client data]** menu, per le risorse personalizzate con più di 100K record. (CAMP-24308)
* È stato risolto un problema con dimensioni di profilo personalizzate che non venivano prese in considerazione quando si utilizzava la funzione di ricerca nei report dinamici.
* È stato risolto un problema con la visualizzazione di dati internazionali per i livelli di account nei report dinamici.
* È ora possibile creare un servizio senza un messaggio di conferma dell'iscrizione o dell'annullamento dell'iscrizione.

## Rilascio 18.5 - maggio 2018 {#release-18-5---may-2018}

### What's new? {#what-s-new--2}

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> GDPR: Integrazione dei servizi di base<br /> </td> 
   <td> Privacy Core Service Integration consente di automatizzare le richieste GDPR in un contesto multisoluzione tramite una singola chiamata API JSON. <br /> Le richieste GDPR inviate dal servizio Privacy Core a tutte le soluzioni Experience Cloud ora vengono gestite automaticamente da Campaign. <br /> Per ulteriori informazioni, consulta la documentazione <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Miglioramenti push - feedback dettagliato sulla distribuzione<br /> </td> 
   <td> Adobe Campaign ora consente di ricevere feedback dettagliati (registri di invio e registri di esclusione) sui messaggi push dai provider (APNS/GCM) tramite MCPNS.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Estensione dei registri di consegna<br /> </td> 
   <td> L’estensione dei registri di distribuzione consente di estendere i registri di invio con dati di profilo e codice del segmento provenienti dai flussi di lavoro. Queste informazioni possono essere usate in Rapporti dinamici e consentono di conservare un’istantanea di alcune informazioni al momento dell’invio di una consegna.<br /> Ci sono altri 2 casi di utilizzo :<br /> 
    <ul> 
     <li> Esportare i file di registro estesi con dati "congelati": Come esperto di marketing, vorrei esportare tutti i profili in cui il codice del segmento è uguale a "A" (proveniente dal motore del flusso di lavoro). </li> 
     <li> Segmentazione su dati "congelati": In qualità di esperto di marketing, vorrei <strong>recuperare</strong> tutti i profili che hanno vinto 1000 punti fedeltà dall'ultimo invio o dove il codice del segmento era uguale a "A". </li> 
    </ul> Per ulteriori informazioni, consulta la documentazione <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Generazione di rapporti dinamici con dati di profilo personalizzati<br /> </td> 
   <td> Questa funzione consente di creare e gestire rapporti basati su dati di profilo personalizzati creati durante l'estensione delle risorse del profilo. Potete suddividere i rapporti per attributo di profilo come programma fedeltà, canale preferito, ecc.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension"></a>dettagliata.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Miglioramenti {#improvements-3}

* È stata migliorata la memoria e l'utilizzo della CPU dell'applicazione

### Altre modifiche {#other-changes-3}

* L'attività del flusso di lavoro Leggi audience ora può leggere le audience di Experience Cloud. In precedenza, questa attività era in grado di leggere solo le audience Query ed Elenco. Fare riferimento alla documentazione [](../../automating/using/read-audience.md)dettagliata. (CAMP-23623)
* L'identificatore dell'origine dati condivisa predefinita ora è in modalità di sola lettura e non può più essere modificato. La modifica di questo identificatore potrebbe causare problemi durante la condivisione di audience con Experience Cloud.
* L'importazione di audience da Audience Manager ora funziona con file suddivisi. In precedenza, solo l’ultimo file del segmento veniva importato dal flusso di lavoro tecnico importSharedAudience.
* Gli account esterni AWS S3 ora supportano le aree geografiche e il meccanismo di autenticazione della versione 4. Fare riferimento alla documentazione [](../../administration/using/external-accounts.md)dettagliata.
* La finestra di selezione delle risorse ora dovrebbe caricarsi più velocemente e consentire di selezionare una risorsa e quindi uscire dalla finestra senza alcun problema.
* Le proprietà e la struttura dei flussi di lavoro tecnici ora possono essere modificate dagli utenti con diritti amministrativi e appartenenti alle unità organizzative e geografiche "All".
* Sono stati apportati miglioramenti all'interfaccia dell'attività di segmentazione al momento della creazione di nuovi segmenti: La scheda Limitazione ora viene visualizzata direttamente dopo l'aggiunta di un limite. I nomi dei nuovi segmenti ora vengono incrementati ("Segmento 1", "Segmento 2", ecc.).
* Alla risorsa Workflow viene aggiunto un campo "nextProcessingDate". Questo campo è visibile solo tramite le chiamate REST API, e consente di visualizzare i flussi di lavoro nelle date di elaborazione successive.
* Il campo "sourceId" ora è esposto nella risorsa dei registri di tracciamento (nms:trackingLog).
* I valori "Totale aperture" e "Totale clic" ora possono essere esportati in un file semplice tramite un flusso di lavoro. (CAMP-24186)
* "English - Danmark" è ora disponibile nell'elenco delle lingue preferite nei profili. (CAMP-23728)
* Quando si utilizza un'attività di segmentazione con un collegamento dati aggiuntivi (targetData), ora viene visualizzato un messaggio che informa che i dati non sono disponibili al di fuori del flusso di lavoro. Questo messaggio viene visualizzato quando si fa clic sul pulsante Conteggio o Anteprima dall'attività Segmentazione. (CAMP-23651)
* Sono stati apportati miglioramenti per ottimizzare lo spazio su disco utilizzato dai flussi di lavoro: (CAMP-21979): I file elaborati dall'attività "Carica file" ora vengono eliminati per impostazione predefinita. Un’opzione consente di mantenerle per esigenze specifiche. Quando un flusso di lavoro viene eliminato, la relativa cartella dedicata viene automaticamente eliminata dalla directory del server.

### Patch {#patches-3}

* È stato risolto un problema che impediva ad alcuni eventi di reporting non elaborato di associare eventi di tracciamento perché il campo eventDate non era popolato correttamente.
* È stato risolto un problema che impediva la visualizzazione dei campi personalizzati nella finestra di anteprima di una notifica push.
* È stato risolto un problema che impediva al testo di mandare a capo il corpo del messaggio di una notifica push nella finestra di anteprima.
* È stato risolto un problema che si verificava durante l'invio di una consegna ricorrente da un flusso di lavoro quando la destinazione principale era vuota.
* È stato risolto un problema che impediva l'accesso a una mappatura di destinazione se collegata a uno schema non esistente.
* È stato risolto un problema che poteva verificarsi durante l'importazione di un file zip tramite un'attività di caricamento del file. (CAMP-24309)
* È stato risolto un problema che causava un errore PostgreSQL durante l'invio di una consegna ricorrente. (CAMP-23613)
* È stato risolto un problema che causava la visualizzazione di un messaggio di errore durante l'invio di una richiesta REST API con un attributo JSON vuoto. (CAMP-23506)
* È stato risolto un problema nei profili che impostava l'opzione maiuscola per i caratteri successivi al carattere "ß". (CAMP-23136)
* È stato risolto un problema che si verificava durante l'invio di invii utilizzati con le condizioni di idoneità del blocco di contenuto dinamico o personalizzato durante l'utilizzo di attributi da uno schema di profilo collegato. (CAMP-22751)
* È stato risolto un problema che impediva l'eliminazione dei servizi. (CAMP-22050)
* È stato risolto un problema che impediva la modifica dei valori Paese o Stato in un profilo di test. (CAMP-20426)
* È stato risolto un problema che poteva impedire il caricamento di Creative Designer. (CAMP-24573)
* È stato risolto un problema che causava la rimozione di caratteri aggiunti dopo i campi di personalizzazione nell’oggetto e-mail. (CAMP-24113)

## Rilascio 18.4 - Aprile 2018 {#release-18-4---april-2018}

### Patch {#patches-4}

#### Piattaforma {#platform}

* È stato corretto un errore che poteva impedire la corretta elaborazione delle richieste di accesso o di eliminazione GDPR. Questo comportamento è stato osservato in alcuni rari casi in cui i dati estratti contenevano uno dei seguenti caratteri: &amp; &lt; &gt; " '.

#### E-mail, SMS e posta diretta {#emails--sms-messages-and-direct-mail}

* È stato risolto un problema che poteva causare la sovrascrittura dei KPI con valori errati se la sincronizzazione del broadcast richiedeva più di un'ora.

#### Flussi di lavoro {#workflows}

* Gestione della memoria migliorata e prestazioni ottimizzate nei flussi di lavoro.

#### Reporting {#reporting}

* Il flusso di lavoro di condivisione KPI ora recupera i valori di consegna per gli ultimi 2 mesi invece degli ultimi 6 mesi. È stato risolto un problema con l'account esterno della condivisione KPI che mostrava date troncate.
* È stato corretto un problema a causa del quale alcuni messaggi non venivano presi in considerazione in **Inviati**, **Consegnati** e **** Bouncemetrics.
* È stato corretto un errore che si verificava quando l'intervallo di tempo scelto nel rapporto **di riepilogo** consegna era troppo lungo.

#### Risorse personalizzate {#custom-resources}

* È stato corretto un errore che causava un errore nella preparazione delle risorse personalizzate.

## Rilascio 18.3 - marzo 2018 {#release-18-3---march-2018}

### Nuove funzionalità {#new-capabilities}

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Regolamento generale UE sulla protezione dei dati (RGPD)<br /> </td> 
   <td> Il GDPR è la nuova legge dell’Unione europea sulla privacy che armonizza e aggiorna i requisiti di protezione dei dati in vigore dal 25 maggio 2018. Il Regolamento GDPR si applica ai clienti Adobe Campaign che detengono dati per i soggetti dati residenti nell'UE.<br /> Oltre alle funzionalità per la privacy già disponibili in Adobe Campaign (compresa la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), stiamo sfruttando questa opportunità in qualità di Data Processor per includere funzionalità aggiuntive, al fine di facilitare la tua disponibilità come Data Controller per determinate richieste GDPR:<br /> 
    <ul> 
     <li> Diritto di accesso: consente all'Oggetto dati di ricevere una copia dei dati personali acquisiti dai Controllori dei dati, che possono includere dati memorizzati in Adobe Campaign. </li> 
     <li> Destra per eliminare: autorizza l'Oggetto dati a cancellare i propri dati personali acquisiti dai Controllori dei dati, includendo potenzialmente i dati archiviati in Adobe Campaign. </li> 
    </ul> Per ulteriori informazioni, consulta la documentazione <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer per e-mail (versione beta)<br /> </td> 
   <td> Il nuovo Creative Designer di Adobe Campaign offre un'esperienza di creazione completamente integrata in Campaign, consentendo la creazione visiva rapida e semplice di e-mail coinvolgenti e personalizzate individualmente senza la necessità di creare script su una sola riga di codice. Grazie alla sua potente interfaccia di trascinamento, Creative Designer consente di ridimensionare la creazione delle e-mail sia per gli utenti che iniziano da una lavagna vuota, sia per sfruttare i frammenti di contenuto o i modelli esistenti. <br /> Le funzionalità principali includono:<br /> 
    <ul> 
     <li> Progettazione visiva e creazione di e-mail reattive completamente personalizzate attraverso un'interfaccia a trascinamento, integrata dalle integrazioni native di Creative Cloud </li> 
     <li> Creazione e salvataggio di un modello di contenuto e-mail e utilizzo dei modelli salvati per la creazione di e-mail </li> 
     <li> Creare e salvare frammenti di contenuto (ad esempio intestazione, piè di pagina, articolo ecc.) per semplificare la creazione di contenuti e garantire la coerenza del marchio </li> 
     <li> Passa facilmente dalla creazione nell’interfaccia di trascinamento alla modifica diretta HTML di un messaggio e-mail facendo clic su un pulsante </li> 
    </ul> Creative Designer per e-mail è disponibile solo in inglese.<br /> Per ulteriori informazioni, consultate la documentazione <a href="../../designing/using/overview.md"></a> dettagliata e guardate questo <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">video</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Distribuzione push multilingue<br /> </td> 
   <td> La stessa semplice interfaccia multilingue, già presente sui canali e-mail e SMS, è stata aggiunta al canale push per aiutarvi a coinvolgere i clienti indipendentemente dalla loro lingua preferita.<br /> Questa funzionalità offre una soluzione scalabile e automatica per i clienti che gestiscono campagne push in più aree geografiche e desiderano indirizzare gli utenti nella lingua desiderata. Consente di caricare tutte le varianti linguistiche tramite un foglio di calcolo modulato su un singolo invio push, con un solo clic. Adobe Campaign esegue quindi una segmentazione automatica in base alle preferenze linguistiche degli utenti, contribuendo a ridurre le ridondanze semplificando i flussi di lavoro e i rapporti.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/creating-a-multilingual-push-notification.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Utilizzo delle risorse personalizzate nei messaggi transazionali<br /> </td> 
   <td> Oltre ai campi out-of-the-box, i messaggi transazionali ora consentono di utilizzare risorse personalizzate per arricchire il contenuto dei messaggi.<br /> Ad esempio:<br /> 
    <ul> 
     <li> Utilizza i campi personalizzati come criteri di riconciliazione per far corrispondere un messaggio transazionale a un profilo </li> 
     <li> Sfruttare profili completi, servizi e dati collegati per personalizzare ulteriormente i messaggi relativi alle transazioni </li> 
    </ul> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/configuring-transactional-messaging.md"></a>dettagliata.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patch {#patches-5}

#### Piattaforma {#platform-1}

* È stato risolto un problema che impediva l'esportazione di più di 5000 record da un elenco.
* È stato risolto un problema che si verificava durante l'esportazione dei dati in file denominati con campi di personalizzazione.

#### E-mail, SMS e posta diretta {#emails--sms-messages-and-direct-mail-1}

* È stato risolto un problema che causava il troncamento degli SMS con più parti in quanto le dimensioni delle parti venivano calcolate in caratteri anziché in byte.
* Aggiunta un'opzione che consente l'aggiornamento in tempo reale dei **[!UICONTROL Delivered]** KPI o **[!UICONTROL Bounces + Errors]** dei KPI dopo l'invio. Vengono ricalcolati direttamente dall'SR (Status Report) ricevuto dal provider.
* È stato risolto un problema relativo al widget del calendario nell'utilità di pianificazione della consegna.
* È stato corretto un problema di visualizzazione quando si apriva una destinazione per la seconda volta in una consegna inviata.
* È stato risolto un problema che causava un messaggio di errore che richiedeva una data di inizio, durante la creazione di un modello e-mail con una data di invio ritardata.
* È stato risolto un problema che poteva causare problemi di rendering delle immagini durante la modifica del contenuto di una consegna.
* È stato risolto un problema relativo alle prove di stampa durante la duplicazione di una campagna.
* È stato risolto un problema che causava un messaggio di errore durante l'accesso a un modello di campagna tramite la barra di navigazione, dopo l'aggiunta di una consegna al flusso di lavoro.
* È stato risolto un problema che poteva impedire la selezione automatica del vincitore di un messaggio e-mail di test A/B, causando l'assenza dell'invio del messaggio e-mail. Questo comportamento può verificarsi se la consegna è in **[!UICONTROL retryInProgress]** stato.
* È stato risolto un problema che poteva causare la visualizzazione di un messaggio di errore durante la riapertura dei parametri di un'e-mail di test A/B.

#### Audience e query {#audiences-e-queries}

* È stato risolto un problema che impediva l'accesso ai dati e l'impostazione di query per i destinatari replicati da Adobe Campaign Classic a Standard.
* È stato risolto un problema che si verificava durante l'utilizzo di un campo del tipo di filtro nell'editor query, dopo l'utilizzo dei pulsanti **Count** o **Preview** .

#### Flussi di lavoro {#workflows-1}

* Il flusso di lavoro **Fatturazione** è stato ottimizzato per migliorare il ritardo nella preparazione della consegna.
* È stato risolto un problema che impediva la visualizzazione dei dati della popolazione in una transizione in uscita durante l'utilizzo di un'attività di consegna ricorrente.
* È stato risolto un problema che impediva la visualizzazione dei record di rifiuto in una transizione dopo un'attività **Aggiorna dati** .
* È stato risolto un problema che poteva causare il fallimento del flusso di lavoro tecnico **recapitoUpdate** .

#### Integrazioni {#integrations}

* È stato risolto un problema che impediva l'invio corretto dei caratteri internazionali ad Adobe Analytics.
* Le risorse ora devono caricarsi più velocemente quando tenti di inserire un'immagine dalla libreria di risorse Experience Cloud in un messaggio.
* È stato risolto un problema che in alcuni casi poteva impedire la chiusura della finestra di selezione delle risorse.
* Da un dettaglio dell'origine dati, ora potete accedere direttamente al relativo flusso di lavoro per verificare lo stato del flusso di lavoro.
* È ora possibile aggiornare lo schema Triggers direttamente quando si definisce o si modifica un evento di attivazione. Con questa modifica, non è più necessario annullare la pubblicazione del trigger e crearne un altro.

#### Messaggi transazionali {#transactional-messages}

* È stato corretto un errore con il modello di messaggio transazionale quando la risorsa di consegna veniva estesa.
* È ora possibile eliminare i messaggi transazionali.

## Rilascio 18.2 - febbraio 2018 {#release-18-2---february-2018}

### Nuove funzionalità {#new-capabilities-1}

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Iscrizione: sottoscrivere o annullare l’iscrizione di un elenco di profili a più servizi<br /> </td> 
   <td> L'attività del flusso di lavoro Servizi <strong></strong> iscrizione ora consente di effettuare o cancellare l'iscrizione di un elenco di profili a più servizi. Nel flusso di lavoro, importate un file contenente i profili e, per ciascun profilo, il tipo di operazione e il servizio. L'attività Servizi <strong></strong> iscrizione sarà in grado di utilizzare queste informazioni e gestire dinamicamente tutte le iscrizioni e le cancellazioni di iscrizioni di profili contemporaneamente.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/subscription-services.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Attività di arricchimento: arricchisci i dati in base alle transizioni precedenti<br /> </td> 
   <td> La nuova attività del flusso di lavoro <span class="uicontrol">Arricchimento</span> consente di sfruttare le transizioni in entrata e completare la transizione in uscita con dati aggiuntivi. Se eseguite il targeting dei profili, l'attività di arricchimento consente di arricchire le informazioni sui profili con dati aggiuntivi non memorizzati nel database (ad esempio, provenienti da un file importato).<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/enrichment.md"></a>dettagliata.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patch {#patches-6}

#### Piattaforma {#platform-2}

* La barra superiore dell'interfaccia di Adobe Campaign è stata aggiornata con il nuovo menu Experience Cloud.
* È stato risolto un problema che impediva la visualizzazione del collegamento **[!UICONTROL Offers]** nell'elenco a discesa della soluzione.

#### E-mail, SMS e posta diretta {#emails--sms-messages-and-direct-mail-2}

* La fase di preparazione della consegna è stata migliorata per migliorare le prestazioni.
* Sono stati risolti diversi problemi che potevano causare il danneggiamento dei registri di monitoraggio in alcune situazioni di nicchia.
* È stato risolto un problema di aggiornamento della data del contatto che si verificava quando la data del contatto veniva modificata tra la preparazione della consegna e la conferma. Ora, quando si modifica la data di contatto dopo la preparazione, è necessario preparare di nuovo la consegna prima di poter confermare l'invio. Consulta la documentazione [](../../sending/using/preparing-the-send.md)dettagliata.

#### Notifiche push {#push-notifications}

* È stato corretto un errore che impediva ad alcuni campi di personalizzazione di funzionare nelle notifiche push di iOS.
* È stato corretto un errore a causa del quale venivano visualizzati clic e tassi di apertura pari a 0% nel dashboard delle notifiche push.

#### Rapporti {#reports}

* È stato risolto un errore che causava la visualizzazione dell'elenco dei report come vuoto in alcuni browser.
* È stato corretto un errore che si verificava nel flusso di lavoro **[!UICONTROL Report sharing]** tecnico subito prima del raggiungimento del limite di scadenza.

#### Flussi di lavoro {#workflows-2}

* È stato risolto un problema che impediva alle attività di essere accessibili dopo il trascinamento.
* È stato risolto un problema che in alcune situazioni poteva modificare l'ordine delle transizioni di output di un' **[!UICONTROL Segmentation]** attività.
* È stato risolto un errore che si verificava durante la lettura di un'audience contenente un campo di tipo enumerazione precedentemente salvato da un flusso di lavoro
* È stato risolto un problema a causa del quale l' **[!UICONTROL Request confirmation before sending messages]** opzione rimaneva selezionata anche dopo l'annullamento del controllo quando si definivano le proprietà di pianificazione di una consegna creata in un flusso di lavoro.
* La rimozione automatica delle righe duplicate (clausola DISTINCT) ora può essere disattivata nelle **[!UICONTROL Query]** attività tramite una nuova opzione che si trova nella **[!UICONTROL Additional data]** scheda. La disattivazione di questa opzione è consigliata quando si definiscono molti (più di 100) elementi aggiuntivi, per motivi di prestazioni.

#### Integrazioni {#integrations-1}

* Sono stati apportati alcuni miglioramenti alla schermata di **[!UICONTROL Data sources]** configurazione.

### Problemi noti {#known-issues}

È consigliabile non utilizzare Internet Explorer versione 11 a causa di possibili problemi di visualizzazione.

Alcuni problemi possono verificarsi quando si utilizzano collegamenti di aiuto contestuali dall'interfaccia di Campaign. Saranno fissate in 18.3.

## Rilascio 18.1 - gennaio 2018 {#release-18-1---january-2018}

### Nuove funzionalità {#new-capabilities-2}

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reporting for Fatigue Management<br /> </td> 
   <td> Reporting for Fatigue Management è un rapporto dedicato e configurabile che mostra l'impatto delle regole di affaticamento sulle consegne tra i canali e-mail, push, SMS e Direct Mail entro un intervallo di date specificato prima dell'invio. Grazie alla possibilità di visualizzare rapidamente tutte le campagne in conflitto in una singola vista, gli addetti al marketing possono pianificare campagne di marketing in base alle regole di affaticamento in modo più efficace e assegnare priorità alle comunicazioni.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Condivisione dei rapporti<br /> </td> 
   <td> La condivisione di rapporti consente di condividere i rapporti con gli utenti di Adobe Campaign come allegati e-mail, anche su base ricorrente automatica. Gli utenti che ricevono rapporti periodici possono annullare l’iscrizione a tali comunicazioni tramite un collegamento dedicato in ogni e-mail.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../reporting/using/reporting-interface.md#share-tab"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nuove funzionalità push<br /> </td> 
   <td> Anteprima messaggi push - Anteprima delle notifiche push su dispositivi iOS e Android dall'editor contenuto delle notifiche push per vedere esattamente cosa vedranno i destinatari prima di testare o eseguire la consegna.<br /> Per ulteriori informazioni, consulta la documentazione <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification"></a>dettagliata.<br /> Contenuto disponibile: quando le app non vengono aperte per periodi di tempo prolungati, i loro dati possono diventare obsoleti. Ciò comporta la necessità di aggiornare o sostituire i dati nel momento in cui un utente apre finalmente l'app, causando ritardi nell'utilizzo dell'app. Con il supporto aggiunto di Contenuto disponibile, gli utenti di Adobe Campaign possono svegliare la propria app per aggiornare i dati in background quando viene inviata una notifica push, consentendo coerenza e controllo maggiori dell'esperienza in-app di un utente.<br /> Contenuto variabile - Con il supporto aggiunto di Contenuto variabile, gli utenti Adobe Campaign possono ora sfruttare le estensioni delle app mobili per modificare ulteriormente il contenuto o la presentazione delle notifiche push in arrivo inviate da Adobe Campaign. Ad esempio, gli utenti possono utilizzare Contenuto variabile per: <br /> 
    <ul> 
     <li> decrittografare i dati inviati in formato crittografato </li> 
     <li> scaricare immagini o altri file multimediali e aggiungerli come allegati a una notifica </li> 
     <li> modifica del corpo o del testo del titolo di una notifica </li> 
     <li> aggiungere un identificatore di thread a una notifica </li> 
    </ul> Per ulteriori informazioni su Contenuto disponibile e Contenuto variabile, consultate la documentazione <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios"></a>dettagliata.<br /><strong> </strong>Avviso: questi aggiornamenti sulle notifiche push richiedono ai clienti di aggiornare le loro applicazioni mobili. Per ulteriori informazioni, consultare <a href="https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">questa nota tecnica</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegne ottimizzate per il fuso orario<br /> </td> 
   <td> Pianificare notifiche e-mail, SMS e push ricorrenti da inviare in un giorno/ora specifico in ogni fuso orario dei destinatari, garantendo che i messaggi vengano recapitati al momento giusto senza configurare più consegne. <br /> Per ulteriori informazioni, consulta la documentazione <a href="../../automating/using/scheduler.md"></a>dettagliata.<br /> </td> 
  </tr> 
  <tr> 
   <td> Attivazione attività segnale API<br /> </td> 
   <td> È ora possibile attivare un'attività di segnale per i flussi di lavoro direttamente dall'API di Adobe Campaign Standard.<br /> Per ulteriori informazioni, consultare la documentazione <a class="anchorLink" href="https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity" target="_blank"></a> dettagliata .<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patch {#patches-7}

#### Piattaforma {#platform-3}

* La ricerca del profilo è stata ottimizzata per migliorare le prestazioni.
* L'identificatore interno dei gruppi di sicurezza predefiniti è ora in modalità di sola lettura per gli utenti standard.

#### E-mail, SMS e posta diretta {#emails--sms-messages-and-direct-mail-3}

* È stato risolto un problema di visualizzazione che si verificava durante l'inserimento di emoji nel contenuto delle consegne.
* È stato risolto un problema che consentiva all'utente di accedere ai log di invio quando la consegna era ancora in edizione.
* L' **[!UICONTROL Scheduler]** attività ora consente di inviare le consegne in base al fuso orario del destinatario.
* SMS: L'opzione **[!UICONTROL Store incoming MO]** nel database è stata aggiunta agli account esterni. Se questa opzione è selezionata, tutti gli SMS in ingresso verranno memorizzati nella tabella **inSMS** .
* SMS: I servizi ora sono collegati a un evento anziché a un modello transazionale.
* SMS: Il timeout di connessione SMTP predefinito è stato ridotto a 30 secondi.

#### Notifiche push {#push-notifications-1}

* È stato corretto un errore che impediva l'interruzione delle consegne delle notifiche push.
* Aggiunta un'opzione nelle opzioni avanzate di notifica push per attivare l'applicazione con una notifica push.
* È stato aggiunto un pulsante di pausa per il video di anteprima della notifica push.
* L'anteprima della notifica push ora è disponibile per diversi dispositivi quali iPhone, Android, tablet.

   tutti i canali

#### Rapporti {#reports-1}

* È stato corretto un errore a causa del quale venivano visualizzate percentuali superiori al 100%.
* È stato risolto un problema che impediva agli utenti di scaricare i rapporti in CSV.
* È stato aggiunto un nuovo **[!UICONTROL Report]** elemento nella pagina principale.

#### Flussi di lavoro {#workflows-3}

* È stato risolto un problema che causava un messaggio di errore durante l'utilizzo di dati aggiuntivi in una query e l'aggiunta di alias contenenti spazi. I caratteri non alfanumerici ora vengono sostituiti da "_".
* È stato corretto un problema a causa del quale, in alcuni casi, il flusso di lavoro tecnico per il calcolo dei KPI poteva essere interrotto per impostazione predefinita.

#### Profili e audience {#profiles-and-audiences}

* È stato corretto un errore che si verificava durante l'aggiunta di più filtri nella query di un'audience.
* È stato risolto un problema di visualizzazione che si verificava durante la modifica dell'immagine di un profilo.
* Aggiunta una descrizione comandi che visualizza il numero esatto del risultato dopo il conteggio della popolazione di una query.
* È stato risolto un problema che poteva impedire a un utente di selezionare un'audience o chiudere la finestra del selettore dell'audience.
* L'elenco delle funzioni disponibili nell'editor di espressioni è stato aggiornato. Le funzioni **FormatCurrency** e **ConvertCurrency** sono state rimosse.

