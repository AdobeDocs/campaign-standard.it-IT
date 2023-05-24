---
title: Personalizzazione degli elenchi
description: "Scopri come personalizzare la visualizzazione e agire sulle schermate elenco in Adobe Campaign Standard:ordinare, filtrare, eliminare o duplicare gli elementi. Nelle schermate dell’elenco vengono visualizzati gli elementi di una o più risorse specificate."
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '776'
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

I profili Adobe Campaign rappresentano tutti i contatti memorizzati nel database. Ogni profilo corrisponde a una voce nel database che contiene le informazioni necessarie per il targeting, la qualificazione e la tracciabilità individuale del profilo. Ciò significa che un profilo può essere: un cliente, un potenziale cliente, una persona abbonata a una newsletter, un destinatario, un utente o qualsiasi altra denominazione a seconda dell’organizzazione.

**Ulteriori informazioni**

* [Informazioni sui profili](../../audiences/using/about-profiles.md)
* [Accesso al numero di profili attivi nell’organizzazione](../../audiences/using/active-profiles.md)

## Arricchimento del database {#populating-database}

<img width="60px" alt="condizioni" src="assets/icon_populate.svg"/>

Campaign Standard offre diversi strumenti per aiutarti a far crescere il tuo database di marketing. Questa sezione descrive i diversi metodi utilizzabili per inserire dati in Campaign, con riferimenti alla documentazione dedicata.

### Importazione di dati tramite flussi di lavoro {#importing-data-through-workflows}

I flussi di lavoro ti consentono di raccogliere dati e importarli nel database di Campaign tramite l’utilizzo di [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) attività. Le informazioni generiche e le best practice per l’importazione di dati tramite flussi di lavoro sono presentate in [questa sezione](../../automating/using/about-data-import-and-export.md).

Inoltre, puoi impostare modelli per l’importazione di dati. È consigliabile utilizzare i modelli di importazione per importare regolarmente file con la stessa struttura. È possibile impostare due tipi di modelli:

* **Modelli di flusso di lavoro**: si tratta di flussi di lavoro preconfigurati che possono essere impostati una sola volta in base alle tue esigenze e riutilizzati ogni volta che desideri importare dati e aggiornare il database. Un esempio di modello di flusso di lavoro per importare i dati è descritto in [questa sezione](../../automating/using/creating-import-workflow-templates.md).

* **Importare modelli di dati**: come i modelli di flusso di lavoro, si tratta di modelli basati sui flussi di lavoro, impostati per caricare i file per aggiornare il database. Una volta configurate, queste vengono rese disponibili agli utenti con una vista semplificata sotto **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** menu. Per ulteriori informazioni sui modelli di dati di importazione, consulta [documentazione dedicata](../../automating/using/importing-data-with-import-templates.md).

### Raccolta di dati dalle pagine di destinazione {#collecting-data-from-landing-pages}

Le pagine di destinazione sono moduli web che possono essere utilizzati per raccogliere dati e creare o aggiornare informazioni esistenti nel database. Il principio è il seguente:

* Crea e progetta la pagina di destinazione aggiungendo campi di input per la raccolta dei dati (nome, cognome, e-mail, ecc.).
* Mappa ogni campo di input con il campo corrispondente del database.
* Rendi la pagina di destinazione disponibile online tramite un sito web o un collegamento diretto a un messaggio.

Per ulteriori informazioni sulle pagine di destinazione, consulta [documentazione dedicata](../../channels/using/getting-started-with-landing-pages.md).

**Ulteriori informazioni**

* xxxx
* xxxx

### Sincronizzazione dei profili da Microsoft Dynamics 365

L’integrazione di Campaign Standard con Microsoft Dynamics 365 ti consente di trasmettere i dati di contatto da Microsoft Dynamics 365 al database di Campaign.
Questi contatti sono quindi visibili nell’elenco Profili e possono essere oggetto di targeting nelle campagne di marketing. Per ulteriori informazioni su questa integrazione, consulta [documentazione dedicata](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Il connettore Campaign Standard-Microsoft Dynamics 365 al momento è a disponibilità limitata e soggetto a diverse limitazioni, descritte in dettaglio nella documentazione.

**Ulteriori informazioni**

* xxxx
* xxxx

### Importazione di dati tramite chiamate API

Le API di Campaign Standard ti consentono di eseguire operazioni per aggiornare il database come la creazione, l’aggiornamento o l’eliminazione di profili o servizi. Per ulteriori informazioni su come utilizzare le API, consulta [documentazione dedicata](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>Prima di eseguire la creazione o l’aggiornamento di massa dei profili tramite chiamate API, controlla le limitazioni di scala corrispondenti al contratto di licenza. Per ulteriori informazioni, consulta [questa pagina](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

**Ulteriori informazioni**

* xxxx
* xxxx

## Organizzazione dei tipi di pubblico {#organizing-audiences}

<img width="60px" alt="condizioni" src="assets/icon_audience.svg"/>

Per consentirti di inviare messaggi pertinenti ed efficaci e coinvolgere in modo efficace i tuoi clienti, Adobe Campaign integra funzionalità avanzate di analisi e targeting.

Grazie ai flussi di lavoro e all’editor delle query, puoi creare tipi di pubblico a cui rivolgerti le diverse campagne, a seconda delle informazioni che hai su di loro, delle loro attività, della loro lingua, delle loro preferenze o della cronologia di marketing. Ciò ti consente, ad esempio, di filtrare i profili abbonati o di creare tipi di pubblico target in base a un numero illimitato di criteri.

**Ulteriori informazioni**

* [Informazioni sui tipi di pubblico](../../audiences/using/about-audiences.md)
* [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md)

## Gestione della privacy {#privacy-management}

<img width="60px" alt="condizioni" src="assets/icon_privacy.svg"/>

Il RGPD è la nuova legge sulla privacy dell’Unione europea (UE) che armonizza e modernizza i requisiti in materia di protezione dei dati. Il GDPR si applica ai clienti di Adobe Campaign che conservano dati per soggetti che risiedono nell’Unione europea. Oltre alle funzionalità per la privacy già disponibili in Adobe Campaign (tra cui la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), in qualità di responsabile del trattamento dei dati vogliamo sfruttare l’opportunità di includere funzionalità aggiuntive per aiutarti ad essere pronto a determinate richieste RGPD in qualità di titolare del trattamento dei dati.

Fai riferimento a [questa sezione](../../start/using/privacy.md) per ulteriori informazioni sugli strumenti e le funzionalità forniti da Adobe Campaign per aiutarti a diventare conforme ai requisiti RGPD.

**Ulteriori informazioni**

* xxxx
* xxxx