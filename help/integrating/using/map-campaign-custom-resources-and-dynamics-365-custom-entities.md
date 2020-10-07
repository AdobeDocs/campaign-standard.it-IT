---
title: Mappatura delle risorse personalizzate di Campaign ed entità personalizzate di Dynamics 365
description: Scoprite come mappare risorse ed entità nel contesto dell'integrazione tra  Adobe Campaign Standard e Microsoft Dynamics 365.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 9%

---


# Mappa risorse campagna ed entità Dynamics 365

Scoprite come mappare risorse personalizzate ed entità personalizzate nel contesto dell&#39;integrazione tra  Adobe Campaign Standard e Microsoft Dynamics 365.

>[!CAUTION]
>
>Questa funzionalità non è disponibile come funzione predefinita del prodotto. La sua implementazione richiede l’intervento della Consulenza Adobe. Per maggiori informazioni, contatta un rappresentante Adobe di fiducia.

## Prerequisiti

L&#39;integrazione [di](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) Microsoft Dynamics 365- Adobe Campaign Standard supporta entità personalizzate, consentendo la sincronizzazione delle entità personalizzate in Dynamics 365 con le risorse personalizzate corrispondenti in Campaign.

I nuovi dati contenuti nelle risorse personalizzate possono essere utilizzati per diversi scopi, tra cui segmentazione e personalizzazione.

L&#39;integrazione supporta tabelle collegate e non collegate. Il collegamento è supportato fino a tre livelli (livello1->livello2->livello3).

>[!CAUTION]
>
>Se un qualsiasi record di risorse personalizzato della campagna contiene informazioni personali, si applicano raccomandazioni specifiche. Ulteriori informazioni [in questa sezione](../../integrating/using/notices-and-recommendations-for-acs-and-ms-dynamics.md#privacy-linked-resources).

## Avvisi

Quando si configurano flussi di dati di entità personalizzati, è importante tenere presente quanto segue:

* La creazione e la modifica di risorse personalizzate per Campaign sono operazioni sensibili che devono essere eseguite solo da utenti esperti.
* Per i flussi di dati di entità personalizzati, il tracciamento delle modifiche deve essere abilitato in Dynamics 365 per le entità personalizzate sincronizzate.
* Se in Dynamics 365 viene creato un record padre e un record figlio collegato vicino alla stessa ora, a causa dell&#39;elaborazione parallela dell&#39;integrazione, è possibile che un nuovo record figlio venga scritto in Campaign prima del record padre.

* Se il padre e il figlio sono collegati sul lato della campagna utilizzando l&#39;opzione di collegamento **semplice cardinalità** 1, il record figlio rimarrà nascosto e inaccessibile (tramite interfaccia utente o API) fino all&#39;arrivo del record padre in Campaign.

* (Presupponendo **1 collegamento** semplice cardinalità in Campaign) Se il record figlio viene aggiornato o eliminato in Dynamics 365 e tale modifica viene scritta in Campaign prima che il record padre venga visualizzato in Campaign (non probabile, ma una possibilità remota), tale aggiornamento o eliminazione non verrà elaborato in Campaign e verrà generato un errore. In caso di aggiornamento, il record in questione dovrà essere aggiornato di nuovo in Dynamics 365 per sincronizzare il record aggiornato. In caso di eliminazione, il record in questione dovrà essere gestito separatamente sul lato Campaign, poiché non esiste più un record in Dynamics 365 da eliminare o aggiornare.

* Se ti imbatti in una situazione in cui credi di avere dei record figlio nascosti e non hai modo di accedervi, puoi cambiare temporaneamente il tipo di collegamento cardinalità a **0 o 1 semplice collegamento** cardinale per accedere a tali record.

Una panoramica più completa delle risorse personalizzate per Campaign è disponibile [in questa sezione](../../developing/using/key-steps-to-add-a-resource.md).
