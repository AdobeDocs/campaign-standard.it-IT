---
title: Note preliminari sulla versione
description: Note preliminari sulla versione
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 20a59e064afeb93a2a6260439b09790692971071
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 26%

---


# Note preliminari sulla versione {#e-new-release}

Questa pagina descrive miglioramenti e correzioni inclusi nella prossima versione di Campaign Standard.

>[!CAUTION]
>
> Questo contenuto è soggetto a modifiche senza preavviso fino alla data di aggiornamento degli ambienti di stage. Ulteriori informazioni sono disponibili nella [pagina di pianificazione del rilascio](../../rn/using/release-planning.md).

## Versione 22.3 - Autunno/Inverno 2022 {#e-rn-2022}

<!--
### Improvement{#e-rn-improvements}


**Accessibility**

Campaign Standard 22.3 comes with accessibility fixes and improvements which facilitate users to navigate and get the most out of Adobe Campaign.

These capabilities are released in Limited Availability and rolled out to a set of customers only. To have these improvements enabled on your Campaign environment(s), contact your Adobe representative.
-->

### Aggiornamento della sicurezza{#e-rn-security}

Questa versione include il seguente aggiornamento della sicurezza: Apache Tomcat è stato aggiornato da v7.0 a v8.0.

### Correzioni{#e-rn-fixes}

* È stato risolto un problema relativo ai rapporti pianificati, che venivano attivati un’ora prima del tempo pianificato. (CAMP-51502)
* È stato risolto un problema sugli indicatori di consegna nel dashboard Consegna che non corrispondevano ai registri di invio (nms:wideLogRcp). (CAMP-51127)
* È stato risolto un problema che impediva l’estensione delle risorse personalizzate con il connettore ACS (Prime Offering). (CAMP-51033)
* È stato migliorato il processo di pubblicazione delle risposte alle richieste di accesso a dati personali per evitare ritardi. (CAMP-50613)