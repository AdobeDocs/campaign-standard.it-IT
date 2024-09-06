---
title: Introduzione ai processi e alla gestione dei dati
description: Automatizza i processi con i flussi di lavoro, gestisci dati e tipi di pubblico, invia messaggi e altro ancora.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
role: Data Architect
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
source-git-commit: 47f47a624b8a1d941d1ab4b49e67f0260ac68cf1
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 26%

---

# Introduzione ai processi e alla gestione dei dati {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Attività del flussi di lavoro</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casi d’uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrare i dati</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importare/esportare dati</a></p></td></tr>
</table>

Adobe Campaign offre un ambiente grafico completo che ti consente di progettare processi complessi, tra cui segmentazione, esecuzione di campagne, elaborazione di file, eccetera. Ad esempio, puoi utilizzare un flusso di lavoro per scaricare un file da un server, decomprimerlo e quindi importare i record nel database di Adobe Campaign.

I flussi di lavoro possono essere utilizzati in contesti diversi, ad esempio:

* Targeting per gestire il pubblico o inviare messaggi.
* Gestione dei dati (ETL) per manipolare i dati.
* Importazione dei dati nel database di Campaign.
* Processi tecnici come la pulizia del database, il recupero delle informazioni di tracciamento, eccetera.

>[!IMPORTANT]
>
> L’Adobe consiglia ai clienti di non eseguire più di 20 esecuzioni di flussi di lavoro attivi contemporaneamente e di assegnare le priorità e distribuire l’esecuzione del flusso di lavoro nel tempo. Per ulteriori informazioni, consulta le best practice fornite in [questa pagina](../../automating/using/best-practices-workflows.md).

## Attività del flussi di lavoro {#workflow-activities}

<img src="assets/do-not-localize/icon_workflows.svg" width="10%px">

Sono disponibili varie attività per aiutarti a progettare i flussi di lavoro.

[Le attività di targeting](../../automating/using/about-targeting-activities.md) ti consentono di creare una o più destinazioni definendo i set e suddividendoli o combinandoli tramite operazioni di intersezione, unione o esclusione.

Con [Attività di esecuzione](../../automating/using/about-execution-activities.md), coordina il flusso di lavoro e le relative attività, mentre [Attività canale](../../automating/using/about-channel-activities.md) ti consente di combinare i canali di comunicazione Campaign Standard per creare flussi di lavoro cross-channel.

Infine, le [attività di gestione dati](../../automating/using/about-data-management-activities.md) ti consentono di manipolare i dati dal database.

Ulteriori informazioni:

* [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)
* [Esecuzione di un flusso di lavoro](../../automating/using/about-workflow-execution.md)
* [Best practice per i flussi di lavoro](../../automating/using/best-practices-workflows.md)

## Filtrare i dati {#filter-data}

<img src="assets/do-not-localize/icon_filter.svg" width="60px">

Sfrutta l&#39;**editor query** per filtrare i dati dal database e creare una popolazione per eseguire meglio il targeting dei destinatari. L’editor delle query è disponibile per eseguire diverse azioni in Campaign Standard: creare tipi di pubblico di tipo Query, definire target di consegna o popolazioni nelle attività del flusso di lavoro.

L&#39;editor delle query viene fornito con **filtri e regole predefiniti** per un filtro rapido e semplice. Tuttavia, puoi anche utilizzare le funzionalità di **modifica avanzata delle espressioni**. Ciò ti consente di inserire manualmente le condizioni e utilizzare le funzioni, al fine di creare regole personalizzate.

Ulteriori informazioni:

* [Modifica delle query](../../automating/using/editing-queries.md)
* [Modifica avanzata delle espressioni](../../automating/using/advanced-expression-editing.md)
* [Elenco delle funzioni](../../automating/using/list-of-functions.md)

## Importare/esportare dati {#import-export-data}

<img src="assets/do-not-localize/icon_manage.svg" width="60px">

Campaign Standard include diverse **funzionalità di gestione dati** per importare ed esportare dati.

[Le attività di gestione dei dati dei flussi di lavoro](../../automating/using/about-data-management-activities.md) consentono di importare dati, eseguire aggiornamenti di massa sui campi, ricevere o inviare file oppure collegare dati non identificati a risorse esistenti.

Con [Modelli di importazione](../../automating/using/importing-data-with-import-templates.md), gestisci alcuni tipi di importazione definiti dagli amministratori tramite funzioni di importazione semplificate.

[L&#39;esportazione dei registri](../../automating/using/exporting-logs.md) consente di esportare i dati dei registri tramite un semplice flusso di lavoro, che consente di analizzare i risultati delle campagne di marketing nei propri strumenti di reporting o BI.

Sfrutta [Pacchetti](../../automating/using/managing-packages.md) per scambiare risorse tra diverse istanze di Campaign, ad esempio per replicare la configurazione di un&#39;istanza o per trasferire dati da un server a un altro, incluse risorse personalizzate.

Infine, [Esportazione di elenchi](../../automating/using/exporting-lists.md) consente di esportare qualsiasi elenco da Campaign Standard, ad esempio l&#39;elenco dei profili di test, l&#39;elenco degli indirizzi e-mail di quarantena e così via.

Ulteriori informazioni:

* [Importazione ed esportazione di dati](../../automating/using/about-data-import-and-export.md)
* [Caso di utilizzo: esportazione/importazione di risorse personalizzate](../../automating/using/exporting-importing-custom-resources.md)

## Risorse aggiuntive

* [Video tutorial su processi e gestione dati](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=it)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Introduzione al modello dati di Campaign Standard](../../developing/using/get-started-data-model.md)
