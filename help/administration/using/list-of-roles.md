---
title: Elenco di ruoli
description: Scopri l’elenco dei ruoli che puoi assegnare ai tuoi utenti.
page-status-flag: mai attivato
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: utenti e sicurezza
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: ruolo,panoramica;ruolo,principale
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c321545b2f5fdc3ed43b9b943601008ff31fba6a

---


# Elenco di ruoli{#list-of-roles}

Per impostazione predefinita, Adobe Campaign offre un set di ruoli che consente di definire autorizzazioni unitarie assegnate a utenti e gruppi di utenti. Insieme alle unità organizzative, i ruoli forniscono agli utenti una visualizzazione filtrata dell'interfaccia e definiscono il loro accesso alle diverse funzioni. Per ulteriori informazioni, consultare la tabella [](/help/administration/using/assets/acs_rights.pdf)Ruoli e autorizzazioni.

![](assets/user_management_3.png)

I ruoli possono essere gestiti dal **[!UICONTROL Administration > Users & Security > Roles]** menu.

I diritti predefiniti sono:

* **[!UICONTROL Administration]**: Diritto di amministrazione generico.
* **[!UICONTROL Datamodel]**: Diritto di eseguire pubblicazioni e creare risorse personalizzate.
* **[!UICONTROL Export]**: Diritto di esportare i dati.
* **[!UICONTROL Generic import]**: Diritto di eseguire un'importazione generica sui dati. Affinché questo funzioni, è necessario collegare il **[!UICONTROL Generic import]** ruolo al **[!UICONTROL Workflow]** ruolo.
* **[!UICONTROL Prepare deliveries]**: Diritto di creare, modificare, preparare ed eliminare consegne. Gli utenti con questo ruolo possono preparare la consegna ma non inviarla.
* **[!UICONTROL Start deliveries]**: Diritto di creare, modificare, preparare, inviare ed eliminare consegne.
* **[!UICONTROL Workflow]**: Diritto di creare, modificare, avviare ed eliminare flussi di lavoro. Gli utenti con questo ruolo non possono inviare una consegna nemmeno in un flusso di lavoro.

>[!CAUTION]
>
>I **[!UICONTROL Deliverability]** ruoli, **[!UICONTROL Command execution]**, **[!UICONTROL Export]****[!UICONTROL File access]** e **[!UICONTROL Message Center push]** sono esclusivamente per gli amministratori Adobe a uso interno. Non devono essere concessi a un utente.

**Argomenti correlati:**

* [Informazioni sulla gestione degli accessi](../../administration/using/about-access-management.md)
* [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md)

