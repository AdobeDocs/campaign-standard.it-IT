---
title: Ultima versione
description: Questa pagina presenta dettagli sul contenuto dell’ultima versione Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: a8013bac719a45442e09d710db12df0abe721cc4
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 38%

---


# Ultima versione{#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

## Versione 24.1 - Inverno 2024 {#winter-24}

### Miglioramenti {#e-rn-improvements}

* **Notifiche push Android** - Adobe Campaign Standard 24.1 utilizza le API HTTP v1 per inviare messaggi di notifica push Android, per garantire la compatibilità con le modifiche FCM imminenti. Per ulteriori informazioni, consulta [questa nota tecnica](../../administration/using/push-technote.md).

* **Notifiche push di iOS** - Adobe Campaign Standard 24.1 ora supporta i certificati di autenticazione p8 per le notifiche push di iOS. Per attivare queste modifiche, è necessario adattare l’implementazione. Per ulteriori informazioni, consulta [questa nota tecnica](../../administration/using/push-technote.md).

* **Annulla iscrizione mailing list con un solo clic** - A partire dal 1° giugno 2024, Google e Yahoo! chiederanno ai mittenti di conformarsi all’opzione Annulla iscrizione elenco con un clic. Campaign ora supporta questa funzionalità in modalità predefinita. Per ulteriori informazioni, consulta [questa sezione](../../administration/using/configuring-email-channel.md#list-of-email-smtp-parameters).

* **Infrastruttura** - Il database Postgres è stato aggiornato dalla versione 11.22 alla versione 12.17.

* **Tracciamento CTA** - Quando gli utenti si aprono e fanno clic su un URL personalizzato, viene ora tracciato l’URL personalizzato risolto invece dell’URL personalizzato codificato. Questa modifica non è attivata per impostazione predefinita. Per abilitarla nell’istanza Campaign, contatta il rappresentante del tuo Adobe.

* **Menu a discesa dei campi di personalizzazione** - Durante la creazione di modelli di messaggi e-mail transazionali in Adobe Experience Manager, ora puoi selezionare i campi di personalizzazione da un elenco a discesa. Questa modifica non è attivata per impostazione predefinita. Per abilitarla nell’istanza Campaign, contatta il rappresentante del tuo Adobe.

### Correzioni {#e-rn-fixes}

* È stato risolto un problema che impediva la rimozione dalla quarantena degli indirizzi e-mail non recapitati dopo 30 giorni. (CAMP-52977)
* È stato risolto un problema che arrestava il flusso di lavoro Avvisi sulla consegna con il seguente errore: `division by zero`. (CAMP-49786)

