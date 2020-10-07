---
title: Creazione o estensione della risorsa
description: Scopri come definire una risorsa da zero.
page-status-flag: never-activated
uuid: 7c26b63d-9587-472b-804f-cde5c45dfb3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 8dc45c37-6908-407e-8e41-4a4188cba2b3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 11%

---


# Creazione o estensione della risorsa{#creating-or-extending-the-resource}

Gli amministratori possono creare una nuova risorsa da zero o creare un&#39;estensione di una risorsa esistente se è necessario lavorare su dati che non fanno parte del modello dati incorporato.

È possibile estendere solo le seguenti risorse integrate:

* **[!UICONTROL Campaign (campaign)]**
* **[!UICONTROL Deliveries (delivery)]**
* **[!UICONTROL Landing page (Landingpage)]**
* **[!UICONTROL Profiles (profile)]**
* **[!UICONTROL Program (program)]**
* **[!UICONTROL Service (service)]**
* **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]**
* **[!UICONTROL Test profiles (seedMember)]**
* **[!UICONTROL Workflow (workflow)]**

Per creare o estendere una risorsa:

1. Da **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**, fate clic sul **[!UICONTROL Create]** pulsante.
1. Scegliete l’azione da eseguire:

   * **[!UICONTROL Create a new resource]**: Immettete i campi **[!UICONTROL Label]** e **[!UICONTROL ID]** . Il campo **[!UICONTROL ID]** è obbligatorio. Se lasciate vuoto il campo Etichetta, verrà compilato automaticamente dall’ID.

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >Utilizza un massimo di 30 caratteri.

   * **[!UICONTROL Extend an existing resource]**: Selezionate la risorsa da estendere.

      ![](assets/schema_extension_10.png)

1. Fate clic **[!UICONTROL Create]** per creare la risorsa, che assumerà lo **[!UICONTROL Draft]** stato in caso di nuova risorsa o lo **[!UICONTROL Editing]** stato in caso di estensione.

La nuova risorsa viene creata e ora può essere configurata. Per ulteriori informazioni sulla configurazione delle risorse, vedere [Configurazione della struttura](../../developing/using/configuring-the-resource-s-data-structure.md)dati della risorsa.
