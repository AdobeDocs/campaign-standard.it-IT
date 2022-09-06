---
title: Ultima versione
description: Questa pagina presenta dettagli sul contenuto dell’ultima versione Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 93f1a6cb0727859f3c3f645366a9d2dc25795a79
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 20%

---


# Ultima versione{#latest-release}

![Pannello di controllo Campaign](assets/do-not-localize/cp-icon.png) **Nuova versione del Pannello di controllo Campaign**. [Ulteriori informazioni](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=it){target=&quot;_blank&quot;}.


## Versione 22.3 - Autunno/Inverno 2022 {#sept-22}

### Miglioramenti{#rn-improvements}

**Accessibilità**

Campaign Standard 2.2.3 include correzioni e miglioramenti a livello di accessibilità che consentono agli utenti di navigare e ottenere il massimo da Adobe Campaign.

Queste funzionalità vengono rilasciate solo in disponibilità limitata e distribuite solo a un set di clienti. Per abilitare questi miglioramenti negli ambienti Campaign, contatta il tuo rappresentante di Adobe.

<!--
* **Data retention**

    Data retention periods have been reduced to avoid overloading Campaign server. However, you can still modify these values and define a custom period of time based on your needs and data retention policies. To change retention periods, contact Adobe.
-->

### Aggiornamento della sicurezza{#rn-security}

Questa versione include il seguente aggiornamento della sicurezza: Apache Tomcat è stato aggiornato da v7.0 a v8.0.

### Correzioni{#e-rn-fixes}

* È stato risolto un problema relativo ai rapporti pianificati, che venivano attivati un’ora prima del tempo pianificato. (CAMP-51502)
* È stato risolto un problema sugli indicatori di consegna nel dashboard Consegna che non corrispondevano ai registri di invio (nms:wideLogRcp). (CAMP-51127)
* È stato risolto un problema che impediva l’estensione delle risorse personalizzate con il connettore ACS (Prime Offering). (CAMP-51033)
* È stato migliorato il processo di pubblicazione delle risposte alle richieste di accesso a dati personali per evitare ritardi. (CAMP-50613)

