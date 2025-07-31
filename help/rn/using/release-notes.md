---
title: Note sulla versione più recente
description: Questa pagina presenta dettagli sul contenuto dell’ultima versione Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c1f64589578c144a9b8eb879684f27834efaf8d8
workflow-type: ht
source-wordcount: '290'
ht-degree: 100%

---


# Note sulla versione più recente {#latest-release}

<!--
## Release notes {#e-new-release}


This section lists improvements and changes included in the next Campaign Standard release.

>[!CAUTION]
>
>This content is subject to changes without prior notice until the stage environments upgrade date. Learn more in the [Release planning page](../../rn/using/release-planning.md).

-->

## Versione 25.2 - Estate 2025 {#summer-25}

### Correzioni di sicurezza {#summer-25-security}

* In questa versione sono state apportate correzioni di sicurezza.
* Questa versione include il seguente aggiornamento della sicurezza: PostgreSQL 14.18, la migrazione da CentOS a Rocky per le istanze di Azure.

### Altre correzioni {#summer-25-fixes}

* Gestione migliorata dell’esaurimento della sequenza per ottimizzare l’affidabilità del sistema. (CAMP-57281)
* Aggiornamenti generali di stabilizzazione del prodotto. (CAMP-57339)
* Reporting dinamico migliorato per una maggiore solidità e una minore mancata corrispondenza dei dati. (CAMP-58157)
* È stato risolto un problema che impediva il corretto ritorno a capo del testo nei menu a discesa. (CAMP-57360)
* È stata aggiornata la funzionalità di reporting per impedire agli utenti di eseguire query sui dati di oltre 2 anni. (CAMP-59262)

## Versione 25.1.2 {#25.1.2}

### Correzioni di sicurezza {#25.1.2-security}

* In questa versione sono state apportate correzioni di sicurezza.
* Questa versione include il seguente aggiornamento di sicurezza: Apache Tomcat è stato aggiornato a v10.1.36.

### Altre correzioni {#25.1.2-fixes}

* È stato risolto un problema di analisi del token che poteva impedire agli utenti di accedere tramite IMS. (CAMP-57337)
* Il meccanismo di sequenza dell’ID generata automaticamente è stato migliorato per migliorare l’affidabilità del sistema. (CAMP-57281)

## Versione 25.1 - Inverno 2025 {#winter-25}

### Correzioni di sicurezza {#winter-25-security}

* In questa versione sono state apportate correzioni di sicurezza.
* Questa versione include il seguente aggiornamento della sicurezza: Apache Tomcat è stato aggiornato a v10.1.33.

### Altre correzioni {#winter-25-fixes}


* È stato corretto l’URL “Schema dati” nella schermata di riepilogo dell’abbonamento (CAMP-56168, CAMP-56296)
* È stato risolto un problema per ignorare le regole di affaticamento quando viene utilizzata l’opzione **Messaggio da inviare immediatamente** (CAMP-56866, CAMP-57033)
* È stato risolto un problema di duplicazione nei modelli (CAMP-56340)
* È stata corretta una regressione di tracciamento quando gli URL dinamici venivano utilizzati nei modelli di Adobe Experience Manager (CAMP-51932)
* È stato risolto un problema di prestazioni sul processo di fatturazione (CAMP-56796)
* È stato risolto un problema di codifica HTML con il carattere `>` nelle pagine web JSSP (CAMP-56497)
* È stato risolto un problema in Dynamic Reporting che si verificava con l’utilizzo dell’opzione **Visualizza nelle righe selezionate** (CAMP-55895)

