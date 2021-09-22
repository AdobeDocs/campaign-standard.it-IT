---
title: Note sulla versione 2018
description: In questa pagina sono elencate tutte le versioni del 2018 di Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: 17521357-14ae-4751-bd7c-aeabbcf71d07
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '5403'
ht-degree: 6%

---

# Note sulla versione 2018{#release-notes}

Stai cercando una versione specifica 2018 di Adobe Campaign Standard?

Ogni versione include nuove funzioni e patch. Fai clic su una versione per visualizzarne il contenuto.

Visualizza gli ultimi [aggiornamenti della documentazione](../../rn/using/documentation-updates.md) per Adobe Campaign Standard. Se cerchi una versione più recente, consulta questa [pagina](../../rn/using/release-notes.md).

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
   <td> Messaggistica in-app (beta)<br /> </td> 
   <td> La messaggistica in-app consente di coinvolgere in modo più efficace gli utenti di app mobili tramite interazione contestuale e la possibilità di raggiungere gli utenti che hanno disattivato le notifiche push. Puoi utilizzare i messaggi in-app insieme alle notifiche push per creare un’esperienza altamente personalizzata e pertinente. Questo migliora la conversione e la fidelizzazione degli utenti dell’app.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/about-in-app-messaging.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrazione di Adobe Launch per le app mobili (beta)<br /> </td> 
   <td> L’integrazione di Adobe Launch con Adobe Campaign semplifica e automatizza il processo di attivazione della proprietà dell’app mobile in Campaign utilizzando l’SDK mobile V5.<br /> Per ulteriori informazioni, consulta la <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Miglioramenti**

* Adobe Campaign Standard ora supporta la versione 4 dell’API Amazon S3.

**Altre modifiche**

