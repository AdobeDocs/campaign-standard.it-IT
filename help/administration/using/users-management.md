---
title: Gestione utenti
description: 'Gli utenti di Adobe Campaign hanno ruoli specifici. Scopri i tipi di utente principali. '
page-status-flag: never-activated
uuid: 8c4cc74a-815f-4815-af66-a7c21bc754f1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 08c8712a-0066-4b8b-8471-2656b8fb23ed
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '1144'
ht-degree: 100%

---


# Gestione utenti{#users-management}

## Informazioni sugli utenti {#about-users}

Adobe Campaign ti consente di assegnare un set di ruoli agli utenti per definire a quale parte dell’interfaccia possono accedere.

I ruoli specifici e le autorizzazioni corrispondenti sono descritti nelle sezioni seguenti: [Elenco di ruoli](../../administration/using/list-of-roles.md) e di [autorizzazioni](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Da Admin Console, gli amministratori possono gestire gli utenti. Gli utenti vengono quindi sincronizzati automaticamente con Adobe Campaign. Per ulteriori informazioni, consulta la documentazione di [Admin Console](https://helpx.adobe.com/it/enterprise/using/users.html).

Per visualizzare gli utenti in Adobe Campaign, fai clic sul logo di **[!UICONTROL Adobe Campaign]**, nell’angolo in alto a sinistra, quindi seleziona **[!UICONTROL Administration > Users & Security > Users]**.

Per accedere all’interfaccia di gestione degli utenti da Adobe Campaign, fai clic su **[!UICONTROL User administration]**.

![](assets/user_management_5.png)

**Argomenti correlati:**

* Video sulla [gestione di autorizzazioni utente](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/access-management.html)
* [Elenco di ruoli](../../administration/using/list-of-roles.md)
* [Elenco delle autorizzazioni](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## Tipo di utenti {#type-of-users}

Questa segmentazione degli utenti non è obbligatoria, ma è solo una rappresentazione dell’utilizzo più comune di Adobe Campaign.

Questa sezione ti aiuta a capire i tipi principali di utenti di Adobe Campaign. In questo caso non approfondiamo tutti i ruoli specifici che un utente può assumere (consegne iniziali, esportazioni, preparazione di consegne, ecc.). Per ulteriori informazioni sui ruoli, consulta le pagine [Elenco di ruoli](../../administration/using/list-of-roles.md) e [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md).

Ci concentreremo piuttosto sulla suddivisione delle diverse attività in Adobe Campaign tra tre tipi di utenti principali:

* [Amministratori funzionali](#functional-administrators): sono i più tecnici tra tutti gli utenti dell’organizzazione.
* [Utenti avanzati](#advanced-users): configurano tutti gli elementi necessari agli esperti marketing per inviare e monitorare le consegne.
* [Utenti di base](#basic-users): sono gli esperti marketing che personalizzano, distribuiscono e monitorano le campagne.

>[!NOTE]
>
>Gli amministratori funzionali differiscono dagli amministratori tecnici di Adobe. Gli amministratori tecnici di Adobe ricoprono un ruolo interno in Adobe che nessun cliente può usare. Gestiscono il provisioning delle istanze, l’hosting, il monitoraggio e la supervisione dell’infrastruttura, nonché la risoluzione dei problemi tecnici.

### Amministratori funzionali {#functional-administrators}

Gli amministratori funzionali sono utenti che possono accedere alle parti più tecniche dell’interfaccia. Hanno il ruolo **[!UICONTROL Administration]** e si accertano che la piattaforma sia configurata in modo che gli esperti marketing debbano concentrarsi solo sulla distribuzione delle campagne.

Gli amministratori funzionali sono gli unici utenti che possono accedere al menu **[!UICONTROL Administration]**, nell’interfaccia di Adobe Campaign. Poiché questi utenti devono accedere alle risorse tecniche, devi assegnare loro ruoli più avanzati, come i predefiniti **[!UICONTROL Administration]** e **[!UICONTROL Datamodel]**. Questi ruoli vengono combinati nel gruppo di sicurezza predefinito **[!UICONTROL Administrators]**. Per ulteriori informazioni, consulta questa [sezione](../../administration/using/list-of-roles.md).

Di seguito sono elencate le attività principali che possono eseguire:

* [Gestione di utenti e autorizzazioni](../../administration/using/about-access-management.md): gestisci l’accesso alla piattaforma (utenti, ruoli, gruppi di sicurezza, unità).
* [Configurazione di diversi canali](../../administration/using/about-channel-configuration.md): imposta i diversi canali della piattaforma, nonché la gestione della tipologia e della quarantena.
* [Configurazione di impostazioni generali dell’applicazione](../../administration/using/external-accounts.md): configura diversi elementi dell’applicazione (account esterni, opzioni, flussi di lavoro tecnici).
* [Sviluppo di nuove funzionalità per migliorare le funzionalità predefinite](../../developing/using/data-model-concepts.md): gestisci risorse personalizzate e accedi agli strumenti diagnostici.
* [Impostazione di parametri di istanze](../../administration/using/branding.md): definisci i brand e ne configuri le impostazioni (logo, gestione del tracciamento, l’URL del per accedere alle pagine di destinazione, ecc.).
* [Esportazione e importazione di pacchetti dati](../../automating/using/managing-packages.md): scambia risorse tra diverse istanze di Adobe Campaign tramite file XML strutturati.
* [Esportazione di file di log](../../automating/using/exporting-logs.md) e [definizione di modelli di importazione](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates).

### Utenti avanzati {#advanced-users}

Gli utenti avanzati sono utenti di marketing che eseguono casi di utilizzo più tecnici in Adobe Campaign. Preconfigurano tutti gli elementi utilizzati dagli esperti marketing per inviare e monitorare le consegne.

Questo tipo di utente richiede ruoli più generali rispetto agli amministratori funzionali, ma deve comunque riuscire a eseguire alcune operazioni tecniche. A questo scopo devono essere assegnati, ad esempio, l’**[!UICONTROL Export]**, il **[!UICONTROL Generic import]** o i ruoli preconfigurati del **[!UICONTROL Workflow]**. Per ulteriori informazioni, consulta questa [sezione](../../administration/using/list-of-roles.md).

Di seguito sono elencate le attività principali che possono eseguire:

* [Creazione ed esecuzione di flussi di lavoro complessi per la gestione dei dati](../../automating/using/about-data-management-activities.md): importa, arricchisci e trasforma dati per alimentare il database oppure esporta i dati necessari in file esterni per elaborarli negli strumenti.
* [Gestione di modelli](../../start/using/marketing-activity-templates.md): gestisci i modelli per preconfigurare alcuni parametri delle attività di marketing in base alle tue esigenze.
* [Creazione di query](../../automating/using/editing-queries.md#about-query-editor) e [gestione di tipi di pubblico](../../audiences/using/about-audiences.md): crea i tipi di pubblico manualmente utilizzando query o automaticamente tramite flussi di lavoro dedicati.
* [Esecuzione della modifica avanzata di espressioni](../../automating/using/editing-queries.md#about-query-editor): utilizza funzioni avanzate per manipolare i valori utilizzati per eseguire query specifiche come date, stringhe, campi numerici, ordinamenti, ecc.
* [Esportazione di elenchi](../../automating/using/exporting-lists.md) e [importazione di dati utilizzando modelli già esistenti](../../automating/using/importing-data-with-import-templates.md).

### Utenti base {#basic-users}

Grazie all’amministratore funzionale e agli utenti avanzati, gli esperti marketing possono personalizzare, distribuire e monitorare campagne senza dover preoccuparsi della configurazione tecnica. A questo scopo, devono essere assegnati, ad esempio, i ruoli predefiniti **[!UICONTROL Prepare deliveries]**, **[!UICONTROL Workflow]** e **[!UICONTROL Start deliveries]**. Questi ruoli vengono combinati nel gruppo di sicurezza predefinito **[!UICONTROL Standard Users]**. Per ulteriori informazioni, consulta questa [sezione](../../administration/using/list-of-roles.md).

Di seguito sono elencate le attività principali che possono eseguire:

* [Gestione di programmi e campagne](../../start/using/programs-and-campaigns.md):crea campagne di marketing con diversi tipi di attività (e-mail, messaggi SMS, notifiche push, flussi di lavoro, pagine di destinazione).
* Gestione di [profili](../../audiences/using/about-profiles.md) e [profili di test](../../audiences/using/managing-test-profiles.md): gestisci i destinatari identificati e di test che rientrano nel target delle consegne. Aggiungi informazioni quali nome, cognome, informazioni di contatto, abbonamenti, e-mail, ecc.
* [Creazione e invio di messaggi](../../sending/using/confirming-the-send.md): crea il messaggio, seleziona il pubblico, definisci il contenuto del messaggio e i relativi elementi di personalizzazione, invia bozze e successivamente il messaggio finale al pubblico.
* [Creazione e pubblicazione di pagine di destinazione](../../channels/using/getting-started-with-landing-pages.md): crea e gestisci un insieme di servizi che desideri offrire ai clienti, ad esempio moduli di abbonamento o del suo annullamento.
* [Creazione ed esecuzione di flussi di lavoro per campagne](../../automating/using/building-a-workflow.md): automatizza i processi delle campagne utilizzando i flussi di lavoro.
* Controlla le attività di marketing attraverso i [rapporti disponibili](../../reporting/using/defining-the-report-period.md).

## Creazione di un utente {#creating-a-user}

Per aggiungere un utente all’istanza, devi innanzitutto crearlo in Admin Console prima di gestirlo in Adobe Campaign Standard.

1. Dal menu avanzato, seleziona **[!UICONTROL Administration > Users & Security > Users]** e fai clic su **[!UICONTROL User administration]** per accedere ad Admin Console.

   ![](assets/user_management_5.png)

1. In **[!UICONTROL Admin Console]**, fai clic sulla scheda **[!UICONTROL Users]**.

1. Fai clic su **[!UICONTROL Add User]**.

   ![](assets/create_user_2.png)

1. Dalla scheda **[!UICONTROL User details]**, inserisci i dettagli dell’utente quali indirizzo e-mail, nome e cognome.

   ![](assets/create_user_3.png)

1. Dalla scheda **[!UICONTROL Assign products]**, assegna uno o più gruppi di sicurezza all’utente. Per ulteriori informazioni sui gruppi di sicurezza, consulta questa [pagina](../../administration/using/managing-groups-and-users.md).

   Al termine della configurazione, fai clic su **[!UICONTROL Save]**.

   ![](assets/create_user_4.png)

L’utente viene ora creato e deve ricevere un messaggio e-mail di reindirizzamento alla finestra seguente, in cui deve impostare una password e accettare il contratto di utilizzo. Questo utente può quindi connettersi all’istanza di Adobe Campaign Standard.

![](assets/create_user_5.png)

Non appena l’utente esegue l’accesso all’istanza, viene sincronizzato con Adobe Campaign Standard.

Puoi quindi verificare che l’utente sia stato sincronizzato correttamente in Adobe Campaign:

1. Dal menu avanzato **[!UICONTROL Administration > Users & Security > Users]**, seleziona l’utente creato in precedenza.

1. Se necessario, aggiorna il **[!UICONTROL Mobile]**, il **[!UICONTROL Time zone]** o le **[!UICONTROL Regional settings]**.

1. Controlla il gruppo di sicurezza dell’utente. In questo caso, puoi vedere che all’utente è stato assegnato il gruppo di sicurezza **[!UICONTROL Administrators]**.

   >[!Note]
   >
   >Puoi rimuovere o aggiungere gruppi di sicurezza a un utente solo in Admin Console.

   ![](assets/create_user_6.png)

1. Se desideri disattivare l’utente, seleziona **[!UICONTROL Account disabled]**.

1. Nel campo **[!UICONTROL Authorized connection zone]**, seleziona il modo in cui l’utente si connette a questa istanza, ad esempio tramite rete interna o VPN.

1. Fai clic su **[!UICONTROL Save]**.

L’utente è ora pronto per utilizzare Adobe Campaign Standard.
