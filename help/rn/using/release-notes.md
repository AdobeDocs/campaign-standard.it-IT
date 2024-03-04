---
title: Ultima versione
description: Questa pagina presenta dettagli sul contenuto dell’ultima versione Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 3baadaf774092bb48a029e098e8f56170660400b
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 84%

---


# Ultima versione{#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->

## Versione 24.1 - Inverno 2024 {#winter-24}

### Miglioramenti {#e-rn-improvements}

Adobe Campaign Standard 24.1 utilizza le API HTTP v1 per inviare messaggi di notifica push Android e garantire la compatibilità con le modifiche FCM imminenti. Per ulteriori informazioni, consulta [questa nota tecnica](../../administration/using/push-technote.md).

Adobe Campaign Standard 24.1 ora supporta i certificati di autenticazione p8 per le notifiche push di iOS. Per attivare queste modifiche, è necessario adattare l’implementazione. Per ulteriori informazioni, consulta [questa nota tecnica](../../administration/using/push-technote.md).

A partire dal 1° giugno 2024, Google e Yahoo! richiederà ai mittenti di conformarsi all’opzione One-Click List-Unsubscribe. Campaign ora supporta questa funzionalità pronta all’uso. Per ulteriori informazioni, consulta [questa sezione](../../administration/using/configuring-email-channel.md#email-channel-parameters).


### Correzioni {#e-rn-fixes}

* È stato risolto un problema che impediva la rimozione dalla quarantena degli indirizzi e-mail non recapitati dopo 30 giorni. (CAMP-52977)
* È stato risolto un problema che arrestava il flusso di lavoro Avvisi sulla consegna con il seguente errore: `division by zero`. (CAMP-49786)

