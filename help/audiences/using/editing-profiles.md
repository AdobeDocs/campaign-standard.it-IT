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
ht-degree: 12%

---

# Modifica dei profili{#editing-profiles}

## Accesso alle proprietà del profilo {#accessing-profile-properties}

Per modificare un profilo esistente e consultare i dati ad esso associati o modificarli, effettua le seguenti operazioni:

1. Dalla pagina Home di Adobe Campaign, fai clic sulla scheda **[!UICONTROL Customer profiles]** o sulla scheda **[!UICONTROL Profiles]**.
1. Seleziona un contatto.
1. Fai clic sul pulsante **[!UICONTROL Edit profile properties]** per accedere alle informazioni dettagliate del profilo.

   ![](assets/profile_creation2.png)

   La finestra delle proprietà del profilo offre diverse schede che consentono di accedere a tutte le informazioni sul profilo.

   Possono essere visualizzate anche altre schede a seconda delle risorse personalizzate create o estese in Adobe Campaign. Per ulteriori informazioni sulle risorse personalizzate, consulta [Informazioni sulle risorse personalizzate](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >È possibile modificare solo le informazioni nel **[!UICONTROL General]** scheda - tranne per **[!UICONTROL Traceability]** sezione .

L’edizione dei profili è possibile anche utilizzando l’API di Adobe Campaign Standard. Per ulteriori informazioni, consulta la [documentazione dedicata](../../api/using/updating-profiles.md).

Argomento correlato:

* [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md)
* [Invio al fuso orario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Dati profilo generali {#general-profile-data}

La **[!UICONTROL General]** la scheda raggruppa le seguenti informazioni sul profilo:

* Informazioni di contatto, che contengono il nome, il cognome, la data di nascita, la foto, la lingua preferita del destinatario (per [e-mail multilingue](../../channels/using/creating-a-multilingual-email.md)), ecc.
* Canali su cui è possibile contattare il profilo, che contiene l’indirizzo e-mail del destinatario, il numero di telefono cellulare, le informazioni di rinuncia.
* Indirizzo postale (per [direct mail](../../channels/using/about-direct-mail.md)) e il fuso orario del contatto (a [pianificazione dei messaggi nel relativo fuso orario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Autorizzazione di accesso, che indica l&#39;unità organizzativa del destinatario (a [gestire le autorizzazioni](../../administration/using/about-access-management.md)). Consulta anche [Profili di partizione](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Invio e tracciamento dei registri {#sending-and-tracking-logs}

La **[!UICONTROL Sending logs]** e **[!UICONTROL Tracking logs]** le schede raggruppano l’elenco delle consegne inviate al profilo e tutti i relativi dati di tracciamento.

Per ulteriori informazioni sull’invio e il tracciamento dei registri, consulta [registri di consegna](../../sending/using/monitoring-a-delivery.md#delivery-logs) e [tracciamento dei messaggi](../../sending/using/tracking-messages.md) sezioni.

## Abbonamenti {#subscriptions}

Gli abbonamenti del contatto sono elencati nella scheda corrispondente. Per ulteriori informazioni sull’abbonamento a un servizio, consulta [questa sezione](../../audiences/using/about-subscriptions.md).

La **[!UICONTROL Mobile App Subscriptions]** fai riferimento alle notifiche push. Per ulteriori informazioni, consulta la [Notifica push](../../channels/using/about-push-notifications.md) canale.
