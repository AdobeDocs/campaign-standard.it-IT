---
title: Arricchimento del database
description: Scopri i diversi metodi per arricchire il database.
page-status-flag: never-activated
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 50991e9b376be5e706d2e8d8dcfa8c3677651281

---


# Arricchimento del database{#enriching-the-database}

Campaign Standard offre diversi strumenti per incrementare il database di marketing. Questa sezione descrive i diversi metodi che potete utilizzare per inserire i dati in Campaign, con riferimenti alle documentazione dedicate.

## Importazione di dati tramite flussi di lavoro {#importing-data-through-workflows}

I flussi di lavoro consentono di raccogliere i dati e importarli nel database Campaign mediante l&#39;uso di [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) attività.

Informazioni generiche e best practice per l&#39;importazione di dati tramite flussi di lavoro sono presentate in [questa sezione](../../automating/using/importing-data.md).

È inoltre possibile impostare modelli per l&#39;importazione di dati. L’utilizzo dei modelli di importazione è una procedura consigliata se è necessario importare file con la stessa struttura su base regolare.

Potete impostare due tipi di modelli:

* **Modelli** flusso di lavoro: si tratta di flussi di lavoro preconfigurati che potete impostare una volta in base alle vostre esigenze e riutilizzare ogni volta che desiderate importare i dati e aggiornare il database.

   Un esempio di modello di flusso di lavoro per l’importazione dei dati è illustrato in [questa sezione](../../automating/using/importing-data.md#example--import-workflow-template).

* **Importa modelli** di dati: come i modelli di workflow, si tratta di modelli basati su flussi di lavoro, configurati per caricare i file per aggiornare il database. Una volta configurati, vengono resi disponibili agli utenti con una visualizzazione semplificata nel menu **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** .

   Per ulteriori informazioni sui modelli di dati di importazione, consulta la documentazione [](../../automating/using/importing-data-with-import-templates.md)dedicata.

## Raccolta di dati dalle pagine di destinazione {#collecting-data-from-landing-pages}

Le pagine di destinazione sono moduli Web che possono essere utilizzati per raccogliere dati e creare o aggiornare informazioni esistenti nel database.

Il principio è il seguente:

* Crea e progetta la pagina di destinazione aggiungendo campi di input per la raccolta dei dati (nome, cognome, e-mail, ecc.).
* Mappare ogni campo di input con il campo corrispondente del database.
* Rendete la pagina di destinazione disponibile online tramite un sito Web o tramite un collegamento diretto a un messaggio.

Per ulteriori informazioni sulle pagine di destinazione, consulta la documentazione [](../../channels/using/getting-started-with-landing-pages.md)dedicata.

## Sincronizzazione dei profili da Microsoft Dynamics 365

L&#39;integrazione di Campaign Standard con Microsoft Dynamics 365 consente di trasmettere i dati di contatto da Microsoft Dynamics 365 al database Campaign.
Questi contatti sono quindi visibili nell&#39;elenco Profili e possono essere indirizzati nelle campagne di marketing.

Per ulteriori informazioni su questa integrazione, consulta la documentazione [](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)dedicata.

>[!NOTE]
>
>Il connettore Campaign Standard-Microsoft Dynamics 365 è attualmente a disponibilità limitata e soggetto a diverse limitazioni, descritte nella documentazione.

## Importazione di dati tramite chiamate API

Le API Campaign Standard consentono di eseguire operazioni per aggiornare il database come la creazione, l&#39;aggiornamento o l&#39;eliminazione di profili o servizi.

Per ulteriori informazioni sull&#39;utilizzo delle API, consulta la documentazione [](../../api/using/about-campaign-standard-apis.md)dedicata.

>[!CAUTION]
>
>Prima di eseguire la creazione di massa dei profili o l&#39;aggiornamento tramite chiamate API, controllate i limiti di scala corrispondenti al contratto di licenza. For more on this, refer to [this page](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).
