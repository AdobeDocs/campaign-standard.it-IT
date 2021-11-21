---
title: Passaggi fondamentali per l’invio di un messaggio
description: Segui questi passaggi per creare e inviare messaggi con Adobe Campaign.
audience: channels
content-type: reference
topic-tags: about-communication-channels
feature: Overview
role: User
level: Beginner
exl-id: a903d7e2-7654-46b3-bc61-4653a065faad
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 14%

---

# Passaggi fondamentali per l’invio di un messaggio{#key-steps-to-send-a-message}

In questa sezione imparerai a creare e inviare messaggi personalizzati a un pubblico di destinazione utilizzando Adobe Campaign Standard.

Informazioni specifiche su come creare e configurare ogni canale di comunicazione sono disponibili nelle sezioni seguenti:

* [Creazione di un messaggio e-mail](../../channels/using/creating-an-email.md)
* [Creazione di un SMS](../../channels/using/creating-an-sms-message.md)
* [Creazione di una consegna di direct mail](../../channels/using/creating-the-direct-mail.md)
* [Creazione di una notifica push](../../channels/using/preparing-and-sending-a-push-notification.md).
* [Preparazione e invio di un messaggio in-app](../../channels/using/preparing-and-sending-an-in-app-message.md)

Per scoprire le best practice per la consegna, consulta la [Best practice per le consegne](../../sending/using/delivery-best-practices.md) sezione .

## Creare il messaggio

Campaign Standard [attività di marketing](../../start/using/marketing-activities.md) per creare e-mail, SMS, direct mailing, notifiche push o messaggi in-app.

![](assets/marketing-activities.png)

I messaggi possono essere creati dall’elenco delle attività di marketing o da un flusso di lavoro tramite [attività dedicate](../../automating/using/about-channel-activities.md).

![](assets/steps-channel.png)

## Definire il pubblico

Definisci i destinatari del messaggio. Per eseguire questa operazione, utilizza la variabile [editor di query](../../automating/using/editing-queries.md) dal riquadro a sinistra per filtrare i dati contenuti nel database e creare regole per eseguire il targeting del pubblico.

Sono disponibili diversi tipi di pubblico:

* **[!UICONTROL Target]** è il target principale della tua e-mail,
* **[!UICONTROL Test profiles]** sono i profili utilizzati per testare e convalidare l’e-mail (consulta [Gestione dei profili di test](../../audiences/using/managing-test-profiles.md)).

![](assets/steps-audience.png)

## Progettare e personalizzare i contenuti

In **[!UICONTROL Content]** blocca, progetta e personalizza il contenuto del messaggio utilizzando i campi del database. Per ulteriori informazioni su come progettare contenuti per un canale specifico, consulta le sezioni elencate nella parte superiore della pagina.

![](assets/steps-content.png)

## Preparare e testare

[Preparare](../../sending/using/preparing-the-send.md) il messaggio. Questo processo calcola la popolazione target e prepara il messaggio personalizzato.

![](assets/steps-prepare.png)

**Controlla e verifica il messaggio** prima di inviarlo utilizzando le funzionalità di Campaign Standard: anteprima, rendering di e-mail, correzione, ecc. Per ulteriori informazioni al riguardo, consulta [questa sezione](../../sending/using/previewing-messages.md).

Utilizza la **[!UICONTROL Schedule]** blocca per definire quando i messaggi verranno inviati (vedi [Pianificazione dei messaggi](../../sending/using/about-scheduling-messages.md)).

![](assets/steps-schedule.png)

## Invio e tracciamento

Quando il messaggio è pronto, puoi confermare l’invio. La **[!UICONTROL Deployment]** block visualizza l’avanzamento dell’invio e il risultato.

![](assets/steps-send.png)

Sono disponibili diversi registri per monitorare la consegna dei messaggi (consulta [monitoraggio di una consegna](../../sending/using/monitoring-a-delivery.md)). Puoi anche tenere traccia del comportamento dei destinatari della consegna grazie a Campaign Standard [funzionalità di tracciamento](../../sending/using/tracking-messages.md).

![](../../sending/using/assets/tracking_logs.png)

Misura l’efficacia dei messaggi e l’evoluzione degli invii e delle campagne attraverso vari indicatori e grafici (vedi [Accesso ai rapporti](../../reporting/using/about-dynamic-reports.md)).

![](assets/steps-reports.png)
