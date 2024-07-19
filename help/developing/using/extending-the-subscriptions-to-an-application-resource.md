---
title: Estensione degli abbonamenti a una risorsa dell’applicazione
description: Scopri come estendere l’abbonamento a una risorsa dell’applicazione
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ac9c556d-c0f6-4b33-8855-1f5f669c148f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 10%

---

# Estensione degli abbonamenti a una risorsa dell’applicazione{#extending-the-subscriptions-to-an-application-resource}

In Adobe Campaign, i dati degli attributi del profilo mobile inviati da dispositivi mobili sono memorizzati nella risorsa **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** che ti consente di definire i dati da raccogliere dagli abbonati alle tue applicazioni. Per ulteriori informazioni sulle risorse personalizzate, fare riferimento a [questa pagina](../../developing/using/key-steps-to-add-a-resource.md).

Questa risorsa può essere estesa per raccogliere i dati che intendi inviare dal dispositivo mobile ad Adobe Campaign.

1. Dal menu avanzato, tramite il logo Adobe Campaign, seleziona **[!UICONTROL Administration]** > **[!UICONTROL Development]**, quindi **[!UICONTROL Custom resources]**.
1. Fare clic su **[!UICONTROL Create]** e scegliere l&#39;opzione **[!UICONTROL Extend an existing resource]**.
1. Selezionare la risorsa **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** e fare clic su **[!UICONTROL Create]**.

   ![](assets/in_app_personal_data_4.png)

1. Nella categoria **[!UICONTROL Fields]** della scheda **[!UICONTROL Data structure]**, definire i dati cliente che si desidera recuperare dall&#39;app mobile facendo clic sul pulsante **[!UICONTROL Add field]**.

   >[!NOTE]
   >
   >Se gestisci più app mobili, è necessario elencare tutti i campi utilizzati da tutte le applicazioni. La chiamata di raccolta dei dati PII di iOS o Android definisce quali campi vengono acquisiti da ogni applicazione.

   ![](assets/in_app_personal_data.png)

1. Aggiungi **[!UICONTROL Label]** e **[!UICONTROL ID]** al nuovo campo. Seleziona il **[!UICONTROL Type]** del tuo campo.

   ![](assets/schema_extension_uc9.png)

1. Nella categoria **[!UICONTROL Link to profiles]** configura la chiave di riconciliazione utilizzata per collegare i profili dal database di Adobe Campaign agli abbonati alle tue applicazioni, ad esempio l’e-mail.

   Tieni presente che per i messaggi in-app puoi definire una sola chiave di riconciliazione per tutte le app mobili.

   ![](assets/in_app_personal_data_3.png)

1. **[!UICONTROL Save]** e pubblica la risorsa personalizzata. Per ulteriori informazioni sulla pubblicazione di risorse personalizzate, consulta questa [pagina](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
