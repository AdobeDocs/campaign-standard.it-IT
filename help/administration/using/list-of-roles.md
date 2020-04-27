---
title: Elenco di ruoli
description: Scoprite l’elenco dei ruoli che potete assegnare ai vostri utenti.
page-status-flag: never-activated
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: role,overview;role,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 18db1b8cade7d88294ef2609dd4fad95c55fbd37

---


# Elenco di ruoli{#list-of-roles}

Per impostazione predefinita, Adobe Campaign offre un set di ruoli che consente di definire autorizzazioni unitarie assegnate a utenti e gruppi di utenti.

Insieme alle unità organizzative, i ruoli forniscono agli utenti una visualizzazione filtrata dell&#39;interfaccia e definiscono il loro accesso alle diverse funzioni.

Per ulteriori informazioni, consultare la tabella [](/help/administration/using/assets/acs_rights.pdf)Ruoli e autorizzazioni, che descrive le funzioni disponibili nell&#39;interfaccia a seconda delle autorizzazioni selezionate.

![](assets/user_management_3.png)

I ruoli possono essere gestiti dal **[!UICONTROL Administration > Users & Security > Roles]** menu.

I diritti predefiniti sono:

* **[!UICONTROL Administration]**: Diritto di amministrazione generico.
* **[!UICONTROL Datamodel]**: Diritto di eseguire pubblicazioni e creare risorse personalizzate.
* **[!UICONTROL Generic import]**: Diritto di eseguire un&#39;importazione generica sui dati. Affinché questo funzioni, è necessario collegare il **[!UICONTROL Generic import]** ruolo al **[!UICONTROL Workflow]** ruolo.
* **[!UICONTROL Prepare deliveries]**: Diritto di creare, modificare, preparare ed eliminare le consegne. Gli utenti con questo ruolo possono preparare la consegna ma non inviarla.
* **[!UICONTROL Start deliveries]**: Diritto di creare, modificare, preparare, inviare ed eliminare consegne.
* **[!UICONTROL Workflow]**: Diritto di gestire l&#39;esecuzione dei flussi di lavoro (avvio, arresto, pausa, ecc.). Gli utenti con questo ruolo non possono inviare una consegna nemmeno in un flusso di lavoro.

**Argomenti correlati:**

* [Informazioni sulla gestione degli accessi](../../administration/using/about-access-management.md)
* [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md)
