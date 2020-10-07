---
title: Modifica dei profili
description: Scopri come modificare i profili esistenti e accedere alle informazioni di contatto, ai canali preferiti, ai registri di tracciamento, alle iscrizioni ecc.
page-status-flag: never-activated
uuid: 6fcdb719-6149-48fc-b400-64c24a51487f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 8d3ba7bf-90ae-4c6d-aaeb-a48572a69f2f
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 11%

---


# Modifica dei profili{#editing-profiles}

## Accesso alle proprietà del profilo {#accessing-profile-properties}

Per modificare un profilo esistente e consultare i dati ad esso associati o modificarlo, procedere come segue:

1. Dalla pagina Home di Adobe Campaign, fai clic sulla scheda **[!UICONTROL Customer profiles]** o sulla scheda **[!UICONTROL Profiles]**.
1. Seleziona un contatto.
1. Fate clic sull&#39; **[!UICONTROL Edit profile properties]** icona per accedere alle informazioni dettagliate del profilo.

   ![](assets/profile_creation2.png)

   La finestra delle proprietà del profilo offre diverse schede che consentono di accedere a tutte le informazioni del profilo.

   Possono essere visualizzate anche altre schede, a seconda delle risorse personalizzate create o estese in  Adobe Campaign. Per ulteriori informazioni sulle risorse personalizzate, consultate [Informazioni sulle risorse](../../developing/using/data-model-concepts.md)personalizzate.

   >[!NOTE]
   >
   >È possibile modificare solo le informazioni nella **[!UICONTROL General]** scheda, fatta eccezione per la **[!UICONTROL Traceability]** sezione.

L&#39;edizione Profili è anche possibile tramite l&#39;API Adobe Campaign Standard . Per ulteriori informazioni, consulta la [documentazione dedicata](../../api/using/updating-profiles.md).

Argomento correlato:

* [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md)
* [Invio al fuso orario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Dati generali del profilo {#general-profile-data}

La **[!UICONTROL General]** scheda raggruppa le seguenti informazioni sul profilo:

* Informazioni di contatto, che contengono il nome, il cognome, la data di nascita, la foto, la lingua preferita del destinatario (per le e-mail [](../../channels/using/creating-a-multilingual-email.md)multilingue), ecc.
* Canali su cui è possibile contattare il profilo, che contiene l&#39;indirizzo e-mail del destinatario, il numero di telefono cellulare, le informazioni di rifiuto.
* Indirizzo postale (per posta [](../../channels/using/about-direct-mail.md)diretta) e fuso orario del contatto (per [pianificare i messaggi nel relativo fuso](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)orario).
* Autorizzazione di accesso, che indica l&#39;unità organizzativa del destinatario (per [gestire le autorizzazioni](../../administration/using/about-access-management.md)). Consulta anche [Profili di partizione](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Sending and tracking logs {#sending-and-tracking-logs}

Le **[!UICONTROL Sending logs]** e **[!UICONTROL Tracking logs]** le schede raggruppano l&#39;elenco delle consegne che sono state inviate al profilo e tutti i dati di tracciamento correlati.

Per ulteriori informazioni sull’invio e il tracciamento dei registri, consulta le sezioni dei registri [di](../../sending/using/monitoring-a-delivery.md#delivery-logs) consegna e dei messaggi [di](../../sending/using/tracking-messages.md) tracciamento.

## Iscrizioni {#subscriptions}

Le iscrizioni del contatto sono elencate nella scheda corrispondente. Per ulteriori informazioni sull’iscrizione a un servizio, consulta [questa sezione](../../audiences/using/about-subscriptions.md).

La **[!UICONTROL Mobile App Subscriptions]** scheda si riferisce alle notifiche push. Per ulteriori informazioni, consultate il canale di notifica [](../../channels/using/about-push-notifications.md) push.
