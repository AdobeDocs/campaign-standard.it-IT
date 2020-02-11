---
title: Gestione utenti
description: 'Gli utenti di Adobe Campaign hanno ruoli specifici. Scoprite i tipi di utente principali. '
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
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# Gestione utenti{#users-management}

## Informazioni sugli utenti {#about-users}

Adobe Campaign consente di assegnare un set di ruoli agli utenti per definire a quale parte dell&#39;interfaccia possono accedere.

I ruoli specifici e le autorizzazioni corrispondenti sono descritti nelle sezioni seguenti: [informazioni su ruoli](../../administration/using/list-of-roles.md) e [autorizzazioni](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Gli amministratori possono gestire gli utenti dalla console di amministrazione. Gli utenti vengono quindi sincronizzati automaticamente con Adobe Campaign. Per ulteriori informazioni, consulta la documentazione di [Admin Console](https://helpx.adobe.com/enterprise/using/users.html) .

Per visualizzare gli utenti in Adobe Campaign, fai clic sul **[!UICONTROL Adobe Campaign]** logo, nell&#39;angolo in alto a sinistra, quindi seleziona **[!UICONTROL Administration > Users & Security > Users]**.

Per accedere all&#39;interfaccia di gestione utenti da Adobe Campaign, fai clic su **[!UICONTROL User administration]**.

![](assets/user_management_5.png)

**Argomenti correlati:**

* [Video sulla gestione delle autorizzazioni](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/access-management.html) utente
* [Elenco di ruoli](../../administration/using/list-of-roles.md)
* [Elenco delle autorizzazioni](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

## Tipo di utenti {#type-of-users}

Questa segmentazione utente non è obbligatoria, ma è solo una rappresentazione dell&#39;utilizzo più comune di Adobe Campaign.

Questa sezione ti aiuterà a capire i tipi principali di utenti di Adobe Campaign. In questo caso, non verranno inclusi tutti i ruoli specifici che un utente può detenere (consegne iniziali, esportazioni, preparazione di consegne, ecc.). Per ulteriori informazioni sui ruoli, consulta [Elenco di ruoli](../../administration/using/list-of-roles.md) e [Gestione di gruppi e pagine di utenti](../../administration/using/managing-groups-and-users.md) .

Ci concentreremo piuttosto sul modo in cui le diverse attività in Adobe Campaign sono suddivise tra tre tipi di utenti principali:

* [Amministratori](#functional-administrators)funzionali: tra tutti gli utenti dell&#39;organizzazione, questi sono i più tecnici.
* [Utenti](#advanced-users)avanzati: configurano tutti gli elementi di cui gli esperti di marketing hanno bisogno per inviare e monitorare le consegne.
* [Utenti](#basic-users)di base: sono gli esperti di marketing che personalizzano, distribuiscono e monitorano le loro campagne.

>[!NOTE]
>
>Gli amministratori funzionali sono diversi dagli amministratori tecnici Adobe. Gli amministratori tecnici Adobe ricoprono un ruolo interno di Adobe che nessun cliente può usare. Gestiscono il provisioning delle istanze, l&#39;hosting, il monitoraggio e la supervisione dell&#39;infrastruttura, la risoluzione dei problemi tecnici.

### Amministratori funzionali {#functional-administrators}

Gli amministratori funzionali sono utenti che possono accedere alle parti più tecniche dell&#39;interfaccia. Hanno il **[!UICONTROL Administration]** ruolo e si accertano che la piattaforma sia configurata in modo che gli esperti di marketing debbano concentrarsi solo sulla distribuzione delle loro campagne.

Gli amministratori di funzionalità sono gli unici utenti che possono accedere al **[!UICONTROL Administration]** menu, nell&#39;interfaccia di Adobe Campaign. Poiché questi utenti devono accedere alle risorse tecniche, è necessario assegnare loro ruoli più avanzati, come i ruoli **[!UICONTROL Administration]** e **[!UICONTROL Datamodel]** out-of-the-box. Questi ruoli vengono combinati nel gruppo di sicurezza **[!UICONTROL Administrators]** out-of-the-box. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Di seguito sono elencate le attività principali che possono eseguire:

* [Gestisci utenti e autorizzazioni](../../administration/using/about-access-management.md): gestire l&#39;accesso alla piattaforma (utenti, ruoli, gruppi di sicurezza, unità).
* [Configurare i diversi canali](../../administration/using/about-channel-configuration.md): impostare i diversi canali della piattaforma, nonché la gestione della tipologia e della quarantena.
* [Configurare le impostazioni](../../administration/using/external-accounts.md)generali dell’applicazione: configurare i diversi elementi dell’applicazione (account esterni, opzioni, flussi di lavoro tecnici).
* [Sviluppare nuove funzionalità per migliorare le funzionalità](../../developing/using/data-model-concepts.md)pronte all&#39;uso: gestire le risorse personalizzate e accedere agli strumenti diagnostici.
* [Impostate i parametri](../../administration/using/branding.md)di istanza: definisci i tuoi marchi e configurane le impostazioni (logo, gestione del tracciamento, dominio URL per accedere alle pagine di destinazione, ecc.).
* [Esportare e importare pacchetti](../../automating/using/managing-packages.md)di dati: scambiare risorse tra diverse istanze di Adobe Campaign tramite file XML strutturati.
* [Esportare registri](../../automating/using/exporting-logs.md) e [definire modelli](../../automating/using/defining-import-templates.md)di importazione.

### Utenti avanzati {#advanced-users}

Gli utenti avanzati sono utenti di marketing che eseguono i casi di utilizzo più tecnici in Adobe Campaign. Preconfigurano tutti gli elementi utilizzati dagli esperti di marketing per inviare e monitorare le consegne.

Questo tipo di utente richiede ruoli più generali rispetto agli amministratori funzionali, ma deve comunque essere in grado di eseguire alcune operazioni tecniche. A tal fine, devono essere assegnati, ad esempio, i ruoli **[!UICONTROL Export]****[!UICONTROL Generic import]** o **[!UICONTROL Workflow]** out-of-the-box. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Di seguito sono elencate le attività principali che possono eseguire:

* [Creazione ed esecuzione di flussi di lavoro](../../automating/using/about-data-management-activities.md)complessi per la gestione dei dati: importare, arricchire e trasformare i dati per alimentare il database oppure esportare i dati necessari in file esterni per elaborarli nei propri strumenti.
* [Gestire i modelli](../../start/using/marketing-activity-templates.md): gestisci i tuoi modelli per preconfigurare alcuni parametri delle tue attività di marketing in base alle tue esigenze.
* [Crea query](../../automating/using/editing-queries.md#about-query-editor) e [gestisci il pubblico](../../audiences/using/about-audiences.md): create i tipi di pubblico manualmente utilizzando le query o automaticamente utilizzando flussi di lavoro dedicati.
* [Eseguire la modifica](../../automating/using/editing-queries.md#about-query-editor)avanzata delle espressioni: utilizzare funzioni avanzate per manipolare i valori utilizzati per eseguire query specifiche come date, stringhe, campi numerici, ordinamento, ecc.
* [Esportare elenchi](../../automating/using/exporting-lists.md) e [importare dati utilizzando modelli](../../automating/using/importing-data-with-import-templates.md)di importazione esistenti.

### Utenti di base {#basic-users}

Grazie all&#39;amministratore funzionale e agli utenti avanzati, gli addetti al marketing possono personalizzare, distribuire e monitorare le proprie campagne senza dover preoccuparsi della configurazione tecnica. A tal fine, devono essere assegnati, ad esempio, i ruoli **[!UICONTROL Prepare deliveries]** e **[!UICONTROL Workflow]** **[!UICONTROL Start deliveries]** out-of-the-box. Questi ruoli vengono combinati nel gruppo di sicurezza **[!UICONTROL Standard Users]** out-of-the-box. For more on this, refer to this [section](../../administration/using/list-of-roles.md).

Di seguito sono elencate le attività principali che possono eseguire:

* [Gestione di programmi e campagne](../../start/using/programs-and-campaigns.md): creare campagne di marketing con diversi tipi di attività (e-mail, messaggi SMS, notifiche push, flussi di lavoro, pagine di destinazione).
* Gestire [profili](../../audiences/using/about-profiles.md) e profili [di](../../audiences/using/managing-test-profiles.md)prova: gestire i destinatari identificati e di test che verranno interessati dalle consegne. Aggiungi informazioni quali nome, cognome, informazioni di contatto, iscrizioni, e-mail, ecc.
* [Crea e invia messaggi](../../sending/using/confirming-the-send.md): create il messaggio, selezionate il pubblico, definite il contenuto del messaggio e i relativi elementi di personalizzazione, inviate prove di autenticità e inviate il messaggio finale al pubblico.
* [Creare e pubblicare pagine](../../channels/using/getting-started-with-landing-pages.md)di destinazione: creare e gestire un set di servizi che si desidera offrire ai clienti, ad esempio moduli di iscrizione o di annullamento dell&#39;iscrizione.
* [Creare ed eseguire flussi di lavoro](../../automating/using/building-a-workflow.md)campagna: automatizza i processi delle campagne utilizzando i flussi di lavoro.
* Controlla le tue attività di marketing attraverso i rapporti [](../../reporting/using/defining-the-report-period.md)disponibili.

## Creazione di un utente {#creating-a-user}

Per aggiungere un utente all&#39;istanza, devi prima crearlo nell&#39;Admin Console prima di gestirlo in Adobe Campaign Standard.

1. Dal menu avanzato, selezionate **[!UICONTROL Administration > Users & Security > Users]** e fate clic **[!UICONTROL User administration]** per accedere alla console di amministrazione.

   ![](assets/user_management_5.png)

1. In **[!UICONTROL Admin Console]**, fare clic sulla **[!UICONTROL Users]** scheda.

1. Clic **[!UICONTROL Add User]**.

   ![](assets/create_user_2.png)

1. Dalla **[!UICONTROL User details]** scheda, inserite i dettagli dell&#39;utente, ad esempio indirizzo e-mail, nome e cognome.

   ![](assets/create_user_3.png)

1. Dalla **[!UICONTROL Assign products]** scheda, assegnate uno o più gruppi di sicurezza all’utente. Per ulteriori informazioni sui gruppi di sicurezza, consultate questa [pagina](../../administration/using/managing-groups-and-users.md).

   Fare clic **[!UICONTROL Save]** al termine della configurazione.

   ![](assets/create_user_4.png)

L&#39;utente viene creato e deve ricevere un messaggio e-mail di reindirizzamento alla finestra seguente, in cui l&#39;utente deve impostare una password e accettare il contratto di utilizzo. Questo utente potrà quindi connettersi all&#39;istanza di Adobe Campaign Standard.

![](assets/create_user_5.png)

L&#39;utente verrà sincronizzato con Adobe Campaign Standard non appena effettuerà l&#39;accesso all&#39;istanza.

Puoi quindi verificare che l&#39;utente sia stato sincronizzato correttamente in Adobe Campaign:

1. Dal menu avanzato **[!UICONTROL Administration > Users & Security > Users]** selezionate l’utente creato in precedenza.

1. Aggiornate il **[!UICONTROL Mobile]**, **[!UICONTROL Time zone]** o **[!UICONTROL Regional settings]** se necessario.

1. Controllare il gruppo di sicurezza dell&#39;utente. Qui potete vedere che all&#39;utente è stato assegnato il gruppo di **[!UICONTROL Administrators]** sicurezza.

   >[!Note]
   >
   >I gruppi di sicurezza possono essere rimossi o aggiunti a un utente solo in Admin Console.

   ![](assets/create_user_6.png)

1. Selezionare **[!UICONTROL Account disabled]** se si desidera disattivare l&#39;utente.

1. Nel **[!UICONTROL Authorized connection zone]** campo, selezionare il modo in cui l&#39;utente si connetterà a questa istanza, ad esempio rete interna o VPN.

1. Clic **[!UICONTROL Save]**.

L&#39;utente è ora pronto per utilizzare Adobe Campaign Standard.
