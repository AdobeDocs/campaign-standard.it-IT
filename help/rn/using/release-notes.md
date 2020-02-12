---
title: Ultima versione
description: In questa pagina sono elencate tutte le versioni recenti di Adobe Campaign Standard.
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
source-git-commit: 8b02b81ef27c8415bc5bcce41178dfbfc90670cf

---


# Ultima versione{#latest-release}

[Release Planning](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) | Rilasci [del Pannello di](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) controllo| Aggiornamenti [alla](../../rn/using/documentation-updates.md) documentazione| [Note](../../rn/using/release-notes-2019.md) sulla versione precedente| Funzioni [obsolete](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## Rilascio 20.1.2 - febbraio 2020 {#release-20-1-2---february-2020}

**Miglioramenti di Email Designer**

È stato risolto un problema che causava l&#39;aggiunta di un elemento tag HTML in un frammento obsoleto al momento della patch e del salvataggio del contenuto. (CAMP-40685) È stato risolto un problema che aggiungeva uno spazio quando si utilizzava il contenuto dinamico. (CAMP-40605) È stato risolto un problema durante la configurazione di un modello di e-mail transazionale. (CAMP-40604)

## Rilascio 20.1 - febbraio 2020 {#release-20-1---february-2020}

**Cosa c&#39;è di nuovo?**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Connettore dati Adobe Experience Platform (versione beta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Experience Platform Data Connector è ora integrato con Adobe Campaign Standard. Puoi rendere disponibili i dati della tua campagna su Adobe Experience Platform mappando i dati XTK (i dati acquisiti in Campaign) su Adobe Experience Platform Data Model (XDM). </p>
    <p>Questa funzionalità è disponibile solo per i clienti ospitati in Azure. Per ulteriori informazioni su questa funzionalità e sulle condizioni di attivazione, consulta la documentazione <a href="../../administration/using/aep-about-data-connector.md"></a> dettagliata e il <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">video</a>sulle procedure.</p>
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

**Altre modifiche**

* Il filtro &quot;Consegne con preparazione non riuscita&quot; ora prende in considerazione la data di creazione delle consegne anziché l&#39;ultima data di modifica.
* L&#39;unità organizzativa del gruppo di sicurezza Amministratori non può più essere modificata.
* Quando si crea un profilo, è necessario compilare il campo Unità organizzativa.
* Ora è possibile eliminare un attivatore Experience Cloud Trigger solo se vengono eliminati sia l&#39;evento che il modello transazionale ad esso collegato.

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
