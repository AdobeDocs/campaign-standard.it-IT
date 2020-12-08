---
solution: Campaign Standard
product: campaign
title: Elenco di ruoli
description: Scopri l’elenco dei ruoli che puoi assegnare agli utenti.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: role,overview;role,main
translation-type: tm+mt
source-git-commit: 2c15273c7614204300f615e9060f29c93a4f8481
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 84%

---


# Elenco di ruoli{#list-of-roles}

Per impostazione predefinita, Adobe Campaign offre un set di ruoli che ti consente di definire autorizzazioni unitarie assegnate a utenti e gruppi di utenti.

Insieme alle unità organizzative, i ruoli forniscono agli utenti una visualizzazione filtrata dell’interfaccia e ne definiscono l’accesso alle diverse funzioni.

Per ulteriori informazioni, consulta la [tabella Ruoli e autorizzazioni](/help/administration/using/assets/acs_rights.pdf), che descrive le funzioni disponibili nell’interfaccia a seconda delle autorizzazioni selezionate.

[![immagine](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)

I ruoli possono essere gestiti dal menu **[!UICONTROL Administration > Users & Security > Roles]**.

I diritti predefiniti sono:

* **[!UICONTROL Administration]**: diritto di amministrazione generico.

   >[!NOTE]
   >
   >Se è necessario creare Triggers, è necessario che **[!UICONTROL Administration]** sia in grado di accedere al menu Triggers. Per ulteriori informazioni sugli attivatori, fare riferimento a questa [pagina](../../integrating/using/about-adobe-experience-cloud-triggers.md).

* **[!UICONTROL Datamodel]**: diritto di eseguire pubblicazioni e creare risorse personalizzate.
* **[!UICONTROL Generic import]**: diritto di eseguire un’importazione generica sui dati. Affinché ciò funzioni, devi collegare il ruolo **[!UICONTROL Generic import]** al ruolo **[!UICONTROL Workflow]**.
* **[!UICONTROL Prepare deliveries]**: diritto di creare, modificare, preparare ed eliminare consegne. Gli utenti con questo ruolo possono preparare la consegna ma non inviarla.
* **[!UICONTROL Start deliveries]**: diritto di creare, modificare, preparare, inviare ed eliminare consegne.
* **[!UICONTROL Workflow]**: diritto di gestire l’esecuzione dei flussi di lavoro (avvio, arresto, pausa, ecc.). Gli utenti con questo ruolo non possono inviare una consegna nemmeno in un flusso di lavoro.

**Argomenti correlati:**

* [Informazioni sulla gestione degli accessi](../../administration/using/about-access-management.md)
* [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md)
