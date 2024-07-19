---
title: Note sulla versione più recente
description: Questa pagina presenta dettagli sul contenuto dell’ultima versione Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 44c436a74a0a4aa688427bfb36d506566d57ac3a
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 100%

---


# Note sulla versione più recente {#latest-release}

<!--
![Control Panel](assets/do-not-localize/cp-icon.png) **New Control Panel release**. [Learn more](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html){target="_blank"}.-->


## Note preliminari sulla versione {#e-new-release}

Questa sezione elenca i miglioramenti e le modifiche inclusi nella prossima versione di Campaign Standard.

>[!CAUTION]
>
>Questo contenuto è soggetto a modifiche senza preavviso fino alla data di aggiornamento degli ambienti di staging. Ulteriori informazioni sono disponibili nella [pagina di pianificazione del rilascio](../../rn/using/release-planning.md).

**Versione 24.2 - Estate 2024**

* **Data di rilascio**: agosto 2024 (disponibilità limitata) - [Ulteriori informazioni](../../rn/using/release-planning.md).

* **Migrazione alle credenziali OAuth server-to-server**

  A partire da questa versione, poiché le credenziali dell’account di servizio (JWT) sono state dichiarate obsolete da Adobe, le integrazioni in uscita di Campaign con le soluzioni e le app Adobe ora si basano sulle credenziali OAuth server-to-server. Adobe eseguirà la migrazione da JWT a OAuth per le integrazioni in uscita, ad esempio l’integrazione Campaign-Analytics o l’integrazione dei trigger di Experience Cloud.

  Se hai implementato integrazioni in entrata con Campaign e utilizzi l’[API Campaign](../../api/using/get-started-apis.md), devi eseguire la migrazione dell’account tecnico come descritto in [questa documentazione](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Le credenziali dell’account di servizio (JWT) esistenti cesseranno di funzionare il **27 gennaio 2025**.


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

