---
title: Introduzione all’amministrazione di Campaign Standard
description: Scopri come gestire utenti e autorizzazioni, le linee guida per il monitoraggio, le configurazioni specifiche per canale e le linee guida sulle impostazioni delle applicazioni
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 9676b5e8-4c34-4848-8616-235e0bac5d6b
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 15%

---

# Introduzione all’amministrazione di Campaign Standard {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">Menu Amministrazione</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">Utenti e sicurezza</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">Configurazione dei canali</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">Impostazioni applicazione</a></p></td></tr>
</table>

In qualità di soluzione basata su cloud, Adobe Campaign offre agli amministratori diversi modi per configurare l’applicazione. Sebbene la configurazione dell&#39;infrastruttura sia eseguita per Adobe, gli amministratori funzionali possono eseguire varie operazioni di configurazione descritte di seguito.

>[!NOTE]
>
>In caso di domande o richieste su questioni di implementazione e configurazione, contatta l’amministratore del tuo account Adobe.

Gli utenti amministratori possono inoltre utilizzare il Pannello di controllo Campaign Campaign per gestire le impostazioni e tenere traccia degli utilizzi per ciascuna istanza. Per ulteriori informazioni, consulta la [documentazione dedicata](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it).

## Menu Amministrazione {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

Le diverse operazioni di amministrazione di Adobe Campaign vengono eseguite tramite il **[!UICONTROL Administration]** accessibile facendo clic sul logo Adobe Campaign nell’angolo in alto a sinistra. Questa parte dell’interfaccia è accessibile solo dagli amministratori funzionali della piattaforma.

I diversi menu disponibili sono:

* [Utenti e sicurezza](../../administration/using/about-access-management.md): Questo menu ti consente di gestire l’accesso alla piattaforma (utenti, ruoli, gruppi di sicurezza, unità).
* [Canali](../../administration/using/about-channel-configuration.md): Questo menu raggruppa i parametri tecnici collegati ai diversi canali della piattaforma (E-mail, mobile), nonché la gestione della tipologia e della quarantena.
* [Impostazioni applicazione](../../administration/using/external-accounts.md): Questo menu ti consente di configurare diversi elementi dell’applicazione (account esterni, opzioni, flussi di lavoro tecnici).
* [Sviluppo](../../developing/using/data-model-concepts.md): Questo menu consente di gestire le risorse personalizzate e accedere agli strumenti diagnostici.
* [Impostazioni delle istanze](../../administration/using/branding.md): In questo menu puoi definire i diversi marchi e configurarne le impostazioni (logo, gestione del tracciamento, dominio URL per accedere alle pagine di destinazione, ecc.).
* [Distribuzione](../../automating/using/managing-packages.md): Questo menu raggruppa le opzioni di importazione ed esportazione del pacchetto.
* [Metriche cliente](../../audiences/using/active-profiles.md): Adobe Campaign fornisce un rapporto che mostra il numero di profili attivi. Questo rapporto è solo informativo, non ha un impatto diretto sulla fatturazione.
* [Strumenti per la privacy](../../start/using/privacy-management.md): Questo menu ti consente di creare le richieste di accesso e di cancellazione RGPD e di tracciarne l’evoluzione.

## Utenti e sicurezza {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Invita gli utenti ad accedere all’applicazione e a gestire **gruppi di sicurezza**: set di utenti che condividono gli stessi ruoli e diritti all’interno della tua organizzazione. Per impostazione predefinita, Adobe Campaign offre un set di **ruoli** che consente di definire autorizzazioni unitarie assegnate a utenti e gruppi di utenti. Combinato con **unità organizzative**, i ruoli forniscono agli utenti una visualizzazione filtrata dell’interfaccia e ne definiscono l’accesso alle diverse funzioni.

Campaign Standard consente inoltre di monitorare le informazioni relative alla sicurezza. Puoi recuperare informazioni sulle esportazioni di dati effettuate dagli utenti tramite **[!UICONTROL Export audits]** e sfrutta la **[!UICONTROL Licenses]** per monitorare tutte le licenze Campaign installate all’interno della tua organizzazione, nonché diverse informazioni quali il numero di build, la versione di rilascio e i termini del contratto.

Maggiori informazioni:

* [Gestione utenti](../../administration/using/users-management.md)
* [Unità organizzative](../../administration/using/organizational-units.md)
* [Elenco di ruoli](../../administration/using/list-of-roles.md)
* [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md)
* [Controllo dei registri di esportazione](../../administration/using/auditing-export-logs.md)
* [Licenze](../../administration/using/licenses.md)

## Configurazione dei canali {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Tutti i canali di comunicazione in Adobe Campaign devono essere configurati correttamente per essere in grado di inviare messaggi in modo efficace.,Il **[!UICONTROL Channel]**  consente di gestire i parametri tecnici collegati ai diversi canali.

Configura vari **email** parametri: regole di elaborazione per rimbalzo, quarantena, proprietà e-mail e parametri di indirizzamento, regole di tipologia. Definire le configurazioni di routing e le proprietà per **SMS** , nonché la codifica e i formati SMS.

Configurazione **applicazioni mobili** per poter inviare messaggi in-app e notifiche push utilizzando gli SDK Adobe Experience Platform.

Maggiori informazioni:

* [Informazioni sulla configurazione dei canali](../../administration/using/about-channel-configuration.md)
* [Configurazione del canale e-mail](../../administration/using/configuring-email-channel.md)
* [Configurazione del canale SMS](../../administration/using/configuring-sms-channel.md)
* [Configurazione di un’app per dispositivi mobili](../../administration/using/configuring-a-mobile-application.md)

## Impostazioni applicazione {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard viene fornito con diversi elementi dell’applicazione che possono essere configurati in base alle tue esigenze.

Configurazione **conti esterni**, che vengono utilizzati per collegare Adobe Campaign a server esterni. Accedi alle mappature di destinazione di Campaign Standard e monitora la tua piattaforma utilizzando **flussi di lavoro tecnici**.

Definisci uno o più **marchi** per la tua organizzazione e configura l’invio di **notifiche in tempo reale** nell&#39;ambito dell&#39;applicazione in caso di importanti attività del sistema.

Maggiori informazioni:

* [Informazioni sulle impostazioni di Campaign Standard](../../administration/using/about-campaign-standard-settings.md)
* [Account esterni](../../administration/using/external-accounts.md)
* [Mappature target in Campaign](../../administration/using/target-mappings-in-campaign.md)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Branding](../../administration/using/branding.md)
* [Invio di notifiche interne](../../administration/using/sending-internal-notifications.md)
