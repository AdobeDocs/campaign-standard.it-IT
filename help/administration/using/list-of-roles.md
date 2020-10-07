---
title: Elenco di ruoli
description: Scopri l’elenco dei ruoli che puoi assegnare agli utenti.
page-status-flag: never-activated
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: role,overview;role,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 94%

---


# Elenco di ruoli{#list-of-roles}

Per impostazione predefinita, Adobe Campaign offre un set di ruoli che ti consente di definire autorizzazioni unitarie assegnate a utenti e gruppi di utenti.

Insieme alle unità organizzative, i ruoli forniscono agli utenti una visualizzazione filtrata dell’interfaccia e ne definiscono l’accesso alle diverse funzioni.

Per ulteriori informazioni, consulta la [tabella Ruoli e autorizzazioni](/help/administration/using/assets/acs_rights.pdf), che descrive le funzioni disponibili nell’interfaccia a seconda delle autorizzazioni selezionate.

[![immagine](assets/user_management_3.png)](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/users-and-security/assets/acs_rights.pdf)

I ruoli possono essere gestiti dal menu **[!UICONTROL Administration > Users & Security > Roles]**.

I diritti predefiniti sono:

* **[!UICONTROL Administration]**: diritto di amministrazione generico.
* **[!UICONTROL Datamodel]**: diritto di eseguire pubblicazioni e creare risorse personalizzate.
* **[!UICONTROL Generic import]**: diritto di eseguire un’importazione generica sui dati. Affinché ciò funzioni, devi collegare il ruolo **[!UICONTROL Generic import]** al ruolo **[!UICONTROL Workflow]**.
* **[!UICONTROL Prepare deliveries]**: diritto di creare, modificare, preparare ed eliminare consegne. Gli utenti con questo ruolo possono preparare la consegna ma non inviarla.
* **[!UICONTROL Start deliveries]**: diritto di creare, modificare, preparare, inviare ed eliminare consegne.
* **[!UICONTROL Workflow]**: diritto di gestire l’esecuzione dei flussi di lavoro (avvio, arresto, pausa, ecc.). Gli utenti con questo ruolo non possono inviare una consegna nemmeno in un flusso di lavoro.

**Argomenti correlati:**

* [Informazioni sulla gestione degli accessi](../../administration/using/about-access-management.md)
* [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md)
