---
title: Note sulla versione 2018
description: In questa pagina sono elencate tutte le versioni di Adobe Campaign Standard del 2018.
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 17521357-14ae-4751-bd7c-aeabbcf71d07
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '5355'
ht-degree: 6%

---

# Note sulla versione 2018{#release-notes}

## Versione 18.9 - Settembre 2018 {#release-18-9---september-2018}

**Novità**

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
   <td> La messaggistica in-app consente di coinvolgere in modo più efficace gli utenti di app mobili tramite interazione contestuale e la possibilità di raggiungere gli utenti che hanno disattivato le notifiche push. Utilizza la messaggistica in-app insieme alle notifiche push per creare un’esperienza altamente personalizzata e rilevante. Questo porta a una migliore conversione e conservazione degli utenti dell’app.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/about-in-app-messaging.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrazione di Adobe Launch per le app mobili (beta)<br /> </td> 
   <td> L’integrazione di Adobe Launch con Adobe Campaign semplifica e automatizza ora il processo di attivazione delle proprietà di app mobili in Campaign, utilizzando l’SDK Mobile v5.<br /> Per ulteriori informazioni, consulta la <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html?lang=it">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Miglioramenti**

* Adobe Campaign Standard ora supporta la versione 4 dell’API Amazon S3.

**Altre modifiche**

* Nei broadlog esiste ora una distinzione tra il numero massimo di connessioni e il numero massimo di messaggi all&#39;ora. Una volta raggiunti i limiti, è possibile comprendere perché il throughput è limitato. In precedenza, lo stesso messaggio (&quot;quota soddisfatta&quot;) si applicava a entrambi i casi.
* Durante la configurazione di un’app mobile in Campaign, l’utente ora può sapere se il certificato iOS e la chiave del server Android sono stati caricati correttamente e la loro data di scadenza.

   Per ulteriori informazioni, consulta la documentazione dettagliata su come configurare un’app mobile utilizzando [SDK V4](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html) e [SDK V5](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html).

