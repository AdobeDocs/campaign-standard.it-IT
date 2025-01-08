---
title: Note sulla versione 2024
description: In questa pagina sono elencate tutte le versioni del 2024 di Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 26616ecc-a009-485c-b13d-d4e0c23969f2
source-git-commit: 85f3a3d8fe9e41eaa78fac955bc2d0f3f3d2c35e
workflow-type: tm+mt
source-wordcount: '490'
ht-degree: 100%

---

# Note sulla versione 2024 {#release-notes-2024}


## Versione 24.2 - Versione estate 2024 (LA) {#summer-24}

### Miglioramento {#summer-24-rn-improvements}

**Migrazione alle credenziali OAuth server-to-server**

A partire da questa versione, poiché le credenziali dell’account di servizio (JWT) sono state dichiarate obsolete da Adobe, le integrazioni in uscita di Campaign con le soluzioni e le app Adobe ora si basano sulle credenziali OAuth server-to-server. Adobe eseguirà la migrazione da JWT a OAuth per le integrazioni in uscita, ad esempio l’integrazione Campaign-Analytics o l’integrazione dei trigger di Experience Cloud.

Se hai implementato integrazioni in entrata con Campaign e utilizzi l’[API Campaign](../../api/using/get-started-apis.md), devi eseguire la migrazione dell’account tecnico come descritto in [questa documentazione](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Le credenziali dell’account di servizio (JWT) esistenti cesseranno di funzionare il **27 gennaio 2025**.

### Correzioni {#summer-24-rn-fixes}

* È stato risolto un problema che causava l’avvio del modulo di pianificazione del flusso di lavoro prima dell’ora pianificata. (CAMP-55412)
* È stato risolto un problema che causava un errore durante la duplicazione di campi personalizzati nelle notifiche push transazionali. (CAMP-54459)
* Sono stati risolti i problemi che influivano sull’usabilità del modulo di pianificazione di data e ora per la messaggistica in-app. (CAMP-54495)
* È stato risolto un problema che impediva il funzionamento del tracciamento quando si utilizzava la funzione di alias di tracciamento personalizzato e l’intero collegamento era dinamico. (CAMP-56044)
* È stato risolto un problema che causava la visualizzazione di un numero limitato di modelli quando si utilizzava la ricerca per trovare modelli specifici. (CAMP-55273)
* Sono state aggiunte le seguenti lingue all’elenco a discesa delle lingue preferite: en_kz (Inglese - Kazakistan) e en_ua (Inglese - Ucraina). (CAMP-55336)
* È stato risolto un problema che impediva il funzionamento dei pulsanti di regolazione dell’ora nelle impostazioni del modulo di pianificazione. (CAMP-53602)
* Sono stati risolti diversi problemi relativi all’interfaccia utente riguardanti la barra di regolazione dell’ora nelle impostazioni del modulo di pianificazione. (CAMP-55291)


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
