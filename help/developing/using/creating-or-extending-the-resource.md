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
TQID: https://experienceleague.adobe.com/hdn9Hj-zHdqoD2fKbv5Rl-GcV5EpH-L8p95e7W0ouzA
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 156
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
