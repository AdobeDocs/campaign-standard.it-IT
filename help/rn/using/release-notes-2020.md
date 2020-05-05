---
title: Note sulla versione 2020
description: In questa pagina sono elencate tutte le 2020 versioni di Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f4c6b74d9b80d80befed65d853cf82b32084c49d

---


# Note sulla versione 2020{#release-notes-2020}

[Pianificazione rilascio](https://helpx.adobe.com/it/campaign/kb/acs-release-planning.html) | Rilasci del [Pannello di controllo](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) | Aggiornamenti [alla documentazione](../../rn/using/documentation-updates.md) | Note sulla versione [precedente](../../rn/using/release-notes-2019.md) | Funzioni [obsolete](https://helpx.adobe.com/it/campaign/kb/acs-deprecated-and-removed-features.html)

## Rilascio 20.2 - aprile 2020 {#release-20-2---april-2020}

**Novità?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integrazione BLOB di Azure</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Il connettore di archiviazione BLOB di Azure ora può essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un'attività di flusso di lavoro <strong>di trasferimento file</strong> . </p>
    <p>Per ulteriori informazioni, consulta la documentazione <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account"></a>dettagliata.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Test e-mail con profili di destinazione</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Oltre ai profili di test, ora puoi testare le e-mail su profili di destinazione reali. Questo consente di ottenere una rappresentazione esatta del messaggio che il profilo riceverà: campi personalizzati, informazioni dinamiche e personalizzate, compresi dati aggiuntivi provenienti dai flussi di lavoro, ecc. </p>
    <p>Per ulteriori informazioni, consultate la documentazione <a href="../../sending/using/testing-messages-using-target.md"></a> dettagliata e il video <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html"></a>dell'esercitazione. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Nuove funzionalità verranno rilasciate nel Pannello di controllo delle campagne in aprile, tra cui la gestione dei record Google TXT, il monitoraggio dello spazio del database e l&#39;avviso via e-mail. Per ulteriori informazioni su queste funzioni, consulta la nota [sulla versione del pannello di](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)controllo.

**Miglioramenti**

* È stata migliorata l&#39;esperienza utente dei messaggi transazionali e la coerenza dell&#39;interfaccia è stata migliorata. [Leggi tutto](../../channels/using/about-transactional-messaging.md)
* Campaign Standard ora consente di inviare prove di stampa ai profili di test utilizzando dati aggiuntivi dai flussi di lavoro.
* Sono stati aggiornati i gestori per l&#39;attività API esterna. [Leggi tutto](../../automating/using/external-api.md)

**Miglioramenti di Email Designer**

* È stato risolto un problema che impediva l&#39;escape quando si faceva clic più volte su un&#39;immagine personalizzata.
* È stato risolto un problema che si verificava durante la duplicazione di componenti di testo dinamici che poteva causare la duplicazione della riga errata. (CAMP-41249)
* È stato risolto un problema relativo alla spaziatura in Outlook durante la definizione della spaziatura a livello di tabella anziché a livello div.
* È stato risolto un problema che causava la modifica della larghezza di un&#39;immagine quando si passava alla modalità HTML. (CAMP-41116)
* È stato risolto un problema che impediva al componente social media di essere accessibile quando si forniva testo alternativo alle icone. (CAMP-41345)
* È stato risolto un problema che causava la visualizzazione di `<br>` tag visibili durante l&#39;utilizzo del comando Copia/Incolla in Designer e-mail.
* È stato risolto un problema che causava la visualizzazione dei tag HTML nell&#39;e-mail dopo il passaggio dal contenuto HTML al testo normale. (CAMP-41138)
* È stato risolto un problema che impediva il rendering dei pulsanti con un solo bordo definito.
* È stato risolto un problema nel rientro HTML che causava lo spostamento a sinistra del piè di pagina delle e-mail in Microsoft Outlook. (CAMP-40987)
* È stato risolto un problema che causava la copia dei campi di personalizzazione per un attributo di raccolta definito in HTML nel contenuto di testo normale quando si passava alla modalità di testo normale. (CAMP-40365)
* È stato risolto un problema che impediva l&#39;inserimento di collegamenti in un segmento di testo selezionato. (CAMP-41406)
* È stato risolto un problema che causava la modifica della data durante la selezione di un fuso orario nell&#39;editor query. (CAMP-38277)

**Altre modifiche**

* La riconciliazione **KPI con il flusso di lavoro out-of-the-box di Adobe Analytics** ora viene eseguita fino alla data corrente, invece di essere eseguita per un singolo giorno.
* MCPNS non supporta l&#39;aggiunta di APNS e APNS-SANDBOX come piattaforme in un&#39;app. Dopo l&#39;aggiunta del certificato in Adobe Campaign Standard, ora non è più possibile ripristinare le impostazioni perché è possibile aggiungere una sola piattaforma APNS (produzione o sandbox) all&#39;app MCPNS.

**Integrazioni con la piattaforma Experience**

>[!NOTE]
>
>Le funzionalità di Adobe Experience Platform di Campaign Standard sono attualmente in versione beta, e potrebbero essere soggette a aggiornamenti frequenti senza preavviso. Consultare la documentazione dettagliata: [Connettore](../../developing/using/aep-about-data-connector.md)dati della piattaforma Experience, Destinazioni [Pubblico](../../audiences/using/aep-about-audience-destinations-service.md)

* Nei registri del flusso di lavoro, ogni 10 minuti, Campaign ora visualizza il numero di record già elaborati dal processo attualmente in esecuzione.
* È stato risolto un problema che poteva verificarsi durante l&#39;importazione di un profilo Adobe Experience Platform eliminato dal database.
* È stato risolto un problema nei registri del flusso di lavoro che poteva generare un risultato non corretto per il numero totale di record importati.

**Patch**

* È stato risolto un problema relativo all&#39;attività del flusso di lavoro **Arricchimento** che poteva verificarsi quando si aggiungevano spazi nel campo **Alias** e in seguito si creava un nuovo elemento riga. (CAMP-39229)
* È stato risolto un problema per il quale ogni profilo di test poteva essere mirato durante l&#39;invio di un messaggio di prova.
* È stato risolto un problema che si verificava dopo l&#39;annullamento della pubblicazione ed eliminazione di una configurazione di evento. [Leggi tutto](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* È stato risolto un problema che causava la scomparsa del pulsante **Salva** durante le modifiche ai flussi di lavoro.
* È stato risolto un problema che impediva l&#39;eliminazione manuale di una richiesta di privacy in Campaign dopo l&#39;elaborazione, anche dopo la pulizia, dei dati associati alla richiesta.
* È stato risolto un problema che poteva verificarsi durante l&#39;anteprima o l&#39;invio di messaggi che includevano caratteri speciali da Adobe Experience Manager.
* È stato risolto un problema che poteva verificarsi nei flussi di lavoro durante l&#39;esecuzione di un&#39;attività con diverse transizioni in entrata.
* È stato risolto un problema che impediva agli utenti standard di utilizzare &quot;Iscrizioni a un&#39;applicazione&quot; come dimensione di destinazione in una query di workflow o una consegna. (CAMP-37618)

## Rilascio 20.1.4 - febbraio 2020 {#release-20-1-4---february-2020}

* È stato risolto un problema che si verificava all&#39;apertura di un&#39;attività **Leggi pubblico** sui flussi di lavoro esistenti. (CAMP-41002)

## Rilascio 20.1.3 - febbraio 2020 {#release-20-1-3---february-2020}

* È stato risolto un problema di regressione introdotto in 20.1 da CAMP-39273 per i clienti che utilizzano la scappatoia. CAMP-39273 è stato ripristinato.

## Rilascio 20.1.2 - febbraio 2020 {#release-20-1-2---february-2020}

**Miglioramenti di Email Designer**

* È stato risolto un problema che causava l&#39;aggiunta di un elemento tag HTML in un frammento obsoleto al momento della patch e del salvataggio del contenuto. (CAMP-40685)
* È stato risolto un problema che aggiungeva uno spazio quando si utilizzava il contenuto dinamico. (CAMP-40605)
* È stato risolto un problema durante la configurazione di un modello e-mail transazionale. (CAMP-40604)

## Rilascio 20.1 - febbraio 2020 {#release-20-1---february-2020}

**Novità?**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Connettore dati Adobe Experience Platform (versione beta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Data Connector è ora integrato con Adobe Campaign Standard. Puoi rendere disponibili i dati della tua campagna su Adobe Experience Platform mappando i dati XTK (i dati acquisiti in Campaign) su Adobe Experience Platform Data Model (XDM). </p>
    <p>Questa funzionalità è disponibile solo per i clienti ospitati in Azure. Per ulteriori informazioni su questa funzionalità e sulle condizioni di attivazione, consulta la documentazione <a href="../../developing/using/aep-about-data-connector.md"></a> dettagliata e il <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">video</a>sulle procedure.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Destinazioni audience (beta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Destinazioni audience consente di condividere segmenti da Adobe Experience Platform ad Adobe Campaign.</p>
    <p>Questa funzionalità è disponibile solo per i clienti ospitati in Azure. Per ulteriori informazioni su questa funzionalità e sulle condizioni di attivazione, consulta la documentazione <a href="../../audiences/using/aep-about-audience-destinations-service.md"></a> dettagliata e il <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">video</a>sulle procedure. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Miglioramenti**

* Disponibilità globale del MTA avanzato: i messaggi (inclusi i messaggi transazionali) ora vengono inviati dall&#39;MTA avanzato di Adobe Campaign, che fornisce un&#39;infrastruttura di invio aggiornata che consente di migliorare la recapito, il throughput e la gestione dei bounce. [Leggi tutto](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)

* È stata migliorata la gestione del fuso orario. Ora puoi definire un fuso orario [specifico](../../automating/using/building-a-workflow.md) per un intero flusso di lavoro. Il fuso orario selezionato verrà applicato a tutte le attività del flusso di lavoro. Le informazioni sul fuso orario configurato per l&#39;operatore o il server ora vengono visualizzate nell&#39;interfaccia (nei registri e dopo aver selezionato un fuso orario). (CAMP-37672)

* Le API Campaign Standard ora consentono di eseguire l&#39;impaginazione quando si utilizzano tabelle di grandi dimensioni, aggiungendo il `_forcePagination=true` parametro all&#39;URL della chiamata. [Leggi tutto](../../api/using/pagination.md)

* L&#39;ID del registro di distribuzione (un identificatore univoco per ciascun registro) è ora disponibile nei registri di consegna e nei registri di tracciamento delle risorse per tutte le dimensioni di targeting. Questo consente di identificare i registri di invio o tracciamento, ad esempio durante l’esportazione. [Leggi tutto](../../automating/using/exporting-logs.md)

**Miglioramenti di Email Designer**

* Aggiunte istruzioni di testo obbligatorie mancanti durante la creazione di un pubblico.
* È stato risolto un problema che si verificava facendo clic sul pulsante **Modifica contenuto** nella procedura guidata dell’editor e-mail legacy.
* È stato risolto un problema che impediva l&#39;allineamento delle intestazioni con il contenuto del rapporto Riepilogo servizi. (CAMP-38103)
* È stato risolto un problema che impediva l&#39;eliminazione delle varianti di contenuto dinamico senza influire sul resto dell&#39;oggetto. (CAMP-40096)
* È stato risolto un problema di test A/B quando si utilizzava la variante B sulla riga dell&#39;oggetto. (CAMP-40327)
* È stato risolto un problema che impediva il trascinamento dei file durante l&#39;utilizzo della funzione di importazione HTML Carica. (CAMP-39326)
* È stato risolto un problema che impediva di copiare e incollare testo da un editor di testo. (CAMP-39028)
* È stato risolto un problema che impediva la visualizzazione dei suggerimenti sulla parola. (CAMP-38970)
* È stato risolto un problema che impediva agli utenti di salvare i frammenti. (ATU-2447)
* È stato risolto un problema che impediva la duplicazione delle strutture dinamiche. (CAMP-38367)
* È stato risolto un problema che impediva al contenuto dinamico di mantenere le condizioni in caso di duplicazione. (CAMP-39051)

**Altre modifiche**

* Il filtro &quot;Consegne con preparazione non riuscita&quot; ora prende in considerazione la data di creazione delle consegne anziché l&#39;ultima data di modifica.
* L&#39;unità organizzativa del gruppo di sicurezza Amministratori non può più essere modificata.
* Quando si crea un profilo, è necessario compilare il campo Unità organizzativa.
* Ora è possibile eliminare un attivatore Experience Cloud Trigger solo se vengono eliminati sia l&#39;evento che il modello transazionale ad esso collegato.
* Adobe Creative SDK è stato disattivato. Ora è obsoleto in Campaign Standard. Consultate la pagina Funzioni [obsolete e rimosse](https://helpx.adobe.com/it/campaign/kb/acs-deprecated-and-removed-features.html).


**Patch**

* È stato risolto un problema che impediva l&#39;eliminazione dei dati utente nei registri di esclusione durante l&#39;esecuzione di una richiesta di eliminazione della privacy. (CAMP-39003)
* È stato risolto un problema che causava problemi di accessibilità durante il ridimensionamento del testo in un elemento contenitore.
* È stato risolto un problema che impediva agli utenti di ignorare la finestra a comparsa Calendario visualizzata al passaggio del mouse nelle attività di marketing.
* È stato risolto un problema nell&#39; **[!UICONTROL External API]** attività che visualizzava il **[!UICONTROL Confirm]** pulsante anche quando non venivano modificati dati.
* È stato risolto un problema che si verificava durante l&#39;utilizzo di un&#39; **[!UICONTROL Union]** attività su query con dimensioni target diverse. I dati di transizione mostravano solo record dalla dimensione di targeting del set principale. (CAMP-36831)
* È stato risolto un problema che poteva causare un errore durante l&#39;utilizzo di un&#39; **[!UICONTROL Reconciliation]** attività in contesti specifici, ad esempio con due attività in entrata, una delle quali era un&#39;attività di esclusione. (CAMP-37490)
* Sono stati risolti i problemi di prestazioni che possono verificarsi durante la selezione e l&#39;aggiornamento dei profili di test. (CAMP-37976)
* È stato risolto un problema che poteva visualizzare le pagine di errore durante la sottoscrizione o l&#39;annullamento della sottoscrizione tramite le pagine di destinazione. (CAMP-37771)
* È stato risolto un problema che si verificava durante il caricamento del contenuto in formato zip, con i file PNG a cui veniva fatto riferimento nell’HTML con la loro estensione in lettere maiuscole. (CAMP-37913)
* È stato risolto un problema che impediva l&#39;invio di messaggi in-app quando si aggiungeva un profilo di test alla consegna.
* È stato corretto un errore con l&#39;attività del flusso di lavoro API esterna che non riusciva se collegata ad attività di arricchimento.
* È stato risolto un problema che poteva causare una visualizzazione errata dello stato dei messaggi SMS.
* È stato risolto un problema con le risorse personalizzate che causava la visualizzazione di voci duplicate in endpoint API diversi.
* È stato risolto un problema che impediva la disponibilità delle pagine di destinazione dopo la pubblicazione. (CAMP-38695)
* È stato corretto un bug che si verificava durante la visualizzazione dei dati da una transizione Intersezione proveniente da due risorse diverse. (CAMP-38974)
* È stato risolto un problema che causava l&#39;impostazione errata del valore di enumerazione in un modello di consegna. (CAMP-38388)
* È stato corretto un errore con le consegne di massa e-mail che visualizzava lo stato delle consegne come In sospeso e lo stato Inviato come Completato. (CAMP-35355)
* È stato risolto un errore che causava la visualizzazione errata del dominio del mittente nel reporting dinamico. (CAMP-33123)
* È stato risolto un problema che causava discrepanze nei conteggi di annullamento sottoscrizione nel reporting dinamico. (CAMP-39949)
* È stato risolto un problema che impediva la visualizzazione degli indirizzi nella schermata dei registri di invio durante l&#39;invio di messaggi in-app.
* È stato risolto un problema che impediva l&#39;aggiornamento dei registri di invio SMS con il numero corretto di errori. (CAMP-38395)
* Risolto un problema che consentiva alle chiamate post di iscrizione dell&#39;applicazione di aggiornare i token di notifica push. (CAMP-39273)
