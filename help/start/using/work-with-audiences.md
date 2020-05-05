---
title: Personalizzazione degli elenchi
description: '"Scopri come personalizzare la visualizzazione e agire sulle schermate degli elenchi in Adobe Campaign Standard: ordinamento, filtro, eliminazione o duplicazione di elementi. Nelle schermate sono visualizzati elementi di una o più risorse."'
page-status-flag: never-activated
uuid: 3350583c-91ca-4ea5-ac14-6b6f11c4a64a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 4ba4f766-fdee-4ff0-8fe4-0612ed2b69a4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 816d550d8bd0de085a47f97c1f6cc2fbb5e7acb9

---


# Utilizzo di profili e audience

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
<td>Organizzare il pubblico</td>
<td>Gestione della privacy</td>
</tr>
</table>

## Profili cliente {#customer-profiles}

<img width="60px" alt="condizioni" src="assets/icon_profile.svg"/>

I profili di Adobe Campaign rappresentano tutti i contatti memorizzati nel database. Ogni profilo corrisponde a una voce nel database che contiene le informazioni necessarie affinché il profilo sia mirato, qualificato e monitorato individualmente. Questo significa che un profilo può essere: un cliente, un potenziale, un singolo iscritto a una newsletter, un destinatario, un utente o qualsiasi altra denominazione a seconda dell’organizzazione.

**Leggi tutto**

* [Informazioni sui profili](../../audiences/using/about-profiles.md)
* [Accesso al numero di profili attivi nell’organizzazione](../../audiences/using/active-profiles.md)

## Arricchimento del database {#populating-database}

<img width="60px" alt="condizioni" src="assets/icon_populate.svg"/>

Campaign Standard offre diversi strumenti per incrementare il database di marketing. Questa sezione descrive i diversi metodi che potete utilizzare per inserire i dati in Campaign, con riferimenti alle documentazione dedicate.

### Importazione di dati tramite flussi di lavoro {#importing-data-through-workflows}

I flussi di lavoro consentono di raccogliere i dati e importarli nel database Campaign mediante l&#39;uso di [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) attività. Informazioni generiche e best practice per l&#39;importazione di dati tramite flussi di lavoro sono presentate in [questa sezione](../../automating/using/importing-data.md).

È inoltre possibile impostare modelli per l&#39;importazione di dati. L’utilizzo dei modelli di importazione è una procedura consigliata se è necessario importare file con la stessa struttura su base regolare. Potete impostare due tipi di modelli:

* **Modelli** flusso di lavoro: si tratta di flussi di lavoro preconfigurati che potete impostare una volta in base alle vostre esigenze e riutilizzare ogni volta che desiderate importare i dati e aggiornare il database. Un esempio di modello di flusso di lavoro per l’importazione dei dati è illustrato in [questa sezione](../../automating/using/importing-data.md#example--import-workflow-template).

* **Importa modelli** di dati: come i modelli di workflow, si tratta di modelli basati su flussi di lavoro, configurati per caricare i file per aggiornare il database. Una volta configurati, vengono resi disponibili agli utenti con una visualizzazione semplificata nel menu **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** . Per ulteriori informazioni sui modelli di dati di importazione, consulta la documentazione [](../../automating/using/importing-data-with-import-templates.md)dedicata.

### Raccolta di dati dalle pagine di destinazione {#collecting-data-from-landing-pages}

Le pagine di destinazione sono moduli Web che possono essere utilizzati per raccogliere dati e creare o aggiornare informazioni esistenti nel database. Il principio è il seguente:

* Crea e progetta la pagina di destinazione aggiungendo campi di input per la raccolta dei dati (nome, cognome, e-mail, ecc.).
* Mappare ogni campo di input con il campo corrispondente del database.
* Rendete la pagina di destinazione disponibile online tramite un sito Web o tramite un collegamento diretto a un messaggio.

Per ulteriori informazioni sulle pagine di destinazione, consulta la documentazione [](../../channels/using/getting-started-with-landing-pages.md)dedicata.

**Leggi tutto**

* xxxx
* xxxx

### Sincronizzazione dei profili da Microsoft Dynamics 365

L&#39;integrazione di Campaign Standard con Microsoft Dynamics 365 consente di trasmettere i dati di contatto da Microsoft Dynamics 365 al database Campaign.
Questi contatti sono quindi visibili nell&#39;elenco Profili e possono essere indirizzati nelle campagne di marketing. Per ulteriori informazioni su questa integrazione, consulta la documentazione [](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)dedicata.

>[!NOTE]
>
>Il connettore Campaign Standard-Microsoft Dynamics 365 è attualmente a disponibilità limitata e soggetto a diverse limitazioni, descritte nella documentazione.

**Leggi tutto**

* xxxx
* xxxx

### Importazione di dati tramite chiamate API

Le API Campaign Standard consentono di eseguire operazioni per aggiornare il database come la creazione, l&#39;aggiornamento o l&#39;eliminazione di profili o servizi. Per ulteriori informazioni sull&#39;utilizzo delle API, consulta la documentazione [](../../api/using/get-started-apis.md)dedicata.

>[!CAUTION]
>
>Prima di eseguire la creazione di massa dei profili o l&#39;aggiornamento tramite chiamate API, controllate i limiti di scala corrispondenti al contratto di licenza. For more on this, refer to
[this page](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

**Leggi tutto**

* xxxx
* xxxx

## Organizzazione dei tipi di pubblico {#organizing-audiences}

<img width="60px" alt="condizioni" src="assets/icon_audience.svg"/>

Per consentirti di inviare messaggi rilevanti ed efficaci e coinvolgere in modo efficace i clienti, Adobe Campaign integra funzionalità avanzate di analisi e targeting.

Grazie ai flussi di lavoro e all&#39;editor di query, puoi creare audience che verranno indirizzate alle tue diverse campagne, in base alle informazioni disponibili, alle loro attività, alla lingua, alle preferenze o alla cronologia di marketing. Questo consente di filtrare i profili sottoscritti, ad esempio, o di creare audience target su un numero illimitato di criteri.

**Leggi tutto**

* [Informazioni sui tipi di audience](../../audiences/using/about-audiences.md)
* [Creazione di audience](../../audiences/using/creating-audiences.md)

## Gestione della privacy {#privacy-management}

<img width="60px" alt="condizioni" src="assets/icon_privacy.svg"/>

Il GDPR è la nuova legge dell’Unione europea sulla privacy che armonizza e aggiorna i requisiti in materia di protezione dei dati. Il Regolamento GDPR si applica ai clienti Adobe Campaign che detengono dati per i soggetti dati residenti nell&#39;UE. Oltre alle funzionalità per la privacy già disponibili in Adobe Campaign (compresa la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), stiamo sfruttando questa opportunità in qualità di Data Processor per includere funzionalità aggiuntive, al fine di facilitare la tua disponibilità in qualità di Data Controller per determinate richieste GDPR.

Fai riferimento a questa [guida](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html) per saperne di più sugli strumenti e le funzionalità forniti da Adobe Campaign per aiutarti a diventare conforme ai requisiti GDPR.

**Leggi tutto**

* xxxx
* xxxx