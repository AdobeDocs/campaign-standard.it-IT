---
title: Modifica dei profili
description: Scopri come modificare i profili esistenti e accedere alle informazioni di contatto, ai canali preferiti, ai registri di tracciamento, agli abbonamenti, ecc.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: User
level: Intermediate
exl-id: d0c7dc09-6f2b-4336-b545-7afe3a704164
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 7%

---

# Modifica dei profili{#editing-profiles}

## Accesso alle proprietà del profilo {#accessing-profile-properties}

Per modificare un profilo esistente e consultare i dati ad esso associati o modificarlo, effettuare le seguenti operazioni:

1. Dalla pagina Home di Adobe Campaign, fai clic su **[!UICONTROL Customer profiles]** scheda o **[!UICONTROL Profiles]** scheda.
1. Seleziona un contatto.
1. Fai clic su **[!UICONTROL Edit profile properties]** per accedere alle informazioni dettagliate del profilo.

   ![](assets/profile_creation2.png)

   La finestra delle proprietà del profilo offre diverse schede che consentono di accedere a tutte le informazioni sul profilo.

   A seconda delle risorse personalizzate create o estese in Adobe Campaign, possono essere visualizzate anche altre schede. Per ulteriori informazioni sulle risorse personalizzate, consulta [Informazioni sulle risorse personalizzate](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >È possibile modificare le informazioni solo nel **[!UICONTROL General]** scheda - ad eccezione della **[!UICONTROL Traceability]** sezione.

L’edizione dei profili è possibile anche utilizzando l’API di Adobe Campaign Standard. Per ulteriori informazioni, consulta la [documentazione dedicata](../../api/using/updating-profiles.md).

Argomento correlato:

* [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md)
* [Invio al fuso orario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Dati generali del profilo {#general-profile-data}

Il **[!UICONTROL General]** La scheda raggruppa le seguenti informazioni sul profilo:

* Informazioni di contatto, che contengono nome, cognome, data di nascita, foto, lingua preferita del destinatario (per [e-mail multilingue](../../channels/using/creating-a-multilingual-email.md)), ecc.
* Canali su cui è possibile contattare il profilo, che contengono l’indirizzo e-mail del destinatario, il numero di telefono cellulare e informazioni sulla rinuncia.
* Indirizzo postale (per [direct mail](../../channels/using/about-direct-mail.md)) e il fuso orario del contatto (a [pianificare i messaggi nel relativo fuso orario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Autorizzazione di accesso, che indica l&#39;unità organizzativa del destinatario (a [gestire le autorizzazioni](../../administration/using/about-access-management.md)). Consulta anche [Profili di partizione](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Registri di invio e tracciamento {#sending-and-tracking-logs}

Il **[!UICONTROL Sending logs]** e **[!UICONTROL Tracking logs]** Le schede raggruppano l’elenco delle consegne inviate al profilo e tutti i relativi dati di tracciamento.

Per ulteriori informazioni sull’invio e il tracciamento dei registri, consulta [registri di consegna](../../sending/using/monitoring-a-delivery.md#delivery-logs) e [tracciamento dei messaggi](../../sending/using/tracking-messages.md) sezioni.

## Abbonamenti {#subscriptions}

Gli abbonamenti del contatto sono elencati nella scheda corrispondente. Per ulteriori informazioni sull’abbonamento a un servizio, consulta [questa sezione](../../audiences/using/about-subscriptions.md).

Il **[!UICONTROL Mobile App Subscriptions]** fai riferimento alle notifiche push. Per ulteriori informazioni, consulta [Notifica push](../../channels/using/about-push-notifications.md) canale.
