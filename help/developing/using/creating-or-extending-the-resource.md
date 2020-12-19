---
solution: Campaign Standard
product: campaign
title: Creazione o estensione della risorsa
description: Scopri come definire una risorsa da zero.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
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

1. In **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**, fare clic sul pulsante **[!UICONTROL Create]**.
1. Scegliete l’azione da eseguire:

   * **[!UICONTROL Create a new resource]**: Immettete i  **[!UICONTROL Label]** campi e  **[!UICONTROL ID]** campi. Il campo **[!UICONTROL ID]** è obbligatorio. Se lasciate vuoto il campo Etichetta, verrà compilato automaticamente dall’ID.

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >Utilizza un massimo di 30 caratteri.

   * **[!UICONTROL Extend an existing resource]**: Selezionate la risorsa da estendere.

      ![](assets/schema_extension_10.png)

1. Fare clic su **[!UICONTROL Create]** per creare la risorsa, che assumerà lo stato **[!UICONTROL Draft]** in caso di nuova risorsa o lo stato **[!UICONTROL Editing]** in caso di estensione.

La nuova risorsa viene creata e ora può essere configurata. Per ulteriori informazioni sulla configurazione delle risorse, vedere [Configurazione della struttura dati della risorsa](../../developing/using/configuring-the-resource-s-data-structure.md).
