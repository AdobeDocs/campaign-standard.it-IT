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
source-git-commit: c4500832b87e986cdbbbf72b9b8c0591f64f7da8

---


# Ultima versione{#latest-release}

[Release Planning](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) | Rilasci [del Pannello di](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) controllo| Aggiornamenti [alla](../../rn/using/documentation-updates.md) documentazione| [Note](../../rn/using/release-notes-2019.md) sulla versione precedente| Funzioni [obsolete](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## Rilascio 20.2 - marzo 2020 {#release-20-2---march-2020}

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
>Le funzionalità di Adobe Experience Platform di Campaign Standard sono attualmente in versione beta, e potrebbero essere soggette a aggiornamenti frequenti senza preavviso. Consultare la documentazione dettagliata: Connettore [dati della piattaforma](../../administration/using/aep-about-data-connector.md)Experience, Destinazioni [Pubblico](../../audiences/using/aep-about-audience-destinations-service.md)

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