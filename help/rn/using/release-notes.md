---
title: Note sulla versione più recente
description: Questa pagina presenta dettagli sul contenuto dell’ultima versione Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c2d2f3843801d108f007fea52a76e41abe16d76c
workflow-type: ht
source-wordcount: '390'
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

### Versione 25.1 - Inverno 2025 {#winter-25}

#### Correzioni di sicurezza {#winter-25-security}

* In questa versione sono state apportate correzioni di sicurezza.
* Questa versione include il seguente aggiornamento della sicurezza: Apache Tomcat è stato aggiornato a v10.1.33.

#### Altre correzioni {#winter-25-fixes}

* È stato risolto un problema di duplicazione nei modelli (CAMP-56340)
* È stata corretta una regressione di tracciamento quando gli URL dinamici venivano utilizzati nei modelli di Adobe Experience Manager (CAMP-51932)
* È stato risolto un problema di prestazioni sul processo di fatturazione (CAMP-56796)
* È stato risolto un problema di codifica HTML con il carattere `>` nelle pagine web JSSP (CAMP-56497)
* È stato risolto un problema in Dynamic Reporting che si verificava con l’utilizzo dell’opzione **Visualizza nelle righe selezionate** (CAMP-55895)


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