* Nei registri di trasmissione, esiste ora una distinzione tra il numero massimo di connessioni e il numero massimo di messaggi all’ora. Una volta raggiunti i limiti, è possibile sapere perché la velocità effettiva è limitata. Precedentemente, lo stesso messaggio (&quot;quota soddisfatta&quot;) si applicava a entrambi i casi.
* Durante la configurazione di un’app mobile in Campaign, l’utente ora può sapere se il certificato iOS e la chiave del server Android sono stati caricati correttamente e la relativa data di scadenza.

   Per ulteriori informazioni, consulta la documentazione dettagliata su come configurare un’app mobile utilizzando [SDK V4](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html) e [SDK V5](https://docs.adobe.com/content/help/it-IT/campaign-standard/using/administrating/configuring-channels/configuring-a-mobile-application.html).

* Puoi indirizzare l’attività agli utenti su una specifica app mobile selezionando un’app mobile mentre definisci le proprietà della campagna. Questa funzione è per i canali di messaggistica push e in-app.

   Per ulteriori informazioni, consulta la [documentazione dettagliata](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Quando si seleziona un blocco di contenuto tramite l’interfaccia di Creative Designer, tutti i blocchi di contenuto dall’elenco vengono ora caricati e visualizzati. (CAMP-27311)

   Per ulteriori informazioni, consulta la [documentazione dettagliata](../../designing/using/personalization.md#adding-a-content-block).

**Patch**

* È stato risolto un problema che mostrava una discrepanza nei conteggi dei registri tra il dashboard e-mail e il rapporto di riepilogo e-mail per le e-mail transazionali. (CAMP-28237
* È stato risolto un problema nei flussi di lavoro che poteva visualizzare un messaggio di errore durante l’importazione di un file tramite un’attività di trasferimento file . (CAMP-27435)
* È stato risolto un problema relativo alle pagine di destinazione contenenti più di 25 servizi che causava la deselezione casuale dei servizi nel modulo. (CAMP-26572)
* È stato risolto un problema nei flussi di lavoro che impediva la configurazione di account esterni con un URL SFTP durante l’utilizzo dell’attività File transfer. (CAMP-26475)
* È stato risolto un problema che impediva l’aggiornamento del rapporto di riepilogo dei servizi. (CAMP-26301)
* È stato risolto un problema nei flussi di lavoro che impediva a un campo personalizzato di visualizzare la data corretta durante l’utilizzo di un’attività Arricchimento . (CAMP-26242)
* È stato risolto un problema che impediva l’aggiornamento delle date di abbonamento al servizio in caso di importazione tramite un’importazione di file.
* È stato corretto un errore nell’attività di caricamento file che impediva ai flussi di lavoro di importare file (CAMP-27068).
* È stato risolto un problema che causava la visualizzazione di un numero errato di sottoscrizioni nei rapporti di riepilogo del servizio (CAMP-25587).
* È stato risolto un problema di discrepanza di dati tra i rapporti Adobe Analytics e Adobe Campaign. (CAMP-25393)
* È stato risolto un problema che poteva impedire l’accesso a un utente con accesso limitato. (CAMP-27381)
* È stato risolto un problema che poteva impedire la visualizzazione dell’elenco dei contenuti di Adobe Experience Manager durante la modifica di un’e-mail tramite Creative Designer. (CAMP-27181)
* È stato risolto un problema che poteva impedire l’apertura di Creative Designer, causando un errore. (CAMP-27304)
* È stato risolto un problema che impediva il corretto funzionamento del trascinamento in Creative Designer quando si utilizzava Internet Explorer 11.
* È stato risolto un problema che causava la visualizzazione delle immagini caricate da una fotocamera e scattate in modalità verticale in una posizione ruotata indesiderata.
* È stato risolto un problema che visualizzava informazioni di selezione non chiare quando si utilizzava l’interfaccia dell’editor delle query in Creative Designer.
* È stato risolto un problema che impediva la corretta duplicazione di un elemento quando si utilizzava l’interfaccia dell’editor delle query in Creative Designer.
* È stato risolto un problema che continuava a inviare messaggi SMS ai destinatari al elenco Bloccati, anche se l’abbonamento era stato annullato tramite una risposta automatica. (CAMP-27128)
* È stato risolto un problema che impediva la visualizzazione degli errori che causavano errori nel flusso di lavoro **Pulizia database**. (CAMP-26876)
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
   <td> Flag ad alta priorità per le notifiche push Android<br /> </td> 
   <td> Flag ad alta priorità per Android - Abilita la consegna di una notifica push con priorità elevata per le app Android che fa sì che il dispositivo in attesa si riattivi ed esegua un'elaborazione limitata. La priorità predefinita è Normale, che può ritardare la consegna del messaggio per salvare la batteria. <br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Filtro della tipologia per gli abbonati alle app mobili<br /> </td> 
   <td> Supporto delle sottoscrizioni nel filtro della tipologia : quando si specificano i criteri di filtro per una regola di tipologia, le sottoscrizioni di applicazione possono essere selezionate come dimensioni di filtro e targeting, fornendo la possibilità di filtrare gli attributi per gli utenti con o senza un profilo. <br /> Per ulteriori informazioni, consulta la <a href="../../sending/using/about-typology-rules.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importazione automatica dei contenuti da un URL durante la preparazione dei messaggi<br /> </td> 
   <td> È ora possibile importare contenuti e-mail da un URL durante la fase di preparazione. Per le consegne ricorrenti di e-mail, il contenuto HTML più recente viene recuperato ogni volta che il messaggio viene preparato assicurando che il contenuto sia sempre aggiornato al momento dell’invio dell’e-mail. Questa funzione ti consente inoltre di creare una consegna pianificata con contenuto da un URL anche se il contenuto non è ancora pronto.<br /> Per ulteriori informazioni, consulta la <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Messaggio di notifica della versione di Campaign<br /> </td> 
   <td> Ora viene visualizzato un messaggio a comparsa quando un utente effettua l’accesso dopo l’aggiornamento dell’istanza a una nuova versione. Il messaggio indica il numero di versione e include un collegamento alle note sulla versione. Puoi scegliere di nascondere il messaggio fino alla versione successiva. <br /> </td> 
  </tr> 
  <tr> 
   <td> Gestione utente<br /> </td> 
   <td> A partire dalla versione 18.7, la funzionalità dell’unità geografica non è più disponibile per le nuove istanze di Campaign Standard, così come per le istanze esistenti prive di unità geografiche.<br /><a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=it#"> Per ulteriori informazioni, consulta questa pagina</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Miglioramenti**

* L’integrazione di Adobe Campaign e Adobe Target ora consente di sfruttare la funzione [Autorizzazioni](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html) di Target. Quando includi un’immagine dinamica da Adobe Target in un messaggio e-mail, ora puoi specificare una proprietà Target (codice at_property).
* Le risorse personalizzate che dispongono di un collegamento di copia alla risorsa dei profili vengono ora prese in considerazione dalle richieste di accesso/eliminazione relative alla privacy RGPD. Per 1 collegamenti semplici cardinalità e N collegamenti di raccolta cardinalità, è necessario selezionare &quot;Eliminazione/Duplicazione del record di destinazione implica l&#39;eliminazione/duplicazione dei record a cui fa riferimento il collegamento&quot; nella risorsa personalizzata. Per i collegamenti semplici con 0 o 1 cardinalità, selezionare &quot;Eliminazione/duplicazione del record implica l&#39;eliminazione/duplicazione del record di destinazione a cui fa riferimento il collegamento&quot;.

**Altre modifiche**

* Il timeout di condivisione dei rapporti è stato aumentato da uno a quattro minuti per evitare errori di timeout.
* Quando si modifica il contenuto di un’e-mail, per impostazione predefinita viene aperto il nuovo Creative Designer. Se lo desideri, puoi comunque tornare all’editor di contenuti predefinito in qualsiasi momento dopo aver salvato le modifiche. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../designing/using/designing-content-in-adobe-campaign.md).
* In Creative Designer è ora possibile aggiungere un nuovo componente di contenuto in un messaggio e-mail: il carosello. Per ulteriori informazioni, consulta la [documentazione dettagliata](../../designing/using/designing-from-scratch.md#about-content-components).
* In un rapporto sui clic con il pulsante di scelta rapida di un messaggio sulle transazioni, quando fai clic sul pulsante **Cambia profilo** , vengono elencati solo i profili di test collegati all’evento definito per il messaggio sulle transazioni.

**Patch**

* È stato risolto un problema relativo al filtro di query byEmail che non restituiva alcun risultato. (CAMP-23420)
* È stato risolto un problema che consentiva a un utente standard di accedere a determinate funzioni o schermate limitate agli amministratori (/rest/head/* endpoint, schermate di messaggistica transazionale, profili e schermate di importazione di tipi di pubblico).
* È stato risolto un problema che impediva alle richieste di cancellazione RGPD di elaborare risorse personalizzate se il loro nome era iniziato da un numero.
* È stato corretto un errore che impediva all’attività Save Audience di condividere gli abbonati alle applicazioni in Adobe Experience Cloud.
* È stato risolto un problema relativo all’attività Trasferimento file che poteva verificarsi quando il nome del file conteneva spazi vuoti. (CAMP-25936)
* È stato risolto un problema che poteva verificarsi quando si utilizzava il pulsante di riconnessione dopo la scadenza di una sessione. (CAMP-25560)
* È stato risolto un problema che poteva causare esclusioni durante l’invio di consegne con ottimizzazione del fuso orario associata alle regole di affaticamento. (CAMP-25425)
* È stato risolto un problema che poteva impedire l’eliminazione di dati con un collegamento di tipo 0-1 durante l’utilizzo della funzione RGPD API.
* È stato risolto un problema che poteva causare un messaggio di errore durante l’annullamento della modifica di una regola di tipologia di affaticamento.
* È stato risolto un problema che poteva verificarsi durante l’anteprima di un contenuto di consegna dopo la modifica.
* È stato risolto un problema che poteva verificarsi durante l’elaborazione di file zip CSV durante l’utilizzo dell’opzione Decompressione .
* È stato risolto un problema in Creative Designer a causa del quale il font e la formattazione del colore non desiderati venivano modificati quando si cambiava del testo con lo stile incorporato in un collegamento o quando si modificava tale collegamento. (CAMP-26001)
* È stato risolto un problema che impediva al rapporto sugli hot click di visualizzare le percentuali di ciascuna condizione nelle consegne contenenti contenuto dinamico. In precedenza venivano visualizzati solo i clic sulla variante predefinita.

## Versione 18.6 - Giugno 2018 {#release-18-6---june-2018}

**Miglioramenti**

* L’ API **[!UICONTROL History]** è stata aggiunta a Adobe.IO. Ti consente di accedere alle informazioni relative alla cronologia di marketing di un profilo: numero di punti di contatto, consegne inviate, URL della pagina speculare, ecc. Per ulteriori informazioni, consulta il [caso d’uso dedicato](../../api/using/interacting-with-marketing-history.md) .
* Il flusso di lavoro tecnico **[!UICONTROL Database cleanup]** è stato ottimizzato per garantire prestazioni migliori per il backup del database.
* Creative Designer per e-mail è ora disponibile anche in francese e tedesco.

**Altre modifiche**

* Nella finestra **[!UICONTROL Deployment]** delle consegne inviate è stato aggiunto un pulsante **[!UICONTROL Compute stats]** . Ti consente di recuperare i KPI più recenti, ad esempio se i risultati dell’invio richiedono troppo tempo per essere aggiornati o se non sono stati presi in considerazione. Per ulteriori informazioni, consulta questa [sezione](../../sending/using/confirming-the-send.md).
* Nel flusso di lavoro tecnico preconfigurato **Aggiorna per recapito** , gli amministratori funzionali possono ora definire il numero di errori consecutivi da ignorare nell&#39;attività javascript **Aggiorna regole** . Per impostazione predefinita, il valore del campo è impostato su 0, il che significa che tutti gli errori verranno ignorati.
* L&#39;SQL generato durante la gestione delle condizioni di restrizione dell&#39;accesso all&#39;unità è stato ottimizzato.
* L’attività **[!UICONTROL Update]** ora ti consente di aggiungere, aggiornare o eliminare dati relativi alle sottoscrizioni (tabella nms:appSubscriptionRcp).
* Il flusso di lavoro tecnico **[!UICONTROL Update delivery execution]** è stato suddiviso in due flussi di lavoro per ottimizzare le prestazioni: - **[!UICONTROL Update delivery execution]**: aggiorna il tracciamento della consegna. Per impostazione predefinita viene avviato ogni 10 minuti. **[!UICONTROL Update delivery indicators]**: aggiorna i KPI della consegna, che vengono avviati ogni ora per impostazione predefinita. Per ulteriori informazioni sui flussi di lavoro tecnici, consulta questa [sezione](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* Quando una consegna invia messaggi, lo stato della sezione **[!UICONTROL Deployment]** può ora avere due valori: **[!UICONTROL Sending]**: i messaggi vengono inviati. **[!UICONTROL Sending (retry)]**: è in corso un nuovo passaggio.
* Gli utenti con il ruolo **[!UICONTROL Delivery preparation]** possono ora inviare bozze. (CAMP-24313)
* L’opzione **Abilita TLS su SMPP** è stata aggiunta al routing **SMS tramite l’account esterno SMPP**. Per ulteriori informazioni, consulta questa [sezione](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

**Patch**

* È stato risolto un problema che poteva impedire l’invio di e-mail quando includeva un’immagine dinamica da Adobe Target (CAMP-24848).
* È stato risolto un problema relativo ai flussi di lavoro tecnici **[!UICONTROL Privacy Access/Delete Request]** che non veniva completato se una delle richieste non andava a buon fine.
* È stato risolto un problema che impediva al servizio core Privacy di ricevere gli aggiornamenti sullo stato della richiesta da Campaign.
* È stato risolto un problema che impediva il corretto funzionamento del flusso di lavoro tecnico **[!UICONTROL Import shared audience]** (CAMP-25465).
* È stato risolto un problema che impediva alle richieste di privacy Campaign di essere contrassegnate come completate in Core Privacy Service.
* È stato risolto un problema che poteva impedire ad alcuni utenti di accedere ad Campaign Standard tramite l’autenticazione IMS quando Adobe ID era troppo lungo. (CAMP-24095)
* È stato risolto un problema in Creative Designer che poteva verificarsi durante la rimozione dei moduli di contenuto. (CAMP-25242)
* È stato risolto un problema che si verificava durante l’utilizzo delle regole di affaticamento delle notifiche push per gli abbonati privi di profilo nel database. (CAMP-25344)
* È stato risolto un problema che poteva visualizzare un messaggio di errore durante l’accesso ai registri di esclusione delle consegne. (CAMP-24724)
* È stato risolto un problema che impediva la preparazione delle bozze nelle istanze con registri di invio estesi.
* Sono stati risolti due problemi che potevano verificarsi durante la pubblicazione di risorse personalizzate con l’estensione **[!UICONTROL Sending log]** attivata.
* È stato risolto un problema che poteva verificarsi quando la durata della consegna non veniva presa in considerazione nelle consegne ricorrenti.
* È stato risolto un problema che poteva verificarsi durante l’ordinamento dei dati nel menu **[!UICONTROL Client data]** per risorse personalizzate con più di 100.000 record. (CAMP-24308)
* È stato risolto un problema relativo alle dimensioni di profilo personalizzate che non venivano prese in considerazione quando si utilizzava la funzione di ricerca nei report dinamici .
* È stato risolto un problema relativo alla visualizzazione dei dati internazionali per i livelli Account nei report dinamici .
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
   <td> RGPD: Integrazione del servizio core<br /> </td> 
   <td> L’integrazione dei servizi core per la privacy consente di automatizzare le richieste RGPD in un contesto con più soluzioni tramite una singola chiamata API JSON. <br /> Le richieste RGPD inviate dal servizio core Privacy a tutte le soluzioni Experience Cloud ora vengono gestite automaticamente da Campaign. <br /> Per ulteriori informazioni, consulta la <a href="https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=it">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Miglioramenti push - feedback dettagliato sulla consegna<br /> </td> 
   <td> Adobe Campaign ora offre la possibilità di ricevere feedback dettagliati (registri di invio e registri di esclusione) sui messaggi push dai provider (APNS/GCM) tramite MCPNS.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Estensione dei registri di consegna<br /> </td> 
   <td> L’estensione dei registri di consegna ti consente di estendere i registri di invio con i dati di profilo e il codice dei segmenti provenienti dai flussi di lavoro. Queste informazioni possono quindi essere utilizzate nei rapporti dinamici e consentono di conservare un’istantanea di alcune informazioni al momento dell’invio di una consegna.<br /> Ci sono altri 2 casi d’uso :<br /> 
    <ul> 
     <li> Esporta i log di trasmissione estesi con dati "congelati": In qualità di addetto al marketing, vorrei esportare tutti i profili in cui il codice del segmento è uguale a "A" (proveniente dal motore del flusso di lavoro). </li> 
     <li> Segmentazione dei dati "congelati": In qualità di addetto al marketing, vorrei <strong>effettuare il retargeting</strong> per tutti i profili che hanno vinto 1000 punti fedeltà dall’ultimo invio o in cui il codice del segmento era uguale a "A". </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Reporting dinamico con dati di profilo personalizzati<br /> </td> 
   <td> Questa funzione ti consente di creare e gestire rapporti basati sui dati di profilo personalizzati creati durante l’estensione della risorsa profilo. Puoi suddividere i rapporti per attributo di profilo, ad esempio programma fedeltà, canale preferito, ecc.<br /> Per ulteriori informazioni, consulta la <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Miglioramenti**

* È stato migliorato l’utilizzo complessivo della memoria e della CPU dell’applicazione

**Altre modifiche**

* L’attività del flusso di lavoro Read audience può ora leggere i tipi di pubblico di Experience Cloud. In precedenza, questa attività poteva leggere solo i tipi di pubblico Query ed Elenco . Fare riferimento alla [documentazione dettagliata](../../automating/using/read-audience.md). (CAMP-23623)
* L&#39;identificatore dell&#39;origine dati condivisa predefinita è ora in modalità di sola lettura e non può più essere modificato. La modifica di questo identificatore potrebbe causare alcuni problemi durante la condivisione di tipi di pubblico con l’Experience Cloud.
* L’importazione di tipi di pubblico da Audience Manager ora funziona con file suddivisi. In precedenza, solo l’ultimo file del segmento veniva importato dal flusso di lavoro tecnico importSharedAudience .
* Gli account esterni AWS S3 ora supportano le aree geografiche e il meccanismo di autenticazione versione 4. Fare riferimento alla [documentazione dettagliata](../../administration/using/external-accounts.md).
* La finestra di selezione delle risorse dovrebbe ora essere caricata più velocemente e consentire di selezionare una risorsa e quindi uscire dalla finestra senza alcun problema.
* Le proprietà e la struttura dei flussi di lavoro tecnici possono ora essere modificati dagli utenti con diritti di amministrazione e appartenenti alle unità organizzative e geografiche &quot;All&quot;.
* Sono stati apportati miglioramenti nell’interfaccia dell’attività Segmentazione durante la creazione di nuovi segmenti: La scheda Limitazione ora viene visualizzata direttamente dopo l’aggiunta di un limite. I nomi dei nuovi segmenti vengono ora incrementati (&quot;Segmento 1&quot;, &quot;Segmento 2&quot;, ecc.).
* Alla risorsa Workflow viene aggiunto un campo &quot;nextProcessingDate&quot;. Questo campo è visibile solo tramite le chiamate API REST e consente di visualizzare i flussi di lavoro nelle date di elaborazione successive.
* Il campo &quot;sourceId&quot; è ora esposto nella risorsa dei registri di tracciamento (nms:trackingLog).
* I valori &quot;Aperture totali&quot; e &quot;Clic totale&quot; ora possono essere esportati in un file flat tramite un flusso di lavoro. (CAMP-24186)
* &quot;English - Danmark&quot; è ora disponibile nell’elenco delle lingue preferite nei profili. (CAMP-23728)
* Quando utilizzi un’attività di segmentazione con un collegamento Dati aggiuntivi (targetData), ora un messaggio ti informa che i dati non sono disponibili all’esterno del flusso di lavoro. Questo messaggio viene visualizzato quando si fa clic sul pulsante Conteggio o Anteprima dall’attività Segmentazione. (CAMP-23651)
* Sono stati apportati miglioramenti per ottimizzare lo spazio su disco utilizzato dai flussi di lavoro: (CAMP-21979): I file elaborati dall’attività &quot;Load file&quot; vengono ora eliminati per impostazione predefinita. Un’opzione ti consente di mantenerli per esigenze specifiche. Quando un flusso di lavoro viene eliminato, la relativa cartella dedicata viene automaticamente eliminata dalla directory del server.

**Patch**

* È stato risolto un problema a causa del quale alcuni eventi di reporting non elaborati non presentavano eventi di tracciamento associati perché il campo eventDate non veniva popolato correttamente.
* È stato risolto un problema che impediva la visualizzazione di campi personalizzati nella finestra di anteprima di una consegna di notifiche push.
* È stato risolto un problema che impediva al testo di includere a capo automatico il corpo del messaggio di una notifica push nella finestra di anteprima.
* È stato risolto un problema che si verificava durante l’invio di una consegna ricorrente da un flusso di lavoro se la destinazione principale era vuota.
* È stato risolto un problema che impediva l&#39;accesso a una mappatura di destinazione se collegata a uno schema inesistente.
* È stato risolto un problema che poteva verificarsi durante l’importazione di un file zip tramite un’attività di caricamento file . (CAMP-24309)
* È stato risolto un problema che causava un errore PostgreSQL durante l’invio di una consegna ricorrente. (CAMP-23613)
* È stato risolto un problema che causava la visualizzazione di un messaggio di errore durante l’invio di una richiesta API REST con un attributo JSON vuoto. (CAMP-23506)
* È stato risolto un problema nei profili impostati in maiuscolo per i caratteri che seguono il carattere &quot;ß&quot;. (CAMP-23136)
* È stato risolto un problema che si verificava durante l’invio di consegne utilizzate con la condizione di idoneità di personalizzazione o blocchi di contenuto dinamici durante l’utilizzo di attributi da uno schema di profilo collegato. (CAMP-22751)
* È stato risolto un problema che impediva l’eliminazione dei servizi. (CAMP-22050)
* È stato risolto un problema che impediva la modifica dei valori Paese o Stato in un profilo di test. (CAMP-20426)
* È stato risolto un problema che poteva impedire il caricamento di Creative Designer. (CAMP-24573)
* È stato risolto un problema che rimuoveva i caratteri aggiunti dopo i campi di personalizzazione nell’oggetto e-mail. (CAMP-24113)

## Versione 18.4 - Aprile 2018 {#release-18-4---april-2018}

**Patch**

_Piattaforma_

* È stato corretto un errore che poteva impedire la corretta elaborazione delle richieste di accesso o di cancellazione RGPD. Questo comportamento è stato osservato in alcuni rari casi in cui i dati estratti contenevano uno dei seguenti caratteri: &amp; &lt; > &quot; &#39;.

_E-mail, messaggi SMS e direct mail_

* È stato risolto un problema che poteva causare la sovrascrittura dei KPI con valori errati se la sincronizzazione del registro di trasmissione richiedeva più di un&#39;ora.

_Flussi di lavoro_

* Gestione della memoria migliorata e prestazioni ottimizzate nei flussi di lavoro.

_Generazione rapporti_

* Il flusso di lavoro di condivisione KPI ora recupera i valori di consegna per gli ultimi 2 mesi anziché per gli ultimi 6 mesi. È stato risolto un problema a causa del quale l’account esterno per la condivisione di KPI (Key Performance Indicator) mostrava le date troncate.
* È stato risolto un problema che poteva causare la mancata considerazione di alcuni messaggi nelle metriche **Inviato**, **Consegnato** e **Rimbalzo**.
* È stato corretto un errore che si verificava quando l’intervallo di tempo scelto nel **Rapporto di riepilogo consegne** era troppo lungo.

_Risorse personalizzate_

* È stato corretto un errore che impediva la preparazione personalizzata delle risorse.

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
   <td> Regolamento generale UE sulla protezione dei dati (RGPD)<br /> </td> 
   <td> Il RGPD è la nuova legge sulla privacy dell’Unione europea (UE) che armonizza e modernizza i requisiti in materia di protezione dei dati in vigore dal 25 maggio 2018. Il GDPR si applica ai clienti di Adobe Campaign che conservano dati per soggetti che risiedono nell’Unione europea.<br /> Oltre alle funzionalità per la privacy già disponibili in Adobe Campaign (tra cui la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), stiamo sfruttando questa opportunità nel nostro ruolo di Incaricato del trattamento dei dati per includere funzionalità aggiuntive, per aiutarti a essere pronto come Titolare del trattamento dei dati per alcune richieste RGPD:<br /> 
    <ul> 
     <li> Diritto di accesso: consente all’interessato di ricevere una copia dei propri dati personali acquisiti dai Titolari del trattamento dei dati, che potrebbero includere i dati archiviati in Adobe Campaign. </li> 
     <li> Diritto di cancellazione: concede all’interessato il diritto di cancellare i propri dati personali acquisiti dai Titolari del trattamento dei dati, potenzialmente inclusi i dati archiviati in Adobe Campaign. </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer per e-mail (Beta)<br /> </td> 
   <td> Il nuovo Creative Designer di Adobe Campaign offre un’esperienza di creazione completamente integrata in Campaign, consentendo di creare visivamente in modo rapido e semplice e-mail accattivanti e personalizzate in modo individuale senza la necessità di scrivere una singola riga di codice. Tramite la sua potente interfaccia di trascinamento, Creative Designer consente di ridimensionare la creazione delle e-mail, sia che gli utenti partano da una tabula rasa, sia che sfruttino i frammenti di contenuto o i modelli esistenti. <br /> Le funzionalità principali includono:<br /> 
    <ul> 
     <li> Progetta visivamente e crea e-mail completamente personalizzate e reattive tramite un’interfaccia a trascinamento, ottimizzata dalle integrazioni native di Creative Cloud </li> 
     <li> Crea e salva un modello di contenuto e-mail e sfrutta i modelli salvati per scalare la creazione di e-mail </li> 
     <li> Creazione e salvataggio di frammenti di contenuto (come intestazione, piè di pagina, articolo, ecc.) per semplificare la creazione dei contenuti e garantire la coerenza del brand </li> 
     <li> Passa facilmente dalla creazione nell’interfaccia di trascinamento alla modifica diretta dell’HTML di un messaggio e-mail con un clic </li> 
    </ul> Creative Designer for Email è disponibile solo in inglese.<br /> Per ulteriori informazioni, consulta la  <a href="../../designing/using/designing-content-in-adobe-campaign.md">documentazione </a> dettagliata e guarda questo  <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">video</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegne push multilingue<br /> </td> 
   <td> Al canale push è stata aggiunta la stessa semplice interfaccia multilingue, già presente sui canali e-mail e SMS, che consente di coinvolgere i clienti indipendentemente dalla loro lingua preferita.<br /> Questa funzionalità offre una soluzione scalabile e automatica per i clienti che gestiscono campagne push su più aree geografiche e desiderano eseguire il targeting degli utenti nella lingua preferita. Ti consente di caricare tutte le varianti linguistiche tramite un foglio di calcolo templato in una singola consegna push, con un solo clic. Adobe Campaign esegue quindi una segmentazione automatica in base alle preferenze linguistiche degli utenti, contribuendo a ridurre le ridondanze semplificando i flussi di lavoro e le attività di reporting.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/creating-a-multilingual-push-notification.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Utilizzo delle risorse personalizzate nella messaggistica transazionale<br /> </td> 
   <td> Oltre ai campi predefiniti, la messaggistica transazionale ora consente di utilizzare risorse personalizzate per arricchire il contenuto dei messaggi.<br /> Ad esempio:<br /> 
    <ul> 
     <li> Utilizza campi personalizzati come criterio di riconciliazione per far corrispondere un messaggio sulle transazioni a un profilo </li> 
     <li> Sfrutta profili completi, servizi e dati collegati per personalizzare ulteriormente i messaggi transazionali </li> 
    </ul> Per ulteriori informazioni, consulta la <a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Piattaforma_

* È stato risolto un problema che impediva l’esportazione di più di 5000 record da un elenco.
* È stato risolto un problema che si verificava durante l’esportazione dei dati in file denominati con campi di personalizzazione.

_E-mail, messaggi SMS e direct mail_

* È stato risolto un problema che causava il troncamento dell’SMS in più parti perché le dimensioni delle parti venivano calcolate in caratteri anziché in byte.
* È stata aggiunta un’opzione che consente di aggiornare i KPI **[!UICONTROL Delivered]** o **[!UICONTROL Bounces + Errors]** in tempo reale dopo l’invio. Vengono ricalcolati direttamente dall’SR (Status Report) ricevuto dal provider.
* È stato risolto un problema relativo al widget del calendario nell’utilità di pianificazione della consegna.
* È stato risolto un problema di visualizzazione che si verificava all’apertura di una destinazione per una seconda volta in una consegna inviata.
* È stato risolto un problema che causava la richiesta di una data di inizio da parte di un messaggio di errore durante la creazione di un modello e-mail con una data di invio ritardata.
* È stato risolto un problema che poteva causare problemi di rendering delle immagini durante la modifica del contenuto di una consegna.
* È stato risolto un problema relativo alle bozze durante la duplicazione di una campagna.
* È stato risolto un problema che causava un messaggio di errore durante l’accesso a un modello di campagna tramite la barra di navigazione, dopo l’aggiunta di una consegna al flusso di lavoro.
* È stato risolto un problema che poteva impedire la selezione automatica del vincitore di un’e-mail per test A/B, causando l’assenza dell’invio dell’e-mail. Questo comportamento potrebbe verificarsi se la consegna è in stato **[!UICONTROL retryInProgress]**.
* È stato risolto un problema che poteva causare la visualizzazione di un messaggio di errore durante la riapertura dei parametri di un messaggio e-mail per test A/B.

_Tipi di pubblico e query_

* È stato risolto un problema che impediva l’accesso ai dati e l’impostazione di query per i destinatari replicati da Adobe Campaign Classic a Standard.
* È stato risolto un problema che si verificava durante l’utilizzo di un campo del tipo di filtro nell’editor delle query, dopo aver utilizzato i pulsanti **Count** o **Preview** .

_Flussi di lavoro_

* Il flusso di lavoro **Billing** è stato ottimizzato per migliorare il ritardo nella preparazione della consegna.
* È stato risolto un problema che impediva la visualizzazione dei dati sulla popolazione in una transizione in uscita durante l’utilizzo di un’attività di consegna ricorrente .
* È stato risolto un problema che impediva la visualizzazione dei record rifiutati in una transizione dopo un&#39;attività **Update data** .
* È stato risolto un problema che poteva causare il mancato funzionamento del flusso di lavoro tecnico **deliverabilityUpdate** .

_Integrazioni_

* È stato risolto un problema che impediva l’invio corretto dei caratteri internazionali ad Adobe Analytics.
* Le risorse ora devono essere caricate più velocemente quando si tenta di inserire un’immagine dalla libreria delle risorse di Experience Cloud in un messaggio.
* È stato risolto un problema che in alcuni casi impediva la chiusura della finestra di selezione delle risorse.
* Da un dettaglio dell’origine dati, ora puoi accedere direttamente al relativo flusso di lavoro per controllare lo stato del flusso di lavoro.
* Ora puoi aggiornare lo schema Triggers direttamente quando definisci o modifichi un evento trigger. Con questa modifica, non dovrai più annullare la pubblicazione del trigger e crearne un altro.

_Messaggi transazionali_

* È stato corretto un errore relativo al modello di messaggio transazionale quando la risorsa di consegna veniva estesa.
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
   <td> Abbonamento: sottoscrivi o annulla l’abbonamento a più servizi di un elenco di profili<br /> </td> 
   <td> L’attività del flusso di lavoro <strong>Subscription Services</strong> ti consente ora di abbonarti o annullare l’abbonamento di un elenco di profili a più servizi. Nel flusso di lavoro, importa un file contenente i profili e, per ciascun profilo, il tipo di operazione e il servizio. L'attività <strong>Subscription Services</strong> sarà in grado di utilizzare queste informazioni e gestire dinamicamente tutti gli abbonamenti e gli annullamenti degli abbonamenti ai profili contemporaneamente.<br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/subscription-services.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Attività di arricchimento: arricchisci i dati in base alle transizioni precedenti<br /> </td> 
   <td> La nuova attività del flusso di lavoro <span class="uicontrol">Arricchimento</span> ti consente di sfruttare le transizioni in entrata e completare la transizione in uscita con dati aggiuntivi. Se esegui il targeting dei profili, l’attività di arricchimento ti consente di arricchire le informazioni dei profili con dati aggiuntivi non memorizzati nel database (ad esempio, provenienti da un file importato).<br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/enrichment.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Piattaforma_

* La barra superiore dell’interfaccia Adobe Campaign è stata aggiornata con il nuovo menu Experience Cloud.
* È stato risolto un problema che impediva la visualizzazione del collegamento a **[!UICONTROL Offers]** nell’elenco a discesa della soluzione.

_E-mail, messaggi SMS e direct mail_

* La fase di preparazione della consegna è stata migliorata per migliorare le prestazioni.
* Sono stati risolti diversi problemi che potevano causare il danneggiamento dei log di tracking in alcune situazioni di nicchia.
* È stato risolto un problema relativo all’aggiornamento della data di contatto che si verificava quando la data di contatto veniva modificata tra la preparazione della consegna e la conferma. Ora, quando modifichi la data di contatto dopo la preparazione, devi preparare nuovamente la consegna prima di poter confermare l’invio. Consulta la [documentazione dettagliata](../../sending/using/preparing-the-send.md).

_Notifiche push_

* È stato corretto un errore che impediva ad alcuni campi di personalizzazione di funzionare nelle notifiche push iOS.
* È stato risolto un errore che causava la visualizzazione di tassi di apertura e clic come 0% nel dashboard di notifica push.

_Rapporti_

* È stato corretto un errore che mostrava l’elenco dei report come vuoto in alcuni browser.
* È stato corretto un errore che si verificava nel flusso di lavoro tecnico **[!UICONTROL Report sharing]** poco prima del raggiungimento del relativo limite di scadenza.

_Flussi di lavoro_

* È stato risolto un problema che impediva l’accesso alle attività dopo il trascinamento.
* È stato risolto un problema che in alcune situazioni poteva causare il cambiamento dell&#39;ordine delle transizioni di output di un&#39;attività **[!UICONTROL Segmentation]** .
* È stato corretto un errore che si verificava durante la lettura di un pubblico contenente un campo di enumerazione e che era stato salvato in precedenza da un flusso di lavoro
* È stato risolto un problema a causa del quale l’opzione **[!UICONTROL Request confirmation before sending messages]** veniva selezionata anche dopo averlo deselezionato durante la definizione delle proprietà di pianificazione di una consegna creata in un flusso di lavoro.
* La rimozione automatica delle righe duplicate (clausola DISTINCT) può ora essere disabilitata nelle attività **[!UICONTROL Query]** tramite una nuova opzione situata nella scheda **[!UICONTROL Additional data]** . La disattivazione di questa opzione è consigliata quando si definiscono molti (più di 100) elementi aggiuntivi, per motivi di prestazioni.

_Integrazioni_

* Sono stati apportati alcuni miglioramenti alla schermata di configurazione **[!UICONTROL Data sources]**.

_Problemi noti_

È consigliabile non utilizzare Internet Explorer versione 11 a causa di possibili problemi di visualizzazione.

Potrebbero verificarsi alcuni problemi durante l’utilizzo di collegamenti di aiuto contestuali dall’interfaccia di Campaign. Essi saranno fissati nel 18.3.

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
   <td> Reporting per la gestione dell'affaticamento<br /> </td> 
   <td> Reporting for Fatigue Management è un rapporto dedicato e configurabile che mostra l’impatto delle regole di affaticamento sulle consegne tra i canali e-mail, push, SMS e Direct Mail entro un intervallo di date specificato prima dell’invio. Grazie alla possibilità aggiunta di poter visualizzare rapidamente tutte le campagne in conflitto in un’unica vista, gli esperti di marketing possono pianificare le campagne di marketing in base a impostare le regole di affaticamento in modo più efficace e assegnare priorità alle comunicazioni.<br /> Per ulteriori informazioni, consulta la <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Condivisione dei rapporti<br /> </td> 
   <td> La condivisione di rapporti consente di condividere i rapporti con gli utenti Adobe Campaign come allegato e-mail, anche su base ricorrente automatica. Gli utenti che ricevono rapporti ricorrenti possono annullare l’iscrizione a tali comunicazioni tramite un collegamento dedicato in ogni e-mail.<br /> Per ulteriori informazioni, consulta la <a href="../../reporting/using/reporting-interface.md#share-tab">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nuove funzionalità push<br /> </td> 
   <td> Anteprima messaggi push - Anteprima di notifiche push su dispositivi iOS e Android dall'editor contenuti notifiche push per visualizzare esattamente ciò che i destinatari vedranno prima di testare o eseguire la consegna.<br /> Per ulteriori informazioni, consulta la <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">documentazione dettagliata</a>.<br /> Contenuto disponibile : quando non si aprono le app per periodi di tempo prolungati, i loro dati possono non essere più aggiornati. Questo comporta la necessità di aggiornare o sostituire i dati nel momento in cui un utente apre finalmente l’app, il che può causare ritardi nell’utilizzo dell’app. Con il supporto aggiunto di Contenuto disponibile, gli utenti Adobe Campaign possono svegliare la propria app per aggiornare i propri dati in background durante la distribuzione di una notifica push, consentendo una maggiore coerenza e un maggiore controllo sull’esperienza in-app di un utente.<br /> Contenuto variabile - Con il supporto aggiunto di Contenuto variabile, gli utenti Adobe Campaign possono ora utilizzare le estensioni della loro app mobile per modificare ulteriormente il contenuto o la presentazione delle notifiche push in arrivo inviate da Adobe Campaign. Ad esempio, gli utenti possono utilizzare Contenuto variabile per: <br /> 
    <ul> 
     <li> decrittografare i dati consegnati in un formato crittografato </li> 
     <li> scaricare immagini o altri file multimediali e aggiungerli come allegati a una notifica </li> 
     <li> modificare il corpo o il testo del titolo di una notifica </li> 
     <li> aggiungere un identificatore di thread a una notifica </li> 
    </ul> Per ulteriori informazioni su Contenuto disponibile e Contenuto variabile, consulta la <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">documentazione dettagliata</a>.<br /> <strong>Avvertenza:</strong> questi aggiornamenti sulle notifiche push richiedono ai clienti di aggiornare le loro applicazioni mobili. Per ulteriori informazioni, consultare <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/push-payload.html">questa nota tecnica</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Consegne ottimizzate in base al fuso orario<br /> </td> 
   <td> Pianifica notifiche e-mail, SMS e push ricorrenti da inviare in un giorno/ora specifico in ogni fuso orario dei destinatari, garantendo che i messaggi vengano consegnati al momento giusto senza configurare più consegne. <br /> Per ulteriori informazioni, consulta la <a href="../../automating/using/scheduler.md">documentazione dettagliata</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Attivazione attività segnale API<br /> </td> 
   <td> È ora possibile attivare un’attività di segnale per i flussi di lavoro direttamente dall’API di Adobe Campaign Standard.<br /> Per ulteriori informazioni, consulta la <a href="/help/api/using/triggering-a-signal-activity.md">documentazione dettagliata</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Patch**

_Piattaforma_

* La ricerca del profilo è stata ottimizzata per migliorare le prestazioni.
* L’identificatore interno dei gruppi di sicurezza predefiniti è ora in modalità di sola lettura per gli utenti standard.

_E-mail, messaggi SMS e direct mail_

* È stato risolto un problema di visualizzazione che si verificava durante l’inserimento di emoticon nel contenuto delle consegne.
* È stato risolto un problema che consentiva all’utente di accedere ai registri di invio quando la consegna era ancora in edizione.
* L’attività **[!UICONTROL Scheduler]** ora ti consente di inviare le consegne a seconda del fuso orario del destinatario.
* SMS: L’opzione **[!UICONTROL Store incoming MO]** nel database è stata aggiunta agli account esterni. Se questa opzione è selezionata, tutti gli SMS in entrata verranno memorizzati nella tabella **inSMS** .
* SMS: I servizi sono ora collegati a un evento anziché a un modello transazionale.
* SMS: Il timeout predefinito della connessione SMTP è stato ridotto a 30 secondi.

_Notifiche push_

* È stato corretto un errore che impediva l’arresto delle consegne di notifiche push.
* È stata aggiunta un’opzione nelle opzioni avanzate di notifica push per svegliare l’applicazione con una notifica push.
* È stato aggiunto un pulsante di pausa per il video di anteprima della notifica push.
* L’anteprima della notifica push è ora disponibile per diversi dispositivi quali iPhone, Android, tablet.

_Rapporti_

* È stato corretto un errore che causava la visualizzazione di percentuali superiori al 100%.
* È stato risolto un problema che impediva agli utenti di scaricare i rapporti in CSV.
* È stato aggiunto un nuovo elemento **[!UICONTROL Report]** nella home page.

_Flussi di lavoro_

* È stato risolto un problema che causava un messaggio di errore durante l’utilizzo di dati aggiuntivi in una query e l’aggiunta di alias contenenti spazi. I caratteri non alfanumerici sono ora sostituiti da &quot;_&quot;.
* È stato risolto un problema che in alcuni casi causava l’arresto predefinito dei KPI per il calcolo del flusso di lavoro tecnico.

_Profili e pubblico_

* È stato corretto un errore che si verificava durante l’aggiunta di più filtri nella query di un pubblico.
* È stato risolto un problema di visualizzazione che si verificava durante la modifica dell’immagine di un profilo.
* È stata aggiunta una descrizione che mostra il numero esatto del risultato dopo il conteggio della popolazione di una query.
* È stato risolto un problema che poteva impedire agli utenti di selezionare un pubblico o chiudere la finestra del selettore del pubblico.
* L’elenco delle funzioni disponibili nell’editor di espressioni è stato aggiornato. Le funzioni **FormatCurrency** e **ConvertCurrency** sono state rimosse.
