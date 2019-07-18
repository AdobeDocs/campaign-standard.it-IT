---
title: Segmentazione e targeting
seo-title: Segmentazione e targeting
description: Segmentazione e targeting
seo-description: '" Informazioni su profili, targeting e creazione di audience in Campaign: creare audience, importare tipi di pubblico con le soluzioni Experience Cloud ed evitare l''affaticamento di marketing. "'
page-status-flag: never-activated
uuid: 71 f 53808-0309-49 f 6-a 4 ee -3446 eac 9758 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: riferimento
topic-tags: about-adobe-campaign
discoiquuid: d 8 c 8 a 318-9433-4 aec-b 378-fd 0 beb 50 e 9 fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Segmentation and targeting{#segmentation-and-targeting}

## Profiles {#profiles}

Usa il modello dati flessibile di Adobe Campaign per arricchire i dati del profilo cliente e aggiungere nuovi attributi o tabelle. Quindi, usa questi profili cliente per segmentazione, personalizzazione e reporting più precisi.

I profili Adobe Campaign rappresentano tutti i contatti archiviati nel database. Ogni profilo corrisponde a una voce nel database contenente le informazioni necessarie per il targeting, la qualifica e il tracciamento individuale del profilo. Ciò significa che un profilo può essere: un client, un prospect, una singola sottoscrizione a una newsletter, un destinatario, un utente o qualsiasi altra denominazione a seconda dell'organizzazione.

La funzionalità dei profili cliente integra tutti i dati dei clienti in un'unica posizione:

![](assets/mkt_hist_view.png)

Adobe Campaign proposes various mechanisms for profile acquisition: collecting data online via [landing pages](../../channels/using/about-landing-pages.md), manual or [automated import mechanisms](../../automating/using/about-data-import-and-export.md), [direct input](../../audiences/using/creating-profiles.md) in the Adobe Campaign interface, bulk creation through [Campaign APIs](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

**Argomenti correlati:**

* Learn about different types of profiles in the [Profiles](../../audiences/using/about-profiles.md) section.
* Access the number of **Active Profiles** in your organization in [this section](../../audiences/using/active-profiles.md).
* Learn how to customize your data, handle complex data management tasks, such as calculations, aggregates, de-dupes, and merges, using [workflow targeting capabilities](../../automating/using/about-targeting-activities.md)

## Audiences {#audiences}

Per offrire messaggi pertinenti ed efficaci e coinvolgere efficacemente i clienti, Adobe Campaign integra l'analisi avanzata e le funzionalità di targeting. Grazie ai flussi di lavoro e all'editor query, potete creare tipi di pubblico destinati alle diverse campagne, in base alle informazioni di cui disponete, alle attività, alla lingua, alle preferenze o alla cronologia di marketing. Questo consente di filtrare i profili sottoscrittori ad esempio o di creare audience Target su un numero illimitato di criteri.

Audiences are presented [in this page](../../audiences/using/about-audiences.md) and detailed in the [Audiences](../../audiences/using/creating-audiences.md) section.

**Argomenti correlati:**

* Learn how to reach multilingual audiences across multiple regions by sending [multilingual push notifications](../../channels/using/creating-a-multilingual-push-notification.md) or [multilingual emails](../../channels/using/creating-a-multilingual-email.md)
* Learn how to [create queries](../../audiences/using/creating-audiences.md#creating-query-audiences) to build audiences
* Learn how to [create list audiences](../../audiences/using/creating-audiences.md#creating-list-audiences) in a workflow
* Learn how to [import an audience from a file](../../audiences/using/creating-audiences.md#creating-file-audiences) in a workflow
* Learn how to [share audiences](../../audiences/using/creating-audiences.md#creating-experience-cloud-audiences) with Experience Cloud solutions

## General Data Protection Regulation {#general-data-protection-regulation}

GDPR è la nuova legge sulla privacy dell'Unione Europea (EU), che armonizza e modernizza i requisiti di protezione dei dati. Il GDPR si applica ai clienti di Adobe Campaign che contengono dati per i dati dei dati residenti nell'Unione Europea. In aggiunta alle funzionalità sulla privacy già disponibili in Adobe Campaign (comprese la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), stiamo sfruttando questa opportunità come elaboratore dati per includere funzionalità aggiuntive, per semplificare la preparazione come controller dati per determinate richieste GDPR.

Refer to this [guide](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) to learn more about the tools and functionalities that Adobe Campaign provides to help you become GDPR compliant.

## Fatigue management {#fatigue-management}

Le regole di affaticamento consentono agli esperti di marketing di impostare regole aziendali multicanale globali che escluderanno automaticamente i profili superflui dalle campagne.

Per implementare le regole di affaticamento, definite un numero massimo di messaggi per profilo e selezionate un periodo in cui applicare la regola. Durante la preparazione di consegna, i profili sono esclusi dalla consegna, se applicabile, a seconda del numero di messaggi già inviati.

**Argomenti correlati:**

* Learn how to [design fatigue rules](../../administration/using/fatigue-rules.md#examples) through a set of samples
* Learn how to create [typology rules](../../administration/using/about-typology-rules.md)
* Use [filter rules](../../administration/using/filtering-rules.md) to refine the audience of your messages
