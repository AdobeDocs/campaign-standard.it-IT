---
title: Note sulla versione 2024
description: In questa pagina sono elencate tutte le versioni del 2024 di Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 26616ecc-a009-485c-b13d-d4e0c23969f2
TQID: https://experienceleague.adobe.com/L1RnV5WNdVWVn8oRUtFp4BDW-GzuP6xWZXpFYgupbQs
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: b12f6872-9271-4369-85e5-86969a0b99a2id: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2: id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0id: cbcf4d90-26be-46e2-b16a-aebc529dc41e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 516
ht-degree: 93%

---

# Note sulla versione 2024 {#release-notes-2024}


## Versione 24.2 - Versione estate 2024 (LA) {#summer-24}

### Miglioramento {#summer-24-rn-improvements}

**Migrazione alle credenziali OAuth server-to-server**

A partire da questa versione, poiché le credenziali dell’account di servizio (JWT) sono state dichiarate obsolete da Adobe, le integrazioni in uscita di Campaign con le soluzioni e le app Adobe ora si basano sulle credenziali OAuth server-to-server. Adobe eseguirà la migrazione da JWT a OAuth per le integrazioni in uscita, ad esempio l’integrazione Campaign-Analytics o l’integrazione dei trigger di Experience Cloud.

Se hai implementato integrazioni in entrata con Campaign e utilizzi [API Campaign](../../api/using/get-started-apis.md), devi migrare l&#39;account tecnico come descritto in [questa documentazione](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/){target="_blank"}. Le credenziali dell’account di servizio (JWT) esistenti cesseranno di funzionare il **27 gennaio 2025**.

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
* È stato risolto un problema che interrompeva il flusso di lavoro Avvisi sulla consegna con il seguente errore: `division by zero`. (CAMP-49786)
