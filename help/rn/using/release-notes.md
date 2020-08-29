---
title: Ultima versione
description: Questa pagina elenca tutte le versioni recenti di Adobe Campaign Standard.
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
source-git-commit: f45985c030c3d5059bfef444287c10b842298f49
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 90%

---


# Ultima versione{#latest-release}

[Pianificazione del rilascio](../../rn/using/release-planning.md) | [Versioni del Pannello di controllo Campaign](https://docs.adobe.com/content/help/it-IT/control-panel/using/release-notes.html) | [Aggiornamenti alla documentazione](../../rn/using/documentation-updates.md) | [Note sulla versione precedenti](../../rn/using/release-notes-2020.md) | [Funzioni obsolete](../../rn/using/deprecated-features.md)

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
