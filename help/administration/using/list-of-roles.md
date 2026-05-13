---
title: Elenco di ruoli
description: Scopri l’elenco dei ruoli che puoi assegnare ai tuoi utenti
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 00714c80-bdaf-4241-bf2f-51498ca1dbef
TQID: https://experienceleague.adobe.com/HvLFiLS2GV0iJODsGL3AMMWd-lXbvDXYyLSJ8Mj20-w
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
subfeature_v2: id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 75%

---

# Elenco di ruoli{#list-of-roles}

Per impostazione predefinita, Adobe Campaign offre un set di ruoli che ti consente di definire autorizzazioni unitarie assegnate a utenti e gruppi di utenti.

Insieme alle unità organizzative, i ruoli forniscono agli utenti una visualizzazione filtrata dell’interfaccia e ne definiscono l’accesso alle diverse funzioni.

I ruoli possono essere gestiti dal menu **[!UICONTROL Administration > Users & Security > Roles]**.

I diritti predefiniti sono:

* **[!UICONTROL Administration]**: diritto di amministrazione generico.

  >[!NOTE]
  >
  >Se utilizzi Experience Cloud Triggers, devi disporre del diritto **[!UICONTROL Administration]** per accedere al menu di Experience Cloud Triggers. Per ulteriori informazioni su Experience Cloud Triggers, consulta questa [pagina](../../integrating/using/about-adobe-experience-cloud-triggers.md).

* **[!UICONTROL Datamodel]**: diritto di eseguire pubblicazioni e creare risorse personalizzate.
* **[!UICONTROL Generic import]**: diritto di eseguire un’importazione generica sui dati. Affinché ciò funzioni, devi collegare la mansione **[!UICONTROL Generic import]** alla mansione **[!UICONTROL Workflow]**.
* **[!UICONTROL Prepare deliveries]**: diritto di creare, modificare, preparare ed eliminare consegne. Gli utenti con questo ruolo possono preparare la consegna ma non inviarla.
* **[!UICONTROL Start deliveries]**: diritto di creare, modificare, preparare, inviare ed eliminare consegne.
* **[!UICONTROL Workflow]**: diritto di gestire l’esecuzione dei flussi di lavoro (avvio, interruzione, pausa, ecc.). Gli utenti con questo ruolo non possono inviare una consegna nemmeno in un flusso di lavoro.

Per ulteriori informazioni, consulta la [tabella Ruoli e autorizzazioni](/help/administration/using/assets/acs_rights.pdf), che descrive le funzioni disponibili nell’interfaccia a seconda delle autorizzazioni selezionate.

[![immagine](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf)

**Argomenti correlati:**

* [Informazioni sulla gestione degli accessi](../../administration/using/about-access-management.md)
* [Gestione di gruppi e utenti](../../administration/using/managing-groups-and-users.md)
