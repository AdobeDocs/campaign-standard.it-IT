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
TQID: 'https://experienceleague.adobe.com/hdn9Hj-zHdqoD2fKbv5Rl-GcV5EpH-L8p95e7W0ouzA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '156'
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

1. Da **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**, fare clic sul pulsante **[!UICONTROL Create]**.
1. Scegliere l&#39;azione da eseguire:

   * **[!UICONTROL Create a new resource]**: immettere i campi **[!UICONTROL Label]** e **[!UICONTROL ID]**. Il campo **[!UICONTROL ID]** è obbligatorio. Se lasci vuoto il campo Etichetta, verrà automaticamente completato dall’ID.

     ![](assets/schema_extension_2.png)

     >[!NOTE]
     >
     >Utilizza un massimo di 30 caratteri.

   * **[!UICONTROL Extend an existing resource]**: selezionare la risorsa che si desidera estendere.

     ![](assets/schema_extension_10.png)

1. Fare clic su **[!UICONTROL Create]** per creare la risorsa, che assumerà quindi lo stato **[!UICONTROL Draft]** in caso di nuova risorsa o lo stato **[!UICONTROL Editing]** in caso di estensione.

La nuova risorsa viene creata e ora può essere configurata. Per ulteriori informazioni sulla configurazione della risorsa, consulta [Configurazione della struttura dati della risorsa](../../developing/using/configuring-the-resource-s-data-structure.md).
