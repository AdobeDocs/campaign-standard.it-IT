---
title: Personalizzazione degli elenchi
description: '"Scopri come personalizzare la visualizzazione e intervenire sulle schermate dell’elenco in Adobe Campaign Standard:ordinamento, filtro, eliminazione o duplicazione degli elementi. Elenca schermate che mostrano elementi di una o più risorse specificate."'
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '785'
ht-degree: 9%

---


# Utilizzo di profili e pubblico

<table>
<tr>
    <td valign="top">
        <a href="../../start/using/work-with-audiences.md"><img width="60px" alt="condizioni" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img width="60px" alt="condizioni" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="condizioni" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="condizioni" src="assets/icon_profile.svg"/></a>
    </td>
</tr>
<tr>
<td>Profili cliente</td>
<td>Arricchimento del database</td>
<td>Organizzare i tipi di pubblico</td>
<td>Gestione della privacy</td>
</tr>
</table>

## Profili cliente {#customer-profiles}

<img width="60px" alt="condizioni" src="assets/icon_profile.svg"/>

I profili Adobe Campaign rappresentano tutti i contatti memorizzati nel database. Ogni profilo corrisponde a una voce nel database che contiene le informazioni necessarie affinché tale profilo sia mirato, qualificato e monitorato individualmente. Questo significa che un profilo può essere: un cliente, un potenziale cliente, una persona abbonata a una newsletter, un destinatario, un utente o qualsiasi altra denominazione a seconda dell’organizzazione.

**Ulteriori informazioni**

* [Informazioni sui profili](../../audiences/using/about-profiles.md)
* [Accesso al numero di profili attivi nell&#39;organizzazione](../../audiences/using/active-profiles.md)

## Arricchimento del database {#populating-database}

<img width="60px" alt="condizioni" src="assets/icon_populate.svg"/>

Campaign Standard offre diversi strumenti per incrementare il database di marketing. Questa sezione descrive i diversi metodi che puoi utilizzare per inserire dati in Campaign, con riferimenti alla documentazione dedicata.

### Importazione di dati tramite flussi di lavoro {#importing-data-through-workflows}

I flussi di lavoro ti consentono di raccogliere i dati e importarli nel database Campaign tramite l’utilizzo di attività [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md). Le informazioni generiche e le best practice per l’importazione di dati tramite flussi di lavoro sono presentate in [questa sezione](../../automating/using/about-data-import-and-export.md).

Inoltre, puoi impostare i modelli per importare i dati. L’utilizzo dei modelli di importazione è una best practice per importare regolarmente file con la stessa struttura. È possibile impostare due tipi di modelli:

* **Modelli** di flusso di lavoro: si tratta di flussi di lavoro preconfigurati che è possibile configurare una sola volta in base alle proprie esigenze e riutilizzare ogni volta che si desidera importare i dati e aggiornare il database. Un esempio di modello di flusso di lavoro per importare i dati è descritto in [questa sezione](../../automating/using/creating-import-workflow-templates.md).

* **Importa modelli** dati: come i modelli di flusso di lavoro, si tratta di modelli basati sui flussi di lavoro, configurati per caricare file per aggiornare il database. Una volta configurate, queste vengono rese disponibili agli utenti con una visualizzazione semplificata nel menu **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** . Per ulteriori informazioni sui modelli di dati di importazione, consulta la [documentazione dedicata](../../automating/using/importing-data-with-import-templates.md).

### Raccolta di dati dalle pagine di destinazione {#collecting-data-from-landing-pages}

Le pagine di destinazione sono moduli web che possono essere utilizzati per raccogliere dati e creare o aggiornare informazioni esistenti nel database. Il principio è il seguente:

* Crea e progetta la pagina di destinazione aggiungendo campi di input per raccogliere dati (nome, cognome, e-mail, ecc.).
* Mappa ciascun campo di input con il campo corrispondente del database.
* Rendi la pagina di destinazione disponibile online tramite un sito web o tramite un collegamento diretto a un messaggio.

Per ulteriori informazioni sulle pagine di destinazione, consulta la [documentazione dedicata](../../channels/using/getting-started-with-landing-pages.md).

**Ulteriori informazioni**

* xxxx
* xxxx

### Sincronizzazione dei profili da Microsoft Dynamics 365

L’integrazione di Campaign Standard con Microsoft Dynamics 365 consente di passare i dati di contatto da Microsoft Dynamics 365 al database Campaign.
Questi contatti sono quindi visibili nell’elenco Profili e possono essere indirizzati nelle campagne di marketing. Per ulteriori informazioni su questa integrazione, consulta la [documentazione dedicata](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Il connettore Campaign Standard-Microsoft Dynamics 365 è attualmente a disponibilità limitata e soggetto a diverse limitazioni, descritte nella documentazione.

**Ulteriori informazioni**

* xxxx
* xxxx

### Importazione di dati tramite chiamate API

Le API di Campaign Standard consentono di eseguire operazioni per aggiornare il database, come la creazione, l’aggiornamento o l’eliminazione di profili o servizi. Per ulteriori informazioni su come utilizzare le API, consulta la [documentazione dedicata](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>Prima di eseguire la creazione di massa dei profili o l’aggiornamento tramite chiamate API, controlla le limitazioni di scala corrispondenti al contratto di licenza. Per ulteriori informazioni, consulta [questa pagina](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

**Ulteriori informazioni**

* xxxx
* xxxx

## Organizzazione del pubblico {#organizing-audiences}

<img width="60px" alt="condizioni" src="assets/icon_audience.svg"/>

Per consentirti di inviare messaggi pertinenti ed efficaci e coinvolgere in modo efficace i clienti, Adobe Campaign integra funzionalità di analisi e targeting avanzate.

Grazie ai flussi di lavoro e all’editor delle query, puoi creare tipi di pubblico interessati dalle diverse campagne, in base alle informazioni disponibili, alle loro attività, alla lingua, alle preferenze o alla cronologia di marketing. Questo ti consente di filtrare profili abbonati, ad esempio, o creare tipi di pubblico target su un numero illimitato di criteri.

**Ulteriori informazioni**

* [Informazioni sui tipi di pubblico](../../audiences/using/about-audiences.md)
* [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md)

## Gestione della privacy {#privacy-management}

<img width="60px" alt="condizioni" src="assets/icon_privacy.svg"/>

Il RGPD è la nuova legge sulla privacy dell’Unione europea (UE) che armonizza e modernizza i requisiti in materia di protezione dei dati. Il GDPR si applica ai clienti di Adobe Campaign che conservano dati per soggetti che risiedono nell’Unione europea. Oltre alle funzionalità per la privacy già disponibili in Adobe Campaign (tra cui la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), stiamo sfruttando questa opportunità nel nostro ruolo di Incaricato del trattamento dei dati per includere funzionalità aggiuntive, per aiutarti a essere pronto come titolare del trattamento per alcune richieste RGPD.

Per ulteriori informazioni sugli strumenti e le funzionalità forniti da Adobe Campaign per aiutarti a diventare conforme ai requisiti RGPD, fai riferimento a questa [guida](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=it) .

**Ulteriori informazioni**

* xxxx
* xxxx