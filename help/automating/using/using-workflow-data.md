---
title: Utilizzo dei dati del flusso di lavoro
description: Scopri le diverse possibilità di utilizzare i dati importati o di destinazione.
page-status-flag: mai attivato
uuid: 3dd66aeb-3a26-4214-b6a0-242c2b7fbc49
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizzazione
content-type: reference
topic-tags: workflow generale
discoiquuid: 90b250f1-f32d-4256-83ea-4c0627628610
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Utilizzo dei dati del flusso di lavoro{#using-workflow-data}

Una volta identificati e preparati, i dati possono essere utilizzati nei seguenti contesti:

* L' **[!UICONTROL Update data]** attività consente di eseguire un aggiornamento di massa sui campi del database.
* L' **[!UICONTROL Save audience]** attività consente di aggiornare un'audience esistente o di creare una nuova audience dalla popolazione calcolata a monte in un flusso di lavoro. Le audience create o aggiornate da questa attività sono audience **List** o **File** . Questa attività consente anche di esportare i profili come audience/segmenti di Adobe Experience Cloud.
* L' **[!UICONTROL Subscription Services]** attività consente di prendere profili in massa e iscriverli a un servizio o annullarne l'iscrizione a un servizio.
* L' **[!UICONTROL Extract file]** attività consente di esportare dati da Adobe Campaign sotto forma di file esterno.

Dopo aver definito una destinazione di profilo, puoi utilizzare diverse attività per creare e inviare consegne:

* L' **[!UICONTROL Email delivery]** attività consente di configurare l'invio di un'e-mail in un flusso di lavoro. Può trattarsi di un'e-mail di invio **** singolo e inviata una sola volta, oppure di un'e-mail **ricorrente** .
* L' **[!UICONTROL SMS delivery]** attività consente di configurare l'invio di un SMS in un flusso di lavoro. Può trattarsi di un **singolo SMS inviato** e inviato solo una volta, o può essere un SMS **ricorrente** .
* L' **[!UICONTROL Mobile app delivery]** attività consente di configurare l'invio di una notifica push in un flusso di lavoro. Può trattarsi di una **singola notifica di invio** e inviata una sola volta, oppure di una notifica **ricorrente** .

