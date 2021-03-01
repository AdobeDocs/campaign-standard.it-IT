---
solution: Campaign Standard
product: campaign
title: Guida introduttiva ai processi e alla gestione dei dati
description: Automatizza i processi con i flussi di lavoro, gestisci dati e tipi di pubblico, invia messaggi e altro ancora.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '519'
ht-degree: 13%

---


# Guida introduttiva ai processi e alla gestione dei dati {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Attività flusso di lavoro</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casi d’uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrare i dati</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importazione/esportazione di dati</a></p></td></tr>
</table>

 Adobe Campaign offre un ambiente grafico completo che consente di progettare processi complessi, tra cui segmentazione, esecuzione delle campagne, elaborazione dei file, ecc. Ad esempio, puoi utilizzare un flusso di lavoro per scaricare un file da un server, decomprimerlo e quindi importarne i record nel database di Adobe Campaign.

Un flusso di lavoro può coinvolgere anche gli utenti assegnando loro le attività o facendo loro approvare le attività eseguite. Questo significa che potete assegnare un’attività a uno o più utenti per lavorare sul contenuto o specificare le destinazioni, e approvare le prove prima di inviare il messaggio.

I flussi di lavoro possono essere utilizzati in contesti diversi, ad esempio:

* Targeting per gestire i tipi di pubblico o inviare messaggi.
* Gestione dei dati (ETL) per manipolare i dati.
* Importazione di dati nel database Campaign.
* Processi tecnici come pulizia del database, recupero delle informazioni di tracciamento, ecc.

## Attività del flusso di lavoro {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Sono disponibili diverse attività per aiutarti a progettare i flussi di lavoro.

[Le ](../../automating/using/about-targeting-activities.md) attività di targeting consentono di creare uno o più target definendo set e dividendo o combinando questi set mediante operazioni di intersezione, unione o esclusione.

Con [Attività di esecuzione](../../automating/using/about-execution-activities.md), coordinare il flusso di lavoro e le attività, mentre [Attività canale](../../automating/using/about-channel-activities.md) consente di combinare canali di comunicazione Campaign Standard per creare flussi di lavoro tra canali.

Infine, le [attività di gestione dei dati](../../automating/using/about-data-management-activities.md) consentono di manipolare i dati dal database.

Leggi tutto:

* [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)
* [Esecuzione di un flusso di lavoro](../../automating/using/about-workflow-execution.md)
* [Procedure consigliate per i flussi di lavoro](../../automating/using/best-practices-workflows.md)

## Dati filtro {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Sfruttate l&#39; **editor di query** per filtrare i dati dal database e creare una popolazione in modo da indirizzare meglio i destinatari. L&#39;editor di query è disponibile per eseguire diverse azioni in Campaign Standard: creare tipi di pubblico di query, definire target di consegna o popolazioni nelle attività del flusso di lavoro.

L&#39;editor di query viene fornito con **filtri e regole predefiniti** per un filtraggio rapido e semplice. Tuttavia, è anche possibile utilizzare le funzionalità di modifica delle espressioni avanzate ****. Questo consente di inserire manualmente le condizioni e utilizzare le funzioni, al fine di formare le proprie regole.

Leggi tutto:

* [Modifica delle query](../../automating/using/editing-queries.md)
* [Modifica avanzata delle espressioni](../../automating/using/advanced-expression-editing.md)
* [Elenco delle funzioni](../../automating/using/list-of-functions.md)

## Importa/esporta dati {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard viene fornito con diverse **funzionalità di gestione dei dati** per importare ed esportare i dati.

[Le ](../../automating/using/about-data-management-activities.md) attività di gestione dei dati dei flussi di lavoro consentono di importare dati, eseguire aggiornamenti di massa sui campi, ricevere o inviare file o collegare dati non identificati a risorse esistenti.

Con [Importa modelli](../../automating/using/importing-data-with-import-templates.md), puoi gestire alcuni tipi di importazione definiti dagli amministratori tramite funzioni di importazione semplificate.

[L’esportazione dei ](../../automating/using/exporting-logs.md) log consente di esportare i dati di log tramite un semplice flusso di lavoro, per analizzare i risultati delle campagne di marketing con i propri strumenti di reporting o BI.

Utilizzate [Packages](../../automating/using/managing-packages.md) per scambiare risorse tra diverse istanze di campagne, ad esempio per replicare la configurazione di un&#39;istanza o per trasferire dati da un server a un altro, incluse le risorse personalizzate.

Infine, [Esportazione di elenchi](../../automating/using/exporting-lists.md) consente di esportare qualsiasi elenco da Campaign Standard, ad esempio l&#39;elenco dei profili di test, l&#39;elenco degli indirizzi e-mail delle quarantena e così via.

Leggi tutto:

* [Importazione ed esportazione di dati](../../automating/using/about-data-import-and-export.md)
* [Caso di utilizzo: esportazione/importazione di risorse personalizzate](../../automating/using/exporting-importing-custom-resources.md)

## Risorse aggiuntive

* [Video di esercitazione su processi e gestione dati](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Guida introduttiva al modello dati di Campaign Standard](../../developing/using/get-started-data-model.md)
