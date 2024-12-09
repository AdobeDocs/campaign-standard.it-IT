---
title: Note sulla versione 2024
description: In questa pagina sono elencate tutte le versioni del 2024 di Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
source-git-commit: c70e3058f75ba2b11a8311628198e5c02d489964
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 100%

---

# Note sulla versione 2024 {#release-notes-2024}

## Versione 24.1 - Inverno 2024 {#winter-24}

### Miglioramenti {#e-rn-improvements}

* **Notifiche push Android**: Adobe Campaign Standard 24.1 utilizza le API HTTP v1 per inviare messaggi di notifica push Android e garantire la compatibilità con le modifiche FCM imminenti. Per ulteriori informazioni, consulta [questa nota tecnica](../../administration/using/push-technote.md).

* **Notifiche push iOS**: Adobe Campaign Standard 24.1 ora supporta i certificati di autenticazione p8 per le notifiche push di iOS. Per attivare queste modifiche, è necessario adattare l’implementazione. Per ulteriori informazioni, consulta [questa nota tecnica](../../administration/using/push-technote.md).

* **Annullamento iscrizione a mailing list con un clic**: a partire dal 1° giugno 2024, Google e Yahoo! chiederanno ai mittenti di conformarsi all’opzione Annulla iscrizione elenco con un clic. Campaign ora supporta questa funzionalità in modalità predefinita. Per ulteriori informazioni, consulta [questa sezione](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters).

* **Infrastruttura**: il database Postgres è stato aggiornato dalla versione 11.22 alla versione 12.17.

* **Tracciamento CTA**: quando gli utenti aprono un URL personalizzato e ci cliccano sopra, ora viene tracciato l’URL personalizzato risolto invece dell’URL personalizzato codificato. Questa modifica non è abilitata per impostazione predefinita. Per abilitarla nella tua istanza di Campaign, contatta il tuo rappresentante Adobe.

* **Menu a discesa dei campi di personalizzazione**: durante la creazione di modelli di messaggi e-mail transazionali in Adobe Experience Manager, ora puoi selezionare i campi di personalizzazione da un elenco a discesa. Questa modifica non è abilitata per impostazione predefinita. Per abilitarla nella tua istanza di Campaign, contatta il tuo rappresentante Adobe.

### Correzioni {#e-rn-fixes}

* È stato risolto un problema che impediva la rimozione dalla quarantena degli indirizzi e-mail non recapitati dopo 30 giorni. (CAMP-52977)
* È stato risolto un problema che arrestava il flusso di lavoro Avvisi sulla consegna con il seguente errore: `division by zero`. (CAMP-49786)

