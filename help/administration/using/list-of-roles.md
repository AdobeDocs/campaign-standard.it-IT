---
title: Elenco di ruoli
description: Scopri l’elenco dei ruoli che puoi assegnare agli utenti.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: role,overview;role,main
feature: Access Management
role: Admin
level: Experienced
exl-id: 00714c80-bdaf-4241-bf2f-51498ca1dbef
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 85%

---

# Elenco di ruoli{#list-of-roles}

Per impostazione predefinita, Adobe Campaign offre un set di ruoli che ti consente di definire autorizzazioni unitarie assegnate a utenti e gruppi di utenti.

Insieme alle unità organizzative, i ruoli forniscono agli utenti una visualizzazione filtrata dell’interfaccia e ne definiscono l’accesso alle diverse funzioni.

I ruoli possono essere gestiti dal menu **[!UICONTROL Administration > Users & Security > Roles]**.

I diritti predefiniti sono:

* **[!UICONTROL Administration]**: diritto di amministrazione generico.

   >[!NOTE]
   >
   >Se hai bisogno di lavorare con Experience Cloud Triggers, devi disporre del diritto **[!UICONTROL Administration]** per poter accedere al menu Triggers di Experience Cloud. Per ulteriori informazioni sugli attivatori di Experience Cloud, consulta questa [pagina](../../integrating/using/about-adobe-experience-cloud-triggers.md).

* **[!UICONTROL Datamodel]**: diritto di eseguire pubblicazioni e creare risorse personalizzate.
* **[!UICONTROL Generic import]**: diritto di eseguire un’importazione generica sui dati. Affinché ciò funzioni, devi collegare il ruolo **[!UICONTROL Generic import]** al ruolo **[!UICONTROL Workflow]**.
* **[!UICONTROL Prepare deliveries]**: diritto di creare, modificare, preparare ed eliminare consegne. Gli utenti con questo ruolo possono preparare la consegna ma non inviarla.
* **[!UICONTROL Start deliveries]**: diritto di creare, modificare, preparare, inviare ed eliminare consegne.
* **[!UICONTROL Workflow]**: diritto di gestire l’esecuzione dei flussi di lavoro (avvio, arresto, pausa, ecc.). Gli utenti con questo ruolo non possono inviare una consegna nemmeno in un flusso di lavoro.

Per ulteriori informazioni, consulta la [tabella Ruoli e autorizzazioni](/help/administration/using/assets/acs_rights.pdf), che descrive le funzioni disponibili nell’interfaccia a seconda delle autorizzazioni selezionate.

[![immagine](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)

**Argomenti correlati:**

* [Informazioni sulla gestione degli accessi](../../administration/using/about-access-management.md)
* [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md)
