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
source-git-commit: ad110413fd325894405b421999baccda2c7cef4a
workflow-type: tm+mt
source-wordcount: '1825'
ht-degree: 99%

---


# Note sulla versione 2020{#release-notes-2020}

[Pianificazione del rilascio](https://helpx.adobe.com/it/campaign/kb/acs-release-planning.html) | [Versioni del Pannello di controllo Campaign](https://docs.adobe.com/content/help/it-IT/control-panel/using/release-notes.html) | [Aggiornamenti alla documentazione](../../rn/using/documentation-updates.md) | [Note sulla versione precedenti](../../rn/using/release-notes-2019.md) | [Funzioni obsolete](https://helpx.adobe.com/it/campaign/kb/acs-deprecated-and-removed-features.html)

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

* La user experience dei messaggi transazionali e la coerenza dell’interfaccia sono state migliorate. [Ulteriori informazioni](../../channels/using/about-transactional-messaging.md)
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
