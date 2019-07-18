---
title: Tipi di utenti
seo-title: Tipi di utenti
description: Tipi di utenti
seo-description: 'Gli utenti di Adobe Campaign dispongono di ruoli specifici. Scopri i tipi di utenti principali. '
page-status-flag: never-activated
uuid: 8 c 4 cc 74 a -815 f -4815-af 66-a 7 c 21 bc 754 f 1
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administration
content-type: riferimento
topic-tags: utenti e sicurezza
discoiquuid: 08 c 8712 a -0066-4 b 8 b -8471-2656 b 8 fb 23 ed
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Types of users{#types-of-users}

Gli amministratori possono gestire gli utenti di Admin Console. Gli utenti vengono quindi sincronizzati automaticamente con Adobe Campaign.

For more on this, refer to the [Admin console](https://helpx.adobe.com/enterprise/using/users.html) documentation.

To view the users in Adobe Campaign, click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration > Users & Security > Users]**.

To access the user management interface from Adobe Campaign, click **[!UICONTROL User administration]**.

![](assets/user_management_5.png)

Adobe Campaign consente di assegnare un set di ruoli agli utenti per definire quale parte dell'interfaccia può accedere.

The specific roles and the corresponding authorizations are detailed in the following sections: [understanding roles](../../administration/using/list-of-roles.md) and [authorizations](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Questa segmentazione utente non è obbligatoria, ma solo una rappresentazione dell'utilizzo più comune di Adobe Campaign.

Questa sezione ti aiuterà a capire i tipi principali di utenti di Adobe Campaign. Qui non verranno inclusi tutti i ruoli specifici che l'utente può contenere (avvio di consegne, esportazione, preparazione delle consegne, ecc.). For more information on roles, refer to [List of roles](../../administration/using/list-of-roles.md) and [Managing groups and users](../../administration/using/managing-groups-and-users.md) pages.

Ci concentreremo su come le diverse attività in Adobe Campaign sono suddivise tra tre tipi di utenti principali:

* [Amministratori funzionali](../../administration/using/types-of-users.md#functional-administrators): tra tutti gli utenti dell'organizzazione, sono i più tecnici.
* [Utenti avanzati](../../administration/using/types-of-users.md#advanced-users): configurano tutti gli elementi che gli esperti di marketing devono inviare e monitorare le loro consegne.
* [Utenti di base](../../administration/using/types-of-users.md#basic-users): sono gli addetti al marketing che personalizzano, distribuiscono e monitorano le campagne.

>[!NOTE]
>
>Gli amministratori funzionali sono diversi dagli amministratori tecnici di Adobe. Gli amministratori tecnici di Adobe dispongono di un ruolo interno Adobe che nessun cliente può utilizzare. Gestiscono il provisioning delle istanze, l'hosting, il monitoraggio delle infrastrutture e la supervisione, la risoluzione dei problemi tecnici.

**Argomenti correlati:**

* [Gestione dei video delle autorizzazioni](https://helpx.adobe.com/campaign/kt/acs/using/acs-user-access-rights-feature-video-use.html) utente
* [Elenco dei ruoli](../../administration/using/list-of-roles.md)
* [Elenco di autorizzazioni](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## Functional administrators {#functional-administrators}

Gli amministratori funzionali sono utenti che possono accedere alle parti più tecniche dell'interfaccia. They hold the **[!UICONTROL Administration]** role and make sure that the platform is all set up so that marketers only have to focus on delivering their campaigns.

Functional administrators are the only users who can access the **[!UICONTROL Administration]** menu, in the Adobe Campaign interface. Since these users need to access technical resources, more advanced roles should be assigned to them, such as the **[!UICONTROL Administration]** and **[!UICONTROL Datamodel]** out-of-the-box roles. These roles are combined in the **[!UICONTROL Administrators]** out-of-the-box security group. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Di seguito sono descritte le attività principali che possono eseguire:

* [Gestire utenti e autorizzazioni](../../administration/using/about-access-management.md): gestire l'accesso alla piattaforma (utenti, ruoli, gruppi di sicurezza, unità).
* [Configurate i diversi canali](../../administration/using/about-channel-configuration.md): configurare i diversi canali della piattaforma nonché la gestione di tipologie e quarantena.
* [Configurate le impostazioni generali dell'applicazione](../../administration/using/external-accounts.md): configurare i diversi elementi applicazione (account esterni, opzioni e flussi di lavoro tecnici).
* [Sviluppa nuove funzionalità per migliorare le funzionalità integrate](../../developing/using/data-model-concepts.md): gestire le risorse personalizzate e accedere agli strumenti diagnostici.
* [Configurare i parametri dell'istanza](../../administration/using/branding.md): definire i marchi diversi e configurarne le impostazioni (logo, gestione del tracciamento, dominio dell'URL per accedere alle pagine di destinazione, ecc.).
* [Esportare e importare pacchetti di dati](../../automating/using/managing-packages.md): scambiare risorse tra diverse istanze di Adobe Campaign tramite file XML strutturati.
* [Esportare i registri](../../automating/using/exporting-logs.md) e [definire i modelli di importazione](../../automating/using/defining-import-templates.md).

## Advanced users {#advanced-users}

Gli utenti avanzati sono utenti di marketing che eseguono i casi di utilizzo più tecnici in Adobe Campaign. Configurano tutti gli elementi utilizzati dagli esperti di marketing per inviare e monitorare le loro consegne.

Questo tipo di utente richiede ruoli più generici rispetto agli amministratori funzionali, ma dovrebbe essere ancora in grado di eseguire alcune operazioni tecniche. To do so, they should be assigned, for example, the **[!UICONTROL Export]**, **[!UICONTROL Generic import]** or **[!UICONTROL Workflow]** out-of-the-box roles. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Di seguito sono descritte le attività principali che possono eseguire:

* [Creazione ed esecuzione di flussi di lavoro complessi per la gestione dei dati](../../automating/using/about-data-management-activities.md): importare, arricchire e trasformare dati per trasmettere il database, oppure esportare i dati necessari in file esterni per elaborarli nei propri strumenti.
* [Gestire i modelli](../../start/using/about-templates.md): gestire i modelli per preconfigurare determinati parametri delle attività di marketing in base alle esigenze.
* [Crea query](../../automating/using/editing-queries.md#about-query-editor) e [gestisci i tuoi tipi di pubblico](../../audiences/using/about-audiences.md): creare manualmente i tuoi tipi di pubblico utilizzando query o automaticamente utilizzando flussi di lavoro dedicati.
* [Eseguire la modifica avanzata delle espressioni](../../automating/using/editing-queries.md#about-query-editor): utilizzare funzioni avanzate per manipolare i valori utilizzati per eseguire query specifiche come date, stringhe, campi numerici, ordinamento ecc.
* [Esportare elenchi](../../automating/using/exporting-lists.md) e [importare dati utilizzando modelli esistenti](../../automating/using/importing-data-with-import-templates.md).

## Basic users {#basic-users}

Grazie all'amministratore funzionale e agli utenti avanzati, gli esperti di marketing possono personalizzare, fornire e monitorare le campagne senza doversi preoccupare della configurazione tecnica. To do so, they should be assigned, for example, the **[!UICONTROL Prepare deliveries]**, **[!UICONTROL Workflow]** and **[!UICONTROL Start deliveries]** out-of-the-box roles. These roles are combined in the **[!UICONTROL Standard Users]** out-of-the-box security group. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Di seguito sono descritte le attività principali che possono eseguire:

* [Gestire programmi e campagne](../../start/using/programs-and-campaigns.md): creare campagne di marketing, inclusi diversi tipi di attività (e-mail, messaggi SMS, notifiche push, flussi di lavoro, pagine di destinazione).
* Manage [profiles](../../audiences/using/about-profiles.md) and [test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md): manage the identified and test recipients that will be targeted by your deliveries. Aggiungere informazioni quali nome, cognome, informazioni di contatto, abbonamenti, e-mail, ecc.
* [Creazione e invio di messaggi](../../sending/using/confirming-the-send.md): crea il messaggio, seleziona il pubblico, definisci il contenuto dei messaggi e i suoi elementi di personalizzazione, invia le prove e invia il messaggio finale al pubblico.
* [Creazione e pubblicazione di pagine di destinazione](../../channels/using/about-landing-pages.md): creare e gestire un set di servizi che desideri offrire ai tuoi clienti, ad esempio in abbonamento o in abbonamento.
* [Creazione ed esecuzione dei flussi di lavoro delle campagne](../../automating/using/building-a-workflow.md): automatizzare i processi delle campagne utilizzando i flussi di lavoro.
* Monitor your marketing activities through the [available reports](../../reporting/using/defining-the-report-period.md).

