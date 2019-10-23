---
title: Arricchimento del database
seo-title: Arricchimento del database
description: Arricchimento del database
seo-description: Scopri i diversi metodi per arricchire il database.
page-status-flag: mai attivato
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: lemaite
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2e114c4a9a6d6189c192ba72140a0e0b55f325ed

---


# Arricchimento del database{#enriching-the-database}

Campaign Standard offre diversi strumenti per incrementare il database di marketing. Questa sezione descrive i diversi metodi che potete utilizzare per inserire i dati in Campaign, con riferimenti alle documentazione dedicata.

## Importazione di dati tramite flussi di lavoro {#importing-data-through-workflows}

I flussi di lavoro consentono di raccogliere i dati e importarli nel database Campaign mediante l'uso di [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) attività.

Informazioni generiche e best practice per l'importazione di dati tramite flussi di lavoro sono presentate in [questa sezione](../../automating/using/importing-data.md).

È inoltre possibile impostare modelli per l'importazione di dati. L’utilizzo dei modelli di importazione è una procedura consigliata se è necessario importare file con la stessa struttura su base regolare.

Potete impostare due tipi di modelli:

* **Modelli** flusso di lavoro: si tratta di flussi di lavoro preconfigurati che potete impostare una volta in base alle vostre esigenze e riutilizzare ogni volta che desiderate importare i dati e aggiornare il database.

   Un esempio di modello di flusso di lavoro per l’importazione dei dati è illustrato in [questa sezione](../../automating/using/importing-data.md#example--import-workflow-template).

* **Importa modelli** dati: come per i modelli di workflow, si tratta di modelli basati su flussi di lavoro configurati per caricare i file per aggiornare il database. Una volta configurati, vengono resi disponibili agli utenti con una visualizzazione semplificata nel menu **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** .

   Per ulteriori informazioni sui modelli di dati di importazione, consulta la documentazione [](../../automating/using/importing-data-with-import-templates.md)dedicata.

## Raccolta di dati dalle pagine di destinazione {#collecting-data-from-landing-pages}

Le pagine di destinazione sono moduli Web che possono essere utilizzati per raccogliere dati e creare o aggiornare informazioni esistenti nel database.

Il principio è il seguente:

* Crea e progetta la pagina di destinazione aggiungendo campi di input per la raccolta dei dati (nome, cognome, e-mail, ecc.).
* Mappare ogni campo di input con il campo corrispondente del database.
* Rendere la pagina di destinazione disponibile online tramite un sito Web o tramite un collegamento diretto a un messaggio.

Per ulteriori informazioni sulle pagine di destinazione, consulta la documentazione [](../../channels/using/about-landing-pages.md)dedicata.

## Sincronizzazione dei profili da Microsoft Dynamics 365

L'integrazione di Campaign Standard con Microsoft Dynamics 365 consente di trasmettere i dati di contatto da Microsoft Dynamics 365 al database Campaign.
Questi contatti sono quindi visibili nell'elenco Profili e possono essere indirizzati nelle campagne di marketing.

Per ulteriori informazioni su questa integrazione, consulta la documentazione [](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)dedicata.

>[!NOTE]
>
>Il connettore Campaign Standard-Microsoft Dynamics 365 è attualmente a disponibilità limitata e soggetto a diverse limitazioni, descritte nella documentazione.

## Importazione di dati tramite chiamate API

Le API Campaign Standard consentono di eseguire operazioni per aggiornare il database come la creazione, l'aggiornamento o l'eliminazione di profili o servizi.

Per ulteriori informazioni sull'utilizzo delle API, consulta la documentazione [](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)dedicata.

>[!CAUTION]
>
>Prima di eseguire la creazione di massa dei profili o l'aggiornamento tramite chiamate API, controllate i limiti di scala corrispondenti al contratto di licenza. For more on this, refer to [this page](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).
