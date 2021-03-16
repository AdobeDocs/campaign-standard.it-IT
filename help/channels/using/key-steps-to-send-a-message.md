---
solution: Campaign Standard
product: campaign
title: Passaggi fondamentali per l’invio di un messaggio
description: Segui questi passaggi per creare e inviare messaggi con Adobe Campaign.
audience: channels
content-type: reference
topic-tags: about-communication-channels
feature: Panoramica
role: Professionista
level: Principiante
translation-type: tm+mt
source-git-commit: a7a1aa2841410674597264927325c073fef4ce26
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 12%

---


# Passaggi fondamentali per l’invio di un messaggio{#key-steps-to-send-a-message}

In questa sezione imparerai a creare e inviare messaggi personalizzati a un pubblico di destinazione utilizzando Adobe Campaign Standard.

Informazioni specifiche su come creare e configurare ogni canale di comunicazione sono disponibili nelle sezioni seguenti:

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Creazione di un SMS](../../channels/using/creating-an-sms-message.md)
* [Creazione di una consegna di direct mail](../../channels/using/creating-the-direct-mail.md)
* [Creazione di una notifica push](../../channels/using/preparing-and-sending-a-push-notification.md).
* [Preparazione e invio di un messaggio in-app](../../channels/using/preparing-and-sending-an-in-app-message.md)

Per scoprire le best practice per la consegna, consulta la sezione [Best practice per la consegna](../../sending/using/delivery-best-practices.md) .

## Creare il messaggio

Utilizza le attività di marketing di Campaign Standard [per creare un messaggio e-mail, SMS, direct mailing, notifica push o in-app.](../../start/using/marketing-activities.md)

![](assets/marketing-activities.png)

I messaggi possono essere creati dall&#39;elenco delle attività di marketing o da un flusso di lavoro utilizzando [attività dedicate](../../automating/using/about-channel-activities.md).

![](assets/steps-channel.png)

## Definire il pubblico

Definisci i destinatari del messaggio. A questo scopo, utilizza l&#39; [editor di query](../../automating/using/editing-queries.md) dal riquadro a sinistra per filtrare i dati contenuti nel database e creare regole per indirizzare il pubblico.

Sono disponibili diversi tipi di pubblico:

* **[!UICONTROL Target]** è il target principale della tua e-mail,
* **[!UICONTROL Test profiles]** sono i profili utilizzati per testare e convalidare l’e-mail (consulta  [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md)).

![](assets/steps-audience.png)

## Progettazione e personalizzazione dei contenuti

Nel blocco **[!UICONTROL Content]** , progetta e personalizza il contenuto del messaggio utilizzando i campi del database. Per ulteriori informazioni su come progettare contenuti per un canale specifico, consulta le sezioni elencate nella parte superiore della pagina.

![](assets/steps-content.png)

## Preparare e testare

[](../../sending/using/preparing-the-send.md) Prepara il messaggio. Questo processo calcola la popolazione target e prepara il messaggio personalizzato.

![](assets/steps-prepare.png)

**Controlla e verifica il** messaggio prima di inviarlo utilizzando le funzionalità di Campaign Standard: anteprima, rendering di e-mail, correzione, ecc. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../sending/using/previewing-messages.md).

Usa il blocco **[!UICONTROL Schedule]** per definire quando verranno inviati i messaggi (consulta [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md)).

![](assets/steps-schedule.png)

## Invio e tracciamento

Quando il messaggio è pronto, puoi confermare l’invio. Il blocco **[!UICONTROL Deployment]** visualizza l’avanzamento dell’invio e il risultato.

![](assets/steps-send.png)

Sono disponibili diversi registri per aiutarti a monitorare la consegna dei messaggi (consulta [monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)). Puoi anche tenere traccia del comportamento dei destinatari della consegna grazie alle [funzionalità di tracciamento Campaign Standard](../../sending/using/tracking-messages.md).

![](../../sending/using/assets/tracking_logs.png)

Misura l’efficacia dei messaggi e l’evoluzione degli invii e delle campagne attraverso vari indicatori e grafici (consulta [Accesso ai rapporti](../../reporting/using/about-dynamic-reports.md)).

![](assets/steps-reports.png)
