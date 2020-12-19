---
solution: Campaign Standard
product: campaign
title: Modifica dei profili
description: Scopri come modificare i profili esistenti e accedere alle informazioni di contatto, ai canali preferiti, ai registri di tracciamento, alle iscrizioni ecc.
audience: audiences
content-type: reference
topic-tags: managing-profiles
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 11%

---


# Modifica dei profili{#editing-profiles}

## Accesso alle proprietà del profilo {#accessing-profile-properties}

Per modificare un profilo esistente e consultare i dati ad esso associati o modificarlo, procedere come segue:

1. Dalla pagina Home di Adobe Campaign, fai clic sulla scheda **[!UICONTROL Customer profiles]** o sulla scheda **[!UICONTROL Profiles]**.
1. Seleziona un contatto.
1. Fate clic sull&#39;icona **[!UICONTROL Edit profile properties]** per accedere alle informazioni dettagliate del profilo.

   ![](assets/profile_creation2.png)

   La finestra delle proprietà del profilo offre diverse schede che consentono di accedere a tutte le informazioni del profilo.

   Possono essere visualizzate anche altre schede, a seconda delle risorse personalizzate create o estese in  Adobe Campaign. Per ulteriori informazioni sulle risorse personalizzate, vedere [Informazioni sulle risorse personalizzate](../../developing/using/data-model-concepts.md).

   >[!NOTE]
   >
   >È possibile modificare le informazioni solo nella scheda **[!UICONTROL General]**, fatta eccezione per la sezione **[!UICONTROL Traceability]**.

L&#39;edizione Profili è anche possibile tramite l&#39;API Adobe Campaign Standard . Per ulteriori informazioni, consulta la [documentazione dedicata](../../api/using/updating-profiles.md).

Argomento correlato:

* [Integrated Customer Profile](../../audiences/using/integrated-customer-profile.md)
* [Invio al fuso orario del destinatario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)

## Dati generali del profilo {#general-profile-data}

La scheda **[!UICONTROL General]** raggruppa le seguenti informazioni sul profilo:

* Informazioni di contatto, che contengono il nome, il cognome, la data di nascita, la foto, la lingua preferita del destinatario (per [email multilingue](../../channels/using/creating-a-multilingual-email.md)), ecc.
* Canali su cui è possibile contattare il profilo, che contiene l&#39;indirizzo e-mail del destinatario, il numero di telefono cellulare, le informazioni di rifiuto.
* Indirizzo postale (per [direct mail](../../channels/using/about-direct-mail.md)) e fuso orario del contatto (per [programmare i messaggi nel relativo fuso orario](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md)).
* Autorizzazione di accesso, che indica l&#39;unità organizzativa del destinatario (per [gestire le autorizzazioni](../../administration/using/about-access-management.md)). Consulta anche [Profili di partizione](../../administration/using/organizational-units.md#partitioning-profiles).

![](assets/profile_creation4.png)

## Invio e monitoraggio di registri {#sending-and-tracking-logs}

Le schede **[!UICONTROL Sending logs]** e **[!UICONTROL Tracking logs]** raggruppano l&#39;elenco delle consegne che sono state inviate al profilo e tutti i dati di tracciamento correlati.

Per ulteriori informazioni sull&#39;invio e il monitoraggio dei registri, consultare le sezioni [log di consegna](../../sending/using/monitoring-a-delivery.md#delivery-logs) e [messaggi di tracciamento](../../sending/using/tracking-messages.md).

## Iscrizioni {#subscriptions}

Le iscrizioni del contatto sono elencate nella scheda corrispondente. Per ulteriori informazioni sull&#39;iscrizione a un servizio, consultare [questa sezione](../../audiences/using/about-subscriptions.md).

La scheda **[!UICONTROL Mobile App Subscriptions]** fa riferimento alle notifiche push. Per ulteriori informazioni, fare riferimento al canale [Notifica push](../../channels/using/about-push-notifications.md).
