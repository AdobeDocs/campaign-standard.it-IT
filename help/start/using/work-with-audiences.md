---
solution: Campaign Standard
product: campaign
title: Personalizzazione degli elenchi
description: '"Scopri come personalizzare la visualizzazione e agire sulle schermate elenco in  Adobe Campaign Standard:ordinamento, filtro, eliminazione o duplicazione di elementi. Nelle schermate sono visualizzati elementi di una o più risorse."'
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 9%

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

 profili Adobe Campaign rappresentano tutti i contatti memorizzati nel database. Ogni profilo corrisponde a una voce nel database che contiene le informazioni necessarie affinché il profilo sia mirato, qualificato e monitorato individualmente. Questo significa che un profilo può essere: un cliente, un potenziale, un singolo iscritto a una newsletter, un destinatario, un utente o qualsiasi altra denominazione a seconda dell’organizzazione.

**Leggi tutto**

* [Informazioni sui profili](../../audiences/using/about-profiles.md)
* [Accesso al numero di profili attivi nell’organizzazione](../../audiences/using/active-profiles.md)

## Arricchimento del database {#populating-database}

<img width="60px" alt="condizioni" src="assets/icon_populate.svg"/>

Campaign Standard offre diversi strumenti per incrementare il database di marketing. Questa sezione descrive i diversi metodi che potete utilizzare per inserire i dati in Campaign, con riferimenti alle documentazione dedicate.

### Importazione di dati tramite flussi di lavoro {#importing-data-through-workflows}

I flussi di lavoro consentono di raccogliere i dati e importarli nel database Campaign mediante l&#39;uso di attività [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md). Informazioni generiche e best practice per l&#39;importazione di dati tramite flussi di lavoro sono riportate in [questa sezione](../../automating/using/about-data-import-and-export.md).

È inoltre possibile impostare modelli per l&#39;importazione di dati. L’utilizzo dei modelli di importazione è una procedura consigliata se è necessario importare file con la stessa struttura su base regolare. Potete impostare due tipi di modelli:

* **Modelli** flusso di lavoro: si tratta di flussi di lavoro preconfigurati che potete impostare una volta in base alle vostre esigenze e riutilizzare ogni volta che desiderate importare i dati e aggiornare il database. Un esempio di modello di flusso di lavoro per l&#39;importazione dei dati è dettagliato in [questa sezione](../../automating/using/creating-import-workflow-templates.md).

* **Importa modelli** di dati: come i modelli di workflow, si tratta di modelli basati su flussi di lavoro, configurati per caricare i file per aggiornare il database. Una volta configurati, vengono resi disponibili agli utenti con una visualizzazione semplificata nel menu **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**. Per ulteriori informazioni sui modelli di dati di importazione, consultare la [documentazione dedicata](../../automating/using/importing-data-with-import-templates.md).

### Raccolta di dati dalle pagine di destinazione {#collecting-data-from-landing-pages}

Le pagine di destinazione sono moduli Web che possono essere utilizzati per raccogliere dati e creare o aggiornare informazioni esistenti nel database. Il principio è il seguente:

* Crea e progetta la pagina di destinazione aggiungendo campi di input per la raccolta dei dati (nome, cognome, e-mail, ecc.).
* Mappare ogni campo di input con il campo corrispondente del database.
* Rendete la pagina di destinazione disponibile online tramite un sito Web o tramite un collegamento diretto a un messaggio.

Per ulteriori informazioni sulle pagine di destinazione, consultare la [documentazione dedicata](../../channels/using/getting-started-with-landing-pages.md).

**Leggi tutto**

* xxxx
* xxxx

### Sincronizzazione dei profili da Microsoft Dynamics 365

L&#39;integrazione Campaign Standard con Microsoft Dynamics 365 consente di trasmettere i dati di contatto da Microsoft Dynamics 365 al database Campaign.
Questi contatti sono quindi visibili nell&#39;elenco Profili e possono essere indirizzati nelle campagne di marketing. Per ulteriori informazioni su questa integrazione, consultare la [documentazione dedicata](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!NOTE]
>
>Il connettore Campaign Standard-Microsoft Dynamics 365 è attualmente in disponibilità limitata e soggetto a diverse limitazioni, descritte nella documentazione.

**Leggi tutto**

* xxxx
* xxxx

### Importazione di dati tramite chiamate API

Le API Campaign Standard consentono di eseguire operazioni per aggiornare il database come la creazione, l&#39;aggiornamento o l&#39;eliminazione dei profili o dei servizi. Per ulteriori informazioni sull&#39;utilizzo delle API, consultare la [documentazione dedicata](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>Prima di eseguire la creazione di massa dei profili o l&#39;aggiornamento tramite chiamate API, controllate i limiti di scala corrispondenti al contratto di licenza. Per ulteriori informazioni, consulta [questa pagina](https://helpx.adobe.com/it/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

**Leggi tutto**

* xxxx
* xxxx

## Organizzazione dei tipi di pubblico {#organizing-audiences}

<img width="60px" alt="condizioni" src="assets/icon_audience.svg"/>

Per fornire messaggi rilevanti ed efficaci e coinvolgere in modo efficace i clienti,  Adobe Campaign integra funzionalità avanzate di analisi e targeting.

Grazie ai flussi di lavoro e all&#39;editor di query, puoi creare audience che verranno indirizzate alle tue diverse campagne, in base alle informazioni disponibili, alle loro attività, alla lingua, alle preferenze o alla cronologia di marketing. Questo consente di filtrare i profili sottoscritti, ad esempio, o di creare audience target su un numero illimitato di criteri.

**Leggi tutto**

* [Informazioni sui tipi di pubblico](../../audiences/using/about-audiences.md)
* [Creazione di tipi di pubblico](../../audiences/using/creating-audiences.md)

## Gestione della privacy {#privacy-management}

<img width="60px" alt="condizioni" src="assets/icon_privacy.svg"/>

Il GDPR è la nuova legge dell’Unione europea sulla privacy che armonizza e aggiorna i requisiti in materia di protezione dei dati. Il GDPR si applica ai clienti di Adobe Campaign che conservano dati per soggetti che risiedono nell’Unione europea. Oltre alle funzionalità per la privacy già disponibili in  Adobe Campaign (compresa la gestione del consenso, le impostazioni di conservazione dei dati e i ruoli utente), stiamo sfruttando questa opportunità in qualità di processore dati per includere funzionalità aggiuntive, al fine di facilitare la tua disponibilità come Titolare del trattamento dei dati per determinate richieste GDPR.

Fare riferimento a questa [guida](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=it#getting-started) per saperne di più sugli strumenti e le funzionalità che  Adobe Campaign fornisce per aiutarti a diventare conforme ai requisiti GDPR.

**Leggi tutto**

* xxxx
* xxxx