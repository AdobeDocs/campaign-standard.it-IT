---
solution: Campaign Standard
product: campaign
title: Arricchimento del database
description: Scopri i diversi metodi per arricchire il database.
audience: start
content-type: reference
topic-tags: about-adobe-campaign
translation-type: tm+mt
source-git-commit: b471fddd49037770e33a113374afd60c2e79e69b
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 3%

---


# Arricchimento del database{#enriching-the-database}

Campaign Standard offre diversi strumenti per incrementare il database di marketing. Questa sezione descrive i diversi metodi che potete utilizzare per inserire i dati in Campaign, con riferimenti alle documentazione dedicate.

## Importazione di dati tramite flussi di lavoro {#importing-data-through-workflows}

I flussi di lavoro consentono di raccogliere i dati e importarli nel database Campaign mediante l&#39;uso di attività [[!UICONTROL Data management]](../../automating/using/about-data-management-activities.md).

Informazioni generiche e best practice per l&#39;importazione di dati tramite flussi di lavoro sono riportate in [questa sezione](../../automating/using/about-data-import-and-export.md).

È inoltre possibile impostare modelli per l&#39;importazione di dati. L’utilizzo dei modelli di importazione è una procedura consigliata se è necessario importare file con la stessa struttura su base regolare.

Potete impostare due tipi di modelli:

* **Modelli** flusso di lavoro: si tratta di flussi di lavoro preconfigurati che potete impostare una volta in base alle vostre esigenze e riutilizzare ogni volta che desiderate importare i dati e aggiornare il database.

   Un esempio di modello di flusso di lavoro per l&#39;importazione dei dati è dettagliato in [questa sezione](../../automating/using/creating-import-workflow-templates.md).

* **Importa modelli** di dati: come i modelli di workflow, si tratta di modelli basati su flussi di lavoro, configurati per caricare i file per aggiornare il database. Una volta configurati, vengono resi disponibili agli utenti con una visualizzazione semplificata nel menu **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**.

   Per ulteriori informazioni sui modelli di dati di importazione, consultare la [documentazione dedicata](../../automating/using/importing-data-with-import-templates.md).

## Raccolta di dati dalle pagine di destinazione {#collecting-data-from-landing-pages}

Le pagine di destinazione sono moduli Web che possono essere utilizzati per raccogliere dati e creare o aggiornare informazioni esistenti nel database.

Il principio è il seguente:

* Crea e progetta la pagina di destinazione aggiungendo campi di input per la raccolta dei dati (nome, cognome, e-mail, ecc.).
* Mappare ogni campo di input con il campo corrispondente del database.
* Rendete la pagina di destinazione disponibile online tramite un sito Web o tramite un collegamento diretto a un messaggio.

Per ulteriori informazioni sulle pagine di destinazione, consultare la [documentazione dedicata](../../channels/using/getting-started-with-landing-pages.md).

## Sincronizzazione dei profili da Microsoft Dynamics 365

L&#39;integrazione Campaign Standard con Microsoft Dynamics 365 consente di trasmettere i dati di contatto da Microsoft Dynamics 365 al database Campaign.
Questi contatti sono quindi visibili nell&#39;elenco Profili e possono essere indirizzati nelle campagne di marketing.

Per ulteriori informazioni su questa integrazione, consultare la [documentazione dedicata](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Il connettore Campaign Standard-Microsoft Dynamics 365 è attualmente in disponibilità limitata e soggetto a diverse limitazioni, descritte nella documentazione.

## Importazione di dati tramite chiamate API

Le API Campaign Standard consentono di eseguire operazioni per aggiornare il database come la creazione, l&#39;aggiornamento o l&#39;eliminazione dei profili o dei servizi.

Per ulteriori informazioni sull&#39;utilizzo delle API, consultare la [documentazione dedicata](../../api/using/get-started-apis.md).

>[!IMPORTANT]
>
>Prima di eseguire la creazione di massa dei profili o l&#39;aggiornamento tramite chiamate API, controllate i limiti di scala corrispondenti al contratto di licenza. Per ulteriori informazioni, consulta [questa pagina](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).
