---
title: Introduzione ai processi e alla gestione dei dati
description: Automatizza i processi con i flussi di lavoro, gestisci dati e tipi di pubblico, invia messaggi e altro ancora.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: 26be942a-c252-458f-a590-eb235567ca67
TQID: https://experienceleague.adobe.com/iTJyQV-76oRhjJ4vDLKfSMpYTA27UcYt9UmVW-9YVq4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
  - id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2:
  - id: b5f0aaf4-1e48-400d-95ac-6eb3078cf22f
  - id: f5293531-9312-4099-bfa3-9e67df6a8750
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 520
ht-degree: 21%

---

# Introduzione ai processi e alla gestione dei dati {#get-started-processes-data-management}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_workflows.svg" width="60px"><p><a href="#workflow-activities">Attività dei flussi di lavoro</a></p></td><td><img src="assets/do-not-localize/icon_activities.svg" width="60px"><p><a href="../../automating/using/workflow-created-query-with-complement.md">Casi d’uso</a></p></td><td><img src="assets/do-not-localize/icon_filter.svg" width="60px"><p><a href="#filter-data">Filtrare i dati</a></p></td>
<td><img src="assets/do-not-localize/icon_manage.svg" width="60px"><p><a href="#import-export-data">Importare/esportare dati</a></p></td></tr>
</table>

Adobe Campaign offre un ambiente grafico completo che consente di progettare processi complessi, tra cui segmentazione, esecuzione di campagne, elaborazione di file, ecc. È ad esempio possibile utilizzare un flusso di lavoro per scaricare un file da un server, decomprimerlo e quindi importare i record nel database di Adobe Campaign.

I flussi di lavoro possono essere utilizzati in contesti diversi, ad esempio:

* Targeting per gestire il pubblico o inviare messaggi.
* Gestione dei dati (ETL) per manipolare i dati.
* Importazione dei dati nel database di Campaign.
* Processi tecnici come la pulizia del database, il recupero delle informazioni di tracciamento, eccetera.

>[!IMPORTANT]
>
> Adobe consiglia ai clienti di non eseguire più di 20 esecuzioni di flussi di lavoro attivi in contemporanea, nonché di assegnare priorità e distribuire l’esecuzione dei flussi di lavoro nel tempo. Per ulteriori informazioni, consulta le best practice fornite in [questa pagina](../../automating/using/best-practices-workflows.md).

## Attività del flussi di lavoro {#workflow-activities}

Sono disponibili varie attività per aiutarti a progettare i flussi di lavoro.

[Le attività di targeting](../../automating/using/about-targeting-activities.md) ti consentono di creare una o più destinazioni definendo i set e suddividendoli o combinandoli tramite operazioni di intersezione, unione o esclusione.

Con [Attività di esecuzione](../../automating/using/about-execution-activities.md), coordina il flusso di lavoro e le relative attività, mentre [Attività canale](../../automating/using/about-channel-activities.md) ti consente di combinare i canali di comunicazione di Campaign Standard per creare flussi di lavoro cross-channel.

Infine, le [attività di gestione dati](../../automating/using/about-data-management-activities.md) ti consentono di manipolare i dati dal database.

Ulteriori informazioni:

* [Creazione di un flusso di lavoro](../../automating/using/building-a-workflow.md)
* [Esecuzione di un flusso di lavoro](../../automating/using/about-workflow-execution.md)
* [Best practice per i flussi di lavoro](../../automating/using/best-practices-workflows.md)

## Filtrare i dati {#filter-data}

Sfrutta l&#39;**editor query** per filtrare i dati dal database e creare una popolazione per eseguire meglio il targeting dei destinatari. L’editor delle query è disponibile per eseguire diverse azioni in Campaign Standard: creare tipi di pubblico di tipo Query, definire target di consegna o popolazioni nelle attività del flusso di lavoro.

L&#39;editor delle query viene fornito con **filtri e regole predefiniti** per un filtro rapido e semplice. Tuttavia, puoi anche utilizzare le funzionalità di **modifica avanzata delle espressioni**. Ciò ti consente di inserire manualmente le condizioni e utilizzare le funzioni, al fine di creare regole personalizzate.

Ulteriori informazioni:

* [Modifica delle query](../../automating/using/editing-queries.md)
* [Modifica avanzata delle espressioni](../../automating/using/advanced-expression-editing.md)
* [Elenco delle funzioni](../../automating/using/list-of-functions.md)

## Importare/esportare dati {#import-export-data}

Campaign Standard include diverse **funzionalità di gestione dati** per importare ed esportare dati.

[Le attività di gestione dei dati dei flussi di lavoro](../../automating/using/about-data-management-activities.md) consentono di importare dati, eseguire aggiornamenti di massa sui campi, ricevere o inviare file oppure collegare dati non identificati a risorse esistenti.

Con [Modelli di importazione](../../automating/using/importing-data-with-import-templates.md), gestisci alcuni tipi di importazione definiti dagli amministratori tramite funzioni di importazione semplificate.

[L&#39;esportazione dei registri](../../automating/using/exporting-logs.md) consente di esportare i dati dei registri tramite un semplice flusso di lavoro, che consente di analizzare i risultati delle campagne di marketing nei propri strumenti di reporting o BI.

Sfrutta [Pacchetti](../../automating/using/managing-packages.md) per scambiare risorse tra diverse istanze di Campaign, ad esempio per replicare la configurazione di un&#39;istanza o per trasferire dati da un server a un altro, incluse risorse personalizzate.

Infine, [Esportazione di elenchi](../../automating/using/exporting-lists.md) ti consente di esportare qualsiasi elenco da Campaign Standard, ad esempio l&#39;elenco dei profili di test, l&#39;elenco degli indirizzi e-mail di quarantena e così via.

Ulteriori informazioni:

* [Importazione ed esportazione di dati](../../automating/using/about-data-import-and-export.md)
* [Caso di utilizzo: esportazione/importazione di risorse personalizzate](../../automating/using/exporting-importing-custom-resources.md)

## Risorse aggiuntive

* [Video tutorial su processi e gestione dati](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/managing-processes-and-data/creating-a-workflow.html?lang=it)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Introduzione al modello dati di Campaign Standard](../../developing/using/get-started-data-model.md)
