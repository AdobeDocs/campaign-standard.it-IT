---
title: Arricchimento del database
description: Scopri i vari metodi per arricchire il database.
audience: start
content-type: reference
topic-tags: about-adobe-campaign
feature: Profiles
role: User
level: Intermediate
exl-id: 9c55a8b3-034e-4319-8a88-7b59e83fa458
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 2%

---

# Arricchimento del database{#enriching-the-database}

Campaign Standard offre diversi strumenti per aiutarti a far crescere il tuo database di marketing. Questa sezione descrive i diversi metodi utilizzabili per inserire dati in Campaign, con riferimenti alla documentazione dedicata.

## Importazione di dati tramite flussi di lavoro {#importing-data-through-workflows}

I flussi di lavoro ti consentono di raccogliere dati e importarli nel database di Campaign tramite l’utilizzo di [[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md) attività.

Le informazioni generiche e le best practice per l&#39;importazione di dati tramite flussi di lavoro sono presentate in [questa sezione](../../automating/using/about-data-import-and-export.md).

Inoltre, puoi impostare modelli per l’importazione di dati. L’utilizzo dei modelli di importazione è una best practice se devi importare regolarmente file con la stessa struttura.

È possibile impostare due tipi di modelli:

* **Modelli di flusso di lavoro**: si tratta di flussi di lavoro preconfigurati che è possibile impostare una sola volta in base alle proprie esigenze e riutilizzare ogni volta che si desidera importare dati e aggiornare il database.

  Un esempio di modello di flusso di lavoro per l&#39;importazione dei dati è descritto in [questa sezione](../../automating/using/creating-import-workflow-templates.md).

* **Importa modelli di dati**: come i modelli di flusso di lavoro, si tratta di modelli basati su flussi di lavoro configurati per caricare file per aggiornare il database. Una volta configurate, le visualizzazioni saranno disponibili per gli utenti con una visualizzazione semplificata nel menu **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**.

  Per ulteriori informazioni sui modelli di dati di importazione, consulta la [documentazione dedicata](../../automating/using/importing-data-with-import-templates.md).

## Raccolta di dati dalle pagine di destinazione {#collecting-data-from-landing-pages}

Le pagine di destinazione sono moduli web che possono essere utilizzati per raccogliere dati e creare o aggiornare informazioni esistenti nel database.

Il principio è il seguente:

* Crea e progetta la pagina di destinazione aggiungendo campi di input per la raccolta dei dati (nome, cognome, e-mail, ecc.).
* Mappa ogni campo di input con il campo corrispondente del database.
* Rendi la pagina di destinazione disponibile online tramite un sito web o un collegamento diretto a un messaggio.

Per ulteriori informazioni sulle pagine di destinazione, consulta la [documentazione dedicata](../../channels/using/getting-started-with-landing-pages.md).

## Sincronizzazione dei profili da Microsoft Dynamics 365

L’integrazione di Campaign Standard con Microsoft Dynamics 365 ti consente di trasmettere i dati di contatto da Microsoft Dynamics 365 al database di Campaign.
Questi contatti sono quindi visibili nell’elenco Profili e possono essere oggetto di targeting nelle campagne di marketing.

Per ulteriori informazioni su questa integrazione, consulta la [documentazione dedicata](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Il connettore Campaign Standard-Microsoft Dynamics 365 al momento è a disponibilità limitata e soggetto a diverse limitazioni, descritte in dettaglio nella documentazione.

## Importazione di dati tramite chiamate API

Le API di Campaign Standard ti consentono di eseguire operazioni per aggiornare il database come la creazione, l’aggiornamento o l’eliminazione di profili o servizi.

Per ulteriori informazioni su come utilizzare le API, consulta la [documentazione dedicata](../../api/using/get-started-apis.md).

>[!IMPORTANT]
>
>Prima di eseguire la creazione o l’aggiornamento di massa dei profili tramite chiamate API, controlla le limitazioni di scala corrispondenti al contratto di licenza. Per ulteriori informazioni, consulta [questa pagina](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).
