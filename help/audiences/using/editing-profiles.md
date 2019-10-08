---
title: Modifica dei profili
seo-title: Modifica dei profili
description: Modifica dei profili
seo-description: Scopri come modificare i profili esistenti e accedere alle informazioni di contatto, ai canali preferiti, ai registri di tracciamento, alle iscrizioni ecc.
page-status-flag: mai attivato
uuid: 6fcdb719-6149-48fc-b400-64c24a51487f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profile
discoiquuid: 8d3ba7bf-90ae-4c6d-aaeb-a48572a69f2f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 94c7649448aff859daaf2bbe9a4d17a5187ac71f

---


# Modifica dei profili{#editing-profiles}

## Accesso alle proprietà del profilo {#accessing-profile-properties}

Per modificare un profilo esistente e consultare i dati ad esso associati o modificarlo, procedere come segue:

1. Dalla home page di Adobe Campaign, fai clic sulla **[!UICONTROL Customer profiles]** scheda o sulla **[!UICONTROL Profiles]** scheda.
1. Selezionare un contatto.
1. Fate clic sull' **[!UICONTROL Edit profile properties]** icona per accedere alle informazioni dettagliate del profilo.

   ![](assets/profile_creation2.png)

   La finestra delle proprietà del profilo offre diverse schede che consentono di accedere a tutte le informazioni del profilo.

   Altre schede possono anche essere visualizzate a seconda delle risorse personalizzate create o estese in Adobe Campaign. Per ulteriori informazioni sulle risorse personalizzate, consultate [Informazioni sulle risorse](../../developing/using/data-model-concepts.md)personalizzate.

   >[!NOTE]
   >
   >È possibile modificare solo le informazioni nella **[!UICONTROL General]** scheda, fatta eccezione per la **[!UICONTROL Traceability]** sezione.

L'edizione Profili è anche possibile tramite l'API Adobe Campaign Standard. Per ulteriori informazioni, consulta la documentazione [](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#updating-profiles) dedicata.

Argomento correlato:

* [Profilo cliente integrato](../../audiences/using/integrated-customer-profile.md)
* [Invio al fuso orario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Dati generali del profilo {#general-profile-data}

La **[!UICONTROL General]** scheda raggruppa le seguenti informazioni sul profilo:

* Informazioni di contatto, che contengono il nome, il cognome, la data di nascita, la foto, la lingua preferita del destinatario (per le e-mail [](../../channels/using/creating-a-multilingual-email.md)multilingue), ecc.
* Canali su cui è possibile contattare il profilo, che contiene l'indirizzo e-mail del destinatario, il numero di telefono cellulare, le informazioni di rifiuto.
* Indirizzo postale (per posta [](../../channels/using/about-direct-mail.md)diretta) e fuso orario del contatto (per [pianificare i messaggi nel relativo fuso](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)orario).
* Autorizzazione di accesso, che indica l'unità organizzativa del destinatario (per [gestire le autorizzazioni](../../administration/using/about-access-management.md)). Consultate anche [Profili](../../administration/using/organizational-units.md#partitioning-profiles)di partizionamento.

![](assets/profile_creation4.png)

## Invio e tracciamento dei registri {#sending-and-tracking-logs}

Le **[!UICONTROL Sending logs]** e **[!UICONTROL Tracking logs]** le schede raggruppano l'elenco delle consegne che sono state inviate al profilo e tutti i dati di tracciamento correlati.

Per ulteriori informazioni sull’invio e il tracciamento dei registri, consulta le sezioni dei registri [di](../../sending/using/monitoring-a-delivery.md#delivery-logs) consegna e dei messaggi [di](../../sending/using/tracking-messages.md) tracciamento.

## Iscrizioni {#subscriptions}

Le iscrizioni del contatto sono elencate nella scheda corrispondente. Per ulteriori informazioni sull’iscrizione a un servizio, consulta [questa sezione](../../audiences/using/about-subscriptions.md).

La **[!UICONTROL Mobile App Subscriptions]** scheda si riferisce alle notifiche push. Per ulteriori informazioni, consultate il canale di notifica [](../../channels/using/about-push-notifications.md) push.
