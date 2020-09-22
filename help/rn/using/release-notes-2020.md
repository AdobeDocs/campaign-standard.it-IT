---
title: Note sulla versione 2020
description: In questa pagina sono elencate tutte le versioni del 2020 di Adobe Campaign Standard.
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
source-git-commit: 0b82a9dc86ec9e48e25f1ffe53188ba916a9d074
workflow-type: tm+mt
source-wordcount: '2951'
ht-degree: 95%

---


# Note sulla versione 2020{#release-notes-2020}

[Pianificazione del rilascio](https://helpx.adobe.com/it/campaign/kb/acs-release-planning.html) | [Versioni del Pannello di controllo Campaign](https://docs.adobe.com/content/help/it-IT/control-panel/using/release-notes.html) | [Aggiornamenti alla documentazione](../../rn/using/documentation-updates.md) | [Note sulla versione precedenti](../../rn/using/release-notes-2019.md) | [Funzioni obsolete](https://helpx.adobe.com/it/campaign/kb/acs-deprecated-and-removed-features.html)

![](assets/do-not-localize/cp-icon.png) **Nuova versione del Pannello di controllo Campaign di giugno** con monitoraggio dei profili attivi, audit del recapito messaggi del sottodominio e gestione delle chiavi GPG. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/control-panel/using/release-notes.html).

## Versione 20.3 - maggio 2020 {#release-20-3---may-2020}

**Quali sono le novità?**

