---
title: Note preliminari sulla versione
description: Note preliminari sulla versione
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 93f1a6cb0727859f3c3f645366a9d2dc25795a79
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 19%

---


# Note preliminari sulla versione {#e-new-release}

Questa pagina descrive miglioramenti e correzioni inclusi nella prossima versione di Campaign Standard.

>[!CAUTION]
>
> Questo contenuto è soggetto a modifiche senza preavviso fino alla data di aggiornamento degli ambienti di stage. Ulteriori informazioni sono disponibili nella [pagina di pianificazione del rilascio](../../rn/using/release-planning.md).

## Versione 22.3 - Autunno/Inverno 2022 {#e-rn-2022}

### Miglioramenti{#e-rn-improvements}

**Accessibilità**

Campaign Standard 2.2.3 include correzioni e miglioramenti a livello di accessibilità che consentono agli utenti di navigare e ottenere il massimo da Adobe Campaign.

Queste funzionalità vengono rilasciate solo in disponibilità limitata e distribuite solo a un set di clienti. Per abilitare questi miglioramenti negli ambienti Campaign, contatta il tuo rappresentante di Adobe.

<!--
* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

### Aggiornamento della sicurezza{#e-rn-security}

Questa versione include il seguente aggiornamento della sicurezza: Apache Tomcat è stato aggiornato da v7.0 a v8.0.

### Correzioni{#e-rn-fixes}

* È stato risolto un problema relativo ai rapporti pianificati, che venivano attivati un’ora prima del tempo pianificato. (CAMP-51502)
* È stato risolto un problema sugli indicatori di consegna nel dashboard Consegna che non corrispondevano ai registri di invio (nms:wideLogRcp). (CAMP-51127)
* È stato risolto un problema che impediva l’estensione delle risorse personalizzate con il connettore ACS (Prime Offering). (CAMP-51033)
* È stato migliorato il processo di pubblicazione delle risposte alle richieste di accesso a dati personali per evitare ritardi. (CAMP-50613)