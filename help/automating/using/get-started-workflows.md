---
title: Guida introduttiva ai processi e alla gestione dei dati
description: Automatizza i processi con i flussi di lavoro, gestisci dati e tipi di pubblico, invia messaggi e altro ancora.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
source-git-commit: 6ca3ffe3ba2cf7629e511e4ba035b170b25ad79e
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 37%

---

# Guida introduttiva ai processi e alla gestione dei dati {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Attività del flusso di lavoro</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casi d’uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrare i dati</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importare/esportare dati</a></p></td></tr>
</table>

Adobe Campaign offre un ambiente grafico completo che ti consente di progettare processi complessi, tra cui segmentazione, esecuzione di campagne, elaborazione di file, eccetera. Ad esempio, puoi utilizzare un flusso di lavoro per scaricare un file da un server, decomprimerlo e quindi importare i record nel database di Adobe Campaign.

Un flusso di lavoro può coinvolgere anche gli utenti, assegnando loro attività o facendogli approvare le attività eseguite. Ciò significa che puoi assegnare un’attività a uno o più utenti affinché lavorino sul contenuto oppure specificare destinazioni e approvare le bozze prima di inviare il messaggio.

I flussi di lavoro possono essere utilizzati in contesti diversi, ad esempio:

* Targeting per gestire il pubblico o inviare messaggi.
* Gestione dei dati (ETL) per manipolare i dati.
* Importazione dei dati nel database di Campaign.
* Processi tecnici come la pulizia del database, il recupero delle informazioni di tracciamento, eccetera.

>[!IMPORTANT]
>
> Adobe consiglia ai clienti di non eseguire più di 20 esecuzioni di flussi di lavoro attivi contemporaneamente e di assegnare priorità e distribuire l’esecuzione del flusso di lavoro nel tempo. Per ulteriori informazioni, consulta le best practice fornite in [questa pagina](../../automating/using/best-practices-workflows.md).

## Attività del flusso di lavoro {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="60px">

Sono disponibili varie attività per aiutarti a progettare i flussi di lavoro.

[Attività di targeting](../../automating/using/about-targeting-activities.md) consente di creare uno o più target definendo i set e suddividendo o combinando questi set utilizzando le operazioni di intersezione, unione o esclusione.

Con [Attività di esecuzione](../../automating/using/about-execution-activities.md), coordina il flusso di lavoro e le relative attività, mentre [Attività dei canali](../../automating/using/about-channel-activities.md) consente di combinare canali di comunicazione Campaign Standard per creare flussi di lavoro cross-channel.

Infine, [Attività di gestione dati](../../automating/using/about-data-management-activities.md) consente di manipolare i dati dal database.

Maggiori informazioni:

* [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)
* [Esecuzione di un flusso di lavoro](../../automating/using/about-workflow-execution.md)
* [Best practice per i flussi di lavoro](../../automating/using/best-practices-workflows.md)

## Filtrare i dati {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Sfruttare **editor di query** per filtrare i dati dal database e creare una popolazione con cui eseguire il targeting migliore dei destinatari. L’editor delle query è disponibile per eseguire diverse azioni in Campaign Standard: crea tipi di pubblico di tipo query, definisci target di consegna o popolazioni nelle attività del flusso di lavoro.

L’editor delle query viene fornito con **filtri e regole predefiniti** per un filtraggio rapido e semplice. Tuttavia, puoi anche utilizzare **modifica avanzata delle espressioni** funzionalità. Questo ti consente di inserire manualmente le condizioni e utilizzare le funzioni, al fine di creare le tue regole.

Maggiori informazioni:

* [Modifica delle query](../../automating/using/editing-queries.md)
* [Modifica avanzata delle espressioni](../../automating/using/advanced-expression-editing.md)
* [Elenco delle funzioni](../../automating/using/list-of-functions.md)

## Importare/esportare dati {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard viene fornito con diversi **funzionalità di gestione dati** per importare ed esportare dati.

[Attività di gestione dati flussi di lavoro](../../automating/using/about-data-management-activities.md) consente di importare dati, eseguire aggiornamenti di massa sui campi, ricevere o inviare file o collegare dati non identificati a risorse esistenti.

Con [Importare modelli](../../automating/using/importing-data-with-import-templates.md), gestisci alcuni tipi di importazione definiti dagli amministratori tramite funzioni di importazione semplificate.

[Esportazione dei registri](../../automating/using/exporting-logs.md) consente di esportare i dati di registro tramite un flusso di lavoro semplice, che consente di analizzare i risultati delle campagne di marketing nei propri strumenti di reporting o BI.

Sfruttamento [Pacchetti](../../automating/using/managing-packages.md) per scambiare risorse tra diverse istanze della campagna, ad esempio per replicare la configurazione di un’istanza o per trasferire dati da un server a un altro, incluse le risorse personalizzate.

Infine, [Esportazione di elenchi](../../automating/using/exporting-lists.md) consente di esportare qualsiasi elenco da Campaign Standard, ad esempio l’elenco dei profili di test, l’elenco degli indirizzi e-mail della quarantena e così via.

Maggiori informazioni:

* [Importazione ed esportazione di dati](../../automating/using/about-data-import-and-export.md)
* [Caso di utilizzo: esportazione/importazione di risorse personalizzate](../../automating/using/exporting-importing-custom-resources.md)

## Risorse aggiuntive

* [Video tutorial su processi e gestione dati](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=it)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Introduzione al modello dati di Campaign Standard](../../developing/using/get-started-data-model.md)