* Puoi indirizzare l’attività agli utenti di una specifica app mobile selezionando un’app mobile durante la definizione delle proprietà della campagna. Questa funzione è valida sia per i canali di messaggistica push che in-app.

   Per ulteriori informazioni, consulta la [documentazione dettagliata](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Quando si seleziona un blocco di contenuto tramite l’interfaccia di Creative Designer, ora vengono caricati e visualizzati tutti i blocchi di contenuto dell’elenco. (CAMP-27311)

   Per ulteriori informazioni, consulta [documentazione dettagliata](../../designing/using/personalization.md#adding-a-content-block).

**Patch**

* È stato risolto un problema che mostrava una discrepanza nei conteggi dei registri tra il dashboard e-mail e il rapporto di riepilogo e-mail per le e-mail transazionali. (CAMP-28237
* È stato risolto un problema nei flussi di lavoro che poteva mostrare un messaggio di errore durante l’importazione di un file tramite un’attività di trasferimento dei file. (CAMP-27435)
* È stato risolto un problema relativo alle pagine di destinazione contenenti più di 25 servizi, a causa del quale i servizi venivano deselezionati in modo casuale nel modulo. (CAMP-26572)
* È stato risolto un problema nei flussi di lavoro che impediva la configurazione di account esterni con un URL SFTP durante l’utilizzo dell’attività File transfer. (CAMP-26475)
* È stato risolto un problema che impediva l’aggiornamento del rapporto di riepilogo dei servizi. (CAMP-26301)
* È stato risolto un problema nei flussi di lavoro che impediva a un campo personalizzato di visualizzare la data corretta durante l’utilizzo di un’attività Enrichment. (CAMP-26242)
* È stato risolto un problema che impediva l’aggiornamento delle date di abbonamento al servizio quando importate tramite un’importazione di file.
* È stato corretto un errore con l’attività di caricamento file che impediva ai flussi di lavoro di importare file (CAMP-27068).
* È stato risolto un problema che causava la visualizzazione di un numero errato di abbonamenti nei rapporti di riepilogo del servizio (CAMP-25587).
* È stato risolto un problema di discrepanza di dati tra i rapporti di Adobe Analytics e di Adobe Campaign. (CAMP-25393)
* È stato risolto un problema che poteva impedire a un utente con accesso limitato di accedere. (CAMP-27381)
* È stato risolto un problema che poteva impedire la visualizzazione dell’elenco dei contenuti di Adobe Experience Manager durante la modifica di un’e-mail tramite Creative Designer. (CAMP-27181)
* È stato risolto un problema che poteva impedire l’apertura di Creative Designer, causando un errore. (CAMP-27304)
* È stato risolto un problema che impediva il corretto funzionamento del trascinamento della selezione in Creative Designer durante l’utilizzo di Internet Explorer 11.
* È stato risolto un problema a causa del quale le immagini caricate da una fotocamera e riprese in modalità ritratto venivano visualizzate in una posizione ruotata indesiderata.
* È stato risolto un problema che causava la visualizzazione di informazioni poco chiare sulla selezione quando si utilizzava l’interfaccia dell’editor delle query in Creative Designer.
* È stato risolto un problema che impediva la corretta duplicazione di un elemento quando si utilizzava l’interfaccia dell’editor delle query in Creative Designer.
* È stato risolto un problema che continuava a inviare messaggi SMS ai destinatari durante il inserisco nell&#39;elenco Bloccati di invio del messaggio, anche se l’iscrizione era stata annullata tramite una risposta automatica. (CAMP-27128)
* È stato risolto un problema che impediva la visualizzazione degli errori che causavano **Database Cleanup** flusso di lavoro non riuscito. (CAMP-26876)
* È stato risolto un problema che poteva impedire l’eliminazione di campi personalizzati in una definizione di notifica push. (CAMP-25588)

## Versione 18.7 - Luglio 2018 {#release-18-7---july-2018}

**Novità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Flag ad alta priorità per le notifiche push in Android<br /> </td> 
   <td> Flag ad alta priorità per Android: abilita la consegna di una notifica push con alta priorità per le app Android, che causa la riattivazione del dispositivo inattivo e l’esecuzione di alcune elaborazioni limitate. Si noti che la priorità predefinita è Normale, il che può ritardare la consegna del messaggio per risparmiare batteria. <br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Filtro della tipologia per gli abbonati all’app mobile<br /> </td> 
   <td> Supporta le sottoscrizioni nel filtro della tipologia: quando si specificano i criteri di filtro per una regola di tipologia, è possibile selezionare le sottoscrizioni alle applicazioni come dimensioni di filtro e di targeting, consentendo di filtrare gli attributi per gli utenti con o senza un profilo. <br /> Per ulteriori informazioni, consulta la <a href="../../sending/using/about-typology-rules.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importazione automatizzata dei contenuti da un URL durante la preparazione dei messaggi<br /> </td> 
   <td> È ora possibile importare contenuti e-mail da un URL durante la fase di preparazione. Per le consegne e-mail ricorrenti, viene recuperato il contenuto più recente di HTML ogni volta che il messaggio viene preparato, garantendo che il contenuto sia sempre aggiornato al momento dell’invio dell’e-mail. Questa funzione consente inoltre di creare una consegna pianificata con contenuto da un URL anche se il contenuto non è ancora pronto.<br /> Per ulteriori informazioni, consulta la <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Messaggio di notifica della versione di Campaign<br /> </td> 
   <td> Ora quando un utente effettua l’accesso dopo che l’istanza è stata aggiornata a una nuova versione, viene visualizzato un messaggio a comparsa. Il messaggio indica il numero di versione e include un collegamento alle note sulla versione. Puoi scegliere di nascondere il messaggio fino alla versione successiva. <br /> </td> 
  </tr> 
  <tr> 
   <td> Gestione utente<br /> </td> 
   <td> A partire dalla versione 18.7, la funzionalità di unità geografica non è più disponibile per le nuove istanze di Campaign Standard, né per le istanze esistenti prive di unità geografiche.<br /><a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=it#"> Per ulteriori informazioni, consulta questa pagina</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Miglioramenti**

* L’integrazione di Adobe Campaign e Adobe Target ora consente di sfruttare i [Autorizzazioni](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html) funzionalità. Quando includi un’immagine dinamica da Adobe Target in un messaggio e-mail, ora puoi specificare una proprietà Target (codice at_property).
* Le risorse personalizzate con un collegamento di copia verso la risorsa dei profili ora vengono prese in considerazione dalle richieste di accesso/cancellazione della privacy GDPR. Per i collegamenti semplici a 1 cardinalità e i collegamenti di raccolta con cardinalità N, è necessario selezionare nella risorsa personalizzata &quot;L’eliminazione o la duplicazione del record di destinazione implica l’eliminazione o la duplicazione dei record a cui fa riferimento il collegamento&quot;. Per i collegamenti semplici con cardinalità 0 o 1, seleziona &quot;L’eliminazione o la duplicazione del record implica l’eliminazione o la duplicazione del record di destinazione a cui fa riferimento il collegamento&quot;.

**Altre modifiche**

* Il timeout di condivisione del rapporto è stato aumentato da uno a quattro minuti per evitare errori di timeout.
* Quando si modifica il contenuto di un’e-mail, per impostazione predefinita viene aperto il nuovo Creative Designer. Se lo desideri, puoi comunque tornare all’editor di contenuti predefinito in qualsiasi momento dopo aver salvato le modifiche. Per ulteriori informazioni, consulta [documentazione dettagliata](../../designing/using/designing-content-in-adobe-campaign.md).
* In Creative Designer, ora è possibile aggiungere un nuovo componente di contenuto a un messaggio e-mail: il carosello. Per ulteriori informazioni, consulta [documentazione dettagliata](../../designing/using/designing-from-scratch.md#about-content-components).
* In un rapporto sui messaggi transazionali hot click, quando fai clic su **Cambia profilo** ora sono elencati solo i profili di test collegati all’evento definito per il messaggio sulle transazioni.

**Patch**

* È stato risolto un problema relativo al filtro query byEmail che impediva la restituzione dei risultati. (CAMP-23420)
* È stato risolto un problema che consentiva a un utente standard di accedere a determinate funzioni o schermate limitate agli amministratori (/rest/head/&#42; endpoint, schermate di messaggistica transazionale, profili e tipi di pubblico (schermate di importazione).
* È stato risolto un problema che impediva alle richieste di eliminazione Privacy RGPD di elaborare risorse personalizzate se il nome era iniziato da un numero.
* È stato corretto un errore che impediva all’attività Save Audience di condividere gli abbonati all’applicazione in Adobe Experience Cloud.
* È stato risolto un problema relativo all’attività Trasferimento file che poteva verificarsi se il nome del file conteneva spazi vuoti. (CAMP-25936)
* È stato risolto un problema che poteva verificarsi quando si utilizzava il pulsante di riconnessione dopo la scadenza di una sessione. (CAMP-25560)
* È stato risolto un problema che poteva causare esclusioni durante l’invio di consegne con l’ottimizzazione del fuso orario associata alle regole di affaticamento. (CAMP-25425)
* È stato risolto un problema che si verificava durante l’utilizzo della funzione RGPD dell’API, che poteva impedire l’eliminazione di dati con un collegamento di tipo 0-1.
* È stato risolto un problema che poteva causare un messaggio di errore durante l’annullamento dell’edizione di una regola di tipologia di affaticamento.
* È stato risolto un problema che poteva verificarsi durante l’anteprima di un contenuto di consegna dopo la sua modifica.
* È stato risolto un problema che poteva verificarsi durante l’elaborazione dei file CSV zip durante l’utilizzo dell’opzione Decompressione.
* È stato risolto un problema in Creative Designer che causava font e formattazione di colore indesiderati quando si modificava del testo con stile integrato in un collegamento o quando si modificava tale collegamento. (CAMP-26001)
* È stato risolto un problema che impediva al rapporto sugli hot click di visualizzare le percentuali di ciascuna condizione nelle consegne contenenti contenuto dinamico. In precedenza venivano visualizzati solo i clic sulla variante predefinita.

## Versione 18.6 - Giugno 2018 {#release-18-6---june-2018}

**Miglioramenti**

* Il **[!UICONTROL History]** API aggiunta a Adobe.IO. Ti consente di accedere a informazioni relative alla cronologia di marketing di un profilo: numero di punti di contatto, consegne inviate, URL della pagina speculare, ecc. Per ulteriori informazioni, consulta [caso d’uso dedicato](../../api/using/interacting-with-marketing-history.md) .
* Il **[!UICONTROL Database cleanup]** il flusso di lavoro tecnico è stato ottimizzato per garantire prestazioni migliori per il backup del database.
* Creative Designer for Email è ora disponibile anche in francese e tedesco.

**Altre modifiche**

* A **[!UICONTROL Compute stats]** è stato aggiunto il pulsante in **[!UICONTROL Deployment]** finestra delle consegne inviate. Consente di recuperare i KPI più recenti, ad esempio se i risultati dell’invio richiedono troppo tempo o non sono stati presi in considerazione. Per ulteriori informazioni, consulta questa [sezione](../../sending/using/confirming-the-send.md).
* In **Aggiornamento per il recapito messaggi** flusso di lavoro tecnico preconfigurato, gli amministratori funzionali possono ora definire il numero di errori consecutivi da ignorare nel **Aggiorna regole** attività javascript. Per impostazione predefinita, il valore del campo è impostato su 0, il che significa che tutti gli errori verranno ignorati.
* L&#39;istruzione SQL generata durante la gestione delle condizioni di restrizione di accesso all&#39;unità è stata ottimizzata.
* Il **[!UICONTROL Update]** L’attività ora consente di aggiungere, aggiornare o eliminare i dati relativi agli abbonamenti (tabella nms:appSubscriptionRcp).
* Il **[!UICONTROL Update delivery execution]** il flusso di lavoro tecnico è stato suddiviso in due flussi di lavoro per ottimizzare le prestazioni: **[!UICONTROL Update delivery execution]**: aggiorna il tracciamento della consegna. Viene avviato ogni 10 minuti per impostazione predefinita. **[!UICONTROL Update delivery indicators]**: aggiorna i KPI della consegna, che viene avviata ogni ora per impostazione predefinita. Per ulteriori informazioni sui flussi di lavoro tecnici, consulta questa [sezione](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* Quando una consegna invia messaggi, lo stato in **[!UICONTROL Deployment]** La sezione può ora avere due valori: **[!UICONTROL Sending]**: i messaggi vengono inviati. **[!UICONTROL Sending (retry)]**: è in corso un nuovo passaggio dei tentativi.
* Utenti con **[!UICONTROL Delivery preparation]** Il ruolo ora è in grado di inviare bozze. (CAMP-24313)
* Il **Abilita TLS su SMPP** l&#39;opzione è stata aggiunta al **Indirizzamento SMS tramite SMPP** account esterno. Per ulteriori informazioni, consulta questa pagina [sezione](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**Patch**

* È stato risolto un problema che poteva impedire l’invio di e-mail quando si includeva un’immagine dinamica da Adobe Target (CAMP-24848).
* È stato risolto un problema relativo al **[!UICONTROL Privacy Access/Delete Request]** flussi di lavoro tecnici, che non venivano completati se una delle richieste non riusciva.
* È stato risolto un problema che impediva al servizio core Privacy di ricevere gli aggiornamenti sullo stato delle richieste da Campaign.
* È stato risolto un problema che impediva il corretto funzionamento del flusso di lavoro tecnico **[!UICONTROL Import shared audience]** (CAMP-25465).
* È stato risolto un problema che impediva a Campaign di contrassegnare le richieste di privacy come completate in Core Privacy Service.
* È stato risolto un problema che poteva impedire ad alcuni utenti di accedere a Campaign Standard tramite autenticazione IMS quando l’Adobe ID era troppo lungo. (CAMP-24095)
* È stato risolto un problema in Creative Designer che poteva verificarsi durante la rimozione di moduli di contenuto. (CAMP-25242)
* È stato risolto un problema che si verificava durante l’utilizzo delle regole di affaticamento delle notifiche push per gli abbonati che non disponevano di alcun profilo nel database. (CAMP-25344)
* È stato risolto un problema che poteva mostrare un messaggio di errore durante l’accesso ai registri di esclusione delle consegne. (CAMP-24724)
* È stato risolto un problema che impediva la preparazione delle bozze nelle istanze con registri di invio estesi.
* Sono stati risolti due problemi che potevano verificarsi durante la pubblicazione di risorse personalizzate con **[!UICONTROL Sending log]** estensione attivata.
* È stato risolto un problema che poteva verificarsi se la durata della consegna non veniva considerata nelle consegne ricorrenti.
* È stato risolto un problema che poteva verificarsi durante l’ordinamento dei dati in **[!UICONTROL Client data]** per risorse personalizzate con più di 100.000 record. (CAMP-24308)
* È stato risolto un problema relativo alle dimensioni di profilo personalizzate che non venivano prese in considerazione quando si utilizzava la funzione di ricerca nei report dinamici.
* È stato risolto un problema relativo alla visualizzazione di dati internazionali per i livelli Account nei report dinamici.
* È ora possibile creare un servizio senza un messaggio di conferma dell’abbonamento o del suo annullamento.

## Versione 18.5 - Maggio 2018 {#release-18-5---may-2018}

**Novità**

<table> 
 <thead> 
  <tr> 
   <th> Funzionalità<br /> </th> 
   <th> Descrizione<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> RGPD: integrazione dei servizi core<br /> </td> 
   <td> L’integrazione del servizio core per la privacy consente di automatizzare le richieste RGPD in un contesto multisoluzione tramite una singola chiamata API JSON. <br /> Le richieste RGPD inviate dal servizio core per la privacy a tutte le soluzioni Experience Cloud vengono ora gestite automaticamente da Campaign. <br /> Per ulteriori informazioni, consulta la <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Miglioramenti push - feedback dettagliato sulla consegna<br /> </td> 
   <td> Adobe Campaign ora consente di ricevere feedback dettagliati (registri di invio e registri di esclusione) sui messaggi push dai provider (APNS/GCM) tramite MCPNS.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Estensione dei registri di consegna<br /> </td> 
   <td> L’estensione dei registri di consegna ti consente di estendere l’invio dei registri con i dati di profilo e il codice del segmento provenienti dai flussi di lavoro. Queste informazioni possono quindi essere utilizzate nei report dinamici e consentono di conservare un’istantanea di alcune informazioni al momento dell’invio di una consegna.<br /> Ci sono altri 2 casi d'uso :<br /> 
    <ul> 
     <li> Esportare broadlog estesi con dati "congelati": in qualità di addetto al marketing, vorrei esportare tutti i profili in cui il codice segmento è uguale a "A" (proveniente dal motore del flusso di lavoro). </li> 
     <li> Segmentazione sui dati "congelati": in qualità di esperto di marketing, vorrei <strong>retargeting</strong> tutti i profili che hanno ottenuto 1000 punti fedeltà dall’ultimo invio o in cui il codice segmento era uguale a "A". </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Reporting dinamico con dati di profilo personalizzati<br /> </td> 
   <td> Questa funzione consente di creare e gestire rapporti basati sui dati di profilo personalizzati creati durante l’estensione della risorsa profilo. Puoi suddividere i rapporti per attributo di profilo, ad esempio programma fedeltà, canale preferito, ecc.<br /> Per ulteriori informazioni, consulta la <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Miglioramenti**

* È stato migliorato l’utilizzo complessivo della memoria e della CPU dell’applicazione

**Altre modifiche**

* L’attività del flusso di lavoro Read Audience può ora leggere tipi di pubblico di Experienci Cloud. In precedenza, questa attività poteva leggere solo i tipi di pubblico Query ed List. Consulta la sezione [documentazione dettagliata](../../automating/using/read-audience.md). (CAMP-23623)
* L&#39;identificatore dell&#39;origine dati condivisa predefinita è ora in modalità di sola lettura e non può più essere modificato. La modifica di questo identificatore potrebbe causare alcuni problemi durante la condivisione di tipi di pubblico con l’Experience Cloud.
* L’importazione di tipi di pubblico da Audience Manager ora funziona con file suddivisi. In precedenza, solo l’ultimo file del segmento veniva importato dal flusso di lavoro tecnico importSharedAudience.
* Gli account esterni AWS S3 ora supportano le aree geografiche e il meccanismo di autenticazione versione 4. Consulta la sezione [documentazione dettagliata](../../administration/using/external-accounts.md).
* La finestra di selezione delle risorse ora si carica più rapidamente e consente di selezionare una risorsa e quindi di uscire dalla finestra senza alcun problema.
* Le proprietà e la struttura dei flussi di lavoro tecnici possono ora essere modificati da utenti con diritti di amministrazione e appartenenti alle unità organizzative e geografiche &quot;All&quot;.
* Sono stati apportati miglioramenti all’interfaccia dell’attività Segmentazione durante la creazione di nuovi segmenti: la scheda Limitazione viene ora visualizzata direttamente dopo l’aggiunta di una limitazione. I nomi dei nuovi segmenti vengono ora incrementati (&quot;Segmento 1&quot;, &quot;Segmento 2&quot;, ecc.).
* Alla risorsa del flusso di lavoro viene aggiunto il campo &quot;nextProcessingDate&quot;. Questo campo è visibile solo tramite chiamate API REST, ti consente di visualizzare i flussi di lavoro per le date di elaborazione successive.
* Il campo &quot;sourceId&quot; è ora esposto nella risorsa dei registri di tracciamento (nms:trackingLog).
* I valori &quot;Totale aperture&quot; e &quot;Totale clic&quot; ora possono essere esportati in un file flat tramite un flusso di lavoro. (CAMP-24186)
* &quot;English - Danmark&quot; è ora disponibile nell’elenco Preferred Languages (Lingue preferite) nei profili. (CAMP-23728)
* Quando si utilizza un’attività di segmentazione con un collegamento Dati aggiuntivi (targetData), ora un messaggio informa che i dati non sono disponibili all’esterno del flusso di lavoro. Questo messaggio viene visualizzato quando si fa clic sul pulsante Count (Conteggio) o Preview (Anteprima) nell’attività Segmentation. (CAMP-23651)
* Sono stati apportati miglioramenti per ottimizzare lo spazio su disco utilizzato dai flussi di lavoro: (CAMP-21979): i file elaborati dall’attività &quot;Load file&quot; ora vengono eliminati per impostazione predefinita. Un’opzione ti consente di conservarli per esigenze specifiche. Quando un flusso di lavoro viene eliminato, la relativa cartella dedicata viene eliminata automaticamente dalla directory del server.

**Patch**

* È stato risolto un problema a causa del quale ad alcuni eventi di reporting non elaborati non erano associati eventi di tracciamento, perché il campo eventDate non era popolato correttamente.
* È stato risolto un problema che impediva la visualizzazione dei campi personalizzati nella finestra di anteprima di una consegna di notifica push.
* È stato risolto un problema che impediva al testo di racchiudere il corpo del messaggio di una notifica push nella finestra di anteprima.
* È stato risolto un problema che si verificava durante l’invio di una consegna ricorrente da un flusso di lavoro quando il target principale era vuoto.
* È stato risolto un problema che impediva l’accesso a una mappatura target se collegata a uno schema inesistente.
* È stato risolto un problema che poteva verificarsi durante l’importazione di un file zip tramite un’attività di caricamento file. (CAMP-24309)
* È stato risolto un problema che causava un errore PostgreSQL durante l’invio di una consegna ricorrente. (CAMP-23613)
* È stato risolto un problema che causava la visualizzazione di un messaggio di errore durante l’invio di una richiesta API REST con un attributo JSON vuoto. (CAMP-23506)
* È stato risolto un problema nei profili che impostava il carattere &quot;ß&quot; in maiuscolo dopo il carattere. (CAMP-23136)
* È stato risolto un problema che si verificava durante l’invio di consegne utilizzate con la condizione di idoneità di personalizzazione o blocco di contenuto dinamico durante l’utilizzo di attributi da uno schema di profilo collegato. (CAMP-22751)
* È stato risolto un problema che impediva l’eliminazione dei servizi. (CAMP-22050)
* È stato risolto un problema che impediva la modifica dei valori di Paese o Stato in un profilo di test. (CAMP-20426)
* È stato risolto un problema che poteva impedire il caricamento di Creative Designer. (CAMP-24573)
* È stato risolto un problema che rimuoveva i caratteri aggiunti dopo i campi di personalizzazione nell’oggetto e-mail. (CAMP-24113)

## Versione 18.4 - Aprile 2018 {#release-18-4---april-2018}

**Patch**

_Piattaforma_

* È stato corretto un errore che poteva impedire la corretta elaborazione delle richieste di accesso o cancellazione RGPD. Questo comportamento è stato osservato in alcuni rari casi in cui i dati estratti contenevano uno dei seguenti caratteri: &amp; &lt; > &quot; &quot;.

_E-mail, messaggi SMS e direct mail_

* È stato risolto un problema che poteva causare la sovrascrittura dei KPI con valori errati se la sincronizzazione del broadlog richiedeva più di un’ora.

_Flussi di lavoro_

* Gestione della memoria migliorata e prestazioni ottimizzate nei flussi di lavoro.

_Reportistica_

* Il flusso di lavoro di condivisione dei KPI ora recupera i valori di consegna per gli ultimi 2 mesi invece degli ultimi 6 mesi. È stato risolto un problema a causa del quale l’account esterno di condivisione KPI mostrava date troncate.
* È stato risolto un problema che poteva causare la mancata considerazione di alcuni messaggi in **Inviato**, **Consegnato** e **Mancato recapito** metriche.
* È stato corretto un errore che si verificava quando l’intervallo di tempo scelto in **Rapporto di riepilogo della consegna** era troppo lungo.

_Risorse personalizzate_

* È stato corretto un errore che impediva la preparazione delle risorse personalizzate.

## Versione 18.3 - Marzo 2018 {#release-18-3---march-2018}

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
   <td> Regolamento generale sulla protezione dei dati (RGPD) dell’UE<br /> </td> 
   <td> Il RGPD è la nuova legge sulla privacy dell’Unione europea (UE) che armonizza e modernizza i requisiti in materia di protezione dei dati, in vigore dal 25 maggio 2018. Il GDPR si applica ai clienti di Adobe Campaign che conservano dati per soggetti che risiedono nell’Unione europea.<br /> Oltre alle funzionalità per la privacy già disponibili in Adobe Campaign (tra cui la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), in qualità di responsabile del trattamento dei dati vogliamo sfruttare l’opportunità di includere funzionalità aggiuntive per aiutarti ad essere pronto a determinate richieste RGPD in qualità di titolare del trattamento dei dati:<br /> 
    <ul> 
     <li> Diritto di accesso: consente all’interessato di ricevere una copia dei suoi dati personali acquisiti dai titolari del trattamento, inclusi potenzialmente i dati memorizzati in Adobe Campaign. </li> 
     <li> Diritto di cancellazione: autorizza l’interessato a richiedere la cancellazione dei suoi dati personali acquisiti dai titolari del trattamento, inclusi potenzialmente i dati memorizzati in Adobe Campaign. </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer per e-mail (Beta)<br /> </td> 
   <td> Il nuovo Creative Designer di Adobe Campaign offre un’esperienza di creazione completamente integrata in Campaign, che consente di creare visivamente in modo rapido e semplice e-mail accattivanti e personalizzate in modo individuale, senza la necessità di scrivere una singola riga di codice. Grazie alla potente interfaccia di trascinamento, Creative Designer permette di ridimensionare la creazione delle e-mail sia che gli utenti inizino da una lavagna vuota, sia che sfruttino frammenti di contenuto o modelli esistenti. <br /> Le funzionalità principali includono:<br /> 
    <ul> 
     <li> Progetta visivamente e crea e-mail completamente personalizzate e reattive tramite un’interfaccia a trascinamento, migliorata dalle integrazioni Creative Cloud native </li> 
     <li> Crea e salva un modello di contenuto e-mail e sfrutta i modelli salvati per ridimensionare la creazione di e-mail </li> 
     <li> Creare e salvare frammenti di contenuto (come intestazione, piè di pagina, articolo, ecc.) per semplificare la creazione di contenuti e garantire la coerenza del brand </li> 
     <li> Passa facilmente dalla creazione nell’interfaccia di trascinamento alla modifica diretta di HTML di un’e-mail con un clic </li> 
    </ul> Creative Designer for Email è disponibile solo in inglese.<br /> Per ulteriori informazioni, consulta <a href="../../designing/using/designing-content-in-adobe-campaign.md">documentazione dettagliata</a> e guarda questo <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">video</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegne push multilingue<br /> </td> 
   <td> La stessa semplice interfaccia multilingue, già esistente sui canali E-mail e SMS, è stata aggiunta al canale push per coinvolgere i clienti indipendentemente dalla lingua preferita.<br /> Questa funzionalità offre una soluzione scalabile e automatica per i clienti che gestiscono campagne push in più aree geografiche e desiderano eseguire il targeting degli utenti nella lingua preferita. Consente di caricare tutte le varianti linguistiche tramite un foglio di calcolo basato su modelli in un’unica consegna push, con un solo clic. Adobe Campaign esegue quindi una segmentazione automatica in base alle preferenze della lingua dell’utente, contribuendo a ridurre le ridondanze semplificando i flussi di lavoro e il reporting.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/creating-a-multilingual-push-notification.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Utilizzo di risorse personalizzate nella messaggistica transazionale<br /> </td> 
   <td> Oltre ai campi predefiniti, la messaggistica transazionale ora consente di utilizzare risorse personalizzate per arricchire il contenuto dei messaggi.<br /> Ad esempio:<br /> 
    <ul> 
     <li> Sfruttare i campi personalizzati come criteri di riconciliazione per far corrispondere un messaggio transazionale a un profilo </li> 
     <li> Sfruttare profili completi, servizi e dati collegati per personalizzare ulteriormente i messaggi transazionali </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Piattaforma_

* È stato risolto un problema che impediva l’esportazione di più di 5000 record da un elenco.
* È stato risolto un problema che si verificava durante l’esportazione dei dati in file denominati con campi di personalizzazione.

_E-mail, messaggi SMS e direct mail_

* È stato risolto un problema che causava il troncamento degli SMS in più parti, perché le dimensioni delle parti venivano calcolate in caratteri anziché in byte.
* È stata aggiunta un’opzione che consente di: **[!UICONTROL Delivered]** o **[!UICONTROL Bounces + Errors]** KPI da aggiornare in tempo reale dopo l’invio. Vengono ricalcolati direttamente dall’SR (Status Report) ricevuto dal provider.
* È stato risolto un problema relativo al widget del calendario nella pianificazione delle consegne.
* È stato risolto un problema di visualizzazione che si verificava all’apertura di una destinazione per la seconda volta in una consegna inviata.
* È stato risolto un problema che causava un messaggio di errore in cui si chiedeva una data di inizio durante la creazione di un modello e-mail con una data di invio ritardata.
* È stato risolto un problema che poteva causare problemi di rendering delle immagini durante la modifica del contenuto di una consegna.
* È stato risolto un problema relativo alle bozze durante la duplicazione di una campagna.
* È stato risolto un problema che causava un messaggio di errore durante l’accesso a un modello di campagna tramite la barra di navigazione, dopo l’aggiunta di una consegna al flusso di lavoro.
* È stato risolto un problema che poteva impedire la selezione automatica del vincitore di un messaggio e-mail di test A/B, impedendone l’invio. Questo comportamento poteva verificarsi se la consegna era in **[!UICONTROL retryInProgress]** stato.
* È stato risolto un problema che poteva causare la visualizzazione di un messaggio di errore durante la riapertura dei parametri di un messaggio e-mail di test A/B.

_Tipi di pubblico e query_

* È stato risolto un problema che impediva l’accesso ai dati e la configurazione di query per i destinatari replicati da Adobe Campaign Classic a Standard.
* È stato risolto un problema che si verificava durante l’utilizzo di un campo di tipo filtro nell’editor delle query, dopo aver utilizzato **Conteggio** o **Anteprima** pulsanti.

_Flussi di lavoro_

* Il **Fatturazione** il flusso di lavoro è stato ottimizzato per migliorare il ritardo nella preparazione della consegna.
* È stato risolto un problema che impediva la visualizzazione dei dati di popolazione in una transizione in uscita durante l’utilizzo di un’attività di consegna ricorrente.
* È stato risolto un problema che impediva la visualizzazione dei record rifiutati in una transizione dopo un **Aggiorna dati** attività.
* È stato risolto un problema che poteva causare il **deliverabilityUpdate** errore del flusso di lavoro tecnico.

_Integrazioni_

* È stato risolto un problema che impediva ai caratteri internazionali di essere inviati correttamente ad Adobe Analytics.
* Ora le risorse dovrebbero essere caricate più rapidamente quando si tenta di inserire un’immagine dalla libreria di risorse Experienci Cloud in un messaggio.
* È stato risolto un problema che poteva impedire, in alcuni casi, la chiusura della finestra di selezione cespite.
* Da un dettaglio dell’origine dati, ora puoi accedere direttamente al flusso di lavoro correlato per verificarne lo stato.
* Ora puoi aggiornare direttamente lo schema Triggers quando definisci o modifichi un evento trigger. Con questa modifica, non è più necessario annullare la pubblicazione del trigger e crearne un altro.

_Messaggi transazionali_

* È stato risolto un errore relativo al modello di messaggio transazionale che si verificava quando la risorsa di consegna veniva estesa.
* È ora possibile eliminare i messaggi transazionali.

## Versione 18.2 - Febbraio 2018 {#release-18-2---february-2018}

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
   <td> Abbonamento: attiva o annulla l’abbonamento a servizi multipli di un elenco di profili<br /> </td> 
   <td> Il <strong>Subscription Services</strong> l’attività del flusso di lavoro ora ti consente di abbonarti o annullare l’abbonamento a più servizi di un elenco di profili. Nel flusso di lavoro, importa un file contenente i profili e, per ciascun profilo, specifica il tipo di operazione e il servizio. Il <strong>Subscription Services</strong> L’attività sarà in grado di utilizzare queste informazioni e gestire dinamicamente tutti i profili, gli abbonamenti e i loro annullamenti, in una sola volta.<br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/subscription-services.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Attività Enrichment: arricchisci i dati in base alle transizioni precedenti<br /> </td> 
   <td> Il nuovo <span class="uicontrol">Arricchimento</span> l’attività del flusso di lavoro ti consente di sfruttare le transizioni in entrata e completare la transizione in uscita con dati aggiuntivi. Se esegui il targeting dei profili, l’attività di arricchimento ti consente di arricchire le informazioni sui profili con dati aggiuntivi non memorizzati nel database (provenienti, ad esempio, da un file importato).<br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/enrichment.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Piattaforma_

* La barra superiore dell’interfaccia di Adobe Campaign è stata aggiornata con il nuovo menu di Experience Cloud.
* È stato risolto un problema che impediva il collegamento a **[!UICONTROL Offers]** nell’elenco a discesa della soluzione.

_E-mail, messaggi SMS e direct mail_

* La fase di preparazione della consegna è stata migliorata per migliorarne le prestazioni.
* Sono stati risolti diversi problemi che potevano causare il danneggiamento dei registri di tracciamento in alcune situazioni di nicchia.
* È stato risolto un problema di aggiornamento della data di contatto che si verificava quando la data di contatto veniva modificata tra la preparazione della consegna e la conferma. Ora, quando modifichi la data di contatto dopo la preparazione, devi preparare nuovamente la consegna prima di poter confermare l’invio. Consulta la [documentazione dettagliata](../../sending/using/preparing-the-send.md).

_Notifiche push_

* È stato corretto un errore che impediva il funzionamento di alcuni campi di personalizzazione nelle notifiche push di iOS.
* È stato corretto un errore a causa del quale le percentuali di clic e apertura venivano visualizzate come 0% nel dashboard delle notifiche push.

_Rapporti_

* È stato corretto un errore a causa del quale in alcuni browser l’elenco dei rapporti risultava vuoto.
* È stato corretto un errore che si verificava in **[!UICONTROL Report sharing]** flusso di lavoro tecnico poco prima del raggiungimento del limite di scadenza.

_Flussi di lavoro_

* È stato risolto un problema che impediva l’accesso alle attività dopo il trascinamento.
* È stato risolto un problema che poteva causare l’ordine delle transizioni di output di una **[!UICONTROL Segmentation]** attività di cambiamento in alcune situazioni.
* È stato corretto un errore che si verificava durante la lettura di un pubblico contenente un campo di enumerazione e che era stato precedentemente salvato da un flusso di lavoro
* È stato risolto un problema che causava la **[!UICONTROL Request confirmation before sending messages]** opzione per rimanere selezionata anche dopo averla deselezionata durante la definizione delle proprietà di pianificazione di una consegna creata in un flusso di lavoro.
* È ora possibile disabilitare la rimozione automatica delle righe duplicate (clausola DISTINCT) in **[!UICONTROL Query]** tramite una nuova opzione disponibile nella sezione **[!UICONTROL Additional data]** scheda. Per motivi di prestazioni, si consiglia di disabilitare questa opzione quando si definiscono molti (più di 100) elementi aggiuntivi.

_Integrazioni_

* Sono stati apportati alcuni miglioramenti al **[!UICONTROL Data sources]** schermata di configurazione.

_Problemi noti_

È consigliabile non utilizzare Internet Explorer versione 11 a causa di possibili problemi di visualizzazione.

Potrebbero verificarsi alcuni problemi quando si utilizzano collegamenti di aiuto contestuali dall’interfaccia di Campaign. Saranno corretti in 18.3.

## Versione 18.1 - Gennaio 2018 {#release-18-1---january-2018}

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
   <td> Reporting per la gestione dell’affaticamento<br /> </td> 
   <td> Il reporting per la gestione dell’affaticamento è un rapporto dedicato e configurabile che mostra l’impatto delle regole di affaticamento sulle consegne nei canali e-mail, push, SMS e direct mailing all’interno di un intervallo di date specificato prima dell’invio. Con la possibilità di visualizzare rapidamente tutte le campagne in conflitto in un’unica schermata, gli esperti di marketing sono in grado di pianificare le campagne di marketing in base a regole di affaticamento impostate in modo più efficace e di assegnare priorità alle comunicazioni.<br /> Per ulteriori informazioni, consulta la <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Condivisione dei rapporti<br /> </td> 
   <td> La condivisione dei rapporti ti consente di condividerli con gli utenti di Adobe Campaign sotto forma di allegato e-mail, anche su base periodica e automatizzata. Gli utenti che ricevono report ricorrenti possono annullare l’abbonamento a queste comunicazioni tramite un collegamento dedicato in ogni e-mail.<br /> Per ulteriori informazioni, consulta la <a href="../../reporting/using/reporting-interface.md#share-tab">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nuove funzionalità push<br /> </td> 
   <td> Anteprima messaggi push - Anteprima di notifiche push su dispositivi iOS e Android dall'editor contenuti notifiche push per visualizzare esattamente ciò che i destinatari vedranno prima di testare o eseguire la consegna.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">documentazione dettagliata</a>.<br /> Contenuto disponibile - Quando non si aprono le app per periodi di tempo prolungati, i loro dati possono non essere più aggiornati. Questo comporta la necessità di aggiornare o sostituire i dati nel momento in cui un utente apre finalmente l’app, il che può causare ritardi nell’utilizzo dell’app. Con il supporto aggiunto di Contenuto disponibile, gli utenti di Adobe Campaign possono riattivare la loro app per aggiornare i dati in background durante la distribuzione di una notifica push, consentendo una maggiore coerenza e un maggiore controllo sull’esperienza in-app di un utente.<br /> Contenuto variabile - Con il supporto aggiunto di Contenuto variabile, gli utenti Adobe Campaign possono ora sfruttare le estensioni della loro app mobile per modificare ulteriormente il contenuto o la presentazione delle notifiche push in arrivo inviate da Adobe Campaign. Ad esempio, gli utenti possono sfruttare Contenuto variabile per: <br /> 
    <ul> 
     <li> decrittografare i dati consegnati in un formato crittografato </li> 
     <li> scaricare immagini o altri file multimediali e aggiungerli come allegati a una notifica </li> 
     <li> modificare il testo del corpo o del titolo di una notifica </li> 
     <li> aggiungere un identificatore di thread a una notifica </li> 
    </ul> Per ulteriori informazioni su Contenuto disponibile e Contenuto variabile, consulta <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">documentazione dettagliata</a>.<br /> <strong>Avvertenza:</strong> questi aggiornamenti sulle notifiche push richiedono ai clienti di aggiornare le loro applicazioni mobili. Fai riferimento a <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/push-payload.html">questa nota tecnica</a> per ulteriori informazioni.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegne ottimizzate in base al fuso orario<br /> </td> 
   <td> Pianifica l’invio di notifiche e-mail, SMS e push ricorrenti in un giorno o in un’ora specifica nel fuso orario di ogni destinatario, per garantire che i messaggi vengano consegnati all’ora giusta senza configurare più consegne. <br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/scheduler.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Attivazione attività segnale API<br /> </td> 
   <td> Ora è possibile attivare un’attività di segnale per i flussi di lavoro direttamente dall’API di Adobe Campaign Standard.<br /> Per ulteriori informazioni, consulta la <a href="/help/api/using/triggering-a-signal-activity.md">documentazione dettagliata</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Piattaforma_

* La ricerca del profilo è stata ottimizzata per migliorarne le prestazioni.
* L’identificatore interno dei gruppi di sicurezza predefiniti è ora in modalità di sola lettura per gli utenti standard.

_E-mail, messaggi SMS e direct mail_

* È stato risolto un problema di visualizzazione che si verificava durante l’inserimento di emoji nel contenuto delle consegne.
* È stato risolto un problema che consentiva all’utente di accedere ai registri di invio quando la consegna era ancora in corso.
* Il **[!UICONTROL Scheduler]** activity (attività) ora consente di inviare le consegne a seconda del fuso orario del destinatario.
* SMS: l’opzione **[!UICONTROL Store incoming MO]** nel database è stato aggiunto ad account esterni. Se questa opzione è selezionata, tutti gli SMS in entrata verranno archiviati in **inSMS** tabella.
* SMS: i servizi sono ora collegati a un evento invece che a un modello transazionale.
* SMS: il timeout predefinito della connessione SMTP è stato ridotto a 30 secondi.

_Notifiche push_

* È stato corretto un errore che impediva l’interruzione delle consegne delle notifiche push.
* È stata aggiunta un’opzione nelle opzioni avanzate per le notifiche push per riattivare l’applicazione con una notifica push.
* È stato aggiunto un pulsante di pausa per il video di anteprima della notifica push.
* L’anteprima della notifica push è ora disponibile per diversi dispositivi come iPhone, Android e tablet.

_Rapporti_

* È stato corretto un errore che causava la visualizzazione di percentuali superiori al 100%.
* È stato risolto un problema che impediva agli utenti di scaricare i rapporti in CSV.
* È stato aggiunto un nuovo **[!UICONTROL Report]** nella home page.

_Flussi di lavoro_

* È stato risolto un problema che causava un messaggio di errore durante l’utilizzo di dati aggiuntivi in una query e l’aggiunta di alias contenenti spazi. I caratteri non alfanumerici sono ora sostituiti da &quot;_&quot;.
* È stato risolto un problema a causa del quale il flusso di lavoro tecnico che calcolava i KPI poteva essere interrotto per impostazione predefinita in alcuni casi.

_Profili e pubblico_

* È stato corretto un errore che si verificava durante l’aggiunta di più filtri nella query di un pubblico.
* È stato risolto un problema che si verificava durante la modifica dell’immagine di un profilo.
* È stata aggiunta una descrizione comando che mostra il numero esatto di risultati dopo il conteggio della popolazione di una query.
* È stato risolto un problema che poteva impedire a un utente di selezionare un pubblico o di chiudere la finestra del selettore del pubblico.
* L’elenco delle funzioni disponibili nell’editor espressioni è stato aggiornato. Il **FormatoValuta** e **ConvertCurrency** funzioni sono state rimosse.
