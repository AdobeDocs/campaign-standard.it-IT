---
title: Creazione o estensione della risorsa
description: Scopri come definire una risorsa da zero.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: b8731088-a675-4070-9036-bf2b5254e4e8
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 11%

---

# Creazione o estensione della risorsa{#creating-or-extending-the-resource}

Se hai bisogno di lavorare su dati che non fanno parte del modello dati integrato, gli amministratori possono creare una nuova risorsa da zero o creare un’estensione di una risorsa esistente.

È possibile estendere solo le seguenti risorse incorporate:

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

1. Da **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**, fare clic su **[!UICONTROL Create]** pulsante.
1. Scegliere l&#39;azione da eseguire:

   * **[!UICONTROL Create a new resource]**: immetti il **[!UICONTROL Label]** e **[!UICONTROL ID]** campi. Il campo **[!UICONTROL ID]** è obbligatorio. Se lasci vuoto il campo Etichetta, verrà automaticamente completato dall’ID.

     ![](assets/schema_extension_2.png)

     >[!NOTE]
     >
     >Utilizza un massimo di 30 caratteri.

   * **[!UICONTROL Extend an existing resource]**: seleziona la risorsa da estendere.

     ![](assets/schema_extension_10.png)

1. Clic **[!UICONTROL Create]** per creare la risorsa, che assumerà quindi il **[!UICONTROL Draft]** stato in caso di nuova risorsa o **[!UICONTROL Editing]** in caso di estensione.

La nuova risorsa viene creata e ora può essere configurata. Per ulteriori informazioni sulla configurazione delle risorse, consulta [Configurazione della struttura dati della risorsa](../../developing/using/configuring-the-resource-s-data-structure.md).
