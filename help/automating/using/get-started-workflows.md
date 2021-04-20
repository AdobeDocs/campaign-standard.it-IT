---
solution: Campaign Standard
product: campaign
title: Guida introduttiva ai processi e alla gestione dei dati
description: Automatizza i processi con i flussi di lavoro, gestisci dati e tipi di pubblico, invia messaggi e altro ancora.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 13%

---


# Guida introduttiva ai processi e alla gestione dei dati {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Attività del flusso di lavoro</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casi d’uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrare i dati</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importare/esportare dati</a></p></td></tr>
</table>

Adobe Campaign offre un ambiente grafico completo che ti consente di progettare processi complessi, tra cui segmentazione, esecuzione di campagne, elaborazione di file, ecc. Ad esempio, puoi utilizzare un flusso di lavoro per scaricare un file da un server, decomprimerlo e quindi importarne i record nel database di Adobe Campaign.

Un flusso di lavoro può coinvolgere anche gli utenti assegnando loro attività o facendogli approvare le attività eseguite. Ciò significa che puoi assegnare un’attività a uno o più utenti per lavorare sul contenuto o specificare destinazioni e approvare le bozze prima di inviare il messaggio.

I flussi di lavoro possono essere utilizzati in contesti diversi, ad esempio:

* Targeting per gestire il pubblico o inviare messaggi.
* Gestione dei dati (ETL) per manipolare i dati.
* Importazione di dati nel database Campaign.
* Processi tecnici come la pulizia del database, il recupero delle informazioni di tracciamento, ecc.

## Attività del flusso di lavoro {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Sono disponibili varie attività per aiutarti a progettare i flussi di lavoro.

[Le ](../../automating/using/about-targeting-activities.md) attività di targeting ti consentono di creare uno o più target definendo i set e suddividendo o combinando questi set utilizzando le operazioni di intersezione, unione o esclusione.

Con [Attività di esecuzione](../../automating/using/about-execution-activities.md), coordina il flusso di lavoro e le relative attività, mentre [Attività canale](../../automating/using/about-channel-activities.md) consente di combinare canali di comunicazione Campaign Standard per creare flussi di lavoro cross-channel.

Infine, [Le attività di gestione dati](../../automating/using/about-data-management-activities.md) ti consentono di manipolare i dati dal database.

Leggi tutto:

* [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)
* [Esecuzione di un flusso di lavoro](../../automating/using/about-workflow-execution.md)
* [Procedure consigliate per i flussi di lavoro](../../automating/using/best-practices-workflows.md)

## Filtra dati {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Sfrutta l’ **editor di query** per filtrare i dati dal database e generare una popolazione per eseguire il targeting migliore dei destinatari. L’editor delle query è disponibile per eseguire diverse azioni in Campaign Standard: crea tipi di pubblico di tipo query, definisci target di consegna o popolazioni nelle attività del flusso di lavoro.

L&#39;editor delle query viene fornito con **filtri e regole predefiniti** per un filtraggio rapido e semplice. Tuttavia, puoi anche utilizzare le funzionalità di modifica delle espressioni avanzate **.** Questo ti consente di inserire manualmente le condizioni e utilizzare le funzioni, al fine di creare le tue regole.

Leggi tutto:

* [Modifica delle query](../../automating/using/editing-queries.md)
* [Modifica avanzata delle espressioni](../../automating/using/advanced-expression-editing.md)
* [Elenco delle funzioni](../../automating/using/list-of-functions.md)

## Importare/esportare dati {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard offre diverse funzionalità di **gestione dati** per importare ed esportare dati.

[Le ](../../automating/using/about-data-management-activities.md) attività di gestione dei dati dei flussi di lavoro consentono di importare dati, eseguire aggiornamenti di massa sui campi, ricevere o inviare file o collegare dati non identificati a risorse esistenti.

Con [Modelli di importazione](../../automating/using/importing-data-with-import-templates.md), gestisci alcuni tipi di importazione definiti dagli amministratori tramite funzioni di importazione semplificate.

[L’esportazione dei ](../../automating/using/exporting-logs.md) registri consente di esportare i dati di registro tramite un flusso di lavoro semplice, che consente di analizzare i risultati delle campagne di marketing nei propri strumenti di reporting o BI.

Sfrutta [Pacchetti](../../automating/using/managing-packages.md) per scambiare risorse tra diverse istanze della campagna, ad esempio per replicare la configurazione di un&#39;istanza o per trasferire dati da un server a un altro, incluse le risorse personalizzate.

Infine, [Esportazione di elenchi](../../automating/using/exporting-lists.md) consente di esportare qualsiasi elenco da Campaign Standard, ad esempio l’elenco dei profili di test, l’elenco degli indirizzi e-mail delle quarantene e così via.

Leggi tutto:

* [Importazione ed esportazione di dati](../../automating/using/about-data-import-and-export.md)
* [Caso di utilizzo: esportazione/importazione di risorse personalizzate](../../automating/using/exporting-importing-custom-resources.md)

## Risorse aggiuntive

* [Video tutorial su processi e gestione dati](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/getting-started/create-workflow.html)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Guida introduttiva al modello dati di Campaign Standard](../../developing/using/get-started-data-model.md)
