---
title: Guida introduttiva ai processi e alla gestione dei dati
description: Automatizza i processi con flussi di lavoro, gestisci dati e audience, invia messaggi e molto altro.
page-status-flag: never-activated
uuid: 7c1e8cea-90d0-491f-ab8f-6cd69f8a6c3b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 40503917-7a53-4d99-96a4-57aa9e98ec87
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 11%

---


# Guida introduttiva ai processi e alla gestione dei dati {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Attività flusso di lavoro</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casi d’uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrare i dati</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importazione/esportazione di dati</a></p></td></tr>
</table>

 Adobe Campaign offre un ambiente grafico completo che consente di progettare processi complessi, tra cui segmentazione, esecuzione delle campagne, elaborazione dei file, ecc. Ad esempio, potete utilizzare un flusso di lavoro per scaricare un file da un server, decomprimerlo e quindi importare i relativi record nel database Adobe Campaign .

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

Con le attività [di](../../automating/using/about-execution-activities.md)esecuzione, coordinate il flusso di lavoro e le relative attività, mentre le attività [di](../../automating/using/about-channel-activities.md) canale consentono di combinare canali di comunicazione Campaign Standard per creare flussi di lavoro multicanale.

Infine, le attività [di gestione dei](../../automating/using/about-data-management-activities.md) dati consentono di manipolare i dati dal database.

Leggi tutto:

* [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)
* [Esecuzione di un flusso di lavoro](../../automating/using/about-workflow-execution.md)
* [Procedure consigliate per i flussi di lavoro](../../automating/using/best-practices-workflows.md)

## Filtrare i dati {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Sfruttate l&#39;editor **di** query per filtrare i dati dal database e creare una popolazione in modo da indirizzare meglio i destinatari. L&#39;editor di query è disponibile per eseguire diverse azioni in Campaign Standard: creare tipi di pubblico di query, definire target di consegna o popolazioni nelle attività del flusso di lavoro.

L&#39;editor di query include filtri e regole **** predefiniti per un filtraggio rapido e semplice. Tuttavia, potete anche utilizzare funzionalità di modifica **delle espressioni** avanzate. Questo consente di inserire manualmente le condizioni e utilizzare le funzioni, al fine di formare le proprie regole.

Leggi tutto:

* [Modifica delle query](../../automating/using/editing-queries.md)
* [Modifica avanzata delle espressioni](../../automating/using/advanced-expression-editing.md)
* [Elenco delle funzioni](../../automating/using/list-of-functions.md)

## Importazione/esportazione di dati {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard viene fornito con diverse funzionalità **di gestione** dei dati per importare ed esportare i dati.

[Le attività](../../automating/using/about-data-management-activities.md) di gestione dei dati dei flussi di lavoro consentono di importare dati, eseguire aggiornamenti di massa sui campi, ricevere o inviare file o collegare dati non identificati a risorse esistenti.

Con i modelli [di](../../automating/using/importing-data-with-import-templates.md)importazione, gestite alcuni tipi di importazione definiti dagli amministratori tramite funzioni di importazione semplificate.

[I registri](../../automating/using/exporting-logs.md) di esportazione consentono di esportare i dati di registro attraverso un semplice flusso di lavoro, consentendo di analizzare i risultati delle campagne di marketing con i propri strumenti di reporting o BI.

Sfruttate [i pacchetti](../../automating/using/managing-packages.md) per scambiare risorse tra diverse istanze di campagne, ad esempio per replicare la configurazione di un&#39;istanza o per trasferire dati da un server a un altro, incluse le risorse personalizzate.

Infine, [Esportazione di elenchi](../../automating/using/exporting-lists.md) consente di esportare qualsiasi elenco da Campaign Standard, ad esempio l’elenco dei profili di test, l’elenco degli indirizzi e-mail delle quarantena e così via.

Leggi tutto:

* [Importazione ed esportazione di dati](../../automating/using/about-data-import-and-export.md)
* [Caso di utilizzo: esportazione/importazione di risorse personalizzate](../../automating/using/exporting-importing-custom-resources.md)

## Risorse aggiuntive

* [Video di esercitazione su processi e gestione dati](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Guida introduttiva al modello dati di Campaign Standard](../../developing/using/get-started-data-model.md)
