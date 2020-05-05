---
title: Introduzione a processi e gestione dei dati
description: Adobe Campaign offre un ambiente grafico completo che consente di progettare e automatizzare i processi.
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Introduzione a processi e gestione dei dati {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Attività flusso di lavoro</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casi d’uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrare i dati</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importazione/esportazione di dati</a></p></td></tr>
</table>

Adobe Campaign offre un ambiente grafico completo che consente di progettare processi complessi, tra cui segmentazione, esecuzione delle campagne, elaborazione dei file, approvazioni ecc. Ad esempio, puoi utilizzare un flusso di lavoro per scaricare un file da un server, decomprimerlo e importare i relativi record nel database di Adobe Campaign.

Un flusso di lavoro può coinvolgere anche gli utenti assegnando loro le attività o facendo loro approvare le attività eseguite. Questo significa che potete assegnare un’attività a uno o più utenti per lavorare sul contenuto o specificare le destinazioni, e approvare le prove prima di inviare il messaggio.

I flussi di lavoro possono essere utilizzati in contesti diversi, ad esempio:

* Targeting per gestire i tipi di pubblico o inviare messaggi.
* Gestione dei dati (ETL) per manipolare i dati.
* Importazione di dati nel database Campaign.
* Processi tecnici come pulizia del database, recupero delle informazioni di tracciamento, ecc.

## Attività flusso di lavoro {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Sono disponibili diverse attività per aiutarti a progettare i flussi di lavoro.

[Le attività](../../automating/using/about-targeting-activities.md) di targeting consentono di creare uno o più target definendo set e dividendo o combinando questi set mediante operazioni di intersezione, unione o esclusione.

Con le attività [di](../../automating/using/about-execution-activities.md)esecuzione, coordinate il flusso di lavoro e le relative attività, mentre le attività [di](../../automating/using/about-channel-activities.md) canale consentono di combinare canali di comunicazione Campaign Standard per creare flussi di lavoro tra canali.

Infine, le attività [di gestione dei](../../automating/using/about-data-management-activities.md) dati consentono di manipolare i dati dal database.

Ulteriori informazioni:

* [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)
* [Esecuzione di un flusso di lavoro](../../automating/using/executing-a-workflow.md)
* [Procedure consigliate per i flussi di lavoro](../../automating/using/best-practices-workflows.md)

## Filtrare i dati {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Sfruttate l&#39;editor **di** query per filtrare i dati dal database e creare una popolazione in modo da indirizzare meglio i destinatari. L&#39;editor di query è disponibile per eseguire diverse azioni in Campaign Standard: creare tipi di pubblico di query, definire target di consegna o popolazioni nelle attività del flusso di lavoro.

L&#39;editor di query include filtri e regole **** predefiniti per un filtraggio rapido e semplice. Tuttavia, potete anche utilizzare funzionalità di modifica **delle espressioni** avanzate. Questo consente di inserire manualmente le condizioni e utilizzare le funzioni, al fine di formare le proprie regole.

Ulteriori informazioni:

* [Modifica delle query](../../automating/using/editing-queries.md)
* [Modifica avanzata delle espressioni](../../automating/using/advanced-expression-editing.md)
* [Elenco delle funzioni](../../automating/using/list-of-functions.md)

## Importazione/esportazione di dati {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard include diverse funzionalità **di gestione** dei dati per l&#39;importazione e l&#39;esportazione di dati.

[Le attività](../../automating/using/about-data-management-activities.md) di gestione dei dati dei flussi di lavoro consentono di importare dati, eseguire aggiornamenti di massa sui campi, ricevere o inviare file o collegare dati non identificati a risorse esistenti.

Con i modelli [di](../../automating/using/importing-data-with-import-templates.md)importazione, gestite alcuni tipi di importazione definiti dagli amministratori tramite funzioni di importazione semplificate.

[I registri](../../automating/using/exporting-logs.md) di esportazione consentono di esportare i dati di registro attraverso un semplice flusso di lavoro, consentendo di analizzare i risultati delle campagne di marketing con i propri strumenti di reporting o BI.

Sfruttate [i pacchetti](../../automating/using/managing-packages.md) per scambiare risorse tra diverse istanze di campagne, ad esempio per replicare la configurazione di un&#39;istanza o per trasferire dati da un server a un altro, incluse le risorse personalizzate.

Infine, gli elenchi [di](../../automating/using/exporting-lists.md) esportazione consentono di esportare qualsiasi elenco da Campaign Standard, ad esempio l&#39;elenco dei profili di test, l&#39;elenco degli indirizzi e-mail delle quarantena e così via.

Ulteriori informazioni:

* [Importazione di dati](../../automating/using/importing-data.md)
* [Utilizzo dei dati del flusso di lavoro](../../automating/using/using-workflow-data.md)
* [Caso di utilizzo: esportazione/importazione di risorse personalizzate](../../automating/using/exporting-importing-custom-resources.md)

## Risorse aggiuntive

* [Video di esercitazione su processi e gestione dati](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Introduzione al modello dati Campaign Standard](../../developing/using/get-started-data-model.md)
