---
title: Prossime modifiche del canale di notifica push
description: Prossime modifiche del canale di notifica push
audience: channels
feature: Push
role: Admin
level: Experienced
exl-id: e273b443-7c43-482b-8f86-60ada4b57cbf
source-git-commit: ac4a52263482557a6d5c370af6df5d54a42671b4
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 5%

---

# Prossime modifiche del canale di notifica push {#push-upgrade}

Puoi utilizzare Campaign per inviare notifiche push su dispositivi Android e iOS. Per eseguire questa operazione, Campaign si basa su servizi di abbonamento specifici. Alcune modifiche importanti al servizio Android Firebase Cloud Messaging (FCM) saranno rilasciate a partire dalla versione invernale 2024.1 e avranno un impatto sulla tua implementazione di Adobe Campaign. Inoltre, per le app iOS, Adobe sta modificando il modo in cui gli amministratori possono configurare i certificati.

## Cosa è cambiato? {#push-changes}

### Android {#push-android}

Come parte del continuo sforzo di Google per migliorare i suoi servizi, le API FCM legacy saranno interrotte il **20 giugno 2024**. Ulteriori informazioni sul protocollo HTTP Firebase Cloud Messaging in [Documentazione di Google Firebase](https://firebase.google.com/docs/cloud-messaging/http-server-ref){target="_blank"}.

Attualmente Adobe Campaign Standard utilizza API HTTP legacy per inviare messaggi di notifica push Android e apporterà modifiche nei prossimi mesi per effettuare l’aggiornamento alle API HTTP v1.

### iOS {#push-ios}

Adobe sarà anche l’aggiornamento di Adobe Campaign Standard per il canale di notifica push di iOS e la modifica del modo in cui consentiamo agli amministratori di configurare i certificati per le loro applicazioni iOS. A partire dalla versione invernale del 24.2 2024, gli amministratori devono caricare i certificati iOS tramite l’interfaccia utente di Adobe Campaign Standard, nelle proprietà dell’app mobile.

## Sei interessato? {#push-impact}

In qualità di utente Campaign Standard, sei interessato dai messaggi di notifica push inviati ai tuoi tipi di pubblico.

## Come effettuare la migrazione? {#push-migration}

Questi aggiornamenti richiedono un aggiornamento della build Campaign Standard alla versione invernale 24.1 2024, in quanto influiscono sulla configurazione del canale mobile e sulla gestione delle autorizzazioni.

Presto saranno fornite istruzioni dettagliate per facilitare un processo di transizione senza intoppi.

Il nostro team di assistenza clienti sarà a tua disposizione per assisterti durante questa transizione. Possiamo anche ospitare webinar e sessioni di abilitazione per coprire gli aspetti tecnici e le best practice per la transizione.

Nel frattempo, ti consigliamo di rivedere la configurazione e la personalizzazione correnti in Adobe Campaign Standard in modo da essere pronti a apportare eventuali modifiche, se necessario.

In caso di dubbi o domande immediate, non esitare a contattare il nostro team di supporto.
