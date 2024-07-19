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
source-wordcount: '631'
ht-degree: 12%

---

# Introduzione all’amministrazione di Campaign Standard {#about-administrating-adobe-campaign}

<table>
<tr><td><img src="assets/do-not-localize/icon_menu.svg" width="60px"><p><a href="#administration-menu">Menu Amministrazione</a></p></td>
<td><img src="assets/do-not-localize/icon_users.svg" width="60px"><p><a href="#users-security">Utenti e sicurezza</a></p></td>
<td><img src="assets/do-not-localize/icon_channels.svg" width="60px"><p><a href="#channels-configuration">Configurazione canali</a></p></td>
<td><img src="assets/do-not-localize/icon_settings.svg" width="60px"><p><a href="#application-settings">Impostazioni applicazione</a></p></td></tr>
</table>

In quanto soluzione basata su cloud, Adobe Campaign offre agli amministratori diversi modi per configurare l’applicazione. Anche se la configurazione dell’infrastruttura viene eseguita da Adobe, gli amministratori funzionali possono eseguire varie operazioni di configurazione descritte di seguito.

>[!NOTE]
>
>In caso di domande o richieste su questioni relative all’implementazione e alla configurazione, contatta il responsabile dell’account di Adobe.

Gli utenti Admin possono inoltre sfruttare il Pannello di controllo Campaign Campaign per gestire le impostazioni e tenere traccia dell’utilizzo di ciascuna istanza. Per ulteriori informazioni, consulta la [documentazione dedicata](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=it).

## Menu Amministrazione {#administration-menu}

<img src="assets/do-not-localize/icon_menu.svg" width="60px">

Le diverse operazioni di amministrazione di Adobe Campaign vengono eseguite tramite il menu **[!UICONTROL Administration]** accessibile facendo clic sul logo Adobe Campaign nell&#39;angolo in alto a sinistra. Questa parte dell’interfaccia è accessibile solo dagli amministratori funzionali della piattaforma.

I diversi menu disponibili sono:

* [Utenti e sicurezza](../../administration/using/about-access-management.md): questo menu ti consente di gestire l&#39;accesso alla piattaforma (utenti, ruoli, gruppi di sicurezza, unità).
* [Canali](../../administration/using/about-channel-configuration.md): questo menu raggruppa i parametri tecnici collegati ai diversi canali della piattaforma (e-mail, dispositivi mobili), nonché alla gestione della tipologia e della quarantena.
* [Impostazioni applicazione](../../administration/using/external-accounts.md): questo menu consente di configurare diversi elementi dell&#39;applicazione (account esterni, opzioni, flussi di lavoro tecnici).
* [Sviluppo](../../developing/using/data-model-concepts.md): questo menu ti consente di gestire le risorse personalizzate e di accedere agli strumenti di diagnostica.
* [Impostazioni istanza](../../administration/using/branding.md): in questo menu puoi definire i diversi brand e configurarne le impostazioni (logo, gestione del tracciamento, URL di accesso alle pagine di destinazione, ecc.).
* [Distribuzione](../../automating/using/managing-packages.md): questo menu raggruppa le opzioni di importazione ed esportazione del pacchetto.
* [Metriche cliente](../../audiences/using/active-profiles.md): Adobe Campaign fornisce un rapporto che mostra il numero di profili attivi. Questo report è solo informativo, non ha un impatto diretto sulla fatturazione.
* [Strumenti per la privacy](../../start/using/privacy-management.md): questo menu ti consente di creare l&#39;accesso RGPD e di eliminare le richieste e di tenere traccia della loro evoluzione.

## Utenti e sicurezza {#users-security}

<img src="assets/do-not-localize/icon_users.svg"  width="60px">

Invita gli utenti ad accedere all&#39;applicazione e a gestire **gruppi di sicurezza**, ovvero insiemi di utenti che condividono gli stessi ruoli e diritti all&#39;interno dell&#39;organizzazione. Per impostazione predefinita, Adobe Campaign offre un set di **ruoli** che ti consente di definire autorizzazioni unitarie assegnate a utenti e gruppi di utenti. In combinazione con **unità organizzative**, i ruoli forniscono agli utenti una visualizzazione filtrata dell&#39;interfaccia e ne definiscono l&#39;accesso alle diverse funzionalità.

Campaign standard consente inoltre di monitorare le informazioni relative alla sicurezza. È possibile recuperare le informazioni relative alle esportazioni di dati eseguite dagli utenti tramite la schermata **[!UICONTROL Export audits]** e utilizzare la schermata **[!UICONTROL Licenses]** per monitorare tutte le licenze di Campaign installate all&#39;interno dell&#39;organizzazione, nonché informazioni diverse come il numero di build, la versione del rilascio e i termini del contratto.

Ulteriori informazioni:

* [Gestione utenti](../../administration/using/users-management.md)
* [Unità organizzative](../../administration/using/organizational-units.md)
* [Elenco di ruoli](../../administration/using/list-of-roles.md)
* [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md)
* [Controllo dei registri di esportazione](../../administration/using/auditing-export-logs.md)
* [Licenze](../../administration/using/licenses.md)

## Configurazione canali {#channels-configuration}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Tutti i canali di comunicazione in Adobe Campaign devono essere configurati correttamente per poter inviare messaggi in modo efficace. Il menu **[!UICONTROL Channel]** ti consente di gestire i parametri tecnici collegati ai diversi canali.

Configura vari parametri **email**: regole di elaborazione per mancati recapiti, quarantene, proprietà e parametri di indirizzamento e regole di tipo. Definisci le configurazioni e le proprietà di indirizzamento per il canale **SMS**, nonché la codifica e i formati di SMS.

Configura **applicazioni mobili** per poter inviare messaggi in-app e notifiche push tramite gli SDK di Adobe Experience Platform.

Ulteriori informazioni:

* [Informazioni sulla configurazione dei canali](../../administration/using/about-channel-configuration.md)
* [Configurazione del canale e-mail](../../administration/using/configuring-email-channel.md)
* [Configurazione del canale SMS](../../administration/using/configuring-sms-channel.md)
* [Configurazione di un’app per dispositivi mobili](../../administration/using/configuring-a-mobile-application.md)

## Impostazioni applicazione {#application-settings}

<img src="assets/do-not-localize/icon_settings.svg" width="60px">

Campaign Standard viene fornito con diversi elementi dell’applicazione che possono essere configurati in base alle tue esigenze.

Configura **account esterni**, utilizzati per connettere Adobe Campaign a server esterni. Accedi alle mappature di destinazione di Campaign Standard e monitora la tua piattaforma utilizzando **flussi di lavoro tecnici**.

Definisci uno o più **marchi** per la tua organizzazione e configura l&#39;invio di **notifiche in tempo reale** all&#39;interno dell&#39;applicazione in caso di attività importanti del sistema.

Ulteriori informazioni:

* [Informazioni sulle impostazioni di Campaign Standard](../../administration/using/about-campaign-standard-settings.md)
* [Account esterni](../../administration/using/external-accounts.md)
* [Mappature target in Campaign](../../administration/using/target-mappings-in-campaign.md)
* [Flussi di lavoro tecnici](../../administration/using/technical-workflows.md)
* [Branding](../../administration/using/branding.md)
* [Invio di notifiche interne](../../administration/using/sending-internal-notifications.md)
