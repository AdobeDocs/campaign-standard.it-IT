---
solution: Campaign Standard
product: campaign
title: Creazione o estensione della risorsa
description: Scopri come definire una risorsa da zero.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Modello dati
role: Sviluppatore
level: Esperienza
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 10%

---


# Creazione o estensione della risorsa{#creating-or-extending-the-resource}

Gli amministratori possono creare una nuova risorsa da zero o creare un’estensione di una risorsa esistente se hai bisogno di lavorare su dati che non fanno parte del modello dati integrato.

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

1. In **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]** fare clic sul pulsante **[!UICONTROL Create]**.
1. Scegli l’azione da eseguire:

   * **[!UICONTROL Create a new resource]**: Immetti i  **[!UICONTROL Label]** campi  **[!UICONTROL ID]** e . Il campo **[!UICONTROL ID]** è obbligatorio. Se lasci vuoto il campo Etichetta , verrà compilato automaticamente dall’ID.

      ![](assets/schema_extension_2.png)

      >[!NOTE]
      >
      >Utilizza un massimo di 30 caratteri.

   * **[!UICONTROL Extend an existing resource]**: Seleziona la risorsa da estendere.

      ![](assets/schema_extension_10.png)

1. Fai clic su **[!UICONTROL Create]** per creare la risorsa, che assume lo stato **[!UICONTROL Draft]** in caso di nuova risorsa o lo stato **[!UICONTROL Editing]** in caso di estensione.

La nuova risorsa viene creata e può essere configurata. Per ulteriori informazioni sulla configurazione delle risorse, consulta [Configurazione della struttura dati della risorsa](../../developing/using/configuring-the-resource-s-data-structure.md).
