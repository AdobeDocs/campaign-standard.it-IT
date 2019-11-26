---
title: Segmentazione e targeting
description: '"Ulteriori informazioni su profili, targeting e creazione di audience in Campaign: crea tipi di pubblico, importa contatti e condividi i tipi di pubblico con le soluzioni Experience Cloud, evitando affaticamenti di marketing."'
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 13430243e8f2840ca85e557798168f6380a7b0fa

---


# Segmentazione e targeting{#segmentation-and-targeting}

## Profili {#profiles}

Utilizza il modello dati flessibile di Adobe Campaign per arricchire i dati del profilo cliente e aggiungere nuovi attributi o tabelle. Quindi, usa questi profili cliente per segmentazione, personalizzazione e reporting più precisi.

I profili di Adobe Campaign rappresentano tutti i contatti memorizzati nel database. Ogni profilo corrisponde a una voce nel database che contiene le informazioni necessarie affinché il profilo sia mirato, qualificato e monitorato individualmente. Questo significa che un profilo può essere: un cliente, un potenziale, un singolo iscritto a una newsletter, un destinatario, un utente o qualsiasi altra denominazione a seconda dell’organizzazione.

La funzione profili cliente integra tutti i dati dei clienti in un'unica posizione:

![](assets/mkt_hist_view.png)

Adobe Campaign propone diversi meccanismi per l'acquisizione dei profili: raccolta di dati online tramite pagine [di](../../channels/using/getting-started-with-landing-pages.md)destinazione, meccanismi [di importazione manuali o](../../automating/using/about-data-import-and-export.md)automatizzati, input [](../../audiences/using/creating-profiles.md) diretto nell'interfaccia di Adobe Campaign, creazione in blocco tramite le API [](../../api/using/about-campaign-standard-apis.md)Campaign.

**Argomenti correlati:**

* Scopri i diversi tipi di profili nella sezione [Profili](../../audiences/using/about-profiles.md) .
* Accedi al numero di profili **attivi** nella tua organizzazione in [questa sezione](../../audiences/using/active-profiles.md).
* Scoprite come personalizzare i dati, gestire complesse attività di gestione dei dati, come calcoli, aggregati, deduplicazione e unione, utilizzando le funzionalità di targeting dei [flussi di lavoro](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

Per consentirti di inviare messaggi rilevanti ed efficaci e coinvolgere in modo efficace i clienti, Adobe Campaign integra funzionalità avanzate di analisi e targeting. Grazie ai flussi di lavoro e all'editor di query, puoi creare audience che verranno indirizzate alle tue diverse campagne, in base alle informazioni disponibili, alle loro attività, alla lingua, alle preferenze o alla cronologia di marketing. Questo consente di filtrare i profili sottoscritti, ad esempio, o di creare audience target su un numero illimitato di criteri.

Le audience sono presentate [in questa pagina](../../audiences/using/about-audiences.md) e dettagliate nella sezione [Audiences](../../audiences/using/creating-audiences.md) .

**Argomenti correlati:**

* Scopri come raggiungere un pubblico multilingue in più regioni inviando notifiche [push](../../channels/using/creating-a-multilingual-push-notification.md) multilingue o e-mail [multilingue](../../channels/using/creating-a-multilingual-email.md)
* Scopri come [creare query](../../audiences/using/creating-audiences.md#creating-query-audiences) per creare audience
* Scopri come [creare audience](../../audiences/using/creating-audiences.md#creating-list-audiences) di elenchi in un flusso di lavoro
* Scopri come [importare un'audience da un file](../../audiences/using/creating-audiences.md#creating-file-audiences) in un flusso di lavoro
* Scopri come [condividere i tipi di pubblico](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) con le soluzioni Experience Cloud

## Regolamento generale sulla protezione dei dati {#general-data-protection-regulation}

Il GDPR è la nuova legge dell’Unione europea sulla privacy che armonizza e aggiorna i requisiti in materia di protezione dei dati. Il Regolamento GDPR si applica ai clienti Adobe Campaign che detengono dati per i soggetti dati residenti nell'UE. Oltre alle funzionalità per la privacy già disponibili in Adobe Campaign (compresa la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), stiamo sfruttando questa opportunità in qualità di Data Processor per includere funzionalità aggiuntive, al fine di facilitare la tua disponibilità come Data Controller per determinate richieste GDPR.

Fai riferimento a questa [guida](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) per saperne di più sugli strumenti e le funzionalità forniti da Adobe Campaign per aiutarti a diventare conforme ai requisiti GDPR.

## Gestione della fatica {#fatigue-management}

Le regole di Fatigue consentono agli esperti di marketing di impostare regole di business globali tra canali che escluderanno automaticamente i profili richiesti in eccesso dalle campagne.

Per implementare le regole di affaticamento, è necessario definire un numero massimo di messaggi per profilo e selezionare un periodo in cui applicare la regola. Durante la preparazione della consegna, i profili sono esclusi dalla consegna, se applicabile, a seconda del numero di messaggi già inviati.

**Argomenti correlati:**

* Scopri come [progettare regole](../../administration/using/fatigue-rules.md#examples) di affaticamento tramite un set di esempi
* Scopri come creare regole di [tipologia](../../administration/using/about-typology-rules.md)
* Utilizza le regole [del](../../administration/using/filtering-rules.md) filtro per migliorare il pubblico dei messaggi
