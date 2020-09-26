---
title: Guida introduttiva all’amministrazione di Campaign Standard
description: Scopri utenti e autorizzazioni di gestione, linee guida per il monitoraggio, configurazioni specifiche per il canale e linee guida sulle impostazioni delle applicazioni.
page-status-flag: never-activated
uuid: 64c34729-5c98-4db0-9131-af6dd0e78fb4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: about-administrating-adobe-campaign
discoiquuid: 5587530a-2308-4be1-9f56-19eeb7a924d5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4ae70ca95cb282a694c41361d859b19385db5673
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 14%

---


# Guida introduttiva all’amministrazione di Campaign Standard {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">Menu Amministrazione</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">Utenti e sicurezza</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">Configurazione canali</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">Impostazioni applicazione</a></p></td></tr>
</table>

Come soluzione basata su cloud,  Adobe Campaign offre agli amministratori diversi modi per configurare l&#39;applicazione. Sebbene la configurazione dell&#39;infrastruttura sia eseguita dal Adobe , gli amministratori funzionali possono eseguire varie operazioni di configurazione descritte di seguito.

>[!NOTE]
>
>In caso di domande o richieste su questioni relative all&#39;implementazione e alla configurazione, contatta l&#39;amministratore dell&#39;account  Adobe.

## Menu Amministrazione {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

Le diverse operazioni di amministrazione  Adobe Campaign vengono eseguite tramite il **[!UICONTROL Administration]** menu accessibile quando si fa clic sul logo Adobe Campaign  nell&#39;angolo superiore sinistro. Questa parte dell&#39;interfaccia è accessibile solo dagli amministratori funzionali della piattaforma.

I diversi menu disponibili sono:

* [Utenti e protezione](../../administration/using/about-access-management.md): Questo menu consente di gestire l&#39;accesso alla piattaforma (utenti, ruoli, gruppi di sicurezza, unità).
* [Canali](../../administration/using/about-channel-configuration.md): Questo menu raggruppa i parametri tecnici collegati ai diversi canali della piattaforma (E-mail, mobile), nonché la gestione della tipologia e della quarantena.
* [Impostazioni](../../administration/using/external-accounts.md)applicazione: Questo menu consente di configurare diversi elementi dell’applicazione (account esterni, opzioni, flussi di lavoro tecnici).
* [Sviluppo](../../developing/using/data-model-concepts.md): Questo menu consente di gestire le risorse personalizzate e di accedere agli strumenti diagnostici.
* [Impostazioni](../../administration/using/branding.md)istanza: Questo menu consente di definire i diversi marchi e configurarne le impostazioni (logo, gestione del tracciamento, dominio URL per accedere alle pagine di destinazione, ecc.).
* [Distribuzione](../../automating/using/managing-packages.md): Questo menu raggruppa le opzioni di importazione ed esportazione del pacchetto.
* [Metriche](../../audiences/using/active-profiles.md)cliente:  Adobe Campaign fornisce un rapporto che mostra il numero di profili attivi. Questo rapporto è solo informativo, non ha un impatto diretto sulla fatturazione.
* [Strumenti](https://helpx.adobe.com/it/campaign/kb/campaign-privacy.html)per la privacy: Questo menu consente di creare e eliminare le richieste di accesso e di tracciarne l’evoluzione.

## Utenti e sicurezza {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Invitate gli utenti ad accedere all&#39;applicazione e a gestire i gruppi **di** sicurezza, ovvero insiemi di utenti che condividono gli stessi ruoli e diritti all&#39;interno dell&#39;organizzazione. By default, Adobe Campaign offers a set of **roles** which allows you to define unitary authorizations assigned to users and user groups. Combined with **organizational units**, roles give users a filtered view of the interface and define their access to the different features.

Lo standard Campaign consente inoltre di monitorare le informazioni relative alla sicurezza. Puoi recuperare informazioni sulle esportazioni di dati eseguite dagli utenti tramite **[!UICONTROL Export audits]** lo schermo e utilizzare lo **[!UICONTROL Licenses]** schermo per monitorare tutte le licenze Campaign installate all&#39;interno dell&#39;organizzazione, nonché informazioni diverse come il numero di build, la versione del rilascio e i termini di contratto.

Leggi tutto:

* [Gestione utenti](../../administration/using/users-management.md)
* [Unità organizzative](../../administration/using/organizational-units.md)
* [Elenco di ruoli](../../administration/using/list-of-roles.md)
* [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md)
* [Controllo dei registri di esportazione](../../administration/using/auditing-export-logs.md)
* [Licenze](../../administration/using/licenses.md)

## Configurazione canali {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Tutti i canali di comunicazione  Adobe Campaign devono essere configurati correttamente per poter inviare messaggi in modo efficace., **[!UICONTROL Channel]** il menu consente di gestire i parametri tecnici collegati ai diversi canali.

Configurare vari parametri **e-mail** : regole di elaborazione per rimbalzi, quarantena, proprietà e-mail e parametri di routing, regole del tipo. Definite le configurazioni e le proprietà di routing per il canale **SMS** , nonché la codifica e i formati SMS.

Configurate le applicazioni **** mobili per poter inviare messaggi in-app e notifiche push tramite gli SDK Adobe Experience Platform, e configurate i messaggi **** transazionali creando e configurando eventi.

Leggi tutto:

* [Informazioni sulla configurazione dei canali](../../administration/using/about-channel-configuration.md)
* [Configurazione del canale e-mail](../../administration/using/configuring-email-channel.md)
* [Configurazione del canale SMS](../../administration/using/configuring-sms-channel.md)
* [Configurazione di un’applicazione mobile](../../administration/using/configuring-a-mobile-application.md)
* [Configurazione della messaggistica transazionale](../../administration/using/configuring-transactional-messaging.md)

## Impostazioni applicazione {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard viene fornito con diversi elementi dell&#39;applicazione che possono essere configurati in base alle proprie esigenze.

Configurate account **** esterni, utilizzati per collegare  Adobe Campaign ai server esterni. Accedi alle mappature di destinazione Campaign Standard e monitora la tua piattaforma tramite flussi di lavoro **** tecnici.

Definite uno o più **marchi** per la vostra organizzazione e configurate l&#39;invio di notifiche **in tempo** reale all&#39;interno dell&#39;applicazione in caso di importanti attività di sistema.

Leggi tutto:

* [Informazioni sulle impostazioni di Campaign Standard](../../administration/using/about-campaign-standard-settings.md)
* [Account esterni](../../administration/using/external-accounts.md)
* [Mappature target in Campaign](../../administration/using/target-mappings-in-campaign.md)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Branding](../../administration/using/branding.md)
* [Invio di notifiche interne](../../administration/using/sending-internal-notifications.md)

## Risorse aggiuntive

* [Gestione dei diritti di accesso degli utenti (video)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/administrating/managing-user-access-rights.html)
* [Documentazione del Pannello di controllo Campaign](https://docs.adobe.com/content/help/it-IT/control-panel/using/control-panel-home.html)
