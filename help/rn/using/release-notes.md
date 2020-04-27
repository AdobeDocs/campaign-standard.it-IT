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
source-git-commit: b4cbc56973a57cde8af6cefa9ff89c7d29ab7b79

---


# Ultima versione{#latest-release}

[Release Planning](../../rn/using/release-planning.md) | Rilasci [del Pannello di](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) controllo| Aggiornamenti [alla](../../rn/using/documentation-updates.md) documentazione| [Note](../../rn/using/release-notes-2020.md) sulla versione precedente| Funzioni [obsolete](../../rn/using/deprecated-features.md)

## Rilascio 20.3 - maggio 2020 {#release-20-3---may-2020}

**Novità?**

<table> 
<thead> 
<tr> 
<th> <strong>Legge tailandese sulla protezione dei dati personali (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>Il Personal Data Protection Act (PDPA) della Thailandia è la nuova legge sulla privacy che armonizza e aggiorna i requisiti di protezione dei dati per la Thailandia. Questo regolamento si applica ai clienti Adobe Campaign che detengono i dati per gli oggetti Data che risiedono in questo paese.</p>
<p>Oltre alle funzionalità per la privacy già disponibili in Adobe Campaign (compresa la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), stiamo colta l'opportunità per includere funzionalità aggiuntive, per facilitare la preparazione del PDF da parte dell'utente:</p>
<ul>
<li>Diritto di accesso e Diritto di eliminazione: stiamo sfruttando le funzionalità aggiunte per il GDPR e il CCPA. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">Ulteriori informazioni</a> </li>
<li><p>Durante la creazione di una richiesta per la privacy, il tipo di regolamento PDPA è stato aggiunto nel servizio di base per la privacy. Questo metodo è quello da utilizzare per tutte le richieste di accesso ed eliminazione. L'utilizzo dell'API e dell'interfaccia di Campaign per le richieste di accesso ed eliminazione è obsoleto.  Consultate l'articolo <a href="../../rn/using/deprecated-features.md">Funzioni</a>obsolete e rimosse.</p></li>
</ul>
<p>Fate riferimento al <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">video</a>dimostrativo.</p>
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
  <td> <p>L'attività API <strong></strong> esterna è in fase di transizione dalla versione beta a GA. Questa versione offre ulteriore flessibilità al parser del corpo di risposta JSON. È ora possibile:</p>
<ul>
<li>analizzare un JSON nidificato con una profondità massima di 10 livelli. </li>
<li>analizzare le proprietà selezionate come nodi foglia da un JSON e appiattirle in una singola riga di tabella.</li>
<li>selezionare e utilizzare un oggetto array da un JSON senza dover denominare l'oggetto "data" o farlo essere al livello superiore.</li>
</ul>
<p><strong>Attenzione:</strong> I clienti dovranno <strong>sostituire tutte le attività</strong> Beta External API con le attività GA External API nei loro flussi di lavoro.  I flussi di lavoro che utilizzano la versione beta dell'API esterna cesseranno di funzionare in 20.3.</p>
<p>Per ulteriori informazioni, consultate la documentazione <a href="../../automating/using/external-api.md"></a> dettagliata e il video <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">sulle</a>procedure.</p>
</td> 
</tr> 
</tbody> 
</table>

**Miglioramenti**

* Il numero di caratteri utilizzabili nel campo **Prefisso** per [testare i messaggi tramite i profili](../../sending/using/testing-messages-using-target.md) di destinazione è stato aumentato da 32 a 500 caratteri.
* Il numero massimo di eventi in tempo reale che possono essere pubblicati in un’istanza è stato aumentato da 350 a 2000. (CAMP-41608)
* La sincronizzazione tra Adobe Launch e Campaign Standard è stata migliorata mediante il flusso di lavoro tecnico syncWithLaunch. Questo flusso di lavoro consente l&#39;importazione automatica di tutte le proprietà mobili di Adobe Launch in Adobe Campaign Standard. Per ulteriori informazioni, consultare [questa pagina](../../administration/using/technical-workflows.md).

   Dovrai inviare un ticket all&#39;Assistenza clienti Adobe (direttamente o tramite il contatto Adobe) per far sì che il flusso di lavoro tecnico syncWithLaunch sia abilitato nell&#39;istanza Campaign. (CAMP-40082)

**Miglioramenti di Email Designer**

* Designer e-mail ora può gestire una formattazione HTML più flessibile rispetto a W3C rigido. (CAMP-42529)
* È stato risolto un problema relativo alle immagini [](../../designing/using/links.md#inserting-a-link) su cui era possibile fare clic per impedire la visualizzazione dei collegamenti accanto all’immagine nei blocchi di contenuto. (CAMP-41586)
* È stato risolto un problema che impediva il reindirizzamento a una pagina di destinazione quando l’URL [](../../designing/using/links.md#about-tracked-urls) tracciato aveva una categoria aggiunta nel modello. (CAMP-41537)
* È stato risolto un problema relativo alla spaziatura dei pulsanti in Outlook.
* È stato risolto un problema che causava la visualizzazione dei tag HTML in testo normale.
* La ricerca per blocchi di contenuto ora mostra i risultati della ricerca sul server e i risultati precaricati. (CAMP-41870)

**Altre modifiche**

* L&#39;interfaccia di pubblicazione delle risorse personalizzata è stata migliorata con messaggi di errore più chiari.
* Le mappature di distribuzione non utilizzate sono state rimosse dall&#39;interfaccia.
* I ruoli di amministratore non necessari sono stati rimossi dall&#39;interfaccia.
* Le caselle di controllo ora possono essere obbligatorie in una pagina di destinazione.
* Quando si scarica il file CSV di un rapporto dinamico, il limite di 200 righe è stato rimosso. Ora puoi includere ogni riga del rapporto. (CAMP-40810)
* È stata aggiunta la lingua ES-US nell&#39;elenco delle lingue pronte all&#39;uso per le e-mail in più lingue. (CAMP-42279)
* I file scaricati con un&#39;attività di trasferimento file ora verranno eliminati dopo X giorni, dove X è determinato dal campo **Cronologia in giorni** nel menu **Esecuzione** delle proprietà Flusso di lavoro. [Leggi tutto](../../automating/using/executing-a-workflow.md#workflow-properties)

**Integrazioni con la piattaforma Experience**

* L&#39;attivazione di Adobe [Experience Platform Audiences](../../automating/using/aep-targeting-audiences.md) dall&#39;attività di **lettura dell&#39;audience** è stata migliorata per fornire prestazioni e stabilità migliori. Inoltre, i registri del flusso di lavoro sono stati resi più chiari e dettagliati per quanto riguarda i processi di attivazione, consentendo un monitoraggio e una risoluzione più semplici dei problemi durante la lettura dei tipi di pubblico Adobe Experience Platform.

**Patch**

* È stato corretto un errore che causava la creazione di una risorsa fantasma durante il processo di pubblicazione di una risorsa personalizzata.
* È stato risolto un problema che poteva impedire la visualizzazione della cronologia marketing dei profili se la risorsa Profilo era stata estesa con una risorsa personalizzata. (CAMP-41009)
* È stato risolto un problema relativo ai modelli di pagina di destinazione predefiniti che visualizzavano il contenuto in francese all’apertura dell’editor. (CAMP-41639)
* È stato risolto un problema nelle notifiche push con contenuto dinamico che poteva impedire la visualizzazione delle emoticon. (CAMP-40715)
* È stato risolto un problema nell&#39;attività **Deduplicazione** che poteva causare l&#39;assegnazione di un codice di segmento errato a una delle transizioni di complemento in uscita. (CAMP-41400)
* È stato corretto un errore che impediva l&#39;eliminazione dei rapporti pianificati. (CAMP-41302)
* È stato risolto un problema che causava discrepanze tra il dashboard di consegna e il rapporto Riepilogo **** consegna. (CAMP-41145)
* È stato risolto un problema che causava un problema di visualizzazione della sovrapposizione dei caratteri nei rapporti scaricati.
* È stato risolto un problema che impediva il funzionamento dell&#39;anteprima di una consegna per la sostituzione della prova.
* È stato corretto un errore durante l&#39;eliminazione di campi personalizzati di una notifica locale in-app.
* È stato risolto un problema che impediva il funzionamento della funzione charIndex con un&#39;attività di trasferimento **** End **o** File in un flusso di lavoro.
* È stato risolto un problema nei flussi di lavoro che poteva verificarsi quando si utilizzava un&#39;attività di **arricchimento** con due attività di input, tra cui le risorse di destinazione con un collegamento tra di esse. (CAMP-42133)
* È stato risolto un problema che poteva impedire l&#39;esecuzione di un flusso di lavoro quando si utilizzavano funzioni sconosciute. (CAMP-41873)
* È stato risolto un problema nei flussi di lavoro che poteva verificarsi durante la creazione di audience utilizzando diverse attività **Salva audience** con transizioni in uscita complementari. (CAMP-39992)
* È stato risolto un problema che causava discrepanze di dati quando si utilizzava la personalizzazione nelle e-mail transazionali. (CAMP-41842)
* Sono stati risolti i problemi che si verificavano durante l&#39;eliminazione di campi personalizzati nelle consegne di notifiche push. (CAMP-37586)
* È stato corretto un errore che impediva agli utenti di apportare modifiche ai rapporti. (CAMP-42505)