<table> 
<thead> 
<tr> 
<th> <strong>Legge tailandese sulla protezione dei dati personali (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>La legge tailandese sulla protezione dei dati personali (PDPA) è la nuova legge sulla privacy che armonizza e aggiorna i requisiti di protezione dei dati in Thailandia. Questo regolamento si applica ai clienti di Adobe Campaign che detengono i relativi dati dei soggetti residenti in questo paese.</p>
<p>Oltre alle funzionalità per la privacy già disponibili in Adobe Campaign (compresa la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), sono state incluse funzionalità aggiuntive per facilitare la tuo preparazione al PDPA:</p>
<ul>
<li>Diritto di accesso e Diritto di eliminazione: sono state sfruttate le funzionalità aggiunte del RGPD e del CCPA. <a href="https://helpx.adobe.com/it/campaign/kb/acs-privacy.html#righttoaccess">Ulteriori informazioni</a> </li>
<li><p>Durante la creazione di una richiesta di accesso a dati personali, il tipo di regolamento PDPA è stato aggiunto al servizio core Privacy. Dovresti utilizzare questo metodo per tutte le richieste di accesso ed eliminazione. L’utilizzo dell’API e dell’interfaccia di Campaign per le richieste di accesso ed eliminazione è obsoleto. Consulta l’articolo <a href="../../rn/using/deprecated-features.md">Funzioni obsolete e rimosse</a>.</p></li>
</ul>
<p>Consulta il <a href="https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/privacy/privacy-overview.html">video tutorial</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Attività API esterna (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>L’attività <strong>External API</strong> è in fase di transizione dalla versione beta a GA. Questa versione offre ulteriore flessibilità al parser del corpo della risposta JSON. Ora puoi:</p>
<ul>
<li>analizzare un JSON nidificato con una profondità massima di 10 livelli; </li>
<li>analizzare le proprietà selezionate come nodi foglia da un JSON e uniformarle in una singola riga di tabella;</li>
<li>selezionare e utilizzare un oggetto array da un JSON senza dover denominare l’oggetto "data" o posizionarlo sul livello superiore.</li>
</ul>
<p><strong>Attenzione:</strong> i clienti devono <strong>sostituire tutte le attività API esterne in versione beta</strong> con attività API esterne GA nei relativi flussi di lavoro. I flussi di lavoro che utilizzano la versione beta dell’API esterna non funzionano più in 20.3.</p>
<p>Per ulteriori informazioni, consulta la <a href="../../automating/using/external-api.md">documentazione dettagliata</a> e il <a href="https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">video tutorial</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Funzionalità** aggiuntive (a partire dal 13 luglio)

* **Ottimizzazione dei tempi di invio e valutazione** del profilo con tecnologia AI: ora puoi ottimizzare la progettazione e la consegna dei percorsi dei clienti per prevedere le preferenze di coinvolgimento di ogni individuo. Basato su Journey AI,  Adobe Campaign può analizzare e prevedere le tariffe aperte, i tempi di invio ottimali e il probabile churn in base alle metriche di coinvolgimento storiche. [Ulteriori informazioni](../../sending/using/predictive.md)
* **Brasile: nuova normativa** sulla privacy - Oltre alle funzionalità per la privacy già disponibili in Campaign,  Adobe aiuta a facilitare la tua disponibilità per la società brasiliana Lei Geral de Proteçao de Datos (LGPD). Durante la creazione di una richiesta per la privacy, il regolamento LGPD è stato aggiunto  Adobe Privacy Core Service. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/campaign-privacy-overview.html)

**Miglioramenti**

* Il numero dei caratteri utilizzabili nel campo **Prefix** per [verificare messaggi tramite i profili target](../../sending/using/testing-messages-using-target.md) è stato aumentato da 32 a 500 caratteri.
* Il numero massimo degli eventi in tempo reale pubblicabili su un’istanza è stato aumentato da 350 a 2000. (CAMP-41608)
* La sincronizzazione tra Adobe Launch e Campaign Standard è stata migliorata mediante il flusso di lavoro tecnico syncWithLaunch. Questo flusso di lavoro abilita l’importazione automatica di tutte le proprietà mobili di Adobe Launch in Adobe Campaign Standard. Per ulteriori informazioni, consulta [questa pagina](../../administration/using/technical-workflows.md).

   Devi inviare un ticket all’Assistenza cliente di Adobe (direttamente o tramite il contatto di Adobe) per far sì che il flusso di lavoro tecnico syncWithLaunch sia abilitato nell’istanza Campaign. (CAMP-40082)

**Miglioramenti di E-mail Designer**

* L’Email Designer può ora gestire una formattazione HTML più flessibile rispetto al rigido W3C. (CAMP-42529)
* È stato risolto un problema relativo alle [immagini cliccabili](../../designing/using/links.md#inserting-a-link) per impedire la visualizzazione di collegamenti accanto all’immagine nei blocchi di contenuto. (CAMP-41586)
* È stato risolto un problema che impediva il reindirizzamento a una pagina di destinazione quando l’[URL tracciato](../../designing/using/links.md#about-tracked-urls) aveva una categoria aggiunta nel modello. (CAMP-41537)
* È stato risolto un problema relativo alla spaziatura dei pulsanti in Outlook.
* È stato risolto un problema che causava la visualizzazione dei tag HTML nel testo normale.
* La ricerca per blocchi di contenuto visualizza ora i risultati della ricerca sul server e i risultati precaricati. (CAMP-41870)

**Altre modifiche**

* L’interfaccia di pubblicazione delle risorse personalizzate è stata migliorata con messaggi di errore più chiari.
* Le mappature di consegna non utilizzate sono state rimosse dall’interfaccia.
* I ruoli di amministratore non necessari sono stati rimossi dall’interfaccia.
* Le caselle di controllo possono ora diventare obbligatorie in una pagina di destinazione.
* È stato rimosso il limite di 200 righe durante il download del file CSV di un rapporto dinamico. Ora puoi includere ogni riga del rapporto. (CAMP-40810)
* È stata aggiunta la lingua ES-US nell’elenco delle lingue predefinite per le e-mail multilingue. (CAMP-42279)
* I file scaricati con un’attività Transfer file vengono ora eliminati dopo X giorni, dove X è determinato dal campo **History in days** nel menu **Execution** delle proprietà del flusso di lavoro. [Ulteriori informazioni](../../automating/using/managing-execution-options.md)

**Integrazioni con Experience Platform**

* L’attivazione di Adobe [Experience Platform Audiences](../../automating/using/aep-targeting-audiences.md)dall’attività **Read audience** è stata migliorata per fornire prestazioni e stabilità migliori. Inoltre, i log del flusso di lavoro sono stati resi più chiari e dettagliati per quanto riguarda i processi di attivazione, consentendo un monitoraggio e una risoluzione dei problemi più semplice durante la lettura dei tipi di pubblico in Adobe Experience Platform.

**Patch**

* È stato corretto un errore che causava la creazione di una risorsa fantasma durante il processo di pubblicazione di una risorsa personalizzata.
* È stato risolto un problema che poteva impedire la visualizzazione dello storico dei dati marketing dei profili se la risorsa Profile era stata estesa con una risorsa personalizzata. (CAMP-41009)
* È stato risolto un problema relativo ai modelli di pagine di destinazione preconfigurati che visualizzavano il contenuto in francese all’apertura dell’editor. (CAMP-41639)
* È stato risolto un problema nelle notifiche push con contenuto dinamico che poteva impedire la visualizzazione delle emoticon. (CAMP-40715)
* È stato risolto un problema nell’attività **Deduplication** che poteva causare l’assegnazione di un codice di segmento errato a una delle transizioni di complemento in uscita. (CAMP-41400)
* È stato corretto un errore che impediva l’eliminazione dei rapporti pianificati. (CAMP-41302)
* È stato risolto un problema che causava discrepanze tra il dashboard di consegna e il rapporto **Delivery Summary**. (CAMP-41145)
* È stato risolto un problema che causava un problema di visualizzazione di sovrapposizione dei caratteri nei rapporti scaricati.
* È stato risolto un problema che impediva il funzionamento dell’anteprima di una consegna per la sostituzione della bozza.
* È stato corretto un errore durante l’eliminazione dei campi di personalizzazione di una notifica locale in-app.
* È stato risolto un problema che impediva il funzionamento della funzione charIndex con un’attività **End** o **File transfer** in un flusso di lavoro.
* È stato risolto un problema nei flussi di lavoro che poteva verificarsi durante un’attività **Enrichment** con due attività di input, incluse le risorse target con un collegamento tra loro. (CAMP-42133)
* È stato risolto un problema che poteva impedire l’esecuzione di un flusso di lavoro durante l’utilizzo di funzioni sconosciute. (CAMP-41873)
* È stato risolto un problema nei flussi di lavoro che poteva verificarsi durante la creazione di tipi di pubblico utilizzando diverse attività **Save audience** con transizioni di complemento in uscita. (CAMP-39992)
* È stato risolto un problema che causava discrepanze di dati durante la personalizzazione nelle e-mail transazionali. (CAMP-41842)
* Sono stati risolti i problemi che si verificavano durante l’eliminazione dei campi di personalizzazione nelle consegne di notifiche push. (CAMP-37586)
* È stato corretto un errore che impediva agli utenti di apportare modifiche ai rapporti. (CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **Il nuovo Pannello di controllo Campaign potrebbe rilasciare** con rinnovo del certificato per i sottodomini CNAME. [Ulteriori informazioni](https://docs.adobe.com/content/help/it-IT/control-panel/using/release-notes.html).

## Versione 20.2 - Aprile 2020 {#release-20-2---april-2020}

**Quali sono le novità?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integrazione con Azure Blob</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Il connettore di archiviazione Azure Blob può ora essere utilizzato per importare o esportare dati in Adobe Campaign utilizzando un’attività di flusso di lavoro <strong>Trasferisci file</strong>. </p>
    <p>Per ulteriori informazioni, consulta la <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">documentazione dettagliata</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Verifica dei messaggi e-mail tramite profili di destinazione</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Oltre ai profili di test, ora puoi testare le e-mail su profili di destinazione reali. Ciò ti consente di ottenere una rappresentazione esatta del messaggio ricevuto dal profilo: campi personalizzati, informazioni dinamiche e personalizzate, compresi dati aggiuntivi dei flussi di lavoro, ecc. </p>
    <p>Per ulteriori informazioni, consulta la <a href="../../sending/using/testing-messages-using-target.md">documentazione dettagliata</a> e il <a href="https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">video tutorial</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Nuove funzionalità verranno rilasciate nel Pannello di controllo Campaign ad aprile, tra cui la gestione dei record TXT di Google, il monitoraggio dello spazio del database e l’avviso e-mail. Per ulteriori informazioni su queste funzioni, consulta le [Note sulla versione del Pannello di controllo Campaign](https://docs.adobe.com/content/help/it-IT/control-panel/using/release-notes.html).

**Miglioramenti**

* La user experience dei messaggi transazionali e la coerenza dell’interfaccia sono state migliorate. [Ulteriori informazioni](../../channels/using/getting-started-with-transactional-msg.md)
* Campaign Standard ora ti consente di inviare bozze ai profili di test utilizzando dati aggiuntivi dei flussi di lavoro.
* I guardrail per l’attività External API sono stati aggiornati. [Ulteriori informazioni](../../automating/using/external-api.md)

**Miglioramenti di E-mail Designer**

* È stato risolto un problema che riguardava l’uscita quando si faceva clic più volte su un’immagine personalizzata.
* È stato risolto un problema che si verificava durante la duplicazione di componenti di testo dinamico che poteva causare la duplicazione della riga errata. (CAMP-41249)
* È stato risolto un problema relativo alla spaziatura in Outlook che si verificava durante la definizione della spaziatura a livello di tabella anziché a livello div.
* È stato risolto un problema che causava la modifica della larghezza di un’immagine quando si passava alla modalità HTML. (CAMP-41116)
* È stato risolto un problema che impediva al componente social media di essere accessibile quando si forniva testo alternativo alle icone. (CAMP-41345)
* È stato risolto un problema che causava la visualizzazione di tag `<br>` visibili durante l’utilizzo del comando Copia/Incolla in E-mail Designer.
* È stato risolto un problema che causava la visualizzazione di tag HTML nell’e-mail dopo il passaggio dal contenuto HTML al testo normale. (CAMP-41138)
* È stato risolto un problema che impediva il rendering dei pulsanti con un solo bordo definito.
* È stato risolto un problema nel rientro HTML che causava lo spostamento a sinistra del piè di pagina delle e-mail in Microsoft Outlook. (CAMP-40987)
* È stato risolto un problema che causava la copia dei campi di personalizzazione per un attributo di raccolta definito in HTML nel contenuto di testo normale quando si passava alla modalità di testo normale. (CAMP-40365)
* È stato risolto un problema che impediva l’inserimento di collegamenti in un segmento di testo selezionato. (CAMP-41406)
* È stato risolto un problema che causava la modifica della data durante la selezione di un fuso orario nell’editor delle query. (CAMP-38277)

**Altre modifiche**

* Il flusso di lavoro preconfigurato **Riconciliazione dei KPI con Adobe Analytics** viene ora eseguito fino alla data corrente, invece di essere eseguito per un singolo giorno.
* MCPNS non supporta l’aggiunta di APNS e APNS-SANDBOX come piattaforme in un’app. Dopo l’aggiunta del certificato in Adobe Campaign Standard, ora non è più possibile ripristinare le impostazioni perché è possibile aggiungere una sola piattaforma APNS (produzione o sandbox) all’app MCPNS.

**Integrazioni con Experience Platform**

>[!NOTE]
>
>Le funzionalità di Adobe Experience Platform in Campaign Standard sono attualmente in versione beta, e potrebbero essere soggette ad aggiornamenti frequenti senza preavviso. Consulta la documentazione dettagliata: [Connettore dati di Experience Platform](../../developing/using/aep-about-data-connector.md), [Audience Destinations](../../audiences/using/aep-about-audience-destinations-service.md)

* Nei registri del flusso di lavoro, Campaign ora visualizza ogni 10 minuti il numero di record già elaborati dal processo attualmente in esecuzione.
* È stato risolto un problema che poteva verificarsi durante l’importazione di un profilo Adobe Experience Platform eliminato dal database.
* È stato risolto un problema nei registri del flusso di lavoro che poteva visualizzare un risultato errato per il numero totale di record importati.

**Patch**

* È stato risolto un problema relativo all’attività del flusso di lavoro **Arricchimento** che poteva verificarsi quando si aggiungevano spazi nel campo **Alias** e creava un nuovo elemento riga. (CAMP-39229)
* È stato risolto un problema a causa del quale ogni profilo di test poteva essere oggetto di targeting durante l’invio di un messaggio di bozza.
* È stato risolto un problema che si verificava dopo l’annullamento della pubblicazione e l’eliminazione di una configurazione di evento. [Ulteriori informazioni](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* È stato risolto un problema che causava la scomparsa del pulsante **Save** quando si apportavano modifiche ai flussi di lavoro.
* È stato risolto un problema che si verificava durante l’eliminazione manuale di una richiesta di accesso a dati personali in Campaign a seguito dell’elaborazione, a causa del quale i dati associati alla richiesta non potevano essere eliminati anche dopo la pulizia.
* È stato risolto un problema che poteva verificarsi durante l’anteprima o l’invio di messaggi che includevano caratteri speciali da Adobe Experience Manager.
* È stato risolto un problema che poteva verificarsi nei flussi di lavoro durante l’esecuzione di un’attività con diverse transizioni in entrata.
* È stato risolto un problema che impediva agli utenti standard di utilizzare “Abbonamenti a un’applicazione” come dimensione di destinazione in una query del flusso di lavoro o una consegna. (CAMP-37618)

## Versione 20.1.4 - Febbraio 2020 {#release-20-1-4---february-2020}

* È stato risolto un problema che si verificava all’apertura di un’attività **Read Audience** sui flussi di lavoro esistenti. (CAMP-41002)

## Versione 20.1.3 - Febbraio 2020 {#release-20-1-3---february-2020}

* È stato risolto un problema di regressione introdotto in 20.1 da CAMP-39273 per i clienti che utilizzano la scappatoia. CAMP-39273 è stato ripristinato.

## Versione 20.1.2 - Febbraio 2020 {#release-20-1-2---february-2020}

**Miglioramenti di E-mail Designer**

* È stato risolto un problema che causava l’aggiunta di un elemento tag HTML in un frammento obsoleto al momento dell’applicazione della patch e del salvataggio del contenuto. (CAMP-40685)
* È stato risolto un problema che aggiungeva uno spazio quando si utilizzava contenuto dinamico. (CAMP-40605)
* È stato risolto un problema durante la configurazione di un modello e-mail transazionale. (CAMP-40604)

## Versione 20.1 - Febbraio 2020 {#release-20-1---february-2020}

**Quali sono le novità?**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Connettore dati di Adobe Experience Platform (beta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Il Connettore dati di Adobe Experience Platform è ora integrato con Adobe Campaign Standard. Puoi rendere disponibili i dati di Campaign su Adobe Experience Platform mappando i dati XTK (dati acquisiti in Campaign) su Adobe Experience Platform Data Model (XDM). </p>
    <p>Questa funzionalità è disponibile solo per i clienti in hosting su Azure. Per ulteriori informazioni su questa funzionalità e sulle relative condizioni di attivazione, consulta la <a href="../../developing/using/aep-about-data-connector.md">documentazione dettagliata</a> e il <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">video di istruzioni</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Audience Destinations (beta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Audience Destinations ti consente di condividere segmenti da Adobe Experience Platform ad Adobe Campaign.</p>
    <p>Questa funzionalità è disponibile solo per i clienti in hosting su Azure. Per ulteriori informazioni su questa funzionalità e sulle relative condizioni di attivazione, consulta la <a href="../../audiences/using/aep-about-audience-destinations-service.md">documentazione dettagliata</a> e il <a href="https://docs.adobe.com/content/help/it-IT/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">video di istruzioni</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Miglioramenti**

* Disponibilità globale dell’MTA avanzato: i messaggi (inclusi i messaggi transazionali) vengono ora inviati dall’MTA avanzato di Adobe Campaign, che fornisce un’infrastruttura di invio aggiornata che consente di migliorare la consegna, la velocità effettiva e la gestione delle mancate consegne. [Ulteriori informazioni](https://helpx.adobe.com/it/campaign/kb/campaign-enhanced-mta.html)

* La gestione del fuso orario è stata migliorata. Ora puoi definire un [fuso orario specifico](../../automating/using/building-a-workflow.md) per un intero flusso di lavoro. Il fuso orario selezionato verrà applicato a tutte le attività del flusso di lavoro. Le informazioni sul fuso orario configurato per l’operatore o il server vengono ora visualizzate nell’interfaccia (nei registri e dopo aver selezionato un fuso orario). (CAMP-37672)

* Le API di Campaign Standard ti consentono ora di eseguire l’impaginazione quando utilizzi tabelle di grandi dimensioni, aggiungendo il parametro `_forcePagination=true` all’URL della chiamata. [Ulteriori informazioni](../../api/using/pagination.md)

* L’ID del registro di consegna (un identificatore univoco per ciascun registro) è ora disponibile nelle risorse Registri di consegna e Registri di tracciamento per tutte le dimensioni di targeting. Ciò consente ad esempio di identificare i registri di invio o di tracciamento durante l’esportazione. [Ulteriori informazioni](../../automating/using/exporting-logs.md)

**Miglioramenti di E-mail Designer**

* Sono state aggiunte istruzioni di testo obbligatorie mancanti durante la creazione di un pubblico.
* È stato risolto un problema che si verificava facendo clic sul pulsante **Change content** nella procedura guidata dell’editor e-mail legacy.
* È stato risolto un problema che impediva l’allineamento delle intestazioni con il contenuto del report Riepilogo del servizio. (CAMP-38103)
* È stato risolto un problema che impediva l’eliminazione delle varianti di contenuto dinamico senza influire sul resto dell’oggetto. (CAMP-40096)
* È stato risolto un problema di test A/B che si verificava quando si utilizzava la variante B nell’oggetto. (CAMP-40327)
* È stato risolto un problema che impediva il trascinamento e il rilascio di file durante l’utilizzo della funzione di importazione Carica HTML. (CAMP-39326)
* È stato risolto un problema che impediva di copiare e incollare testo da un editor di testo. (CAMP-39028)
* È stato risolto un problema che impediva la visualizzazione delle parole suggerite. (CAMP-38970)
* È stato risolto un problema che impediva agli utenti di salvare frammenti. (ATU-2447)
* È stato risolto un problema che impediva la duplicazione delle strutture dinamiche. (CAMP-38367)
* È stato risolto un problema che impediva il mantenimento delle condizioni del contenuto dinamico in caso di duplicazione. (CAMP-39051)

**Altre modifiche**

* Il filtro &quot;Consegne con preparazione non riuscita&quot; ora prende in considerazione la data di creazione delle consegne anziché l’ultima data di modifica.
* L’unità organizzativa del gruppo di protezione Amministratori non può più essere modificata.
* Quando si crea un profilo, è necessario compilare il campo Unità organizzativa.
* Ora è possibile eliminare un trigger di Experience Cloud solo se vengono eliminati sia l’evento sia il modello transazionale ad esso collegato.
* L’SDK Adobe Creative è stato ritirato. È ora obsoleto in Campaign Standard. Consulta la pagina [Funzioni obsolete e rimosse](https://helpx.adobe.com/it/campaign/kb/acs-deprecated-and-removed-features.html).


**Patch**

* È stato risolto un problema che impediva l’eliminazione dei dati utente nei registri di esclusione durante l’esecuzione di una richiesta di eliminazione di dati personali. (CAMP-39003)
* È stato risolto un problema che causava problemi di accessibilità durante il ridimensionamento del testo in un elemento contenitore.
* È stato risolto un problema che impediva agli utenti di chiudere il pop-up Calendario visualizzato al passaggio del mouse nelle attività di marketing.
* È stato risolto un problema nell’attività **[!UICONTROL External API]** che visualizzava il pulsante **[!UICONTROL Confirm]** anche quando non venivano modificati dati.
* È stato risolto un problema che si verificava durante l’utilizzo di un’attività **[!UICONTROL Union]** su query con dimensioni di destinazione diverse. I dati di transizione mostravano solo record della dimensione di targeting del set principale. (CAMP-36831)
* È stato risolto un problema che poteva causare un errore durante l’utilizzo di un’attività **[!UICONTROL Reconciliation]** in contesti specifici, ad esempio con due attività in entrata, una delle quali era un’attività di esclusione. (CAMP-37490)
* Sono stati risolti dei problemi di prestazioni che potevano verificarsi durante la selezione e l’aggiornamento dei profili di test. (CAMP-37976)
* È stato risolto un problema che poteva provocare la visualizzazione di pagine di errore durante l’abbonamento o l’annullamento dell’abbonamento tramite pagine di destinazione. (CAMP-37771)
* È stato risolto un problema che si verificava durante il caricamento di contenuto in formato zip, in cui l’estensione dei file PNG a cui si faceva riferimento nell’HTML era in lettere maiuscole. (CAMP-37913)
* È stato risolto un problema che impediva l&#39;invio di messaggi in-app quando si aggiungeva un profilo di test alla consegna.
* È stato risolto un errore che impediva il funzionamento dell’attività del flusso di lavoro External API quando era collegata ad attività di arricchimento.
* È stato risolto un problema che poteva causare una visualizzazione errata dello stato dei messaggi SMS.
* È stato risolto un problema relativo alle risorse personalizzate che provocava la visualizzazione di voci duplicate in endpoint API diversi.
* È stato risolto un problema che rendeva non disponibili le pagine di destinazione dopo la pubblicazione. (CAMP-38695)
* È stato risolto un bug che si verificava durante la visualizzazione di dati da una transizione Intersezione proveniente da due risorse diverse. (CAMP-38974)
* È stato risolto un problema che causava l’impostazione errata del valore di enumerazione in un modello di consegna. (CAMP-38388)
* È stato risolto un errore riguardante le consegne di gruppo di e-mail che visualizzava lo stato delle consegne come In sospeso e lo stato Inviato come Completato. (CAMP-35355)
* È stato risolto un errore che causava la visualizzazione errata del dominio del mittente nel Reporting dinamico. (CAMP-33123)
* È stato risolto un problema che causava discrepanze nei conteggi di annullamento dell’abbonamento nel Reporting dinamico. (CAMP-39949)
* È stato risolto un problema che impediva la visualizzazione degli indirizzi nella schermata dei registri di invio durante l’invio di messaggi in-app.
* È stato risolto un problema che impediva l’aggiornamento dei registri di invio SMS con il numero corretto di mancate consegne. (CAMP-38395)
* Risolta una scappatoia che consentiva alle chiamate successive all’abbonamento a un’applicazione di aggiornare i token di notifica push. (CAMP-39273)
